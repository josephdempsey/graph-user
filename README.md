# graph-user
django + graphql + auth
https://django-graphql-auth.readthedocs.io/en/latest/quickstart/

initial repo setup 
```
py -m venv venv
source venv/bin/activate
pip install django
django-admin startproject core .
py manage.py startapp users  
pip install graphene-django  
pip install django-graphql-jwt 
```

Graphql Mutations

```
mutation {
  register(
    email: "d@a.com",
    username: "user3",
    password1: "123[]abc",
    password2: "123[]abc"
  ), {
    success
    errors
  }
}
```

```
mutation {
verifyAccount(token: "eyJ1c2VybmFtZSI6InVzZXIyIiwiYWN0aW9uIjoiYWN0aXZhdGlvbiJ9:1lsmZq:PkFBiaJG5_ypwJ4Tq6XXqs-3XQtyFDRumbW3mzixeoU") {
  success,
  errors
}
}
```

```
mutation {
tokenAuth(username: "admin2", password: "admin") {
  success,
  errors,
  user {
    username
  },
  token, 
  refreshToken
}
}
```

```
mutation {
  sendPasswordResetEmail(email: "d@a.com") {
    success
    errors
  }
}
```

```
mutation {
  passwordReset(token: "eyJ1c2VybmFtZSI6InVzZXIzIiwiYWN0aW9uIjoicGFzc3dvcmRfcmVzZXQifQ:1lsnOb:cm7SsnVWTTEUlG_HSsRUbFqeiczPemLoaoSEyYZZaSY", 
  newPassword1: "12345[]abc", newPassword2: "12345[]abc") {
    success
    errors
  }
}
```