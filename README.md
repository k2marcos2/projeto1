# Manual de Utilização do Sistema/Site

## Parte 1 - Configuração do Git no Computador

### Instalação do Git

Para instalar o Git no Windows, acesse o link abaixo e siga as instruções:

[Instalar Git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)

#### Verificando a Versão do Git Instalado

Após a instalação, verifique se o Git foi instalado corretamente executando o seguinte comando no terminal:

<p align="center">
    <img src="docs/images/Git.png" width="400" alt="Instalação do git">
</p>

```git --version```

Se o comando funcionar corretamente, você verá a versão instalada. Exemplo de saída:

<p align="center">
    <img src="docs/images/GitVersion.png" width="400" alt="Exemplo de comando git --version">
</p>

---

### Gerando e Configurando Chave SSH

1. **Verifique se Já Existe uma Chave SSH:**
   - No terminal, execute:
     ```ls ./.ssh```
   - Se você já tiver uma chave SSH (ex.: `id_rsa` e `id_rsa.pub`), pule para a etapa de adição ao GitHub. Caso contrário, siga para o próximo passo.

2. **Gere uma Nova Chave SSH:**
   - Execute o comando abaixo e pressione "Enter" em todas as etapas, a menos que deseje personalizar:
     ```ssh-keygen```
   - Isso criará uma chave privada (`id_rsa`) e uma pública (`id_rsa.pub`) na pasta `~/.ssh`.

3. **Copie a Chave Pública Gerada:**
   - Use o comando para copiar o conteúdo da chave pública:
     ```cat ~/.ssh/id_rsa.pub```
   - Copie o texto que aparece no terminal.

4. **Adicione a Chave Pública ao GitHub/GitLab/Outro Serviço:**
   - Acesse as configurações da sua conta no serviço Git (ex.: GitHub, GitLab).
   - Vá para a seção "SSH and GPG keys" ou similar.
   - Clique em "Add SSH Key", cole o conteúdo copiado e salve.
---

### Comandos Administrativos do Git

Aqui estão alguns comandos básicos e suas respectivas descrições:

1. **Verificar o status dos arquivos no repositório:**

```git status```

2. **Adicionar arquivos ao área de staging:**

Para adicionar um arquivo específico:

```git add index.html```

Ou para adicionar todos os arquivos:

```git add .```

3. **Criar um commit com uma mensagem descritiva:**

```git commit -m "Mensagem do desenvolvedor"```

Exemplo de mensagem: 

```git commit -m "Update file README"```

4. **Enviar alterações para o repositório remoto:**

```git push -u origin master```

Ou, caso esteja utilizando a branch `main`:

```git push -u origin main```

---

## Parte 2 - Transferindo Arquivos e Configurando no VS Code

### 1. **Abra o VS Code no Projeto**
   - Abra o VS Code e clique em **"File" > "Open Folder"** para selecionar a pasta onde seus arquivos estão salvos.
   - Alternativamente, no terminal, você pode abrir diretamente com:
     ```code /caminho/da/sua/pasta```

### 2. **Abra o Terminal Integrado do VS Code**
   - No VS Code, pressione `Ctrl + Shift+'` para abrir um novo terminal.
   - Você também pode acessar o terminal pelo menu **"View" > "Terminal"**.

### 3. **Inicialize o Repositório Local**
   - No terminal integrado, inicialize o repositório local com:
     ```git init```

### 4. **Adicione os Arquivos ao Repositório Local**
   - Para adicionar todos os arquivos do projeto:
     ```bashgit add .```

### 5. **Faça o Commit Inicial**
   - Crie um commit inicial com uma mensagem descritiva:
     ```git commit -m "Commit inicial: Adicionando arquivos do projeto"```

### 6. **Conecte o Repositório Local ao Repositório Remoto**
   - Configure o repositório remoto com a URL SSH:
     ```git remote add origin git@github.com:usuario/repositorio.git```

### 7. **Envie os Arquivos para o Repositório Remoto**
   - Envie as alterações para o repositório remoto:
     ```git push -u origin main```
   - Caso esteja usando a branch `master`:
     ```git push -u origin master```

### 8. **Verifique o Status no VS Code**
   - Clique no ícone de "Source Control" (Controle de Versão) no painel lateral esquerdo.
   - Certifique-se de que as alterações estão sincronizadas.

