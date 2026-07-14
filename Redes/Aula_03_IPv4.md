# 🌐 Aula 3 — IPv4

## 🎯 Objetivo

Compreender o que é um endereço IPv4, sua estrutura, como ele funciona e por que todo dispositivo conectado a uma rede precisa de um endereço IP.

---

## O que é um endereço IP?

**IP (Internet Protocol)** é um endereço único que identifica um dispositivo dentro de uma rede.

Assim como uma casa possui um endereço para receber correspondências, um computador também precisa de um endereço para enviar e receber dados.

Exemplo de IPv4:

```text
192.168.1.10
```

---

## Analogia

Imagine uma cidade.

Cada casa possui um endereço.

```
Rua A, nº 10
Rua B, nº 25
Rua C, nº 100
```

Quando alguém envia uma carta, ela precisa saber exatamente para qual endereço deve ir.

Nas redes acontece a mesma coisa.

```
Notebook
192.168.1.10

↓

Roteador

↓

Internet

↓

Servidor
142.250.78.46
```

Sem um endereço IP, os dispositivos não conseguem se comunicar.

---

## O que significa IPv4?

IPv4 significa:

**Internet Protocol Version 4**

É a quarta versão do protocolo IP e continua sendo a mais utilizada no mundo.

---

## Estrutura do IPv4

Um endereço IPv4 possui **32 bits**, divididos em **4 grupos de 8 bits**, chamados de **octetos**.

Exemplo:

```
192.168.1.10
```

Separando os octetos:

```
192
168
1
10
```

Cada octeto pode possuir valores entre:

```
0 até 255
```

Por isso um IPv4 sempre possui quatro números separados por pontos.

---

## Exemplos

### Endereços válidos

```
192.168.0.1

10.0.0.25

172.16.15.8

8.8.8.8
```

### Endereços inválidos

```
300.168.1.1

192.168.500.1

192.168.1

192.168.1.1.5
```

---

## IP Público e IP Privado

### IP Privado

É utilizado dentro da rede local.

Exemplo:

```
192.168.1.15
```

Faixas privadas:

```
10.0.0.0 – 10.255.255.255

172.16.0.0 – 172.31.255.255

192.168.0.0 – 192.168.255.255
```

Esses endereços não podem ser acessados diretamente pela Internet.

---

### IP Público

É o endereço fornecido pelo provedor de Internet.

Exemplo:

```
189.xxx.xxx.xxx
```

É através dele que sua casa é identificada na Internet.

---

## Exemplo da rede de uma casa

Imagine a seguinte rede:

```
Notebook
192.168.0.10

Celular
192.168.0.20

PS5
192.168.0.30
```

Todos estão conectados ao mesmo roteador.

O roteador possui um IP público.

```
Notebook
192.168.0.10

↓

Roteador

↓

IP Público

↓

Internet

↓

Servidor do YouTube
```

A Internet enxerga apenas o IP público do roteador.

---

## Como descobrir seu IPv4

### Windows

Abra o Prompt de Comando ou PowerShell.

Execute:

```cmd
ipconfig
```

Procure pela linha:

```
Endereço IPv4 . . . . . . . . . : 192.168.x.x
```

---

### Linux

```bash
ip addr
```

ou

```bash
hostname -I
```

---

## Por que cada dispositivo precisa de um IP?

Imagine dois notebooks conectados ao mesmo roteador.

```
Notebook A

Notebook B
```

Se ambos não possuíssem um endereço IP, o roteador não saberia para qual deles entregar os dados.

O endereço IP resolve exatamente esse problema.

Cada dispositivo recebe um endereço único dentro da rede.

---

## Curiosidade

O IPv4 possui aproximadamente:

```
4.294.967.296
```

endereços possíveis.

Esse número parecia enorme quando o protocolo foi criado.

Com bilhões de celulares, computadores, consoles, servidores e dispositivos IoT conectados atualmente, essa quantidade se tornou insuficiente.

Por esse motivo surgiu o **IPv6**, que será o tema da próxima aula.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| IPv4 | Quarta versão do protocolo IP |
| Tamanho | 32 bits |
| Formato | 4 números separados por pontos |
| Faixa de cada número | 0 a 255 |
| Função | Identificar dispositivos na rede |
| IP Privado | Utilizado dentro da rede local |
| IP Público | Identifica sua rede na Internet |

---

# Conceitos importantes

- Todo dispositivo conectado à rede precisa de um endereço IP.
- O IP funciona como o endereço de uma residência.
- Existem IPs públicos e privados.
- O roteador conecta a rede local à Internet.
- O IPv4 possui uma quantidade limitada de endereços.

---

# Laboratório

No Windows, execute:

```cmd
ipconfig
```

Responda:

1. Qual é o seu endereço IPv4?
2. Ele começa com `192.168`, `10` ou `172`?
3. Seu endereço é público ou privado?

---

# Próxima aula

➡️ Aula 4 — IPv6

---

#### Feito por Lucas Siqueira
