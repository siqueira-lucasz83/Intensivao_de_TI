# Linux - Aula 06: SSH (Secure Shell)

> **Objetivo:** Aprender a acessar computadores remotamente de forma segura, utilizar autenticação por senha e por chaves, copiar arquivos e compreender como administradores gerenciam servidores Linux.

---

# O que é SSH?

SSH significa:

**Secure Shell**

É um protocolo que permite acessar outro computador remotamente através da rede de forma criptografada.

Em vez de estar fisicamente na frente do computador, você controla tudo pelo terminal.

---

# Onde o SSH é utilizado?

Praticamente em todo lugar.

Exemplos:

- Servidores Linux
- AWS EC2
- Azure Virtual Machines
- Google Cloud
- Raspberry Pi
- NAS
- VPS
- Laboratórios
- Data Centers

Se você pretende trabalhar com Infraestrutura, Cloud ou DevOps, utilizará SSH diariamente.

---

# Como funciona?

Imagine dois computadores.

```text
┌──────────────┐
│ Seu Notebook │
└──────┬───────┘
       │
       │ SSH
       │
┌──────▼───────┐
│ Servidor     │
└──────────────┘
```

Você executa comandos no notebook e eles são processados no servidor.

---

# Sintaxe

```bash
ssh usuario@ip
```

Exemplo:

```bash
ssh lucas@192.168.0.10
```

---

# Primeiro acesso

Na primeira conexão aparecerá:

```text
Are you sure you want to continue connecting?
```

Digite:

```text
yes
```

Depois informe a senha do usuário remoto.

---

# Descobrindo o IP

No computador remoto:

```bash
hostname -I
```

Ou:

```bash
ip addr
```

---

# Verificando se o SSH está instalado

Ubuntu:

```bash
systemctl status ssh
```

Se não estiver instalado:

```bash
sudo apt install openssh-server
```

Depois:

```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```

---

# Testando o serviço

```bash
systemctl status ssh
```

Se aparecer:

```text
Active: active (running)
```

Está funcionando.

---

# Chaves SSH

Ao invés de utilizar senha, podemos utilizar criptografia.

Criando uma chave:

```bash
ssh-keygen
```

O sistema criará dois arquivos.

---

# Tipos de chave

Privada:

```text
id_ed25519
```

Nunca compartilhe.

Pública:

```text
id_ed25519.pub
```

Pode ser enviada ao servidor.

---

# Enviando a chave

```bash
ssh-copy-id usuario@ip
```

Depois disso, normalmente não será mais necessário digitar senha.

---

# Copiando arquivos

Utilizando SCP.

Copiar para o servidor:

```bash
scp arquivo.txt usuario@ip:/home/usuario
```

Copiar do servidor:

```bash
scp usuario@ip:/home/usuario/arquivo.txt .
```

---

# Encerrando uma sessão

```bash
exit
```

Ou:

```text
Ctrl + D
```

---

# Segurança

Nunca compartilhe:

- Chave privada
- Senhas
- Arquivo id_ed25519

Sempre compartilhe apenas:

```text
id_ed25519.pub
```

---

# Laboratório

## Exercício 1

Verifique o status do SSH.

```bash
systemctl status ssh
```

---

## Exercício 2

Descubra seu IP.

```bash
hostname -I
```

---

## Exercício 3

Crie uma chave.

```bash
ssh-keygen
```

---

## Exercício 4

Liste as chaves.

```bash
ls ~/.ssh
```

---

## Exercício 5

Visualize sua chave pública.

```bash
cat ~/.ssh/id_ed25519.pub
```

---

## Exercício 6

Conecte-se a outro computador (caso tenha um servidor disponível).

```bash
ssh usuario@ip
```

---

# Biblioteca

| Comando | Função |
|----------|--------|
| `ssh` | Conectar remotamente |
| `ssh-keygen` | Criar chaves |
| `ssh-copy-id` | Copiar chave pública |
| `scp` | Copiar arquivos |
| `hostname -I` | Mostrar IP |
| `systemctl status ssh` | Status do SSH |
| `exit` | Encerrar sessão |

---

# Erros Comuns

❌ Compartilhar a chave privada.

❌ Esquecer de iniciar o serviço SSH.

❌ Digitar o IP errado.

❌ Confundir `scp` com `cp`.

---

# Cenário Real

Você foi contratado para administrar um servidor Linux na AWS.

O servidor não possui interface gráfica.

Você recebe:

```text
IP: 18.xxx.xxx.xxx

Usuário: ubuntu
```

Sua primeira ação será:

```bash
ssh ubuntu@18.xxx.xxx.xxx
```

Depois disso, toda a administração será feita pelo terminal.

---

# Resumo

Nesta aula você aprendeu:

- O que é SSH
- Como funciona
- Conexão remota
- Descobrir IP
- Serviço SSH
- Chaves SSH
- ssh-keygen
- ssh-copy-id
- SCP
- Segurança

---

# Próxima Aula

## Cron

Você aprenderá:

- Automatizar tarefas
- Agendar comandos
- Backups automáticos
- Atualizações programadas
- Rotinas administrativas

---

#### Feito por Lucas Siqueira