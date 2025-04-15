---
title: Commit Semântico.
description: Lista e descrição das tag para o commit semantico
tag: [dicas, git]
category: [dicas, git]
date: 2025-03-19 17:44:00 -03:00
image: /assets/img/nssc.jpg
---

## Como usar  
Após adicionar o arquivo que você editou, na hora de commitar, utilize a seguinte estrutura:  

- O tipo do commit:  
  Ex.: `feat`, `fix`, `docs` ...  
- Abra parênteses e escreva o nome do arquivo editado e, caso queira, um emoji.  
- Ao fechar o parênteses, coloque `:` e, por fim, escreva a mensagem do commit de forma clara.  

> Não use letra maiúscula em lugar nenhum. 
{: .prompt-danger  } 

### Exemplo:  

```
fix(arquivo :bug:) bug no arquivo corrigido
```

## feat

Commits do tipo feat indicam que seu trecho de código está incluindo um **novo recurso** (se relaciona com o MINOR do
versionamento semântico).

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Estilização de interface</td>
            <td>💄 <code>:lipstick:</code></td>
        </tr>
        <tr>
            <td>Novo recurso</td>
            <td>✨ <code>:sparkles:</code></td>
        </tr>
    </tbody>
</table>

## fix

Commits do tipo fix indicam que seu trecho de código commitado está **solucionando um problema** (bug fix), (se
relaciona com o PATCH do versionamento semântico).

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Revertendo mudanças</td>
            <td>💥 <code>:boom:</code></td>
        </tr>
        <tr>
            <td>Bugfix</td>
            <td>🐛 <code>:bug:</code></td>
        </tr>
    </tbody>
</table>

## docs

Commits do tipo docs indicam que houveram **mudanças na documentação**, como por exemplo no Readme do seu repositório.
(Não inclui alterações em código).

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Comentários</td>
            <td>💡 <code>:bulb:</code></td>
        </tr>
        <tr>
            <td>Documentação</td>
            <td>📚 <code>:books:</code></td>
        </tr>
    </tbody>
</table>

## test

Commits do tipo test são utilizados quando são realizadas **alterações em testes**, seja criando, alterando ou excluindo
testes unitários. (Não inclui alterações em código)

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Teste de aprovação</td>
            <td>✔️ <code>:heavy_check_mark:</code></td>
        </tr>
        <tr>
            <td>Testes</td>
            <td>🧪 <code>:test_tube:</code></td>
        </tr>
        <tr>
            <td>Adicionando um teste</td>
            <td>✅ <code>:white_check_mark:</code></td>
        </tr>
    </tbody>
</table>

## build

Commits do tipo build são utilizados quando são realizadas modificações em **arquivos de build e dependências**.

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Removendo uma dependência</td>
            <td>➖ <code>:heavy_minus_sign:</code></td>
        </tr>
        <tr>
            <td>Package.json em JS</td>
            <td>📦 <code>:package:</code></td>
        </tr>
        <tr>
            <td>Adicionando uma dependência</td>
            <td>➕ <code>:heavy_plus_sign:</code></td>
        </tr>
    </tbody>
</table>

## perf

Commits do tipo perf servem para identificar quaisquer alterações de código que estejam relacionadas a **performance**.

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Performance</td>
            <td>⚡ <code>:zap:</code></td>
        </tr>
    </tbody>
</table>

## style

Commits do tipo style indicam que houveram alterações referentes a **formatações de código**, semicolons, trailing
spaces, lint... (Não inclui alterações em código).

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Alterações de revisão de código</td>
            <td>👌 <code>:ok_hand:</code></td>
        </tr>
    </tbody>
</table>

## refactor

Commits do tipo refactor referem-se a mudanças devido a **refatorações que não alterem sua funcionalidade**, como por
exemplo, uma alteração no formato como é processada determinada parte da tela, mas que manteve a mesma funcionalidade,
ou melhorias de performance devido a um code review.

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Refatoração</td>
            <td>♻️ <code>:recycle:</code></td>
        </tr>
    </tbody>
</table>

## chore

Commits do tipo chore indicam **atualizações de tarefas** de build, configurações de administrador, pacotes... como por
exemplo adicionar um pacote no gitignore. (Não inclui alterações em código)

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Mover/Renomear</td>
            <td>🚚 <code>:truck:</code></td>
        </tr>
        <tr>
            <td>Configuração</td>
            <td>🔧 <code>:wrench:</code></td>
        </tr>
    </tbody>
</table>
## ci
Commits do tipo ci indicam mudanças relacionadas a **integração contínua** (_continuous integration_).
<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Infraestrutura</td>
            <td>🧱 <code>:bricks:</code></td>
        </tr>
    </tbody>
</table>
## raw
Commits do tipo raw indicam mudanças relacionadas a arquivos de configurações, dados, features, parâmetros.
<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Dados</td>
            <td>🗃️ <code>:card_file_box:</code></td>
        </tr>
    </tbody>
</table>
## cleanup
Commits do tipo cleanup são utilizados para remover código comentado, trechos desnecessários ou qualquer outra forma de
limpeza do código-fonte, visando aprimorar sua legibilidade e manutenibilidade.
<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <td>Limpeza de Código</td>
        <td>🧹 <code>:broom:</code></td>
    </tbody>
</table>

## remove

Commits do tipo remove indicam a exclusão de arquivos, diretórios ou funcionalidades obsoletas ou não utilizadas,
reduzindo o tamanho e a complexidade do projeto e mantendo-o mais organizado.

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Removendo um arquivo</td>
            <td>🗑️ <code>:wastebasket:</code></td>
        </tr>
    </tbody>
</table>

## outros emojis

<table>
    <thead>
        <tr>
            <th>Tipo do commit</th>
            <th>Emoji</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Acessibilidade</td>
            <td>♿ <code>:wheelchair:</code></td>
        </tr>
        <tr>
            <td>Atualizando a versão de um submódulo</td>
            <td>⬆️ <code>:arrow_up:</code></td>
        </tr>
        <tr>
            <td>Retrocedendo a versão de um submódulo</td>
            <td>⬇️ <code>:arrow_down:</code></td>
        </tr>
        <tr>
            <td>Animações e transições</td>
            <td>💫 <code>:dizzy:</code></td>
        </tr>
        <tr>
            <td>Deploy</td>
            <td>🚀 <code>:rocket:</code></td>
        </tr>
        <tr>
            <td>Em progresso</td>
            <td>🚧 <code>:construction:</code></td>
        </tr>
        <tr>
            <td>Lista de ideias (tasks)</td>
            <td>🔜 <code> :soon: </code></td>
        </tr>
        <tr>
            <td>Responsividade</td>
            <td>📱 <code>:iphone:</code></td>
        </tr>
        <tr>
            <td>Segurança</td>
            <td>🔒️ <code>:lock:</code></td>
        </tr>
        <tr>
            <td>SEO</td>
            <td>🔍️ <code>:mag:</code></td>
        </tr>
        <tr>
            <td>Tag de versão</td>
            <td>🔖 <code>:bookmark:</code></td>
        </tr>
        <tr>
            <td>Texto</td>
            <td>📝 <code>:pencil:</code></td>
        </tr>
        <tr>
            <td>Tipagem</td>
            <td>🏷️ <code>:label:</code></td>
        </tr>
        <tr>
            <td>Tratamento de erros</td>
            <td>🥅 <code>:goal_net:</code></td>
        </tr>
    </tbody>
</table>
