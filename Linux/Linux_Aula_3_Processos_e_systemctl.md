# Linux - Aula 03: Processos e `systemctl`

> **Objetivo:** Entender como o Linux executa programas, gerencia processos e controla serviços.

---

# O que é um processo?

Um **programa** é um arquivo armazenado no disco.

Quando ele é executado, ele se torna um **processo**, ou seja, uma instância em execução na memória RAM.

Exemplo:

```text
VS Code
Firefox
Spotify
Bash
        │
        ▼
    Programa
        │
 Executado pelo Sistema
        ▼
     Processo
```

Todo processo possui:

- PID (Process ID)
- Usuário proprietário
- Uso de CPU
- Uso de Memória
- Estado
- Processo Pai

---

# Programa x Processo

Muita gente confunde esses conceitos.

## Programa

É um arquivo armazenado no HD ou SSD.

Exemplo:

```text
/usr/bin/firefox
```

Ele está parado.

Não está consumindo CPU.

Não está usando RAM.

---

## Processo

É o programa em execução.

Ele:

- ocupa memória RAM;
- utiliza CPU;
- possui um PID;
- pode criar outros processos.

---

# O que é PID?

PID significa:

**Process ID**

Todo processo recebe um identificador único.

Exemplo:

```bash
echo $$
```

Saída:

```text
3158
```

Esse é o PID do seu terminal.

---

## Curiosidade

Normalmente:

- processos criados primeiro possuem PID menor;
- processos mais recentes possuem PID maior.

Com o tempo, o Linux pode reutilizar PIDs.

---

# Visualizando processos

## Apenas os processos do terminal

```bash
ps
```

Exemplo:

```text
PID TTY          TIME CMD
3158 pts/0    00:00:00 bash
3220 pts/0    00:00:00 ps
```

---

## Todos os processos

```bash
ps aux
```

As colunas mais importantes:

| Coluna | Significado |
|---------|-------------|
| USER | Usuário dono |
| PID | Identificador |
| %CPU | Uso da CPU |
| %MEM | Uso da RAM |
| COMMAND | Programa |

---

# Encontrando um processo

```bash
ps aux | grep bash
```

Aqui usamos o operador:

```text
|
```

Chamado de **Pipe**.

Ele envia a saída de um comando para outro.

Exemplo:

```text
ps aux
      │
      ▼
grep bash
```

Resultado:

Somente linhas contendo "bash".

---

# Monitorando processos

## top

```bash
top
```

Mostra:

- CPU
- RAM
- Processos
- Tempo de atividade

Para sair:

```text
q
```

---

## htop

Mais bonito e intuitivo.

Instalação:

```bash
sudo apt install htop
```

Execução:

```bash
htop
```

---

# Encerrando processos

Primeiro descubra o PID.

Depois:

```bash
kill PID
```

Exemplo:

```bash
kill 3158
```

---

## O que acontece?

Na verdade o comando **kill** não mata diretamente o processo.

Ele envia um **sinal**.

O padrão é:

```bash
kill PID
```

equivale a:

```bash
kill -15 PID
```

---

# SIGTERM (15)

É um encerramento seguro.

O programa consegue:

- salvar arquivos;
- fechar conexões;
- liberar memória;
- finalizar corretamente.

Sempre prefira este.

---

# SIGKILL (9)

```bash
kill -9 PID
```

Esse é o famoso "mata na hora".

O processo não consegue:

- salvar dados;
- finalizar tarefas;
- limpar memória.

Use somente quando necessário.

---

# Biblioteca de sinais

| Sinal | Número | Uso |
|---------|---------|------------------------------|
| SIGTERM | 15 | Encerramento seguro |
| SIGKILL | 9 | Mata imediatamente |
| SIGSTOP | 19 | Pausa um processo |
| SIGCONT | 18 | Continua um processo pausado |
| SIGHUP | 1 | Recarrega configurações |

---

# Processo Pai e Filho

Todo processo possui um processo pai.

Veja isso com:

```bash
pstree
```

ou

```bash
pstree -p
```

Exemplo:

```text
systemd(1)
│
├── NetworkManager
├── bluetoothd
├── gnome-shell
│
└── gnome-terminal
        │
        └── bash
```

O terminal cria o Bash.

O Bash cria outros programas.

---

# O que é um serviço?

Nem todo programa possui uma janela.

Alguns ficam executando em segundo plano.

Exemplos:

- SSH
- Docker
- Banco de Dados
- Bluetooth
- Servidor Web

Esses programas são chamados de **Serviços**.

---

# systemctl

É o comando responsável por controlar serviços.

---

## Verificar status

```bash
systemctl status NetworkManager
```

---

## Iniciar

```bash
sudo systemctl start nome_do_servico
```

---

## Parar

```bash
sudo systemctl stop nome_do_servico
```

---

## Reiniciar

```bash
sudo systemctl restart nome_do_servico
```

---

## Habilitar na inicialização

```bash
sudo systemctl enable nome_do_servico
```

---

## Desabilitar

```bash
sudo systemctl disable nome_do_servico
```

---

## Listar serviços ativos

```bash
systemctl list-units --type=service --state=running
```

---

# Diferença entre `start` e `enable`

Muita gente confunde.

| Comando | O que faz |
|-----------|----------------------------|
| start | Inicia agora |
| stop | Para agora |
| restart | Reinicia agora |
| enable | Inicia automaticamente no próximo boot |
| disable | Impede inicialização automática |

---

# Laboratório

## Exercício 1

Veja os processos:

```bash
ps
```

Depois:

```bash
ps aux
```

---

## Exercício 2

Descubra o PID do terminal.

```bash
echo $$
```

Abra outro terminal.

Execute novamente.

Compare os dois PIDs.

---

## Exercício 3

Instale o htop.

```bash
sudo apt install htop
```

Execute:

```bash
htop
```

Saia pressionando:

```text
q
```

---

## Exercício 4

Veja os serviços ativos.

```bash
systemctl list-units --type=service --state=running
```

---

## Exercício 5

Veja informações detalhadas de um serviço.

```bash
systemctl status NetworkManager
```

---

## Exercício 6

Visualize a árvore de processos.

```bash
pstree -p
```

---

# Curiosidades

✅ Todo processo possui um PID.

✅ Todo processo possui um processo pai.

✅ O PID 1 normalmente pertence ao `systemd`, responsável por iniciar o sistema.

✅ O `kill` envia sinais; ele não "mata" diretamente um processo.

---

# Desafio

Sem consultar a aula:

1. Explique a diferença entre programa e processo.
2. O que é um PID?
3. Qual a diferença entre `kill` e `kill -9`?
4. Qual a diferença entre `systemctl start` e `systemctl enable`?
5. Por que matar um terminal não fecha os outros?

---

# Resumo

Nesta aula você aprendeu:

- Programa x Processo
- PID
- `ps`
- `top`
- `htop`
- `kill`
- Sinais (`SIGTERM` e `SIGKILL`)
- Processo Pai e Filho
- `pstree`
- Serviços
- `systemctl`

---

# Próxima Aula

## Logs do Sistema

Você aprenderá:

- `journalctl`
- `/var/log`
- Logs do kernel
- Logs de serviços
- Como descobrir por que um servidor ou serviço falhou

---

#### Feito por Lucas Siqueira
