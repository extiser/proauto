# Вход

`[POST] /auth/v1/login`

| Ключ     | Тип      | Описание                                                       | Обязательно
| :---     | :---     | :---                                                           | :---:       
| login    | String   | Номер телефона в формате 7xxxxxxxxxx или 8xxxxxxxxxx (11 цифр) | Да
| password | String   | Пароль                                                         | Да           

```json
{
  "login": "String",
  "password": "String"
}
```

## Возвращаемые значения

### Статусы

| Статус            | Значение       
| :---:             | :---
| 200               | OK
| 401               | Неправильный пароль
| 404               | Пользователь с таким номером телефона не найден

### Значения

| Ключ            | Тип       | По умолчанию | Описание                                            
| :---            | :---      | :---:        | :---  
| status          | Number    | 200          | Статус
| message         | String    | OK           | Сообщение ошибок
| token           | String    |              | Токен авторизации
| account         | JSON      |              | Объект с данными о верифекации аккаунта
| -> multiAuth    | Boolean   | true         | Двухэатпная аутентификация
| -> isActive     | Boolean   | true         | Заблокирован или нет
| -> blockReason  | String    |              | Причина блокировки аккаунта
| -> role         | String    | user         | [Роль пользователя](user-roles.md)


### Пример успешного запроса

```json
{
    "status": 200,
    "message": "OK",
    "token" : "Bearer jmIGpFBByNnVeI_CLyB889Go2x-b3Q0XlU9w-7_an80",
    "account": {
      "multiAuth": true,
      "isActive": true,
      "blockReason": "",
      "role": "user"
    }
}
```

### Примеры ошибок

```json
{
    "status": 401,
    "message": "Неправильный пароль"
}
```

```json
{
    "status": 404,
    "message": "Пользователь с таким номером телефона не найден"
}
```