# Linux - Aula 05: Bash - O Poder do Terminal

> **Objetivo:** Aprender a utilizar recursos avançados do Bash para combinar comandos, automatizar tarefas e aumentar a produtividade no Linux.

---

# O que é o Bash?

Bash significa:

**Bourne Again SHell**

Ele é o interpretador de comandos padrão da maioria das distribuições Linux.

É através dele que executamos comandos, scripts e automações.

Sempre que você abre um terminal, normalmente está utilizando o Bash.

---

# Como verificar o Bash?

Execute:

```bash
echo $SHELL
```

Resultado esperado:

```text
/bin/bash
```

---

# Como o Bash funciona?

Imagine:

```text
Você
 │
 Digita um comando
 │
 ▼
Bash
 │
 Interpreta o comando
 │
 ▼
Kernel Linux
 │
 Executa
 │
 ▼
Resultado
```

O Bash é o intermediário entre você e o sistema operacional.

---

# Histórico de comandos

Veja todos os comandos já executados:

```bash
history
```

Pesquisar rapidamente:

Pressione:

```text
CTRL + R
```

Digite parte do comando.

Exemplo:

```text
ssh
```

O Bash localizará automaticamente.

---

# Limpando a tela

```bash
clear
```

Atalho:

```text
CTRL + L
```

---

# Autocompletar

Digite:

```text
cd Doc
```

Agora pressione:

```text
TAB
```

O Bash completa automaticamente.

Se houver mais de uma opção:

Pressione TAB duas vezes.

---

# Wildcards

São caracteres especiais para trabalhar com vários arquivos.

## *

Representa qualquer quantidade de caracteres.

```bash
ls *.txt
```

Lista apenas arquivos `.txt`.

---

## ?

Representa apenas um caractere.

```bash
ls foto?.png
```

Encontra:

```text
foto1.png
foto2.png
```

Não encontra:

```text
foto10.png
```

---

## []

Seleciona caracteres específicos.

```bash
ls arquivo[123].txt
```

Encontra:

```text
arquivo1.txt
arquivo2.txt
arquivo3.txt
```

---

# Pipes

Um dos recursos mais importantes do Linux.

Símbolo:

```text
|
```

Ele envia a saída de um comando para outro.

Exemplo:

```bash
ps aux | grep bash
```

Fluxo:

```text
ps aux
     │
     ▼
grep bash
```

Outro exemplo:

```bash
history | grep ssh
```

---

# Redirecionamento

## >

Sobrescreve um arquivo.

```bash
echo "Lucas" > nome.txt
```

Se existir, será substituído.

---

## >>

Acrescenta ao final.

```bash
echo "Linux" >> nome.txt
```

---

## <

Utiliza um arquivo como entrada.

```bash
sort < nomes.txt
```

---

# Variáveis

Criando:

```bash
nome="Lucas"
```

Utilizando:

```bash
echo $nome
```

Resultado:

```text
Lucas
```

---

# Variáveis do Sistema

Usuário atual:

```bash
echo $USER
```

Diretório atual:

```bash
echo $PWD
```

Home:

```bash
echo $HOME
```

Shell:

```bash
echo $SHELL
```

---

# Substituição de comandos

Podemos executar um comando dentro de outro.

```bash
echo "Hoje é $(date)"
```

Exemplo:

```text
Hoje é Qui Jul 03...
```

Muito utilizado em scripts.

---

# Alias

Criam atalhos para comandos.

Exemplo:

```bash
alias atualizar="sudo apt update && sudo apt upgrade"
```

Agora basta executar:

```bash
atualizar
```

Ver todos os aliases:

```bash
alias
```

---

# Operadores Lógicos

## &&

Executa o próximo comando somente se o anterior funcionar.

```bash
mkdir teste && cd teste
```

---

## ||

Executa o próximo comando somente se houver erro.

```bash
cd pasta_inexistente || echo "Pasta não encontrada."
```

---

# Comentários

Em scripts Bash:

```bash
# Isto é um comentário
```

---

# Laboratório

## Exercício 1

Descubra:

```bash
echo $USER
echo $HOME
echo $PWD
echo $SHELL
```

---

## Exercício 2

Veja seu histórico.

```bash
history
```

Pesquise usando:

```text
CTRL + R
```

---

## Exercício 3

Crie:

```bash
touch teste1.txt teste2.txt teste3.txt foto1.png foto2.png foto10.png
```

Agora teste:

```bash
ls *.txt
ls foto?.png
ls foto*.png
```

---

## Exercício 4

Teste Pipes.

```bash
history | grep sudo
```

Depois:

```bash
ps aux | grep bash
```

---

## Exercício 5

Teste redirecionamento.

```bash
echo "Linux" > teste.txt
cat teste.txt
```

Depois:

```bash
echo "Ubuntu" >> teste.txt
cat teste.txt
```

---

## Exercício 6

Crie uma variável.

```bash
nome="Lucas"
echo $nome
```

---

## Exercício 7

Teste comandos dentro de comandos.

```bash
echo "Agora são $(date)"
```

---

## Exercício 8

Crie um alias.

```bash
alias cls="clear"
```

Execute:

```bash
cls
```

---

# Biblioteca de Comandos

| Comando | Função |
|----------|--------|
| `history` | Histórico |
| `clear` | Limpa a tela |
| `Ctrl + R` | Pesquisa histórico |
| `TAB` | Autocompletar |
| `*` | Qualquer sequência |
| `?` | Um caractere |
| `[]` | Grupo de caracteres |
| `|` | Pipe |
| `>` | Sobrescreve arquivo |
| `>>` | Acrescenta ao arquivo |
| `<` | Entrada |
| `&&` | Executa se der certo |
| `||` | Executa se der erro |
| `alias` | Cria atalhos |
| `echo` | Exibe texto |
| `$USER` | Usuário |
| `$HOME` | Pasta Home |
| `$PWD` | Diretório atual |
| `$SHELL` | Shell atual |
| `$(...)` | Executa um comando dentro de outro |

---

# Erros Comuns

❌ Esquecer o espaço entre comandos.

❌ Confundir `>` com `>>`.

❌ Esquecer o `$` ao acessar variáveis.

❌ Criar aliases e esquecer que eles desaparecem após fechar o terminal (a menos que sejam adicionados ao `~/.bashrc`).

---

# Desafio

Sem consultar a aula:

1. Qual a diferença entre `>` e `>>`?
2. O que faz o operador `|`?
3. Para que serve `&&`?
4. Para que serve `||`?
5. O que faz `$(...)`?
6. Como visualizar o histórico?
7. Como pesquisar um comando antigo?

---

# Cenário Real

Você precisa descobrir todas as vezes que utilizou `sudo`.

Como faria?

Dica:

```bash
history | grep sudo
```

Agora imagine que você queira salvar esse resultado em um arquivo chamado `sudo_log.txt`.

Qual operador você usaria?

---

# Resumo

Nesta aula você aprendeu:

- O que é o Bash
- Histórico de comandos
- Autocompletar
- Wildcards
- Pipes
- Redirecionamento
- Variáveis
- Variáveis do sistema
- Substituição de comandos
- Alias
- Operadores lógicos (`&&` e `||`)

---

# Próxima Aula

## SSH

Você aprenderá:

- O que é SSH
- Acesso remoto
- Geração de chaves SSH
- Autenticação
- SCP
- Transferência de arquivos
- Conexão com servidores Linux

---

#### Feito por Lucas Siqueira
