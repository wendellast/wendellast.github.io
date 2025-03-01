# Deploy Automatico GitHub Actions


**Aviso:** No exemplo abaixo, estamos usando o usuário root, mas recomendamos criar um usuário específico na sua VPS para isso.


## Passos a Seguir

1. Crie uma pasta `.github` na raiz do seu repositório.
2. Dentro da pasta `.github`, crie outra pasta chamada `workflows`.
3. Crie um arquivo chamado `deploy.yml` dentro da pasta `workflows`.
4. Cole o exemplo de script abaixo no arquivo `deploy.yml` e ajuste as configurações conforme suas necessidades pessoais.

```yaml
name: "Deploy"

on:
    push:
        branches:
            - main

jobs:
    deploy:
        runs-on: ubuntu-latest
        steps:
              - name: Checkout
                uses: actions/checkout@v4

              - name: Copy files to VPS
                uses: appleboy/scp-action@v0.1.7
                with:
                  host: ${{ secrets.HOST }}
                  username: ${{ secrets.USERNAME }}
                  key: ${{ secrets.KEY }}
                  port: 22
                  source: "."
                  target: "/seu/caminho/do/repositorio"

              - name: Deploy Application
                uses: appleboy/ssh-action@v1.2.1
                with:
                  host: ${{ secrets.HOST }}
                  username: ${{ secrets.USERNAME }}
                  key: ${{ secrets.KEY }}
                  port: 22
                  script: |
                    cd /seu/caminho/do/repositorio
                    docker compose down
                    docker compose up --build -d
```

Substitua `/seu/caminho/do/repositorio` pelo caminho real do seu repositório na VPS.


1. Na sua VPS, entre no repositório que deseja automatizar o deploy.
2. Rode o comando `pwd` e copie a localização exata do repositório.
3. No script, substitua `target` e `cd` pela localização obtida no passo anterior.

*Exemplo*: Substitua `target: "/root/Developer/Phyrexia-Font"` pela localização do seu repositório.
*Exemplo*: Substitua `cd /root/Developer/Phyrexia-Font` pela localização do seu repositório.

## Script

Modifique o script conforme a forma que você utiliza para fazer o deploy da sua aplicação. No exemplo abaixo, usamos Docker.

```yaml
    script: |
        cd /root/Developer/Phyrexia-Font
        docker compose down
        docker compose up --build -d
```

## Configuração no GitHub

1. No repositório do seu projeto, vá em **Configurações** > **Segurança** > **Actions**.

![Img-actions](../imgs/deploy-automatico/actions_secrects.png)
![Img-actions](../imgs/deploy-automatico/reposito-secrect.png)

2. Crie novas chaves secretas:
     - `HOST`: Coloque o IP do seu servidor.
     - `USERNAME`: Coloque o nome do usuário para acessar a VPS (ex: root).
     - `KEY`: Coloque a chave privada SSH do seu servidor.

Para obter a chave privada, rode o comando no seu servidor:

```bash
cat ~/.ssh/id_rsa
```

Copie todo o conteúdo, incluindo `-----BEGIN RSA PRIVATE KEY-----` e `-----END RSA PRIVATE KEY-----`, e cole no campo `KEY` das chaves secretas do GitHub.

## Autorizar Chave SSH

Para autorizar a chave SSH pública, rode o comando:

```bash
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
```

Após isso, basta subir o pipeline para o GitHub.

**Lembre-se:** Altere o script conforme a forma que sua stack faz o deploy e ajuste o caminho do repositório na VPS.
