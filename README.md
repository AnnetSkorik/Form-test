Запуск: npm run dev

Тестовое задание 
Описание задания:
Создать страницу личного кабинета пользователя с возможностью изменения личных данных. 
Figma с макетами
Задание для фронтенда
Описание:
Создать одностраничное приложение (SPA) для отображения и редактирования данных пользователя в личном кабинете. Использовать предоставленные макеты в Figma для ориентира дизайна.
Функционал:
Отображение данных профиля:
Имя.
Фамилия.
Должность.
Номер телефона.
Адрес.
Интересы (список тегов).
Ссылка на профиль (публичный/приватный).
Аватар.
Редактирование данных:
Поля должны быть редактируемыми.
Реализовать возможность загрузки аватара. Загруженное изображение должно отображаться в реальном времени на странице.
Добавить кнопки:
"Сохранить": данные сохраняются в локальной памяти (localStorage) и остаются доступными после перезагрузки страницы.
"Отменить": отменяет изменения и возвращает данные к исходным значениям.
Сохранение данных:
Данные сохраняются локально в localStorage.
При перезагрузке страницы данные профиля восстанавливаются из localStorage.

Минимальные требования:
Дизайн:
Соответствие предоставленным макетам в Figma.
Удобство использования интерфейса (понятная структура, читабельные поля и кнопки).
Функциональность:
Реализовать отображение, редактирование и сохранение всех указанных данных профиля.
Обеспечить интерактивное отображение загруженного аватара.
Валидация данных (поля):
Имя (Name):
Обязательное поле.
Длина: от 2 до 50 символов.
Разрешены только буквы и пробелы (например, "Анна-Мария").
Фамилия (Surname):
Обязательное поле.
Длина: от 2 до 50 символов.
Разрешены только буквы и пробелы.
Должность (Job Title):
Необязательное поле.
Длина: до 100 символов.
Разрешены буквы, цифры и пробелы.
Номер телефона (Phone):
Обязательное поле.
Формат: +<код страны><номер> (например, +79999999999).
Только цифры и символ "+" в начале.
Длина: от 10 до 15 символов (включая код страны).
Адрес (Address):
Необязательное поле.
Длина: до 200 символов.
Допустимые символы: буквы, цифры, запятые, точки, дефисы и пробелы.
Интересы (The scopes of your interest):
Необязательное поле.
Список тегов или текст (каждый тег не более 30 символов).
Максимум 10 тегов.
Разрешены буквы, цифры, пробелы и символы вроде запятых или точек.
Ссылка на профиль (Links):
Необязательное поле.
Должна быть валидным URL (проверка на http:// или https://).
Длина: до 200 символов.
Аватар (Avatar):
Необязательное поле.
Поддерживаемые форматы файлов: .jpg, .jpeg, .png.
Размер файла: не более 5 MB.
Публичный/Приватный профиль (Profile visibility):
Только два значения: Public или Private.
Значение по умолчанию: Private.

Задание для бэкенда
Описание:
Создать REST API для работы с данными профиля пользователя.
Функционал API:
Получение данных профиля:
GET /profile: Возвращает данные профиля в следующем формате:
json
Копировать код
{
  "name": "Ivan",
  "surname": "Ivanov",
  "jobTitle": "Developer",
  "phone": "+79999999999",
  "address": "Moscow",
  "interests": ["Startups", "Tech"],
  "isPublic": true,
  "avatarUrl": "https://example.com/avatar.jpg"
}


Обновление данных профиля:
PUT /profile:
Принимает данные профиля (кроме аватара) в теле запроса.
Возвращает статус 200 OK и обновленные данные.
Загрузка аватара:
POST /upload-avatar:
Принимает изображение через multipart/form-data.
Сохраняет файл в папку проекта.
Возвращает URL загруженного изображения.
Валидация данных:
Проверка всех полей на сервере с выводом ошибок, понятных для тестирования, например, телефон не соответствует формату:
Имя (Name):
Обязательное поле.
Длина: от 2 до 50 символов.
Разрешены только буквы и пробелы (например, "Анна-Мария").
Фамилия (Surname):
Обязательное поле.
Длина: от 2 до 50 символов.
Разрешены только буквы и пробелы.
Должность (Job Title):
Необязательное поле.
Длина: до 100 символов.
Разрешены буквы, цифры и пробелы.
Номер телефона (Phone):
Обязательное поле.
Формат: +<код страны><номер> (например, +79999999999).
Только цифры и символ "+" в начале.
Длина: от 10 до 15 символов (включая код страны).
Адрес (Address):
Необязательное поле.
Длина: до 200 символов.
Допустимые символы: буквы, цифры, запятые, точки, дефисы и пробелы.
Интересы (The scopes of your interest):
Необязательное поле.
Список тегов или текст (каждый тег не более 30 символов).
Максимум 10 тегов.
Разрешены буквы, цифры, пробелы и символы вроде запятых или точек.
Ссылка на профиль (Links):
Необязательное поле.
Должна быть валидным URL (проверка на http:// или https://).
Длина: до 200 символов.
Аватар (Avatar):
Необязательное поле.
Поддерживаемые форматы файлов: .jpg, .jpeg, .png.
Размер файла: не более 5 MB.
Публичный/Приватный профиль (Profile visibility):
Только два значения: Public или Private.
Значение по умолчанию: Private.


Минимальные требования:
Использовать любую базу данных (например, SQLite, PostgreSQL, MongoDB).
Хранить данные профиля в таблице или коллекции.
Обеспечить корректное сохранение изменений данных в базе.
При обработке загрузки аватара сохранить файл локально и возвращать его URL.

Как сдать задание:
Каждая часть задания (фронтенд и бэкенд) должна быть выложена в отдельный публичный репозиторий на GitHub или GitLab
Репозитории должны содержать:
Описание проекта в файле README.md
Полные инструкции по запуску приложения/сервера на локальной машине.
Указание на зависимости и версии используемых инструментов (например, Node.js, npm, Python и т.д.)
Код должен быть написан с учетом читаемости и структурированности, с комментариями в сложных местах

Примерный результат:
Фронтенд: Рабочее SPA с сохранением данных профиля в localStorage.
Бэкенд: API с доступом к эндпоинтам для профиля.
