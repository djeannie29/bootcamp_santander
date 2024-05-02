
# RESUMO AULA GITHUB BOOTCAMP SANTANDER DIO

Uma breve descrição sobre o que esse projeto faz e para quem ele é

# GitHub

## O que é o GitHub?
O GitHub é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. É onde os desenvolvedores podem colaborar em projetos.

## Como usar o GitHub

### 1. Crie uma conta no GitHub
Acesse www.github.com e clique em 'Sign up'.

### 2. Crie um novo repositório
Clique em '+' no canto superior direito e selecione 'New repository'. Nomeie seu repositório e clique em 'Create repository'.

### 3. Clone o repositório
Na linha de comando, digite `git clone [URL do repositório]`.

### 4. Faça alterações no código
Use seu editor de código favorito para fazer alterações no código.

### 5. Commit suas alterações
Na linha de comando, digite `git add .` para adicionar todas as alterações, depois `git commit -m "[mensagem de commit]"` para commitar suas alterações.

### 6. Push suas alterações
Digite `git push origin [nome da branch]` para enviar suas alterações para o GitHub.

### 7. Abra um Pull Request
No GitHub, vá para a página do seu repositório e clique em 'Pull request' e depois em 'New pull request'.



# Branches no GitHub

Um "branch" (ou "ramo", em português) no GitHub é essencialmente uma linha de desenvolvimento separada. Ele permite aos desenvolvedores trabalharem em recursos ou correções de bugs sem interferir diretamente no código principal do projeto. 

Os branches isolam seu trabalho de desenvolvimento de outros branches do repositório. Por exemplo, você poderia usar um branch para desenvolver um novo recurso ou corrigir um erro. Você sempre cria um branch a partir de um branch existente.

Aqui estão alguns comandos úteis relacionados a branches no Git:

## Criar um novo branch
Para criar um novo branch, use:
\`\`\`bash
git branch [nome do branch]
\`\`\`

## Mudar para um branch existente
Para mudar para um branch existente, use:
\`\`\`bash
git checkout [nome do branch]
\`\`\`

## Criar um novo branch e mudar para ele ao mesmo tempo
Para criar um novo branch e mudar para ele ao mesmo tempo, use:
\`\`\`bash
git checkout -b [nome do branch]
\`\`\`

## Combinar as alterações de uma branch na sua branch atual (fazer um "merge")
Para combinar as alterações de uma branch na sua branch atual, use `git merge`:
\`\`\`bash
git merge [nome do branch]
\`\`\`





# Comandos Git

## Clonagem
Para clonar um repositório existente, use:
\`\`\`bash
git clone [URL do repositório]
\`\`\`

## Status
Para verificar o status do seu repositório (por exemplo, quais alterações foram feitas), use:
\`\`\`bash
git status
\`\`\`

## Commit
Para commitar suas alterações, primeiro adicione as alterações com `git add`, depois commit com uma mensagem descritiva:
\`\`\`bash
git add .
git commit -m "[mensagem de commit]"
\`\`\`

## Push
Depois de commitar suas alterações, você pode enviá-las para o repositório remoto com `git push`:
\`\`\`bash
git push origin [nome da branch]
\`\`\`

## Pull
Para atualizar seu repositório local com as últimas alterações do repositório remoto, use `git pull`:
\`\`\`bash
git pull origin [nome da branch]
\`\`\`

## Branches
Para criar uma nova branch, use `git branch`. Para alternar entre branches, use `git checkout`:
\`\`\`bash
git branch [nome da nova branch]
git checkout [nome da branch]
\`\`\`

## Merge
Para combinar as alterações de uma branch na sua branch atual, use `git merge`:
\`\`\`bash
git merge [nome da branch]

\`\`\`
# .gitignore

O arquivo `.gitignore` é um arquivo de texto que diz ao Git quais arquivos ou pastas ele deve ignorar em um projeto. 

## Como usar .gitignore

1. **Criar um arquivo .gitignore**: Crie um arquivo de texto e dê a ele o nome de `.gitignore` (lembre-se de incluir o `.` no começo).

\`\`\`
echo pasta/ >> .gitignore
\`\`\`


2. **Editar o .gitignore**: Cada nova linha deve listar um arquivo ou pasta adicional que você quer que o Git ignore. As entradas neste arquivo também podem seguir um padrão de correspondência.

Exemplo de um arquivo .gitignore:

\`\`\`bash
# Ignore os arquivos de sistema do Mac
.DS_Store

# Ignore a pasta node_modules
node_modules

# Ignore todos os arquivos de texto
*.txt

# Ignore arquivos relacionados às chaves de API
.env

# Ignore arquivos de configuração de SASS
.sass-cache

\`\`\`

3. **Adicionar ou alterar seu arquivo .gitignore global**: Execute este comando:

\`\`\`bash
git config --global core.excludesfile ~/.gitignore_global
\`\`\`

Isso criará o arquivo `~/.gitignore_global`. Agora, você pode editar esse arquivo do mesmo modo que faz com um arquivo .gitignore local.

## Como remover arquivos enviados anteriormente por commit a partir de um novo Gitignore

Para remover um único arquivo, ou seja, para parar de rastrear o arquivo, mas não excluir esse arquivo do sistema, use:

\`\`\`bash
git rm --cached filename
\`\`\`

Para parar de rastrear todos os arquivos no .gitignore:

\`\`\`bash
git rm -r --cached
git add .
git commit -m ".gitignore agora está funcionando"
\`\`\`


# Importante
Se os arquivos que você parou de ignorar já foram rastreados pelo Git antes de serem adicionados ao .gitignore, você precisará desfazer o rastreamento desses arquivos. Você pode fazer isso com o seguinte comando:
\`\`\`
git rm --cached <nome do arquivo>
\`\`\`

# Links para Conteúdo sobre Markdown

[1.O Guia Definitivo de MarkDown para Iniciantes](https://github.com/mende1/guia-definitivo-de-markdown)

[2. Sintaxe básica de gravação e formatação no GitHub](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[3. Criando diagramas](https://docs.github.com/pt/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams)

[4. Criando diagramas para o GitHub Docs](https://docs.github.com/pt/contributing/writing-for-github-docs/creating-diagrams-for-github-docs)


# Fluxo de Trabalho do Git com Branches

```mermaid
graph TD;
    A(Criar um novo branch: `git branch [nome do branch]`) --> B(Mudar para um branch existente: `git checkout [nome do branch]`);
    B --> C(Criar um novo branch e mudar para ele ao mesmo tempo: `git checkout -b [nome do branch]`);
    C --> D(Combinar as alterações de uma branch na sua branch atual: `git merge [nome do branch]`);
