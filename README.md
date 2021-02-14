# Education portal

# [User Auth](#auth)
* [Registration](#auth-registration) 
  * User registration</li>
    
* [Login](#auth-login)
  * Sign-in
    
* [Logout](#auth-logout)

* [About user](#auth-user)

* Password reset
    * [Reset password](#auth-password-reset)
    * [Reset confirmation](#auth-password-reset-confirmation)
    
* [Change password](#auth-password-change)

## <a name='auth'>User auth</a>

### <a name='auth-registration'>Registration</a>

`api/auth/registration/`


**_Params:_**

````json
{
  "actions": {
    "POST": {
      "username": {
        "type": "string",
        "required": true,
        "min_length": 1,
        "max_length": 150
      },
      "email": {
        "type": "email",
        "required": false
      },
      "password1": {
        "type": "string",
        "required": true
      },
      "password2": {
        "type": "string",
        "required": true
      }
    }
  }
}
````
#### Response
`key: string`

### <a name='auth-login'>Login</a>

`api/auth/login/`
````json
{
  "actions": {
    "POST": {
      "username": {
        "type": "string",
        "required": false
      },
      "email": {
        "type": "email",
        "required": false
      },
      "password": {
        "type": "string",
        "required": true
      }
    }
  }
}
````
#### Response
`key: string`

### <a name='auth-logout'>Logout</a>

#### _Method_ **POST**
`api/auth/logout/`

### <a name='auth-user'>About user</a>
#### METHODS: GET, PUT
`api/auth/user/`

#### FOR GET:
RESPONSE:
```json
{
    "pk": "int",
    "username": "string",
    "email": "email",
    "first_name": "string",
    "last_name": "string"
}
```
#### FOR PUT:
```json

{
  "actions" : {
        "PUT": {
            "username": {
                "type": "string",
                "required": true,
                "max_length": 150
            },
            "first_name": {
                "type": "string",
                "required": false,
                "max_length": 150
            },
            "last_name": {
                "type": "string",
                "required": false,
                "max_length": 150
            }
        }
  }
}
```

### <a href='auth-password-reset'>Password reset</a>
`api/auth/password/reset/` 

````json
{
  "actions": {
        "POST": {
            "email": {
                "type": "email",
                "required": true
            }
        }
    }
}
````

### <a name='auth-password-reset-confirmation'>Password reset confirmation</a>
`api/auth/ password/reset/confirm/`
```json
{
  "actions": {
    "POST": {
      "new_password1": {
        "type": "string",
        "required": true,
        "max_length": 128
      },
      "new_password2": {
        "type": "string",
        "required": true,
        "max_length": 128
      },
      "uid": {
        "type": "string",
        "required": true
      },
      "token": {
        "type": "string",
        "required": true
      }
    }
  }
}
```
### <a name='auth-password-change'>Change password</a>
`api/auth/password/change/`
```json
{
  "actions": {
        "POST": {
            "new_password1": {
                "type": "string",
                "required": true,
                "max_length": 128
            },
            "new_password2": {
                "type": "string",
                "required": true,
                "max_length": 128
            }
        }
    }
}
```