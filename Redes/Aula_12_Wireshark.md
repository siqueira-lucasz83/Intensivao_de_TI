# 🌐 Aula 12 — Wireshark

## 🎯 Objetivo

Aprender o que é o Wireshark, como capturar pacotes e como identificar protocolos que já estudamos, como:

* DHCP
* DNS
* TCP
* UDP
* IPv4
* IPv6
* HTTP
* HTTPS/TLS

---

# O que é o Wireshark?

O **Wireshark** é um analisador de protocolos de rede.

Ele permite capturar e visualizar os pacotes que passam por uma interface de rede.

Em vez de apenas imaginar:

```text
Computador → Roteador → Internet
```

podemos observar os pacotes reais sendo transmitidos.

---

# O que é um pacote?

Quando você envia uma informação pela rede, ela é dividida em unidades menores.

De forma simplificada:

```text
Mensagem
   ↓
Dados
   ↓
Pacotes
   ↓
Rede
   ↓
Destino
```

Cada pacote possui informações que ajudam a rede a entregá-lo corretamente.

---

# O que podemos encontrar em um pacote?

Dependendo do protocolo, podemos encontrar informações como:

```text
IP de origem
IP de destino
Porta de origem
Porta de destino
Protocolo
Tamanho
Informações do protocolo
```

Por exemplo:

```text
Origem:
192.168.0.15

Destino:
8.8.8.8

Protocolo:
UDP

Porta destino:
53
```

Isso poderia representar uma consulta DNS.

---

# Instalando o Wireshark

Baixe o Wireshark pelo site oficial:

https://www.wireshark.org/

Durante a instalação no Windows, será oferecida a instalação do **Npcap**.

O Npcap permite que o Wireshark capture o tráfego das interfaces de rede.

Pode manter as opções padrão durante a instalação.

---

# Abrindo o Wireshark

Ao abrir o programa, você verá suas interfaces de rede.

Por exemplo:

```text
Ethernet
Wi-Fi
Loopback
```

Se estiver conectado pelo Wi-Fi, normalmente deverá selecionar:

```text
Wi-Fi
```

Depois clique duas vezes na interface para começar a captura.

---

# Primeira captura

Depois de iniciar a captura, deixe o Wireshark rodando por alguns segundos.

Você provavelmente verá muitos pacotes.

Não se assuste.

Isso é completamente normal.

Um computador realiza várias comunicações de rede mesmo quando você não está fazendo nada diretamente.

---

# Colunas principais

Na captura, você encontrará colunas parecidas com:

| Coluna      | Significado                  |
| ----------- | ---------------------------- |
| No.         | Número do pacote             |
| Time        | Momento em que foi capturado |
| Source      | Origem                       |
| Destination | Destino                      |
| Protocol    | Protocolo                    |
| Length      | Tamanho                      |
| Info        | Informações adicionais       |

---

# Source e Destination

Imagine:

```text
Source

192.168.0.15
```

e:

```text
Destination

8.8.8.8
```

Isso significa:

```text
192.168.0.15
       ↓
    8.8.8.8
```

O primeiro endereço é a origem.

O segundo é o destino.

---

# Filtros

Uma das ferramentas mais importantes do Wireshark são os **Display Filters**.

Eles permitem mostrar somente os pacotes que interessam.

---

## Filtro DNS

```text
dns
```

Mostra pacotes relacionados ao DNS.

---

## Filtro TCP

```text
tcp
```

Mostra pacotes TCP.

---

## Filtro UDP

```text
udp
```

Mostra pacotes UDP.

---

## Filtro IPv4

```text
ip
```

Mostra tráfego IPv4.

---

## Filtro IPv6

```text
ipv6
```

Mostra tráfego IPv6.

---

## Filtro HTTP

```text
http
```

Mostra tráfego HTTP.

---

## Filtro TLS

```text
tls
```

Mostra tráfego relacionado ao TLS, utilizado pelo HTTPS.

---

# Observando DNS

Vamos fazer um teste.

Primeiro, abra o Wireshark e comece uma captura.

Depois abra o Prompt de Comando e execute:

```cmd
nslookup github.com
```

Agora volte para o Wireshark.

Utilize o filtro:

```text
dns
```

Você deverá encontrar consultas DNS.

Algo parecido com:

```text
192.168.0.15 → 192.168.0.1

DNS Query

github.com
```

E depois uma resposta:

```text
192.168.0.1 → 192.168.0.15

DNS Response
```

Você acabou de visualizar na prática aquilo que estudamos na Aula 5.

---

# Observando TCP

Agora utilize:

```text
tcp
```

Você poderá encontrar pacotes como:

```text
SYN
SYN, ACK
ACK
```

Lembra deles?

É o **Three-Way Handshake** que estudamos na Aula 8.

```text
Cliente
   |
   | SYN
   ↓
Servidor
   |
   | SYN + ACK
   ↓
Cliente
   |
   | ACK
   ↓
Conexão estabelecida
```

No Wireshark você consegue observar esse processo acontecendo.

---

# Observando UDP

Utilize:

```text
udp
```

Você verá pacotes UDP.

Diferentemente do TCP, não verá o Three-Way Handshake.

Isso acontece porque UDP não estabelece uma conexão da mesma maneira que TCP.

---

# Observando HTTP

Você pode utilizar:

```text
http
```

Se houver tráfego HTTP na captura, o Wireshark poderá mostrar requisições e respostas HTTP.