#############################################################  lembra de organizar isso bem seu desgraça   ###########################################################################

<!-- PS C:\Users\Aluno> ssh-keygen
Generating public/private ed25519 key pair.
Enter file in which to save the key (C:\Users\Aluno/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Passphrases do not match.  Try again.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in C:\Users\Aluno/.ssh/id_ed25519
Your public key has been saved in C:\Users\Aluno/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:D+F3uMWFob0OIAeNJ6iKnl86UI7j9fdeo14vN3B/oV4 aluno@LAB02-16
The key's randomart image is:
+--[ED25519 256]--+
|     ..o    .    |
|    . o.o  o o   |
|   .  .o+ . o .  |
|  ..   + o o o   |
|..+     S + =    |
|o+ o     + B . . |
|o = ..    o++ oE.|
| + .o. .  +.o+...|
|  .o. . +=  +o. .|
+----[SHA256]-----+
PS C:\Users\Aluno> cd .\.ssh\
PS C:\Users\Aluno\.ssh> ls


    Diretório: C:\Users\Aluno\.ssh


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        24/01/2025     09:04            464 id_ed25519
-a----        24/01/2025     09:04             97 id_ed25519.pub
-a----        24/05/2024     08:58           1861 known_hosts
-a----        21/05/2024     10:31            925 known_hosts.old


PS C:\Users\Aluno\.ssh> cat .\id_ed25519
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAACmFlczI1Ni1jdHIAAAAGYmNyeXB0AAAAGAAAABDzK8lfvP
HcOpXE9J1gJ5YcAAAAGAAAAAEAAAAzAAAAC3NzaC1lZDI1NTE5AAAAIJKE0kBJC6qXUke3
hU0IL5IlUfGhgVez0yN7TU4kvaYAAAAAoNtNzNo636uFTxunpjxTV6v8hvH5aZxcvkWx+d
0zif7mXTTA/Jo7eexBx5qu/Py0GQMZZ4lrsg+3bWRuoWqoBWJTQOBF6K3nigTYw5uuAbcj
uiM3hglF/pdnDMyqz0LW8hYY67LMH9tKsh2j9O+FxiGjRy70RfkAAMVjvV486daeZQPPs7
UQhAP9dBHdfW1BOPZhIswgo6Mqlz0W0w5eFs8=
-----END OPENSSH PRIVATE KEY-----
PS C:\Users\Aluno\.ssh> cat .\id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJKE0kBJC6qXUke3hU0IL5IlUfGhgVez0yN7TU4kvaYA aluno@LAB02-16
PS C:\Users\Aluno\.ssh> -->]

################################################## não esquece isso pau no cu #########################################################################################################

<!-- PS C:\Users\Aluno\Documents\projeto1> git branch
* main
PS C:\Users\Aluno\Documents\projeto1> git branch develop
PS C:\Users\Aluno\Documents\projeto1> git branch
  develop
* main
PS C:\Users\Aluno\Documents\projeto1> git pull origin develop     
fatal: 'branch' does not appear to be a git repository
fatal: Could not read from remote repository.git 

Please make sure you have the correct access rights
and the repository exists.
PS C:\Users\Aluno\Documents\projeto1> git branch
  develop
* main
PS C:\Users\Aluno\Documents\projeto1> git chackout
git: 'chackout' is not a git command. See 'git --help'.

The most similar command is
        checkout
PS C:\Users\Aluno\Documents\projeto1> git checkout
Your branch is up to date with 'origin/main'.
PS C:\Users\Aluno\Documents\projeto1> git checkout develop
Switched to branch 'develop'
PS C:\Users\Aluno\Documents\projeto1> git branch 
* develop
  main
PS C:\Users\Aluno\Documents\projeto1> git add .
PS C:\Users\Aluno\Documents\projeto1> git commit -m "Mensagem do desenvolvedor"
On branch develop
nothing to commit, working tree clean
PS C:\Users\Aluno\Documents\projeto1> git push -u origin develop
Enter passphrase for key '/c/Users/Aluno/.ssh/id_ed25519': 
branch 'develop' set up to track 'origin/develop'.
Everything up-to-date
PS C:\Users\Aluno\Documents\projeto1>  -->