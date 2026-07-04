# Linux - Aula 04: Logs do Sistema

> **Objetivo:** Aprender onde o Linux registra eventos, como consultar logs e como diagnosticar problemas utilizando ferramentas nativas.

---

# O que são Logs?

Logs são registros de tudo o que acontece no sistema.

Sempre que algo importante ocorre, o Linux normalmente grava um registro.

Exemplos:

- Inicialização do sistema
- Login de usuários
- Erros de programas
- Falhas de serviços
- Atualizações
- Conexões de rede
- Dispositivos USB conectados

Os logs são uma das principais ferramentas de um Administrador de Sistemas.

---

# Por que os Logs são importantes?

Imagine que um servidor caiu às 03:15 da manhã.

Como descobrir o motivo?

Você consulta os logs.

Eles mostram:

- O que aconteceu
- Quando aconteceu
- Qual serviço foi afetado
- Qual usuário realizou uma ação
- Mensagens de erro

Sem logs, seria praticamente impossível descobrir muitos problemas.

---

# Onde ficam os Logs?

No Linux, a maioria dos logs fica em:

```bash
/var/log
```

Veja o conteúdo:

```bash
ls /var/log
```

Você verá diversos arquivos e diretórios.

Exemplo:

```text
alternatives.log
apt
auth.log
boot.log
dpkg.log
journal
kern.log
syslog
```

Nem todos existirão em todas as distribuições.

---

# Conhecendo os principais Logs

## syslog

Registro geral do sistema.

Pode conter mensagens de diversos programas.

---

## auth.log

Relacionado à autenticação.

Registra:

- Login
- SSH
- sudo
- Falhas de senha

Muito utilizado em auditorias.

---

## kern.log

Mensagens do Kernel.

Exemplos:

- Drivers
- Hardware
- Inicialização
- Erros

---

## boot.log

Informações da inicialização.

---

## apt

Registra instalações e atualizações feitas pelo APT.

---

# Visualizando arquivos de Log

## cat

Mostra todo o arquivo.

```bash
cat /var/log/syslog
```

Não recomendado para arquivos grandes.

---

## less

Melhor opção.

```bash
less /var/log/syslog
```

Comandos úteis:

- ↑ ↓ navegar
- Page Up
- Page Down
- q → sair

---

## tail

Mostra as últimas linhas.

```bash
tail /var/log/syslog
```

Muito utilizado.

---

## Últimas 30 linhas

```bash
tail -30 /var/log/syslog
```

---

# Acompanhando um Log em Tempo Real

Um dos comandos mais utilizados por administradores Linux.

```bash
tail -f /var/log/syslog
```

Sempre que surgir uma nova linha, ela aparecerá automaticamente.

Para sair:

```
CTRL + C
```

---

# journalctl

Nos sistemas modernos, muitos logs são armazenados pelo **systemd Journal**.

O comando utilizado é:

```bash
journalctl
```

---

## Últimas mensagens

```bash
journalctl -n 20
```

---

## Logs do Boot Atual

```bash
journalctl -b
```

---

## Logs do Boot Anterior

```bash
journalctl -b -1
```

Muito útil quando o computador reiniciou inesperadamente.

---

## Logs em Tempo Real

```bash
journalctl -f
```

Equivalente ao:

```bash
tail -f
```

---

# Consultando Logs de um Serviço

Exemplo:

```bash
journalctl -u NetworkManager
```

Outro exemplo:

```bash
journalctl -u ssh
```

Assim você vê apenas mensagens daquele serviço.

---

# Procurando Erros

Você pode combinar com grep.

Exemplo:

```bash
journalctl | grep error
```

ou

```bash
journalctl | grep failed
```

---

# dmesg

Mostra mensagens do Kernel.

Muito usado para verificar:

- Hardware
- Drivers
- Pendrives
- SSD
- Memória
- Erros

Execute:

```bash
dmesg
```

---

## Conecte um Pendrive

Depois execute:

```bash
dmesg | tail
```

Você verá o Linux detectando o dispositivo.

Muito legal de observar.

---

# Cenários Reais

## Meu pendrive não apareceu.

Primeiro comando:

