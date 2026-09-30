<h1 align="center"> Comandos Git </h1>   

- [🚀 Comando para subir um projeto no GitHub](#-comando-para-subir-um-projeto-no-github) - [🔆 Comandos essenciais do Git](#-comandos-essenciais-do-git) - [☀️ Fluxo diário](#-fluxo-diário) - [🌳 Comandos de manipulação de Branches](#-comandos-de-manipulação-de-branches) - [🔗 Trabalhando com Repositórios Remotos](#-trabalhando-com-repositórios-remotos) - [💾 Comandos uteis Git commit](#-comandos-uteis-git-commit) - [🎯 Mensagens de Commit personalizadas](#-mensagens-de-commit-personalizadas) - [📁 Comandos de manipulação de pastas do LINUX](#-comandos-de-manipulação-de-pastas-do-linux)
---

## 🔧 Configurações iniciais do Git

> git config --global --add --bool push.autoSetupRemote true

### 👤 Configurar `user name`
> git config --global user.name "Nome do usuário"  

### 📪 Configurar `email`
> git config --global user.email "email_que_deseja_usar@email.com"

### 🌳 Configuração para definir branch automaticamente

- Serve para configurar o Git para que, ao fazer o `git push` de uma nova branch local que ainda não tem um branch remoto correspondente, o Git crie automaticamente o branch remoto e vincule ao local.

> git config --global --add --bool push.autoSetupRemote true

<h2 align="center"> 💁 Agora você deve estar se perguntado, por onde começar?! </h2>   
- Abaixo segue o passo a passo para subir um projeto.

## 🚀 Comando para subir um projeto no GitHub

- Criar repositório remoto no [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SEUUSERNAME) com nome do projeto  
- Abrir prompt de comando - `CMD ou  GitBash`
- Necessário estar na pasta do projeto para inicializar o git
```
ls 
```
```
cd nome_da_pasta_do_projeto
```
- Caso já esteja na pasta do projeto:

- E o repositório remoto ainda não estiver inicializado: 
> git init 

- Após...

 ```
git add .  
git commit -m "mensagem_escolhida"   
git branch -M main //Mudar o nome da branch para main  
git remote add origin URL_do_projeto  
git push -u origin main 
```

## 🔆 Comandos essenciais do Git

### Clonar repositório remoto
> git clone URL_do_projeto

### Inicializar um repositório remoto Git dentro de um repositório local
> git init 

### Voltar caso dê git init em algum repositório errado 
- ⚠️ Deve ser usado com cautela pois remove o repositório
> rm -rf .git

### Adiciona todos os arquivos alterados do projeto ao pacote de alterações a serem feitas
> git add .

### Adiciona apenas o arquivo mencionado
> git add nome_do_arquivo

### Adicionar apenas arquivo README ao projeto
> git add README.md

### Criar uma nova versão do projeto a partir de um pacote de alterações
> git commit -m "mensagem_escolhida"

### Verificar o estado em que se encontram os arquivos do repositório
> git status

### Envia as alterações do repositório local para o repositório remoto
> git push

### Atualizar o repositório local com as alterações do repositório remoto
> git pull

## ☀️ Fluxo diário

- Caso esteja trabalhando colaborativamente (em equipe), sugiro sempre subir alterações remotas antes de realizar alterações locais, então:

> git pull

- Após realizar mudanças no projeto local

```
git add .  
git status  
git commit -m "mensagem_escolhida"  
git push
```

## 🌳 Comandos de manipulação de Branches

### 🆕 Criar uma nova branch a partir da atual
`Criará uma branch nova, mas não acessará ela imediatamente`
> git branch nome_da_branch

### Listar as branchs locais existentes / Listar ramificações
> git branch

### Listar as branchs remotas existentes / Listar ramificações
> git branch -r

### Listar todas as branchs (locais + remotas) existentes / Listar ramificações
> git branch -a

### Acessar/mudar para uma determinada branch existente
> git checkout nome_branch

### Atualizar referências remotas
> git fetch --all

### Criar uma nova branch e imediatamente mudar para ela
> git checkout -b nome_da_branch
ou
> git switch -c <new-branch-name>

###Criar branch local a partir de uma remota
> git checkout -b <nome-local> origin/<nome-remoto>

### Mudar o nome da branch atual para `main`
> git branch -M main

### Forçar a exclusão de uma branch
> git branch -D nome_da_branch

### Listar o ultimo commit de cada branch
> git branch -v

### Fazer merge de uma branch 

- Unir a branch que se encontra + mais a listada

> git merge nome_da_branch

## 🔗 Trabalhando com Repositórios Remotos

### Criar uma cópia local de um repositório remoto
> git clone URL_do_projeto

### Vincular o repositório local ao remoto
> git remote add origin URL

### Mostrar o repositorio remoto
> git remote

### Mostrar repositórios remotos configurados
> git remote -v

### Atualizar referências do repositório remoto
> git fetch

## 💾 Comandos uteis Git commit

### Altera a mensagem do último commit
> git commit --amend -m "nova_mensagem_escolhida"

### Abre o editor do último commit para você alterar
> git commit --amend

### Ver o histórico de commits do projeto
> git log  
ou  
> git log --oneline

### Verificar todas as alterações realizadas até as deletadas
> git reflog

### Visualizar modificações feitas entre commits
> git diff hashcode-do-commit-anterior

### Mostrar quais commits tem, apenas na branch remota
- Pode também precisar de um fetch antes para garantir que as referências estejam atualizadas
> git diff nome_branch_local nome_branch_remota

### Criar um novo commit que desfaz as alterações de um commit específico (HEAD~1)
> git revert HEAD~1

### Desfazer o último commit e retornar para o anterior
> git reset --soft HASH_do_commit

### Desfazer commits anteriores e mover a branch para um commit anterior
> git reset  
ou  
> git reset --mixed HASH_do_commit

### Descartar todas as mudanças feitas e retorna para o commit o qual pertence o HASH_do_commit
> git reset --hard HEAD_do_commit_para_o_qual_quero_voltar

### ### Verificar o hash(codigo identificador) dos commits realizados na branch:
> git log <branch-de-origem> --oneline

### Comando para trazer as alterações de um determinado commit para a branch atual, fazendo o commit automatico:
> git cherry-pick <hash-do-commit>

### Comando para trazer as alterações de um determinado commit para a branch atual, fazendo o commit automatico:
> git cherry-pick -n <hash-do-commit>

### Continuar após resolver um conflito de código:
> git cherry-pick --continue

### Cancelar a operação inteira e voltar ao estado anterior:
> git cherry-pick --abort

## 🎯 Mensagens de Commit personalizadas

- **Adote uma convenção clara e semântica para facilitar a leitura e o histórico do seu repositório.**

✅ Seja breve e direto
✅ Use verbos no infinitivo (add, fix, update...)
✅ Padronize com sua equipe

| Tipo          | Descrição                                               | Exemplo de Commit                                    |
|---------------|---------------------------------------------------------|------------------------------------------------------|
| ✨ feat       | Adicionar uma nova funcionalidade                       | `git commit -m "feat(auth): add JWT support"`        |
| 🛠️ fix        | Correção de bugs                                        | `git commit -m "fix(api): handle null response"`     |
| 🧹 delete     | Remoção de recursos                                     | `git commit -m "delete: drop old login"`             |
| 📝 docs       | Alterações/atualizações na documentação                 | `git commit -m "docs(readme): update usage section"` |
| ♻️ refactor   | Melhorias no código sem mudar comportamento             | `git commit -m "refactor(core): cleanup time"`       |
| 🗑️ revert     | Reverter uma alteração anterior                         | `git commit -m "revert: feat(api): add user endpoint"`|
| 🎨 style      | Mudanças de estilo ou formatação sem afetar lógica      | `git commit -m "style: fix code indentation in user service"` |
| 🧪 test       | Criação, atualização ou correção de testes              | `git commit -m "test(api): add unit test for login controller"` |
| 🚀 perf       | Melhorias de performance / desempenho                   | `git commit -m "perf(db): reduce query time"`        |
| 🔧 chore      | Tarefas de manutenção que não afetam a lógica           | `git commit -m "chore: update npm packages"`         |
| 🛠️ build      | Alterar dependências ou configurações de build          | `git commit -m "build(deps): bump axios to 1.7.0"`   |
| 🔧 ops        | Modificar infraestrutura ou processos de deploy         | `"git commit -m "ops(docker): add production compose"`|
| ⚙️ Ci         | Alterações em arquivos/scripts relacionados à CI/CD     | `git commit -m "ci(actions): update Node version"`   |

## Tarefa não finalizada
> WIP = Work In Progress
Exemplos:
> feat(login): start login validation logic (WIP)
ou para commit local
> WIP: login state handling

## 📁 Comandos de manipulação de pastas do LINUX 

```
Padrão do Git Bash
```

### Listar o conteúdo da pasta
> ls

### Entrar em uma pasta 
> cd nome_pasta_que_o_arquivo_se_encontra

### Criar uma nova pasta
> mkdir nome_pasta

### Criar um arquivo dentro da pasta criada
> touch nome_pasta/nome_do_arquivo.extensao

### Criar um arquivo vazio reconhecido pelo Git
> touch nome_pasta/.gitkeep

### Exibir conteúdo da pasta
- O comando `cat` só irá funcionar se o arquivo estiver na pasta atual
> cat config

## 🚫  .gitgnore

- Arquivo de texto que vai indicar quais os arquivos que vc não deseja que seja enviado / seja ignorado para o repositório remoto
> `add .gitgnore`

### 🌐 Site que cria o .gitgnore pela tecnologia utilizada no projeto
> - gitignore.io (https://www.toptal.com/developers/gitignore)
