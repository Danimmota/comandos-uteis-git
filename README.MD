# ![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white) Configurações iniciais do Git 🔧  

> git config --global --add --bool push.autoSetupRemote true

### 👤 Configurar `user name`
> git config --global user.name "Nome do usuário"  

### 📪 Configurar `email`
> git config --global user.email "email_que_deseja_usar@email.com"

### 🌳 Configuração para definir branch automaticamente
- Serve para configurar o Git para que, ao fazer o `git push` de uma nova branch local que ainda não tem um branch remoto correspondente, o Git crie automaticamente o branch remoto e vincule ao local.
> git config --global --add --bool push.autoSetupRemote true

## 💁 Agora você deve estar se perguntado, por onde começar!
- Abaixo segue o passo a passo para subir um projeto.

## 🚀 Comando para subir um projeto no [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SEUUSERNAME)
- Criar repositório remoto no GitHub com nome do projeto  
- Abrir prompt de comando - `CMD ou  GitBash`
- Necessário estar na pasta do projeto para inicializar o git
```
ls 
```
```
cd nome_da_pasta_do_projeto
```
 - Caso já esteja na pasta do projeto
 ```
git clone URL_do_projeto
git add .  
git commit -m "mensagem_escolhida"   
git branch -M main //Mudar o nome da branch para main  
git remote add origin URL do projeto  
git push -u origin main 
```

## 🔆 Comandos essenciais do Git

### 🏁 Inicializar um repositório remoto Git dentro de um repositório local
- Se ainda não estiver inicializado, então: 
> git init 

### 🔙 Voltar caso dê git init em algum repositório errado 
- ⚠️ Deve ser usado com cautela pois remove o repositório
> rm -rf .git

### ➕ Adiciona todos os arquivos alterados do projeto ao pacote de alterações a serem feitas
> git add .

### 💡 Criar uma nova versão do projeto a partir de um pacote de alterações
> git commit -m "mensagem_escolhida"

### 🔍 Verificar o estado em que se encontram os arquivos do repositório
> git status

### 🔼 Envia as alterações do repositório local para o repo remoto
> git push

### 🆙 Atualizar o repositório local com as alterações do repo remoto
> git pull

## ☀️ Fluxo diário / Após realizar mudanças no projeto local
```
git add .  
git status  
git commit -m "mensagem_escolhida"  
git push
```

# 🌳 Comandos de manipulação de Branches

### 🌳🆕 Criar uma nova branch a partir da atual
`Criará uma branch nova, mas não acessará ela imediatamente`
> git branch nome_da_branch

### 📋 Listar as branchs locais existentes / Listar ramificações
> git branch

### 🔀 Acessar/mudar para uma determinada branch existente
> git checkout nome_branch

### 💡🌳 Criar uma branch e imediatamente mudar para ela
> git checkout -b nome_branch

### ♻️ Mudar o nome da branch atual para `main`
> git branch -M main

### 🗑️ Forçar a exclusão de uma branch
> git branch -D nome_branch

### 📋 Listar o ultimo commit de cada branch
> git branch -v

### 🔀 Fazer merge de uma branch 
- Unir a branch que se encontra + mais a listada
> git merge nome_branch

# 🔗 Trabalhando com Repositórios Remotos

### 💡Criar uma cópia local de um repositório remoto
> git clone URL_do_projeto

### 🔗 Vincular o repositório local ao remoto
> git remote add origin URL

### 📖 Mostrar o repositorio remoto
> git remote

### 📖 Mostrar repositórios remotos configurados
> git remote -v

### 🔄 Atualizar referências do repositório remoto
> git fetch

# 💾 Comandos uteis Git commit

### 🔄 Altera a mensagem do último commit
> git commit --amend -m "nova_mensagem_escolhida"

### 📖 Abre o editor do último commit para você alterar
> git commit --amend

### 🔍 Ver o histórico de commits do projeto
> git log  
ou  
> git log --oneline

### 🔍 Verificar todas as alterações realizadas até as deletadas
> git reflog

### 🔍 Visualizar modificações feitas entre commits
> git diff hashcode-do-commit-anterior

### 🔍 Mostrar quais commits tem, apenas na branch remota
- Pode também precisar de um fetch antes para garantir que as referências estejam atualizadas
> git diff nome_branch_local nome_branch_remota

### 🔙 Criar um novo commit que desfaz as alterações de um commit específico (HEAD~1)
> git revert HEAD~1

### 🔙 Desfazer o último commit e retornar para o anterior
> git reset --soft HASH_do_commit

### 🔙 Desfazer commits anteriores e mover a branch para um commit anterior
> git reset  
ou  
> git reset --mixed HASH_do_commit

### 🔙 Descartar todas as mudanças feitas e retorna para o commit o qual pertence o HASH_do_commit
> git reset --hard HEAD_do_commit_para_o_qual_quero_voltar

# 📁 Comandos de manipulação de pastas do LINUX (Padrão do Git Bash)

### 📋 Listar o conteúdo da pasta
> ls

### 📂 Entrar em uma pasta 
> cd nome_pasta_que_o_arquivo_se_encontra

### 📁 Criar uma nova pasta
> mkdir nome_pasta

### 💡Criar um arquivo dentro da pasta criada
> touch nome_pasta/nome_do_arquivo.extensao

### 💡Criar um arquivo vazio reconhecido pelo Git
> touch nome_pasta/.gitkeep

### 📖 Exibir conteúdo da pasta
- O comando `cat`só irá funcionar se o arquivo estiver na pasta atual
> cat config

## 📁 Demais comandos úteis

### 💡 Criar uma cópia local de um repositório remoto
> git clone URL
ou  
> git clone URL nome_que_quero

### ➕ Adiciona apenas o arquivo mencionado
> git add nome_do_arquivo

### 📄 Adicionar arquivo README ao projeto
> git add README.md

## .gitgnore
- 🚫 Arquivo de texto que vai indicar quais os arquivos que vc não deseja que seja enviado / seja ignorado para o repositório remoto
> `add .gitgnore`

### 🌐 Site que cria o .gitgnore pela tecnologia utilizada no projeto
> - gitignore.io (https://www.toptal.com/developers/gitignore)
