# Linux - Aula 05.5: Shell Scripting (Programação em Bash)

> **Objetivo:** Aprender a criar scripts Bash para automatizar tarefas, utilizar estruturas de programação e desenvolver pequenas ferramentas para administração de sistemas.

---

# O que é um Script Bash?

Um script Bash é um arquivo contendo vários comandos que serão executados automaticamente.

Imagine que você sempre executa:

```bash
sudo apt update
sudo apt upgrade -y
sudo apt autoremove -y
```

Ao invés de digitar tudo toda vez, você cria um script.

---

# Primeiro Script

Crie um arquivo:

```bash
nano primeiro_script.sh
```

Digite:

```bash
#!/bin/bash

echo "Olá, Lucas!"

echo "Bem-vindo ao Bash!"
```

Salve.

Agora dê permissão:

```bash
chmod +x primeiro_script.sh
```

Execute:

```bash
./primeiro_script.sh
```

---

# O Shebang

A primeira linha:

```bash
#!/bin/bash
```

Informa qual interpretador executará o script.

É obrigatória na maioria dos scripts.

---

# Comentários

```bash
# Isto é um comentário
```

Comentários ajudam a documentar o código.

---

# Variáveis

Criando:

```bash
nome="Lucas"
```

Usando:

```bash
echo $nome
```

---

# Entrada de Dados

```bash
#!/bin/bash

echo "Digite seu nome:"

read nome

echo "Olá, $nome!"
```

Agora o usuário participa do script.

---

# Argumentos

Imagine executar:

```bash
./script.sh Lucas 20
```

Dentro do script:

```bash
echo $1
```

Resultado:

```text
Lucas
```

```bash
echo $2
```

Resultado:

```text
20
```

---

# Variáveis Especiais

| Variável | Significado |
|-----------|-------------|
| `$0` | Nome do script |
| `$1` | Primeiro argumento |
| `$2` | Segundo argumento |
| `$#` | Quantidade de argumentos |
| `$?` | Código de saída do último comando |
| `$$` | PID do script |

---

# if

```bash
idade=20

if [ $idade -ge 18 ]
then
    echo "Maior de idade"
fi
```

---

# if / else

```bash
read idade

if [ $idade -ge 18 ]
then
    echo "Pode entrar."
else
    echo "Acesso negado."
fi
```

---

# Comparações

| Operador | Significado |
|-----------|-------------|
| `-eq` | Igual |
| `-ne` | Diferente |
| `-gt` | Maior |
| `-lt` | Menor |
| `-ge` | Maior ou igual |
| `-le` | Menor ou igual |

---

# Strings

```bash
nome="Lucas"

if [ "$nome" = "Lucas" ]
then
    echo "Olá!"
fi
```

---

# case

Muito melhor do que vários if.

```bash
read opcao

case $opcao in

1)
echo "Cadastrar"
;;

2)
echo "Excluir"
;;

3)
echo "Sair"
;;

*)
echo "Inválido"
;;

esac
```

---

# for

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

---

# while

```bash
contador=1

while [ $contador -le 5 ]
do

echo $contador

contador=$((contador+1))

done
```

---

# Arrays

```bash
carros=("Golf" "Jetta" "Civic")

echo ${carros[0]}
```

Resultado:

```text
Golf
```

---

# Funções

```bash
saudacao(){

echo "Olá!"

}

saudacao
```

---

# Código de Saída

Todo comando retorna um código.

Veja:

```bash
echo $?
```

Normalmente:

| Código | Significado |
|----------|------------|
| 0 | Sucesso |
| diferente de 0 | Erro |

---

# Operador &&

```bash
mkdir teste && cd teste
```

Só entra se criar a pasta.

---

# Operador ||

```bash
cd pasta || echo "Erro!"
```

Só executa o echo se houver erro.

---

# Exemplo Real

Atualização automática.

```bash
#!/bin/bash

echo "Atualizando..."

sudo apt update &&
sudo apt upgrade -y &&
sudo apt autoremove -y

echo "Fim."
```

---

# Exemplo Real 2

Backup.

```bash
#!/bin/bash

cp documento.txt backup.txt

echo "Backup realizado!"
```

---

# Exemplo Real 3

Descobrir espaço em disco.

```bash
#!/bin/bash

df -h

echo "Espaço verificado."
```

---

# Biblioteca

| Comando | Função |
|----------|--------|
| `#!/bin/bash` | Interpretador |
| `read` | Entrada |
| `echo` | Saída |
| `if` | Decisão |
| `else` | Alternativa |
| `case` | Menu |
| `for` | Repetição |
| `while` | Loop |
| `function` | Função |
| `$1` | Primeiro argumento |
| `$?` | Código de saída |
| `$$` | PID |

---

# Laboratório

## Exercício 1

Crie um script que diga:

```text
Olá Mundo!
```

---

## Exercício 2

Pergunte o nome do usuário.

Resposta:

```text
Olá Lucas!
```

---

## Exercício 3

Pergunte a idade.

Se for maior de 18:

```text
Maior de idade.
```

Caso contrário:

```text
Menor de idade.
```

---

## Exercício 4

Crie um contador de 1 até 10 usando `for`.

---

## Exercício 5

Faça o mesmo usando `while`.

---

## Exercício 6

Crie um menu utilizando `case`.

```text
1 - Atualizar

2 - Mostrar Data

3 - Sair
```

---

## Exercício 7

Mostre:

```bash
date
whoami
pwd
```

Tudo em um único script.

---

# Erros Comuns

❌ Esquecer o `chmod +x`.

❌ Esquecer o `#!/bin/bash`.

❌ Esquecer espaços no `if`.

Errado:

```bash
if[$idade-ge18]
```

Correto:

```bash
if [ $idade -ge 18 ]
```

---

# Desafio Final

Crie um script chamado:

```text
sistema.sh
```

Quando executado, ele deverá mostrar:

```text
==========================
 Sistema Linux
==========================

1 - Usuário Atual

2 - Data

3 - Diretório Atual

4 - Espaço em Disco

5 - Sair
```

Ao escolher uma opção, o script deve executar o comando correspondente.

Utilize:

- `case`
- `read`
- `echo`

---

# Resumo

Nesta aula você aprendeu:

- Criar scripts Bash
- Shebang
- Variáveis
- Entrada de dados
- Argumentos
- if
- else
- case
- for
- while
- Arrays
- Funções
- Código de saída
- Scripts reais

---

# Próxima Aula

## SSH

Você aprenderá:

- Acesso remoto
- Chaves SSH
- SCP
- ssh-copy-id
- Configuração segura
- Conexão com servidores Linux

---

#### Feito por Lucas Siqueira