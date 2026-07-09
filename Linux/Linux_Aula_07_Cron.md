# Linux - Aula 07: Cron (Automação de Tarefas)

> **Objetivo:** Aprender a automatizar tarefas utilizando o Cron, agendar comandos e criar rotinas administrativas.

---

# O que é o Cron?

Cron é um serviço do Linux responsável por executar tarefas automaticamente em horários programados.

Pense nele como um "Agendador de Tarefas" do Windows.

Exemplos:

- Backup diário
- Atualização automática
- Limpeza de arquivos temporários
- Reinício de serviços
- Execução de scripts

---

# Como funciona?

O Cron lê uma tabela chamada:

```text
crontab
```

Nela ficam armazenadas todas as tarefas agendadas.

---

# Visualizar tarefas

```bash
crontab -l
```

Se nunca criou uma:

```text
no crontab for lucas
```

É normal.

---

# Editar o Cron

```bash
crontab -e
```

Na primeira vez o Linux pode perguntar qual editor deseja utilizar.

Escolha o Nano.

---

# Estrutura do Cron

Cada linha possui cinco campos de tempo.

```text
* * * * * comando
```

Significado:

```text
┌──────── Minuto (0-59)
│ ┌────── Hora (0-23)
│ │ ┌──── Dia do mês (1-31)
│ │ │ ┌── Mês (1-12)
│ │ │ │ ┌ Dia da semana (0-7)
│ │ │ │ │
* * * * * comando
```

---

# Exemplos

Todos os dias às 08:00

```text
0 8 * * * comando
```

---

Todos os dias às 23:30

```text
30 23 * * * comando
```

---

Toda segunda-feira às 09:00

```text
0 9 * * 1 comando
```

---

A cada hora

```text
0 * * * * comando
```

---

A cada 5 minutos

```text
*/5 * * * * comando
```

---

# Executando Scripts

Imagine o script:

```text
/home/lucas/backup.sh
```

Agendar às 22:00:

```text
0 22 * * * /home/lucas/backup.sh
```

---

# Redirecionando saída

Salvar um log:

```text
0 22 * * * /home/lucas/backup.sh >> /home/lucas/backup.log
```

---

# Removendo mensagens

```text
> /dev/null 2>&1
```

Exemplo:

```text
0 22 * * * script.sh > /dev/null 2>&1
```

Isso descarta toda a saída do script.

---

# Verificando o serviço

```bash
systemctl status cron
```

Ou em algumas distribuições:

```bash
systemctl status crond
```

---

# Iniciar o serviço

```bash
sudo systemctl start cron
```

---

# Habilitar na inicialização

```bash
sudo systemctl enable cron
```

---

# Remover todas as tarefas

```bash
crontab -r
```

⚠️ Cuidado!

Remove todas as tarefas do usuário.

---

# Laboratório

## Exercício 1

Veja sua crontab.

```bash
crontab -l
```

---

## Exercício 2

Abra para edição.

```bash
crontab -e
```

---

## Exercício 3

Agende um comando para executar a cada minuto.

```text
* * * * * echo "Olá Cron"
```

---

## Exercício 4

Agende um script.

```text
0 18 * * * /home/lucas/script.sh
```

---

## Exercício 5

Confira o serviço.

```bash
systemctl status cron
```

---

# Biblioteca

| Comando | Função |
|----------|--------|
| `crontab -l` | Lista tarefas |
| `crontab -e` | Edita tarefas |
| `crontab -r` | Remove tarefas |
| `systemctl status cron` | Status do Cron |
| `systemctl enable cron` | Inicialização automática |
| `systemctl start cron` | Iniciar serviço |

---

# Operadores Especiais

| Símbolo | Significado |
|----------|-------------|
| `*` | Qualquer valor |
| `*/5` | A cada 5 unidades |
| `1-5` | Intervalo |
| `1,3,5` | Valores específicos |

---

# Cenários Reais

## Backup diário

```text
0 22 * * * /home/lucas/backup.sh
```

---

## Atualizar sistema domingo às 03:00

```text
0 3 * * 0 sudo apt update
```

---

## Limpar arquivos temporários

```text
0 1 * * * rm -rf /tmp/*
```

---

## Verificar espaço em disco

```text
0 */6 * * * df -h >> /home/lucas/disco.log
```

---

# Erros Comuns

❌ Esquecer o caminho completo do script.

❌ Esquecer permissão de execução (`chmod +x`).

❌ Agendar um script sem testar antes manualmente.

❌ Esquecer que o Cron roda com um ambiente diferente do terminal.

---

# Desafio Final

Crie um script chamado:

```text
backup.sh
```

Depois agende sua execução todos os dias às 20:00.

---

# Resumo

Nesta aula você aprendeu:

- O que é o Cron
- Crontab
- Agendamento
- Estrutura do tempo
- Execução automática
- Logs
- Boas práticas

---

#### Feito por Lucas Siqueira