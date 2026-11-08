# Настройка GitHub Releases и автообновления FENIX PRO 1.0.0

Репозиторий: `AndreyFenix/FENIX-PRO`.

## 1. Загрузить полный проект

В скачанном ZIP открой внутреннюю папку `FENIX_PRO`. Именно её **содержимое** нужно скопировать в корень клонированного репозитория. На верхнем уровне должны находиться:

- `.github/workflows/release.yml`
- `.github/workflows/ci.yml`
- `FENIX.sln`
- `build/`
- `docs/`
- `src/`
- `README.md`

Не загружай всю папку `FENIX_PRO` как вложенную папку: workflow ожидает `build/Build-Windows.ps1` относительно корня репозитория.

### Через GitHub Desktop

1. Установи GitHub Desktop и войди в свой GitHub-аккаунт.
2. Выбери `File → Clone repository…` и клонируй `AndreyFenix/FENIX-PRO`.
3. Скопируй в клон все файлы из внутренней папки `FENIX_PRO`, разрешив замену README и workflow.
4. Проверь, что скрытая папка `.github` скопирована. В Проводнике включи `Вид → Показать → Скрытые элементы`.
5. В GitHub Desktop создай commit `Prepare FENIX PRO 1.0.0 source` и нажми `Push origin`.

Не добавляй в репозиторий личную базу SQLite, логи, пароли, токены, приватные материалы или каталог `dist/`.

## 2. Проверить сборку GitHub Actions

Открой вкладку **Actions**. Workflow `Build and test FENIX PRO` должен запускаться на push в `main`. Дождись зелёного результата. Если сборка падает, не выпускай релиз, пока ошибка не исправлена.

В `Settings → Actions → General` Actions должны быть разрешены. Release workflow уже запрашивает `contents: write` для встроенного `GITHUB_TOKEN`. Персональный GitHub-токен в приложение добавлять не нужно.

## 3. Первый релиз 1.0.0

Перед публикацией локально собери проект на Windows 10/11 x64:

1. Запусти `build/Build-Windows.cmd`.
2. Проверь, что в `dist/` появились:
   - `FENIX-PRO-x64.exe`
   - `FENIX-PRO-x64.exe.sha256`
   - `THIRD_PARTY_NOTICES.md`
3. Запусти EXE и проверь основные сценарии по `docs/RELEASE_CHECKLIST.md`.

Когда полный исходный проект уже находится на `main`, открой PowerShell в клонированном репозитории и выполни:

```powershell
git tag v1.0.0
git push origin v1.0.0
```

Tag-triggered workflow соберёт приложение на Windows runner и создаст GitHub Release с тремя файлами: EXE, SHA-256 и notices. Дождись успешного завершения вкладки Actions, затем открой Releases и проверь, что релиз опубликован (не Draft и не Prerelease) и оба updater-assets присутствуют.

## 4. Последующие обновления

Для следующей версии:

1. Измени `<Version>` в `src/FENIX.App/FENIX.App.csproj`, например на `1.0.1`.
2. Commit и push изменений в `main`.
3. Создай и отправь тег:

```powershell
git tag v1.0.1
git push origin v1.0.1
```

Actions создаст новый Release. FENIX проверяет его при запуске и затем каждые 8 часов, пока приложение открыто. Перед установкой пользователь подтверждает обновление. Версия 1.0.0 увидит 1.0.1 как доступное обновление.

Точные имена assets обязательны: `FENIX-PRO-x64.exe` и `FENIX-PRO-x64.exe.sha256`. Updater проверяет SHA-256 до замены EXE.

## 5. Важные условия

- Commit или tag сам по себе не обновляет приложение: нужен опубликованный GitHub Release с EXE и checksum.
- Полный исходный проект и `.github/workflows` должны быть в корне репозитория до отправки тега.
- Публичный репозиторий нужен для обновления без персонального токена.
- SHA-256 проверяет целостность загрузки, но не заменяет защиту GitHub-аккаунта. Включи двухфакторную аутентификацию.
- Не распространяй EXE до Windows QA и проверки сторонних лицензий.
