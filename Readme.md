# Escrow API v1 Documentation

## Endpoints

### Login user
```
    [POST] /api/v1/auth/login/

    {
        login: String,
        password: String
    }

    return {
        header: Berear hash
    }
```



### Register user
`[POST] /api/v1/auth/register/`

### Verify phone number and 2 step auth
`[POST] /api/v1/auth/verify/`

### Remember password
`[POST] /api/v1/auth/remember/`