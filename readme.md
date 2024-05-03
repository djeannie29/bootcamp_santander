
# RESUMO AULAS GIT HUB BOOTCAMP SANTANDER DIO 



# GitHub

## O que é o GitHub?
O GitHub é uma plataforma de hospedagem de código-fonte com controle de versão usando o Git. É onde os desenvolvedores podem colaborar em projetos.

## Como usar o GitHub

### 1. Crie uma conta no GitHub
Acesse www.github.com e clique em 'Sign up'.

### 2. Crie um novo repositório
Clique em '+' no canto superior direito e selecione 'New repository'. Nomeie seu repositório e clique em 'Create repository'.

### 3. Clone o repositório
Na linha de comando, digite:


```bash
git clone [URL do repositório]
```

### 4. Faça alterações no código
Use seu editor de código favorito para fazer alterações no código.

### 5. Commit suas alterações
Na linha de comando, digite 
```bash
git add .
```
Para adicionar todas as alterações e  commitar.
```bash
git commit -m "[mensagem de commit]" 
``` 


### 6. Push suas alterações
Digite o comando abaixo para enviar suas alterações.

```bash 
git push origin [nome da branch]
``` 


# Branches no GitHub

Um "branch" (ou "ramo", em português) no GitHub é essencialmente uma linha de desenvolvimento separada. Ele permite aos desenvolvedores trabalharem em recursos ou correções de bugs sem interferir diretamente no código principal do projeto. 

Os branches isolam seu trabalho de desenvolvimento de outros branches do repositório. Por exemplo, você poderia usar um branch para desenvolver um novo recurso ou corrigir um erro. Você sempre cria um branch a partir de um branch existente.

Aqui estão alguns comandos úteis relacionados a branches no Git:

## Criar um novo branch
Para criar um novo branch, use:
```bash
git branch [nome do branch]
```

## Mudar para um branch existente
Para mudar para um branch existente, use:
```bash
git checkout [nome do branch]
```

## Criar um novo branch e mudar para ele ao mesmo tempo
Para criar um novo branch e mudar para ele ao mesmo tempo, use:
```bash
git checkout -b [nome do branch]
```

## Combinar as alterações de uma branch na sua branch atual (fazer um "merge")
Para combinar as alterações de uma branch na sua branch atual, use `git merge`:
```bash git merge [nome do branch]```


# Fluxo de Trabalho do Git com Branches

1. **Criar um novo branch**: ```bash git branch [nome do bra nch]```
2. **Mudar para um branch existente**: ```bash git checkout [nome do branch]```
3. **Criar um novo branch e mudar para ele ao mesmo tempo**: ```bash git checkout -b [nome do branch]```
4. **Combinar as alterações de uma branch na sua branch atual**: ```bash git merge [nome do branch]```


# Comando Git Clone Branch
Se você quiser clonar um ramo específico do repositório, você pode fazer isso adicionando a opção -b seguida pelo nome do ramo. Por exemplo:
```bash
git clone -b nome_do_ramo https://github.com/usuario/repositorio.git
```
ou

```bash
git clone https://github.com/usuario/repositorio.git --branch nome_do_ramo --single-branch
```


# Comandos Git

## Clonagem
Para clonar um repositório existente, use:
```bash
git clone [URL do repositório]
```

## Status
Para verificar o status do seu repositório (por exemplo, quais alterações foram feitas), use:
```bash
git status
```

## Commit
Para commitar suas alterações, primeiro adicione as alterações com `git add`, depois commit com uma mensagem descritiva:
```bash
git add .
git commit -m "[mensagem de commit]"
```

## Push
Depois de commitar suas alterações, você pode enviá-las para o repositório remoto com `git push`:
```bash
git push origin [nome da branch]
```
## Pull
Para atualizar seu repositório local com as últimas alterações do repositório remoto, use `git pull`:
```bash
git pull origin [nome da branch]
```

## Branches
Para criar uma nova branch, use `git branch`. 

```bash
git branch [nome da nova branch]
```

Para alternar entre branches, use `git checkout`:

```bash
git checkout [nome da branch]
```

## Merge
Para combinar as alterações de uma branch na sua branch atual, use ```bash git merge```:


```bash
git merge [nome da branch]
```

# Removendo uma Pasta ou Arquivo de um Commit Git

Se você cometeu uma pasta ou arquivo que não deveria estar no Git, você pode removê-los do histórico do Git. Aqui estão os passos:

## Removendo um Arquivo

1. **Remova o arquivo do Git**: Use o comando `git rm --cached` seguido pelo nome do arquivo que você deseja remover do Git, mas manter no seu diretório de trabalho.

    ```bash
    git rm --cached <nome do arquivo>
    ```

2. **Commit suas alterações**: Depois de remover o arquivo, você precisa fazer um commit para aplicar essa mudança ao seu histórico do Git

    ```bash
    git commit -m "Removendo <nome do arquivo>"
    ```

## Removendo uma Pasta

