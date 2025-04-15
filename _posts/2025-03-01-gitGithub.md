---
title: Git e GitHub
date: 2025-03-01 14:40:00 -03:00
category: [dicas, pc]
tag: [git, gitHub, dicas, pc]
image: "https://tm.ibxk.com.br/2023/01/18/18110237980090.jpg"
---

Olá galera, Git e GitHub são ferramentas consideradas básicas pra um
desenvolvedor, mas pode ser um pouco demorado para um iniciante conseguir se
acostumar com eles. Então aqui vai um guia básico de como usar eles em conjunto.

---

# Definição

## GitHub

O GitHub é uma plataforma baseada em nuvem onde você pode armazenar seus projetos e colaborar com outros desenvolvedores. É como se fosse uma mistura de Google Drive com rede social para programadores. Ao criar uma conta, você pode criar **repositórios**, que são como pastas digitais para seus projetos. Você pode deixá-los **públicos** ou **privados**. Repositórios públicos são visíveis para qualquer pessoa, enquanto os privados ficam restritos a você e aos colaboradores que você convidar.

## Git

O Git é um sistema de controle de versão. Ele é responsável por salvar e
controlar todas as mudanças feitas no seu projeto ao longo do tempo. Com o Git,
você pode "voltar no tempo", ver o histórico de alterações e compartilhar seu
código de forma eficiente com outros desenvolvedores. O Git é comumente usado no
**Git Bash**, mas também pode ser utilizado em qualquer terminal ou interface
gráfica de sua preferência.

---

## Preparando o Pc

Para que a conexão funcione, é necessário preparar o seu terminal com a sua conta. Para isso, utilizaremos uma chave SSH.

Primeiro, execute o seguinte comando no terminal, substituindo "seu_email@exemplo.com" pelo seu e-mail:

```bash
ssh-keygen -t rsa -b 4096 -C "seu_email@exemplo.com"
```

Aperte **Enter** quando for perguntado o local padrão.  
Caso queira definir uma senha, você pode colocá-la quando for solicitado. Caso contrário, basta apertar **Enter** duas vezes.

Agora, adicione a chave SSH ao agente com os comandos:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

Para copiar a chave pública, execute o seguinte comando:

```bash
cat ~/.ssh/id_rsa.pub
```

Em seguida, abra o GitHub no seu navegador, acesse as configurações e entre na aba de **SSH and GPG keys** [ou clique aqui](https://github.com/settings/keys).

Clique no botão para adicionar uma nova chave. Na tela seguinte, adicione um título para o dispositivo e, em **Key**, cole a chave que você copiou do terminal.

Após clicar em "Adicionar chave", vamos verificar se tudo está certo. No **terminal**, digite:

```bash
ssh -T git@github.com
```

Se tudo estiver funcionando, você verá uma mensagem com o seu nome de usuário.

---

## Comandos Git

Os comandos git se iniciam com `git` e logo em seguida o que vai ser feito. Confira a lista de comandos mais comuns:

- **git clone**
  - Copia um repositório remoto para o seu computador.
  - `git clone https://github.com/Andra-sun/gitEGithub.git`
- **git add**
  - Adiciona as mudanças feitas no seu projeto para que elas sejam salvas no próximo commit.
  - `git add .`
- **git commit**
  - Cria um ponto no tempo para as alterações que você fez. Cada commit deve ser acompanhado por uma mensagem explicando o que foi alterado.
  - `git commit -m "first commit"`
- **git push**
  - Envia suas alterações locais para o repositório remoto no GitHub.
- **git pull**
  - Baixa as alterações do repositório remoto para o seu repositório local.
- **git status**
  - Exibe o estado atual do seu repositório, como arquivos alterados, não rastreados, etc.
- **git checkout**
  - Muda para outra branch (ou cria uma nova, caso não exista).
  - `git checkout -b newBranch`

---

# Exemplo

## Exemplo, Parte 1
Agora irei mostrar para vocês um exemplo de como criar um repositório no GitHub e começar um projeto nele.
### No GitHub

Na sua conta, clique em **New repository**
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301115301.png"
width="400" alt="novo repositorio" style="border-radius: 1rem"/>
<br />
Na tela que vai surgir, preencha o campo **Repository name** e clique no botão **Create repository**. (Os outros campos da página são opcionais, no momento não é necessário nada além do nome.)

Agora, com o repositório criado, vamos "conectar" ele ao Git. O GitHub já facilita o caminho e deixa o código para criar seu repositório local de maneira rápida já pronto, então vamos aproveitá-lo.
```bash
echo "# gitEGithub" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:Andra-sun/gitEGithub.git
git push -u origin main
```
(A penúltima linha vai ser diferente da minha, pois nela tem um link com o seu perfil e o nome do repositório. Logo, não copie e cole ela no seu terminal, pois não vai funcionar.)
### No terminal
Em seu terminal, abra a pasta onde você quer que o seu projeto fique.
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301120309.png"
width="400" alt="abrindo a pasta"  style="border-radius: 1rem"/>
<br />
(`mkdir` é um comando para criar uma pasta e `cd` é um comando para abrir uma pasta.)

Cole o comando dado na tela do GitHub e aperte **Enter**.
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301120454.png"
width="400" alt="concluindo o comando" style="border-radius: 1rem"/>
<br />
E pronto, agora sua pasta está conectada ao GitHub.

---

## Exemplo, Parte 2
Agora com a primeira parte feita, vamos enviar algo para o repositório no GitHub.  
Como exemplo, vou criar um arquivo HTML, mas agora você fica à vontade para criar o arquivo que quiser.
### No terminal
Você pode usar o `git status` para conferir o que foi feito/modificado por você.
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301121343.png"
width="400" alt="Git status" style="border-radius: 1rem"/>
<br />

Agora, como já vem descrito na mensagem, vamos utilizar o `git add` para adicionar as mudanças.  
Neste passo, você pode utilizar:
```bash
git add . # adicionar tudo que foi feito de uma vez  
git add <nome do arquivo> # adicionar o arquivo específico que quiser
```
Após adicionar usando uma das opções acima, usaremos `git commit -m "mensagem do
commit"` para especificar que mudança foi feita. Dentro das aspas, você pode
modificar conforme necessário.
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301121905.png"
width="400" alt="Git commit" style="border-radius: 1rem"/>
<br />
Agora, usaremos o `git push` para enviar a mudança.
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301121957.png"
width="400" alt="Git push" style="border-radius: 1rem"/>
<br />

---

## Exemplo, Parte 3
Agora imagine que você está em um projeto em grupo e tem outras pessoas participando do seu projeto. Seu colega enviou uma atualização, e você precisa baixá-la para sua máquina para continuar o que tem que ser feito.

Para puxar as informações novas do GitHub, basta escrever no terminal:
<br />
<img src="../assets/img/2025-03-01-gitGithub/Pasted image 20250301122542.png"
width="400" alt="Git pull" style="border-radius: 1rem"/>
<br />
![[Pasted image 20250301122542.png]]
Agora está tudo atualizado.

---

## Finalização
Com esses exemplos, você já tem uma boa base para começar a usar o Git e o GitHub.  
Caso precise de mais informações ou queira se aprofundar, sempre pode consultar a [documentação oficial do Git](https://git-scm.com/docs).

Bons commits e bom trabalho! 🚀