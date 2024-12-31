# 1. Микрофронтенды на React с использованием Module Federation

## Описание
Для решения задачи было выбрано использование Module Federation, так как этот подход нацелен на сложные и масштабируемые приложения, а также требуется динамическая подгрузка компонентов в реальном времени. Проанализированы компоненты и выделены следующие микрофронтенды:
- **host** - является точкой входа и объединяет все микрофронтенды
- **profile** - отвечает за работу с профилем пользователя
- **photo** - отвечает за работу с карточками, включая сбор лайков под карточками
- **auth** - отвечает за аутентификацию пользователей
- **common** - содержит общие элементы, необходимые для всех микрофронтов. Отдельно вынес так как popup используется в нескольких микрофронтендах, а также можно добавлять и другие общие элементы.

## Структура проекта
После разбивки приложения на модули получилась следующая структкра компонентов
Также единый файл api.js разбит на два независимых файла и необходимыми функциями для компонента.

### host
- **public** - содержит статические элементы
- **src**
  - **styles**
    - content
    - footer
    - header
    - page
  - **components**
    - App.js
    - Footer.js
    - Header.js
    - Main.js
    - ProtectedRoute.js
  - **contexts**
    - CurrentUserContext.js

### profile
- **src**
  - **styles**
    - profile
  - **images**
    - avatar.png
    - edit-icon.svg
  - **components**
    - EditAvatarPopup.js
    - EditProfilePopup.js
  - **utils**
    - api.js (содержит функции, относящиеся к профилю пользователя)

### photo
- **src**
  - **components**
    - AddPlacePopup.js
    - Card.js
    - ImagePopup.js
  - **styles**
    - card
    - places
  - **utils**
    - api.js (содержит функции, относящиеся к карточкам пользователя)
  - **images**
    - card_1.jpg
    - card_2.jpg
    - card_3.jpg
    - like-active.jpg
    - like-inactive.jpg
    - add-icon.svg
    - delete-icon.svg

### common
- **src**
  - **components**
    - PopupWithForm.js
  - **images**
    - error-icon.svg
    - close.svg
    - success-icon.svg


# 2. Разбивка монолита на микросервисы
Сссылка на файл https://disk.yandex.ru/d/cSWITDgaBmz8bQ