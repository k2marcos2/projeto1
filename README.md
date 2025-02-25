# Manual de Utilização do Git e VS Code

## 📌 Parte 1 - Configuração do Git no Computador

### 📥 Instalação do Git

Para instalar o Git no Windows, acesse o link abaixo e siga as instruções:

🔗 [Instalar Git](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git)

#### 🔍 Verificando a Versão do Git Instalado

Após a instalação, verifique se o Git foi instalado corretamente executando o seguinte comando no terminal:

```bash
git --version
```

Se o comando funcionar corretamente, você verá a versão instalada.

---

### 🔑 Gerando e Configurando Chave SSH

1. **Verifique se Já Existe uma Chave SSH:**
   ```bash
   ls ~/.ssh
   ```
   Se houver arquivos como `id_rsa` e `id_rsa.pub`, pule para a etapa de adição ao GitHub. Caso contrário, siga para o próximo passo.

2. **Gerar uma Nova Chave SSH:**
   ```bash
   ssh-keygen -t ed25519 -C "seu-email@example.com"
   ```
   Pressione "Enter" em todas as etapas, a menos que deseje personalizar.

3. **Copiar a Chave Pública Gerada:**
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   Copie o conteúdo exibido no terminal.

4. **Adicionar a Chave Pública ao GitHub/GitLab:**
   - Acesse as configurações da sua conta no serviço Git.
   - Navegue até "SSH and GPG keys" e clique em "Add SSH Key".
   - Cole a chave copiada e salve.

---

### ⚙️ Comandos Administrativos do Git

1. **Verificar o status dos arquivos no repositório:**
   ```bash
   git status
   ```

2. **Adicionar arquivos à área de staging:**
   ```bash
   git add nome_do_arquivo
   ```
   Ou para adicionar todos os arquivos:
   ```bash
   git add .
   ```

3. **Criar um commit com uma mensagem descritiva:**
   ```bash
   git commit -m "Mensagem do desenvolvedor"
   ```

4. **Enviar alterações para o repositório remoto:**
   ```bash
   git push -u origin main
   ```
   Caso esteja usando a branch `master`:
   ```bash
   git push -u origin master
   ```

---

## 💻 Parte 2 - Configurando o Git no VS Code

### 1️⃣ Abrir o VS Code no Projeto

```bash
code /caminho/da/sua/pasta
```

### 2️⃣ Abrir o Terminal Integrado do VS Code

- Pressione `Ctrl + Shift + '` ou acesse pelo menu **"View" > "Terminal"**.

### 3️⃣ Criar um Arquivo README

```bash
echo "# Nome do Projeto" > README.md
```

### 4️⃣ Inicializar o Repositório Local

```bash
git init
```

### 5️⃣ Adicionar os Arquivos ao Repositório Local

```bash
git add .
```

### 6️⃣ Fazer o Commit Inicial

```bash
git commit -m "Commit inicial: Adicionando arquivos do projeto"
```

### 7️⃣ Conectar o Repositório Local ao Repositório Remoto

```bash
git remote add origin git@github.com:usuario/repositorio.git
```

### 8️⃣ Enviar os Arquivos para o Repositório Remoto

```bash
git push -u origin main
```

Caso esteja usando a branch `master`:
```bash
git push -u origin master
```

### 9️⃣ Verificar o Status no VS Code

- Clique no ícone de "Source Control" no painel lateral esquerdo.
- Certifique-se de que as alterações estão sincronizadas.

---

## 🌱 Parte 3 - Gerenciamento de Branches no Git

1. **Verificar Branch Atual e Listar as Branches**
   ```bash
   git branch
   ```

2. **Criar uma Nova Branch**
   ```bash
   git branch nome_da_branch
   ```

3. **Mudar para uma Branch Específica**
   ```bash
   git checkout nome_da_branch
   ```

4. **Enviar a Branch para o Repositório Remoto**
   ```bash
   git push -u origin nome_da_branch
   ```

5. **Fazer Merge de uma Branch para outra**
   ```bash
   git checkout main
   git merge nome_da_branch
   ```

---

✅ **Este manual cobre a instalação, configuração do Git e SSH, comandos administrativos e o gerenciamento de branches. Caso encontre erros, verifique os comandos digitados e as permissões de acesso ao repositório remoto.** 🚀

