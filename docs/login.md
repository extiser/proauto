# Вход и выход из аккаунта

## Вход

`[POST] /auth/v1/login`

| Ключ     | Тип      |
| :---     | :---     |
| login    | String   |
| password | String   |


```
[POST] /api/v1/auth/login/

{
    login: String,
    password: String
}

{
    "User" : {
        "header" : Bearer token, // Authorization Token
        "multiAuth" : true ? false, // Двухэтапная аутентификация
        "isActivate" : true ? false, // Заблокирован / Не заблокирован
        "activateReason" : String, // Причина блокировки
        "role" : String // Роль
    }
}
```