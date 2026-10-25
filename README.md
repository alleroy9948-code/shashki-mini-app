# Шашки — Telegram Mini App и Android-приложение

Мобильная версия русских шашек с игрой против компьютера, локальной партией на одном устройстве и онлайн-комнатой по приглашению. Есть обязательное взятие, дамки, продолжение цепочки взятий, отмена хода, выбор цвета и переворот доски. Игровая доска открывается сразу; настройки находятся в компактной кнопке меню в углу.

## Веб-версия

Игра опубликована по HTTPS: https://alleroy9948-code.github.io/shashki-mini-app/

Workflow **Deploy checkers Mini App to GitHub Pages** публикует только `index.html`, не выгружая исходники Android в сайт. Если публикация перестала работать, проверьте **Settings → Pages** и установите **Build and deployment → Source → GitHub Actions**.

## Подключение к @Shashki_1_bot

Telegram требует HTTPS-адреса Mini App и его настройки в боте:

1. Откройте [@BotFather](https://t.me/BotFather).
2. Выполните `/mybots` и выберите `@Shashki_1_bot`.
3. В **Bot Settings → Menu Button** укажите HTTPS-адрес игры выше.

Для этой настройки нужен доступ к самому Telegram-боту; из GitHub изменить её нельзя.

## Android APK

Папка `android/` содержит WebView-оболочку с локальной копией игры. Workflow **Build Android APK** собирает debug APK после изменений в `android/` или `index.html`. Скачайте его из **Actions → Build Android APK → Artifacts**. Это APK для ручной установки, а не подписанный релиз для Google Play.

## Проверки и ограничения

- Workflow **Validate checkers app** проверяет синтаксис JavaScript, уникальность HTML ID и идентичность веб-файла и Android-копии.
- Компьютер остаётся простым локальным противником; онлайн-комната работает через PeerJS и требует интернет-соединения.
- Партия не сохраняется и не синхронизируется между разными устройствами после закрытия приложения.
- Настройка URL в Telegram-боте требует доступа к BotFather.
