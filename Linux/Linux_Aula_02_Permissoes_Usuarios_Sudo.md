# Linux - Aula 02: Permissões, Usuários e `sudo`

## Biblioteca de permissões

    Código Permissão   Uso
  -------- ----------- ----------------------------------
       777 rwxrwxrwx   Evite. Todos têm acesso total.
       775 rwxrwxr-x   Projetos compartilhados.
       755 rwxr-xr-x   Scripts e diretórios.
       750 rwxr-x---   Dono e grupo.
       745 rwxr--r-x   Pouco comum.
       700 rwx------   Privado.
       664 rw-rw-r--   Documentos compartilhados.
       655 rw-r-xr-x   Pouco comum.
       644 rw-r--r--   Arquivos de configuração.
       600 rw-------   Chaves SSH e arquivos sensíveis.
       400 r--------   Somente leitura.

r=4, w=2, x=1.

## Comandos

``` bash
ls -l
whoami
id
chmod 755 script.sh
chmod 644 config.conf
chmod +x script.sh
sudo apt update
```

## Laboratório

``` bash
mkdir permissoes
cd permissoes
touch script.sh config.conf dados.txt
whoami
id
chmod +x script.sh
chmod 644 config.conf
chmod 755 script.sh
ls -l
```
