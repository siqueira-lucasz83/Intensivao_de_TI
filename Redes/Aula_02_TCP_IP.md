# 🌐 Aula 2 — Modelo TCP/IP

## 🎯 Objetivo

Compreender o que é o modelo TCP/IP, sua importância e como os dados trafegam entre dispositivos em uma rede.

---

## O que é o TCP/IP?

O **TCP/IP (Transmission Control Protocol / Internet Protocol)** é um conjunto de protocolos responsável por definir como os dispositivos se comunicam em uma rede.

Em outras palavras, ele estabelece as regras para que computadores, celulares, servidores e outros dispositivos consigam trocar informações corretamente.

Sem essas regras, cada fabricante poderia criar seu próprio método de comunicação, tornando impossível a comunicação entre dispositivos diferentes.

---

## Analogia

Imagine uma empresa de entregas.

Para que uma encomenda chegue ao destino, existem algumas etapas:

1. Embalar o produto.
2. Escrever o endereço.
3. Transportar.
4. Entregar.

Na rede acontece algo semelhante: os dados passam por diferentes etapas até chegarem ao destino.

---

# As 4 camadas do Modelo TCP/IP

```
┌──────────────────────────────┐
│ Aplicação                    │
├──────────────────────────────┤
│ Transporte                   │
├──────────────────────────────┤
│ Internet                     │
├──────────────────────────────┤
│ Acesso à Rede                │
└──────────────────────────────┘
```

Cada camada possui uma responsabilidade específica.

---

## 1. Camada de Aplicação

É a camada utilizada pelos programas que usamos diariamente.

Exemplos:

- Navegadores (Chrome, Edge, Firefox)
- WhatsApp
- Discord
- Spotify
- Steam

Essa camada é responsável por iniciar a comunicação entre o usuário e a rede.

Exemplo:

Ao acessar:

```
www.google.com
```

o navegador inicia uma solicitação para o servidor do Google.

---

## 2. Camada de Transporte

Responsável por transportar os dados entre o dispositivo de origem e o destino.

Os principais protocolos dessa camada são:

- TCP
- UDP

Esses protocolos serão estudados em detalhes mais adiante.

---

## 3. Camada da Internet

É responsável pelo endereçamento e roteamento dos dados.

Nessa camada encontramos o protocolo **IP**, que identifica cada dispositivo conectado à rede.

Exemplo de endereço IPv4:

```
192.168.0.10
```

Sem um endereço IP, um dispositivo não consegue enviar ou receber informações pela rede.

---

## 4. Camada de Acesso à Rede

É responsável pela transmissão física dos dados.

Pode utilizar:

- Cabo Ethernet
- Wi-Fi
- Fibra óptica

Essa camada envia e recebe os dados pelo meio físico ou sem fio.

---

# Exemplo completo

Imagine que você abre o YouTube no navegador.

O processo acontece da seguinte forma:

1. O navegador cria a solicitação.
2. A camada de Transporte organiza os dados.
3. A camada da Internet identifica o endereço IP do servidor.
4. A camada de Acesso à Rede transmite os dados pelo Wi-Fi ou cabo.
5. O roteador encaminha os dados para a Internet.
6. O servidor do YouTube responde.
7. O vídeo começa a ser reproduzido.

Tudo isso acontece em poucos milissegundos.

---

# Resumo

| Camada | Função |
|---------|--------|
| Aplicação | Comunicação entre os programas e a rede. |
| Transporte | Transporte dos dados utilizando TCP ou UDP. |
| Internet | Endereçamento IP e roteamento dos pacotes. |
| Acesso à Rede | Transmissão física dos dados através de cabo ou Wi-Fi. |

---

# Conceitos importantes

- O modelo TCP/IP é o padrão utilizado na Internet.
- Cada camada possui uma responsabilidade específica.
- As camadas trabalham juntas para que a comunicação aconteça corretamente.
- O endereço IP pertence à camada de Internet.
- TCP e UDP pertencem à camada de Transporte.

---

# Próxima aula

➡️ Aula 3 — IPv4

---

#### Feito por Lucas Siqueira