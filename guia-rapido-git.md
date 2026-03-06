# Guia Rápido do GitHub

---

### Crie uma pasta local para seu projeto, entre nela e inicialize o Git

```Bash
git init
```
---

### Adicione o endereço remoto. Este é o comando que faz a “ponte” entre o seu PC e o GitHub:

```Bash
git remote add origin https://github.com/seu-usuario/nome-do-repositorio.git
```
>``origin``: É o nome padrão que damos para o servidor principal.

---

### Para ter certeza de que a associação foi feita corretamente
```Bash
git remote -v
```
>O terminal deve responder com duas linhas mostrando a URL do seu GitHub (uma para fetch e outra para push).

---

### Para trazer os arquivos do GitHub para o computador

#### 1. Pegando os arquivos pela primeira vez

```Bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
```

#### 2. Para atualizar os arquivos do computador com os do GitHub

```Bash
git pull origin main
```

---

### Para enviar arquivos do Computador para o GitHub

#### 1. Adiciona todos os arquivos/pastas para envio e deixa preparados
```Bash
git add .
```

#### 2. Fecha o pacote de envio e coloca uma mensagem obrigatória

```BASH
git commit -m "Atualização do manual prático do GitHub"
```

#### 3. Envia os arquivos e atualiza o GitHub com eles

```bash
git push -u origin main
```

