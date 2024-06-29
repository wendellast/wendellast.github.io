---
title: "Como fazer login com Google Django: allauth"
date: 2024-05-18
categories: [Tutorial]
tags: [Django, Google, Allauth, Login, Python]
---

Simplificando a Integração do Django-Allauth para Autenticação com Google

Documentação oficial: https://docs.allauth.org/en/latest/installation/quickstart.html

### Passo 1: Instalação do Django-Allauth

Comece instalando o Django-Allauth via pip:

Atualmente, a versão 0.63 pode apresentar alguns bugs, então é recomendável usar a versão 0.61.

```bash
pip install django-allauth==0.61.0
```

### Passo 2: Configuração no arquivo settings.py

No seu arquivo settings.py, faça as seguintes configurações:

```bash
INSTALLED_APPS = [

    "allauth",
    "allauth.account",
    "allauth.socialaccount",
    "allauth.socialaccount.providers.google",
]

MIDDLEWARE = [

    "allauth.account.middleware.AccountMiddleware",

]

AUTHENTICATION_BACKENDS = [

    "django.contrib.auth.backends.ModelBackend",
    "allauth.account.auth_backends.AuthenticationBackend",

]

SOCIALACCOUNT_PROVIDERS = {
    "google": {
        "APP": {
            "client_id": "SEU_CLIENT_ID",
            "secret": "SEU_SECRET_ID",
            "key": "",
        }
    }
}

LOGIN_REDIRECT_URL = "/"
LOGOUT_REDIRECT_URL = "/"
```

### Passo 3: Configuração das URLs

Adicione as URLs de autenticação do Allauth no seu arquivo de URLs:

```bash
from django.urls import path, include

urlpatterns = [
    ...
    path('accounts/', include('allauth.urls')),
    ...
]
```

### Passo 4: Configuração da API do Gmail

Acesse o Google Cloud Console, procure por “Gmail API”: https://console.cloud.google.com/cloud-resource-manager

### Passo 5: Adicionando ClientID

Depois de criar as credenciais OAuth no Google Cloud Console, copie o client_id e o secret gerados.

Abra o seu arquivo settings.py e encontre a seção SOCIALACCOUNT_PROVIDERS. Dentro dessa seção, localize o provedor "google" e adicione as credenciais do cliente:

```bash
SOCIALACCOUNT_PROVIDERS = {
    "google": {
        "APP": {
            "client_id": "COLE_AQUI_SEU_CLIENT_ID",
            "secret": "COLE_AQUI_SEU_SECRET_ID",
            "key": "",
        }
    }
}
```

### Passo 6: Adicionando o Botão de Login do Google

Em seu template HTML onde deseja adicionar o botão de login do Google, insira o seguinte código:
```bash
{ load- socialaccount }
<a href="{ provider_login_url "google" }?next=/">Login com Google</a>
```

### Passo 7: Migrações e Execução do Servidor

Por fim, aplique as migrações e inicie o servidor Django:

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```
