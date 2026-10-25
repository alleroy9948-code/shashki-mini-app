# Шашки — Telegram Mini App и Android-приложение

Русские шашки для телефона: игра против простого компьютера или вдвоём на одном устройстве. Реализованы обязательное взятие, дамки, отмена хода и переворот доски.

## Публикация Mini App

Для постоянного HTTPS-адреса нужно один раз включить GitHub Pages у владельца репозитория:

1. Открыть **Settings → Pages**: https://github.com/alleroy9948-code/shashki-mini-app/settings/pages
2. В **Build and deployment → Source** выбрать **GitHub Actions**.
3. После этого открыть вкладку **Actions** и проверить workflow **Deploy checkers Mini App to GitHub Pages**.

Адрес игры после успешной публикации: https://alleroy9948-code.github.io/shashki-mini-app/

Я уже добавил workflow автоматической публикации. Первый запуск завершился ошибкой, потому что GitHub Pages ещё не был включён для репозитория; само по себе добавление workflow не включает настройку Pages.

## Подключение к @Shashki_1_bot

Telegram требует, чтобы Mini App был опубликован по HTTPS, и чтобы его URL был указан в настройках бота. После публикации:

1. Открыть [@BotFather](https://t.me/BotFather) в Telegram.
2. Выполнить `/mybots`, выбрать `@Shashki_1_bot`.
3. В **Bot Settings → Menu Button** настроить кнопку меню и указать HTTPS-адрес игры выше.

Эта настройка требует авторизованного доступа к самому Telegram-боту; из GitHub её изменить нельзя.

## Android APK

Папка `android/` содержит WebView-оболочку, которая включает локальную копию игры. Workflow **Build Android APK** собирает отладочный APK при изменениях в `android/` или `index.html`. Его можно скачать в разделе **Actions → Build Android APK → Artifacts**. Это debug APK для установки вручную, а не подписанный релиз для Google Play.

## Ограничения текущей версии

- Компьютер — простой локальный противник, не онлайн-соперник.
- Игра не требует аккаунта; состояние партии не синхронизируется между устройствами.
- Mini App и APK используют один игровой интерфейс, но настройка URL бота и включение GitHub Pages требуют прав владельца.
