# 📚 Estudos - Git

> Anotações do meu intensivão de TI.

---

# O que é Git?

Git é um sistema de controle de versão.

Ele permite:

- Salvar versões do projeto;
- Voltar para versões anteriores;
- Trabalhar em equipe;
- Criar funcionalidades separadas sem afetar a versão principal.

---

# Fluxo básico do Git

```text
Criar/Editar arquivos
        ↓
git status
        ↓
git add .
        ↓
git commit -m "Mensagem"
        ↓
git push
```

---

# Principais comandos

## Navegação

Ver onde estou

```bash
pwd
```

Listar arquivos

```bash
ls
```

Entrar em uma pasta

```bash
cd nome_da_pasta
```

Voltar uma pasta

```bash
cd ..
```

Ir para a pasta do usuário

```bash
cd ~
```

---

# Criando arquivos e pastas

Criar pasta

```bash
mkdir backend
```

Criar arquivo

```bash
touch app.py
```

Abrir no VS Code

```bash
code .
```

---

# Remover arquivos

Apagar arquivo

```bash
rm arquivo.txt
```

Apagar pasta

```bash
rm -r pasta
```

Apagar pasta forçando

```bash
rm -rf pasta
```

Flags:

- `-r` → Recursive
- `-f` → Force

---

# Criando um repositório

```bash
git init
```

---

# Clonando um repositório

```bash
git clone URL
```

---

# Verificando alterações

```bash
git status
```

Mostra:

- arquivos modificados;
- arquivos novos;
- arquivos preparados;
- branch atual.

---

# Adicionando alterações

Adicionar tudo

```bash
git add .
```

Adicionar apenas um arquivo

```bash
git add arquivo.py
```

---

# Criando um commit

```bash
git commit -m "Mensagem"
```

Exemplos:

```bash
git commit -m "Adiciona README"
git commit -m "Corrige bug"
```

---

# Enviando para o GitHub

```bash
git push
```

---

# Atualizando o projeto

```bash
git pull
```

Baixa as alterações do GitHub para o computador.

---

# Branches

Ver branches

```bash
git branch
```

Criar branch

```bash
git branch nova-branch
```

Criar e entrar

```bash
git checkout -b nova-branch
```

ou

```bash
git switch -c nova-branch
```

Trocar de branch

```bash
git switch main
```

---

# Merge

Juntar uma branch na outra

```bash
git merge nome-da-branch
```

---

# Pull Request

Fluxo:

```text
Criar branch
      ↓
Modificar arquivos
      ↓
git add
      ↓
git commit
      ↓
git push
      ↓
Pull Request
      ↓
Merge
      ↓
git pull
```

---

# Git Stash

Guardar alterações temporariamente

```bash
git stash
```

Recuperar

```bash
git stash pop
```

---

# Git Rebase

Reorganiza o histórico de commits, deixando-o mais linear.

Usado principalmente em equipes.

---

# Convenções

Main

- Branch principal.

Feature

- Branch usada para desenvolver uma funcionalidade.

Commit

- Uma "foto" do projeto.

Push

- Envia alterações para o GitHub.

Pull

- Baixa alterações do GitHub.

Merge

- Junta duas branches.

---

# Dicas

Sempre execute antes de qualquer commit:

```bash
git status
```

Sempre escreva mensagens claras nos commits.

Exemplo:

✅ Adiciona tela de login

❌ Atualização

---

# Fluxo profissional

```text
main
│
├── Criar branch
│
├── Desenvolver
│
├── git add
│
├── git commit
│
├── git push
│
├── Pull Request
│
├── Merge
│
└── git pull
```

---

# Status do aprendizado

- [x] Git Init
- [x] Git Clone
- [x] Git Status
- [x] Git Add
- [x] Git Commit
- [x] Git Push
- [x] Git Pull
- [x] Branches
- [x] Merge
- [x] Pull Requests
- [x] Git Stash
- [x] Git Rebase
