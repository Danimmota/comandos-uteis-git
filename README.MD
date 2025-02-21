# ![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white) CONFIGURAÇÕES INICIAIS DO GIT 🔧  

> git config --global --add --bool push.autoSetupRemote true

### 👤 Configurar `user name`
> git config --global user.name "Nome_do_usuário"  

### 📪 Configurar `email`
> git config --global user.email "email_que_deseja_usar"

## 🚀 Como subir um projeto no github
- Criar repositório no github com nome do projeto  
- Abrir prompt de comando - `CMD ou  GitBash`
- Necessário estar na pasta do projeto para inicializar o git
```
cd nome_do_projeto
```
 - Caso já esteja na pasta do projeto
 ```
git init
git add .  
git commit -m "first commit"   
git branch -M main //Mudar o nome da branch para main  
git remote add origin URL do projeto  
git push -u origin main 
```
## ☀️ DIA A DIA
```
git add .  
git status  
git commit -m "mensagem_escolhida"  
git push
```
# 📁 COMANDOS DE MANIPULAÇÃO DE PASTA DO GIT

### 📋 Listará os arquivos presentes no diretório principal
> ls

### 📂 Achar a pasta com o arquivo 
> cd nome_pasta_que_o_arquivo_se_encontra

### 📁 Criar pasta no repositório local
> mkdir nome_pasta

### 📄 Inserir arquivo dentro da pasta criada
> touch nome_pasta/nome_que_quero

### 💡Criar um arquivo para que o Git reconheça um arquivo vazio
> touch nome_pasta/.gitkeep

### 📖 Exibir conteúdo da pasta
- O comando `cat`só irá funcionar se o arquivo estiver na pasta atual
> cat config

### 💡 Criar uma cópia local de um repositório remoto
> git clone endereço  
ou  
> git clone endereço nome_que_quero

### 📖 Mostrar o repositorio remoto
> git remote  
ou  
> git remote -v

### 🔗 Vincular repositório local ao remoto
> git remote add origin URL

# 🌳 COMANDOS UTEIS GIT BRANCH

### 🌳🆕 Criar uma nova branch a partir da atual
> git branch nome_da_branch

### 📋 Listar as branchs locais existentes / Listar ramificações
> git branch

### ♻️ Mudar o nome da branch atual (master) para main
> git branch -M main

### 🔀 Acessa uma determinada branch/Mude para uma ramificação existente
> git checkout nome_branch

### 💡🌳 Criar uma branch e imediatamente mudar para ela
> git checkout -b nome_branch

### 🗑️ Forçar a exclusão de uma branch
> git branch -D nome_branch

### 📋 Listar o ultimo commit de cada branch
> git branch -v 

### 🔀 Comando para merge
> git merge nome_branch

### 🏁 Inicializar um repositório Git dentro de um diretório
> git init

### 🔙 Voltar caso dê git init em algum repositório errado 
- Deve ser usado com cautela pois remove o repositório
> rm -rf .git

### 📄 Adicionar arquivo README ao projeto
> git add README.md
		
### 🔍 Ver o histórico de commits do projeto
> git log  
ou  
> git log --oneline

### 🔍 Verifica todas as alterações que fiz até as deletadas
> git reflog

### 🔍 Verificar o estado em que se encontram os arquivos do repositório
> git status

### 🔍 Mostra o que tem de commit apenas na branch remota
- Pode também precisar de um fetch antes para garantir que as referências estejam atualizadas
> git diff nome_branch_local nome_branch_remota

### ➕ Adiciona todos os arquivos alterados do projeto ao pacote de alterações a serem feitas
> git add .

### ➕ Adiciona apenas o arquivo mencionado
> git add nome_do_arquivo

### 🆙 Atualizar o repositório local com as alterações do repo remoto
> git pull

### 🔼 Envia as alterações do repositório local para o repo remoto
> git push

### 🔗 Conecta o git com o repositório remoto no github
> git init  `//Se ainda não estiver inicializado`

> git remote add origin URL

# 💾 COMANDOS UTEIS GIT commit 

### 💡 Criar uma nova versão do projeto a partir de um pacote de alterações
> git commit -m "mensagem_escolhida"

### 🔄 Altera a mensagem do último commit
> git commit --amend -m "nova_mensagem_escolhida"

### Abre o editor do último commit para você alterar
> git commit --amend

### 🔍 Visualizar modificações feitas entre commits
> git diff hashcode-do-commit-anterior

### 🔙 Criar um novo commit que desfaz as alterações de um commit específico (HEAD~1)
> git revert HEAD~1

⚠️
 - `Todos esses comandos a seguir (reset) são interessantes apenas no repositório local, avaliar antes de enviar remotamente, pois pode dar conflito.`

 - `Se já tiver enviado para o repositório remoto o ideal é dar um novo commit refeito`

⚠️

### 🔙 Desfazer o último commit e retornar para o anterior
> git reset --soft HASH_do_commit

### 🔙 Desfazer commits anteriores e mover a branch para um commit anterior
> git reset  
ou  
> git reset --mixed HASH_do_commit

### 🔙 Descartar todas as mudanças feitas e retorna para o commit o qual pertence o HASH_do_commit
> git reset --hard HEAD_do_commit_para_o_qual_quero_voltar

## .gitgnore
- 🚫 Arquivo de texto que vai indicar quais os arquivos que vc não deseja que seja enviado / seja ignorado para o repositório remoto
> `add .gitgnore`

### 🌐 Site que cria o .gitgnore pela tecnologia utilizada no projeto
> - gitignore.io (https://www.toptal.com/developers/gitignore)
