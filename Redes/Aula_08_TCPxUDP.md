# 🌐 Aula 8 — TCP x UDP

## 🎯 Objetivo

Compreender as diferenças entre TCP e UDP, quando cada protocolo é utilizado e por que eles possuem comportamentos diferentes durante a transmissão de dados.

---

# O que são TCP e UDP?

TCP e UDP são protocolos da **Camada de Transporte** do modelo TCP/IP.

Eles são responsáveis por transportar os dados entre dois dispositivos conectados à rede.

Embora ambos façam esse trabalho, cada um possui características diferentes.

---

# TCP

**TCP (Transmission Control Protocol)** é um protocolo orientado à conexão.

Seu principal objetivo é garantir que os dados cheguem corretamente ao destino.

Ele verifica:

- Se os dados chegaram.
- Se chegaram na ordem correta.
- Se algum pacote foi perdido.
- Se algum pacote precisa ser reenviado.

A prioridade do TCP é a **confiabilidade**.

---

# Analogia do TCP

Imagine enviar um documento importante pelos Correios.

Você deseja:

- Confirmação de entrega.
- Garantia de que nenhuma página foi perdida.
- Ordem correta das páginas.

Mesmo que isso demore um pouco mais, o importante é que tudo chegue corretamente.

É exatamente assim que o TCP funciona.

---

# UDP

**UDP (User Datagram Protocol)** é um protocolo sem conexão.

Ele simplesmente envia os dados.

Não verifica se chegaram.

Não solicita confirmação.

Não reenviará pacotes perdidos.

Sua prioridade é a **velocidade**.

---

# Analogia do UDP

Imagine uma transmissão de rádio.

Se uma palavra falhar durante a transmissão, a rádio continua normalmente.

Ela não interrompe a programação para repetir aquela palavra.

O UDP faz exatamente isso.

---

# Comparação

| TCP | UDP |
|------|------|
| Confiável | Rápido |
| Verifica erros | Não verifica |
| Reenvia pacotes | Não reenvia |
| Mantém a ordem | Não garante ordem |
| Mais lento | Mais rápido |

---

# Como o TCP funciona?

Antes de enviar dados, ele estabelece uma conexão.

Esse processo é chamado de **Three-Way Handshake**.

Acontece assim:

```
Cliente

↓

SYN

↓

Servidor

↓

SYN + ACK

↓

Cliente

↓

ACK

↓

Conexão estabelecida
```

Somente depois disso os dados começam a ser enviados.

---

# Como o UDP funciona?

Muito mais simples.

```
Cliente

↓

Envia dados

↓

Servidor
```

Não existe confirmação.

---

# Quando utilizar TCP?

TCP é utilizado quando perder informações não é aceitável.

Exemplos:

- Sites
- Bancos
- Compras online
- E-mails
- Download de arquivos
- Transferência de documentos

Nesses casos, todos os dados precisam chegar corretamente.

---

# Quando utilizar UDP?

UDP é utilizado quando velocidade é mais importante que confiabilidade.

Exemplos:

- Jogos online
- Chamadas de voz
- Videoconferências
- Streaming ao vivo
- IPTV
- DNS

Se um pacote for perdido, normalmente o usuário nem percebe.

Esperar pelo reenvio poderia causar atraso.

---

# Exemplo

Imagine uma chamada no Discord.

Se uma palavra falhar, você provavelmente entenderá o restante da conversa.

Esperar o reenvio dessa palavra causaria um atraso perceptível.

Por isso aplicações em tempo real costumam utilizar UDP.

Agora imagine uma transferência bancária.

Perder um único pacote pode corromper a transação.

Nesse caso, utiliza-se TCP.

---

# TCP e UDP utilizam portas

Além do endereço IP, cada comunicação utiliza uma porta.

Exemplo:

```
IP

192.168.0.15

↓

Porta

443
```

O IP identifica o dispositivo.

A porta identifica qual serviço dentro do dispositivo deve receber os dados.

---

# Portas conhecidas

| Serviço | Porta |
|----------|------:|
| HTTP | 80 |
| HTTPS | 443 |
| DNS | 53 |
| SSH | 22 |
| FTP | 21 |

Essas portas serão importantes nas próximas aulas.

---

# Resumo

| TCP | UDP |
|------|------|
| Confiável | Rápido |
| Orientado à conexão | Sem conexão |
| Reenvia pacotes | Não reenvia |
| Mantém ordem | Não garante ordem |
| Utilizado em bancos e sites | Utilizado em jogos e chamadas de voz |

---

# Conceitos importantes

- TCP significa **Transmission Control Protocol**.
- UDP significa **User Datagram Protocol**.
- Ambos pertencem à Camada de Transporte.
- TCP prioriza confiabilidade.
- UDP prioriza velocidade.
- Ambos utilizam portas para identificar serviços.

---

# Laboratório

## Ver conexões abertas

No Windows:

```cmd
netstat -ano
```

Observe:

- Endereço IP.
- Porta utilizada.
- Estado da conexão.

---

## Testar conexão

```cmd
ping google.com
```

Depois:

```cmd
nslookup google.com
```

Observe como vários protocolos trabalham juntos.

---

# Desafio

Responda:

1. O que significa TCP?
2. O que significa UDP?
3. Qual deles é mais confiável?
4. Qual deles é mais rápido?
5. Por que um jogo online normalmente utiliza UDP?
6. Por que um banco normalmente utiliza TCP?
7. Em qual camada do modelo TCP/IP eles trabalham?

---

# Próxima aula

➡️ Aula 9 — HTTP x HTTPS

Você vai aprender como funciona a comunicação entre navegador e servidor e entender por que aparece um cadeado 🔒 ao acessar sites seguros.

---

#### Feito por Lucas Siqueira