1. **Remova a pasta do Git**: Use o comando `git rm -r --cached` seguido pelo nome da pasta que você deseja remover do Git, mas manter no seu diretório de trabalho.

    ```bash
    git rm -r --cached <nome da pasta>
    ```

2. **Commit suas alterações**: Assim como ao remover um arquivo, você precisa fazer um commit para aplicar essa mudança ao seu histórico do Git.

    ```bash
    git commit -m "Removendo <nome da pasta>"
    ```


# Git Reset

O comando `git reset` é usado para desfazer alterações. Ele tem três formas principais de invocação que correspondem aos argumentos `--soft`, `--mixed`, `--hard`.

## Soft Reset

O `git reset --soft` move o ponteiro `HASH` para outro commit e deixa o diretório de trabalho e o índice inalterados. Isso é útil se você quiser alterar o último commit.

```bash
git reset --soft HASH
```

## Mixed Reset

O `git reset --mixed` é o padrão. Ele move o ponteiro `HASH` e atualiza o índice para corresponder ao estado do novo `HASH`. O diretório de trabalho não é alterado.

```bash
git reset --mixed HASH
```

## Hard Reset

O `git reset --hard` move o ponteiro `HASH`, atualiza o índice e modifica o diretório de trabalho para corresponder ao estado do novo `HASH`. Isso descarta todas as alterações desde o último commit e apaga todos os aqruivos criados que estavam no commit que foi excluido.

```bash
git reset --hard HASH
```


## Git Restore --staged

O comando ` git restore --staged` é usado para remover arquivos da área de preparação (Staging Area), mas mantém suas modificações reais intactas. Em outras palavras, ele copia o arquivo do commit `HEAD` para o índice, sem tocar na cópia do arquivo na área de trabalho.

Isso significa que as alterações que foram preparadas (staged) serão desfeitas, e os arquivos modificados aparecerão como "alterações não preparadas" (unstaged changes). Você precisará usar `git add` novamente antes de poder confirmar essas alterações.

Aqui está um exemplo de como você pode usar este comando:

```bash
git restore --staged <file>
```



## Compreendendo a diferença entre Git Reset Soft e Mixed

### git reset --soft
Esta opção move o ponteiro **HEAD** para o commit especificado. No entanto, mantém as alterações no índice (área de preparação) e na área de trabalho. Isso significa que os arquivos que foram modificados serão mantidos como "alterações a serem confirmadas" (staged changes), prontos para serem confirmados no próximo commit.

### git reset --mixed
Esta é a opção padrão para o comando reset. Assim como a opção `--soft`, ela move o ponteiro **HEAD** para o commit especificado. No entanto, ao contrário da opção `--soft`, ela também atualiza o índice para corresponder ao conteúdo do commit especificado. Isso significa que as alterações que foram preparadas (staged) serão desfeitas, e os arquivos modificados aparecerão como "alterações não preparadas" (unstaged changes). Você precisará usar `git add` novamente antes de poder confirmar essas alterações.




## Git Reflog

O comando `git reflog` gerencia as informações registradas nos "reflogs". Os "reflogs" registram quando as pontas dos ramos e outras referências são atualizadas no repositório local.

### Função Básica

A função mais básica do `git reflog` é a invocação: `git reflog`. Em resumo, é um atalho equivalente a: `git reflog show HEAD`. Este comando vai emitir o reflog do `HEAD`.

### Subcomandos

- `git reflog show [log-options] [<ref>]`: Exibe o registro log da referência informada através da linha de comando (ou pela predefinição, `HEAD`). O "reflog" cobre todas as ações recentes.
- `git reflog expire [--expire=<time>] [--expire-unreachable=<time>] [--rewrite] [--updateref] [--stale-fix]`: Remove as entradas mais antigas do "reflog". As entradas serão removidas do "reflog" caso tenham o tempo anterior ao expire ou expire-unreachable[^1^][1].
- `git reflog delete [--rewrite] [--updateref] [--dry-run | -n] [--verbose] ref@{specifier}`: Exclui as entradas únicas do reflog.
- `git reflog exists <ref>`: Verifica se uma "ref" tem um reflog.

Os "reflogs" são úteis para especificar o valor antigo de uma referência em vários comandos Git.


# Alterando a Mensagem do Último Commit no Git

Se você cometeu um erro na mensagem do seu último commit ou simplesmente quer alterá-la, você pode fazer isso usando o comando `git commit --amend`. Aqui estão os passos:


1. **Altere a mensagem do último commit**: Use o comando `git commit --amend` para alterar a mensagem do último commit. Isso abrirá um editor de texto no terminal mostrando a mensagem do último commit e permitindo que você a altere.

    ```bash
    git commit --amend
    ```

2. **Salve e saia: Depois de alterar a mensagem do commit, salve e saia do editor de texto. No Vim, por exemplo, você pode fazer isso pressionando `Esc`, digitando `:wq` e pressionando `Enter`.