```bash
dmesg | tail
```

---

## Meu serviço não inicia.

Verifique:

```bash
systemctl status nome_do_servico
```

Depois:

```bash
journalctl -u nome_do_servico
```

---

## O computador reiniciou sozinho.

Veja:

```bash
journalctl -b -1
```

---

## Quero acompanhar um serviço.

```bash
journalctl -f
```

---

# Laboratório

## Exercício 1

Liste os arquivos:

```bash
ls /var/log
```

---

## Exercício 2

Abra um log.

```bash
less /var/log/syslog
```

---

## Exercício 3

Veja as últimas linhas.

```bash
tail /var/log/syslog
```

---

## Exercício 4

Abra o Journal.

```bash
journalctl
```

---

## Exercício 5

Veja apenas as últimas mensagens.

```bash
journalctl -n 20
```

---

## Exercício 6

Veja os logs do boot atual.

```bash
journalctl -b
```

---

## Exercício 7

Veja os logs do NetworkManager.

```bash
journalctl -u NetworkManager
```

---

## Exercício 8

Conecte um pendrive.

Depois:

```bash
dmesg | tail
```

Observe o Kernel detectando o dispositivo.

---

# Biblioteca de Comandos

| Comando | Função |
|---------|--------|
| `cat` | Exibe um arquivo inteiro |
| `less` | Navega por arquivos grandes |
| `tail` | Mostra as últimas linhas |
| `tail -f` | Acompanha o arquivo em tempo real |
| `journalctl` | Consulta o Journal |
| `journalctl -b` | Logs do boot atual |
| `journalctl -b -1` | Boot anterior |
| `journalctl -u serviço` | Logs de um serviço |
| `journalctl -n 20` | Últimas 20 mensagens |
| `journalctl -f` | Logs em tempo real |
| `dmesg` | Mensagens do Kernel |

---

# Erros Comuns

❌ Abrir um log gigante usando `cat`.

Prefira:

```bash
less
```

---

❌ Esquecer que alguns logs exigem sudo.

Exemplo:

```bash
sudo journalctl
```

---

❌ Ignorar mensagens de erro.

Leia sempre as últimas linhas primeiro.

Na maioria dos casos, o problema está nelas.

---

# Curiosidades

📌 O Journal pode armazenar milhões de mensagens.

📌 O Kernel registra praticamente tudo relacionado ao hardware.

📌 Empresas utilizam servidores centralizados para reunir logs de centenas de máquinas.

📌 Em ambientes Cloud, serviços como AWS CloudWatch e Azure Monitor funcionam seguindo a mesma ideia: coletar e analisar logs.

---

# Desafio

Sem consultar a aula:

1. Onde ficam a maioria dos logs do Linux?
2. Qual comando mostra os logs do boot atual?
3. Como acompanhar um log em tempo real?
4. Qual comando mostra mensagens do Kernel?
5. Como visualizar apenas os logs de um serviço?

---

# Cenário Real (Nível Administrador)

Imagine que um usuário informa:

> "Meu notebook reconheceu o pendrive ontem, mas hoje ele não aparece."

Como você investigaria?

Uma possível sequência seria:

1. Conectar o pendrive.
2. Executar `dmesg | tail`.
3. Verificar se o Kernel detectou o dispositivo.
4. Conferir os logs relacionados.
5. Identificar possíveis erros de hardware ou driver.

Esse tipo de raciocínio é muito comum na administração de sistemas Linux.

---

# Resumo

Nesta aula você aprendeu:

- O que são Logs
- Diretório `/var/log`
- `cat`
- `less`
- `tail`
- `tail -f`
- `journalctl`
- `journalctl -b`
- `journalctl -u`
- `dmesg`
- Diagnóstico de problemas utilizando logs

---

# Próxima Aula

## Bash

Você aprenderá:

- Pipes (`|`)
- Redirecionamento (`>`, `>>`, `<`)
- Variáveis
- Alias
- Histórico de comandos
- Wildcards (`*`, `?`, `[]`)
- Automação básica

Essa será uma das aulas mais importantes do módulo Linux.

---

#### Feito por Lucas Siqueira