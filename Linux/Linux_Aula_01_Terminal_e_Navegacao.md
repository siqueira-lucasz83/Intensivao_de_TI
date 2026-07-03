# Linux - Aula 1: Terminal e Navegação

## Objetivos

-   Entender a estrutura do sistema de arquivos.
-   Navegar entre diretórios.
-   Criar, listar e remover arquivos e pastas.
-   Ganhar familiaridade com o terminal.

## Estrutura do sistema

-   `/` → raiz do sistema.
-   `/home` → arquivos dos usuários.
-   `/etc` → configurações do sistema.
-   `/var` → logs, cache e dados variáveis.
-   `/usr` → programas instalados.
-   `/tmp` → arquivos temporários.
-   `/boot` → arquivos de inicialização.

## Comandos aprendidos

### Descobrir o diretório atual

``` bash
pwd
```

### Listar arquivos

``` bash
ls
ls -lah
```

Opções: - `-l` → detalhes. - `-a` → arquivos ocultos. - `-h` → tamanhos
legíveis.

### Navegar

``` bash
cd pasta
cd ..
cd ~
cd /
```

### Criar diretórios

``` bash
mkdir laboratorio
```

### Criar arquivos

``` bash
touch rede.txt
touch python.txt
touch aws.txt
```

### Remover

``` bash
rm arquivo.txt
rmdir pasta_vazia
rm -r pasta
```

> **Atenção:** `rm` não envia arquivos para a lixeira.

## Laboratório realizado

``` bash
pwd
ls -lah
mkdir laboratorio
cd laboratorio
touch rede.txt
touch python.txt
touch aws.txt
ls -lah
```

## Desafio

-   Voltar para a pasta pessoal.
-   Criar `linux`.
-   Entrar em `linux`.
-   Criar `scripts`.
-   Entrar em `scripts`.
-   Criar `backup.sh`.
-   Confirmar o diretório com `pwd`.

## Resumo

Nesta aula foram introduzidos: - Terminal Linux. - Estrutura de
diretórios. - Navegação. - Manipulação básica de arquivos. - Primeiros
comandos essenciais.

Próxima aula: **Permissões, usuários, grupos e sudo**.