3. **Verifique a nova mensagem do commit**: Você pode usar o comando `git log` para ver o histórico de commits e confirmar que a mensagem do último commit foi alterada corretamente.
    ```bash
    git log
	```
	


# Restaurando um Arquivo com Git Restore

O comando `git restore` é usado para descartar alterações no diretório de trabalho. Aqui estão os passos para restaurar um arquivo:

1. **Verifique o status do seu repositório**: Antes de restaurar um arquivo, é uma boa ideia verificar o status do seu repositório com `git status`. Isso mostrará quais arquivos foram modificados.

    ```bash
    git status
    ```

2. **Restaure o arquivo**: Use o comando `git restore` seguido pelo nome do arquivo que você deseja restaurar.

    ```bash
    git restore <nome do arquivo>
    ```

Por favor, substitua `<nome do arquivo>` pelo nome do arquivo que você deseja restaurar.


## Nota Importante

O comando `git restore` irá restaurar o arquivo para o último estado commitado, descartando todas as alterações não commitadas que foram feitas desde então. Se você quiser manter essas alterações, considere commitá-las antes de usar `git restore`



# .gitignore

O arquivo `.gitignore` é um arquivo de texto que diz ao Git quais arquivos ou pastas ele deve ignorar em um projeto. 

## Como usar .gitignore

1. **Criar um arquivo .gitignore**: Crie um arquivo de texto e dê a ele o nome de `.gitignore` (lembre-se de incluir o `.` no começo).

```bash
echo pasta/ >> .gitignore
```

2. **Editar o .gitignore**: Cada nova linha deve listar um arquivo ou pasta adicional que você quer que o Git ignore. As entradas neste arquivo também podem seguir um padrão de correspondência.

Exemplo de um arquivo .gitignore:


# Ignore os arquivos de sistema do Mac
```bash
.DS_Store
```

# Ignore a pasta node_modules
```bash
node_modules
```

# Ignore todos os arquivos de texto
```bash
*.txt
```

# Ignore arquivos relacionados às chaves de API
```bash
.env
```

# Ignore arquivos de configuração de SASS
```bash
.sass-cache
```



3. **Adicionar ou alterar seu arquivo .gitignore global**: Execute este comando:

```bash
git config --global core.excludesfile ~/.gitignore_global
```

Isso criará o arquivo `~/.gitignore_global`. Agora, você pode editar esse arquivo do mesmo modo que faz com um arquivo .gitignore local.

## Como remover arquivos enviados anteriormente por commit a partir de um novo Gitignore

Para remover um único arquivo, ou seja, para parar de rastrear o arquivo, mas não excluir esse arquivo do sistema, use:

```bash
git rm --cached filename
```

Para parar de rastrear todos os arquivos no .gitignore:

```bash
git rm -r --cached
git add .
git commit -m ".gitignore agora está funcionando"
```


# Importante
Se os arquivos que você parou de ignorar já foram rastreados pelo Git antes de serem adicionados ao .gitignore, você precisará desfazer o rastreamento desses arquivos. Você pode fazer isso com o seguinte comando:
```bash
git rm --cached <nome do arquivo>
```


# Comando Git Fetch

O comando `git fetch` é usado para buscar todas as ramificações e commits do repositório remoto que não estão presentes no repositório local. Aqui está um exemplo de como você pode usar este comando:

```bash
git fetch origin
```


Neste exemplo, origin é o nome padrão que o Git dá ao servidor de onde você clonou originalmente.

O git fetch não mescla automaticamente as alterações no seu repositório local. Para incorporar as alterações, você precisará usar o comando git merge ou git pull (que é essencialmente um fetch seguido por um merge).


# Comando Git Diff

O comando `git diff` é usado para mostrar as diferenças entre commits, commit e árvore de trabalho, etc. Aqui está um exemplo de como você pode usar este comando:

```bash
git diff
```
Este comando mostrará as diferenças entre o seu índice (ou seja, a sua área de preparação) e a sua cópia de trabalho. Isso mostra quais alterações você fez desde o último commit que ainda não foram preparadas para o próximo commit.

Se você quiser ver as diferenças entre dois commits específicos, você pode fazer isso fornecendo os hashes de commit para o comando git diff. Por exemplo:

Exemplo:
```bash
git diff 12345abc..67890def
```
Neste exemplo, 12345abc e 67890def são os hashes dos commits que você quer comparar. Este comando irá mostrar as diferenças entre esses dois commits.

Por favor, note que git diff não faz alterações no seu repositório. Ele apenas mostra as diferenças. Para aplicar as alterações, você precisará usar comandos como git add, git commit, etc.

# Links para Conteúdo sobre Markdown

[1.O Guia Definitivo de MarkDown para Iniciantes](https://github.com/mende1/guia-definitivo-de-markdown)

[2. Sintaxe básica de gravação e formatação no GitHub](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[3. Criando diagramas](https://docs.github.com/pt/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams)

[4. Criando diagramas para o GitHub Docs](https://docs.github.com/pt/contributing/writing-for-github-docs/creating-diagrams-for-github-docs)



