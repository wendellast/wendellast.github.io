---
title: "Como fazer deploy de um projeto Django gratuito"
date: 2024-05-18
categories: [Tutorial]
tags: [Django, Google, Allauth, Login, Python]
---

Ok vamos lá, vamos hospeda o projeto django na Railway
### Primeiro vamos fazer a instalação das bibliotecas utilizadas no código:


```bash

pip install gunicorn
pip install whitenoise
```

### Apos a instalação dos dois pacotes vamos cria um requirements.txt

```bash
pip freeze > requirements.txt
```

### Depois vamos criar um arquivo com o nome Procfile

OBS: O arquivo Procfilenão pode ter nenhuma extensão .txt, .py etc, somente o arquivo com o nome Procfile

Agora dentro do arquivo Procfile cole o código:

```bash
web: gunicorn project.wsgi
```

Detalhe onde esta escrito “project.wsgi”, O PROJECT se refere ao seu projeto django onde contem o arquivo settings.py , você vai por ai o nome do seu projeto django

o nome do meu projeto é setup, então ficaria assim setup.wsgi

### Depois disso vamos adiciona 2 MIDDLEWARE

Abra o seu arquivo settings.py vai em MIDDLEWARE e cole os códigos
```bash
"django.middleware.security.SecurityMiddleware",
"whitenoise.middleware.WhiteNoiseMiddleware",
```
Fica assim:

```bash
MIDDLEWARE = [
# ...
"django.middleware.security.SecurityMiddleware",
"whitenoise.middleware.WhiteNoiseMiddleware",
# ...
]
```
### Agora ainda no arquivo settings.py cole esse código nas ultimas linhas:

```bash
STATICFILES_STORAGE = 'whitenoise.storage.CompressedStaticFilesStorage'
```
### Após isso adicionamos os arquivos staticos no final do arquivo settings.py

Se o seu arquivo static estiver configurando de outra forma acredito que possa deixa, do jeito de sua preferência

```bash
import os

STATIC_URL = 'static/'

STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "static")
]

STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
```

### Agora em ALLOWED_HOSTS

Lembre de coloca aspa e um ‘*’ dentro das chaves dessa forma [‘*’]
O debug recomendo deixa False, porem se der algum erro com imagens ou algum do tipo tente deixa em True para ver

```bash
DEBUG = False
ALLOWED_HOSTS = ['*']
```

### Após termina esse código vamos roda para pega os arquivos static
```bash
python manage.py collectstatic
```
isso deve criar uma pasta Static no diretorio raiz

### Depois disso está tudo pronto só enviar para o seu repositório e vamos ao Railway fazer o deploy

https://railway.app/

Entre e faço o login com sua conta pode loja com a conta do github e vamos seleciona o repositório que deseja fazer o deploy

Em novo projeto selecione deploy com Github
Depois selecione o repositório desejado

Depois de seleciona o repositório aperte em deploy now
e Aguarde alguns segundos até o deploy fica completo
