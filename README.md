﻿# Manual de Utilização do Sistema/Site

## Capítulo 1 - Configuração do Git no Computador

### Instalação do Git

Para instalar o Git no Windows, acesse o link abaixo e siga as instruções:

[Instalar Git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)

#### Verificando a Versão do Git Instalado

Após a instalação, verifique se o Git foi instalado corretamente executando o seguinte comando no terminal:

<p align="center">
    <img src="docs/images/Git.png" width="400" alt="Instalação do git">
</p>

```bash
git --version
```

Se o comando funcionar corretamente, você verá a versão instalada. Exemplo de saída:

<p align="center">
    <img src="docs/images/GitVersion.png" width="400" alt="Exemplo de comando git --version">
</p>

---

### Gerando e Configurando Chave SSH

1. **Verifique se Já Existe uma Chave SSH:**
   - No terminal, execute:
     ```bash
     ls ~/.ssh
     ```
   - Se você já tiver uma chave SSH (ex.: `id_rsa` e `id_rsa.pub`), pule para a etapa de adição ao GitHub. Caso contrário, siga para o próximo passo.

2. **Gere uma Nova Chave SSH:**
   - Execute o comando abaixo e pressione "Enter" em todas as etapas, a menos que deseje personalizar:
     ```bash
     ssh-keygen -t rsa -b 4096 -C "seuemail@example.com"
     ```
   - Isso criará uma chave privada (`id_rsa`) e uma pública (`id_rsa.pub`) na pasta `~/.ssh`.

3. **Adicione a Chave SSH ao SSH-Agent:**
   - Inicie o `ssh-agent` no terminal:
     ```bash
     eval "$(ssh-agent -s)"
     ```
   - Adicione sua chave privada ao agente:
     ```bash
     ssh-add ~/.ssh/id_rsa
     ```

4. **Copie a Chave Pública Gerada:**
   - Use o comando para copiar o conteúdo da chave pública:
     ```bash
     cat ~/.ssh/id_rsa.pub
     ```
   - Copie o texto que aparece no terminal.

5. **Adicione a Chave Pública ao GitHub/GitLab/Outro Serviço:**
   - Acesse as configurações da sua conta no serviço Git (ex.: GitHub, GitLab).
   - Vá para a seção "SSH and GPG keys" ou similar.
   - Clique em "Add SSH Key", cole o conteúdo copiado e salve.

6. **Teste a Conexão SSH:**
   - Verifique se a configuração está correta:
     ```bash
     ssh -T git@github.com
     ```
   - Você deve ver uma mensagem como "Hi [username]! You've successfully authenticated...".

---

### Comandos Administrativos do Git

Aqui estão alguns comandos básicos e suas respectivas descrições:

1. **Verificar o status dos arquivos no repositório:**

```bash
git status
```

2. **Adicionar arquivos ao área de staging:**

Para adicionar um arquivo específico:

```bash
git add index.html
```

Ou para adicionar todos os arquivos:

```bash
git add .
```

3. **Criar um commit com uma mensagem descritiva:**

```bash
git commit -m "Mensagem do desenvolvedor"
```

Exemplo de mensagem: 

```bash
git commit -m "Update file README"
```

4. **Enviar alterações para o repositório remoto:**

```bash
git push -u origin master
```

Ou, caso esteja utilizando a branch `main`:

```bash
git push -u origin main
```

---

## Capítulo 2 - Transferindo Arquivos e Configurando no VS Code

### 1. **Abra o VS Code no Projeto**
   - Abra o VS Code e clique em **"File" > "Open Folder"** para selecionar a pasta onde seus arquivos estão salvos.
   - Alternativamente, no terminal, você pode abrir diretamente com:
     ```bash
     code /caminho/da/sua/pasta
     ```

### 2. **Abra o Terminal Integrado do VS Code**
   - No VS Code, pressione `Ctrl + `` (crase)` para abrir o terminal integrado.
   - Você também pode acessar o terminal pelo menu **"View" > "Terminal"**.

### 3. **Inicialize o Repositório Local**
   - No terminal integrado, inicialize o repositório local com:
     ```bash
     git init
     ```

### 4. **Adicione os Arquivos ao Repositório Local**
   - Para adicionar todos os arquivos do projeto:
     ```bash
     git add .
     ```

### 5. **Faça o Commit Inicial**
   - Crie um commit inicial com uma mensagem descritiva:
     ```bash
     git commit -m "Commit inicial: Adicionando arquivos do projeto"
     ```

### 6. **Conecte o Repositório Local ao Repositório Remoto**
   - Configure o repositório remoto com a URL SSH:
     ```bash
     git remote add origin git@github.com:usuario/repositorio.git
     ```

### 7. **Envie os Arquivos para o Repositório Remoto**
   - Envie as alterações para o repositório remoto:
     ```bash
     git push -u origin main
     ```
   - Caso esteja usando a branch `master`:
     ```bash
     git push -u origin master
     ```

### 8. **Verifique o Status no VS Code**
   - Clique no ícone de "Source Control" (Controle de Versão) no painel lateral esquerdo.
   - Certifique-se de que as alterações estão sincronizadas.

---