Por exemplo:

```text
GET
POST
HTTP/1.1
```

Atualmente, porém, a maior parte dos sites utiliza HTTPS.

---

# Observando HTTPS

Utilize:

```text
tls
```

Você poderá encontrar tráfego TLS.

Em uma conexão HTTPS, os dados da aplicação são protegidos por criptografia.

Por isso, você não consegue simplesmente olhar o pacote e visualizar uma senha ou o conteúdo de uma página HTTPS.

---

# Wireshark não quebra HTTPS

É importante entender isso.

O Wireshark consegue mostrar informações como:

```text
IP de origem
IP de destino
Portas
Tamanho
Tempo
TLS
```

Mas o conteúdo protegido permanece criptografado.

---

# Follow Stream

O Wireshark possui uma ferramenta chamada:

```text
Follow Stream
```

Ela permite acompanhar uma comunicação específica.

Em uma captura TCP:

```text
Botão direito no pacote
        ↓
Follow
        ↓
TCP Stream
```

Isso permite analisar o fluxo daquela comunicação.

---

# Wireshark e o modelo TCP/IP

Essa é uma das partes mais importantes da aula.

Quando você olha uma captura, pode começar a relacionar os dados com o modelo TCP/IP.

```text
Aplicação
    ↓
DNS / HTTP / HTTPS

Transporte
    ↓
TCP / UDP

Internet
    ↓
IPv4 / IPv6

Acesso à Rede
    ↓
Ethernet / Wi-Fi
```

Tudo aquilo que estudamos nas primeiras aulas aparece aqui.

---

# 🧪 Laboratório 1 — Capturar DNS

### Passo 1

Abra o Wireshark.

### Passo 2

Comece a captura na interface Wi-Fi.

### Passo 3

Abra o CMD.

Execute:

```cmd
nslookup github.com
```

### Passo 4

No Wireshark, utilize:

```text
dns
```

### Passo 5

Encontre a consulta.

Observe:

```text
Source
Destination
Protocol
Info
```

---

# 🧪 Laboratório 2 — Capturar TCP

Com uma captura ativa, abra algum site.

Depois filtre:

```text
tcp
```

Procure por:

```text
SYN
SYN, ACK
ACK
```

Tente identificar:

```text
IP do cliente
IP do servidor
Porta de origem
Porta de destino
```

---

# 🧪 Laboratório 3 — IPv6

Utilize:

```text
ipv6
```

Se sua rede estiver utilizando IPv6, você poderá encontrar endereços como:

```text
fe80::...
```

ou outros prefixos IPv6.

---

# 🧪 Laboratório 4 — Filtrar seu próprio IP

Primeiro descubra seu IPv4:

```cmd
ipconfig
```

Depois utilize no Wireshark:

```text
ip.addr == 192.168.0.15
```

Substitua `192.168.0.15` pelo endereço IPv4 do seu computador.

Esse filtro mostra pacotes relacionados ao endereço especificado.

---

# Filtros importantes

Guarde estes filtros:

```text
dns
```

```text
tcp
```

```text
udp
```

```text
ip
```

```text
ipv6
```

```text
http
```

```text
tls
```

E:

```text
ip.addr == 192.168.0.15
```

---

# ⚠️ Segurança

Uma captura de rede pode conter informações sensíveis.

Nunca capture ou analise tráfego de outras pessoas sem autorização.

Para estudar, utilize:

* Seu próprio computador.
* Sua própria rede.
* Ambientes de laboratório.
* Redes onde você possui autorização.

---

# 🧠 Resumo

| Conceito       | Explicação                                 |
| -------------- | ------------------------------------------ |
| Wireshark      | Analisador de protocolos                   |
| Pacote         | Unidade de dados transmitida pela rede     |
| Source         | Origem                                     |
| Destination    | Destino                                    |
| Display Filter | Filtro para visualizar pacotes específicos |
| Follow Stream  | Permite acompanhar uma comunicação         |

---

# 🎯 O que você deve conseguir fazer

Depois desta aula, você deve conseguir:

* Abrir uma captura.
* Identificar sua interface de rede.
* Encontrar pacotes DNS.
* Identificar TCP e UDP.
* Identificar IPv4 e IPv6.
* Observar um Three-Way Handshake.
* Utilizar filtros básicos.
* Diferenciar tráfego HTTP e HTTPS/TLS.

---

# 🏁 Fim do módulo de Redes

Você completou o roadmap:

* [x] Modelo TCP/IP
* [x] IPv4
* [x] IPv6
* [x] DNS
* [x] DHCP
* [x] NAT
* [x] VLAN
* [x] TCP x UDP
* [x] HTTP x HTTPS
* [x] Firewall
* [x] Wireshark

---

# 🚀 Próximo passo

Agora vamos fazer uma revisão geral de Redes.

Depois, vamos montar um cenário completo:

```text
Seu computador
      ↓
DHCP
      ↓
IPv4 / IPv6
      ↓
DNS
      ↓
TCP / UDP
      ↓
Firewall
      ↓
NAT
      ↓
Internet
      ↓
Servidor
```

A ideia será acompanhar o caminho de uma conexão e relacionar cada etapa com os conceitos que aprendemos durante o módulo.

Essa será a consolidação final antes de avançarmos para o próximo módulo do Intensivão de TI.

---

#### Feito por Lucas Siqueira
