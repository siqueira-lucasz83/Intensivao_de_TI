# 🌐 Aula 7 — NAT (Network Address Translation)

## 🎯 Objetivo

Compreender o que é o NAT, como ele funciona e por que ele permite que vários dispositivos compartilhem um único endereço IP público.

---

# O que é NAT?

**NAT (Network Address Translation)** é uma técnica utilizada pelos roteadores para traduzir endereços IP privados em um endereço IP público e vice-versa.

Em outras palavras, o NAT faz a comunicação entre a sua rede local e a Internet.

---

# Por que o NAT existe?

Imagine uma casa com os seguintes dispositivos:

```
Notebook
192.168.0.10

Celular
192.168.0.20

PS5
192.168.0.30

Smart TV
192.168.0.40
```

Todos possuem endereços IP privados.

Mas existe um problema:

Esses IPs privados **não podem ser utilizados diretamente na Internet**.

É aí que entra o NAT.

---

# Analogia

Imagine um prédio.

Cada apartamento possui um número.

```
Apartamento 101

Apartamento 102

Apartamento 103
```

Mas, para receber uma encomenda, todos utilizam o mesmo endereço do prédio.

```
Rua das Flores, nº 100
```

O porteiro recebe a encomenda e entrega para o apartamento correto.

O NAT funciona exatamente como esse porteiro.

```
Internet

↓

IP Público

↓

Roteador (NAT)

↓

Notebook

Celular

PS5

Smart TV
```

---

# Como funciona?

Imagine que o notebook deseja acessar o Google.

```
Notebook

192.168.0.10

↓

Roteador

↓

NAT

↓

189.xxx.xxx.xxx

↓

Internet

↓

Google
```

Observe o que aconteceu.

O roteador substituiu o endereço privado:

```
192.168.0.10
```

pelo endereço público:

```
189.xxx.xxx.xxx
```

Para o Google, quem fez a solicitação foi o IP público.

---

# E quando a resposta volta?

O Google responde para:

```
189.xxx.xxx.xxx
```

O roteador recebe essa resposta.

Depois consulta sua tabela NAT.

```
189.xxx.xxx.xxx

↓

192.168.0.10
```

Então entrega a resposta para o notebook correto.

---

# Tabela NAT

O roteador mantém uma tabela parecida com esta:

| IP Privado | IP Público |
|------------|------------|
| 192.168.0.10 | 189.xxx.xxx.xxx |
| 192.168.0.20 | 189.xxx.xxx.xxx |
| 192.168.0.30 | 189.xxx.xxx.xxx |

Todos compartilham o mesmo IP público.

---

# Por que isso é importante?

Sem NAT...

Cada dispositivo precisaria de um IP público.

Imagine uma casa com:

- Notebook
- Celular
- Tablet
- PS5
- Smart TV
- Alexa
- Câmeras
- Impressora

Seriam vários IPs públicos apenas para uma residência.

Com o NAT, basta um único IP público.

---

# NAT e IPv4

O NAT surgiu principalmente porque o IPv4 possui uma quantidade limitada de endereços.

Compartilhar um único IP público economiza milhões de endereços IPv4.

---

# NAT e IPv6

No IPv6, cada dispositivo pode possuir seu próprio endereço público.

Por isso, o NAT não é tão necessário quanto no IPv4.

Mesmo assim, algumas redes ainda utilizam técnicas semelhantes por questões de segurança ou organização.

---

# Tipos de NAT

## NAT Estático

Um IP privado sempre corresponde ao mesmo IP público.

Muito utilizado para servidores.

Exemplo:

```
192.168.0.100

↓

200.100.50.10
```

Sempre será esse endereço.

---

## NAT Dinâmico

O roteador utiliza um conjunto de IPs públicos disponíveis.

Cada dispositivo recebe um deles quando necessário.

É menos comum em redes domésticas.

---

## PAT (Port Address Translation)

Também chamado de **NAT Overload**.

É o tipo mais utilizado em residências.

Vários dispositivos compartilham o mesmo IP público.

A diferenciação é feita utilizando portas de comunicação.

---

# Como tudo se conecta

Imagine o seguinte cenário.

Você liga o notebook.

↓

DHCP entrega:

```
IP

192.168.0.15
```

↓

Você digita:

```
www.google.com
```

↓

DNS responde:

```
142.250.xxx.xxx
```

↓

NAT troca:

```
192.168.0.15

↓

189.xxx.xxx.xxx
```

↓

O Google responde.

↓

O roteador identifica qual dispositivo fez a solicitação.

↓

O notebook recebe a resposta.

Perceba que praticamente todas as aulas estudadas até agora participaram dessa conexão.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| NAT | Traduz IP privado para IP público |
| Objetivo | Permitir acesso à Internet utilizando um único IP público |
| Onde acontece | Normalmente no roteador |
| NAT Estático | Um IP privado corresponde sempre ao mesmo IP público |
| PAT | Vários dispositivos compartilham um único IP público utilizando portas |

---

# Conceitos importantes

- NAT significa Network Address Translation.
- O NAT normalmente acontece no roteador.
- Ele traduz IPs privados em IPs públicos.
- O NAT economiza endereços IPv4.
- Em redes domésticas, normalmente utilizamos PAT.

---

# Laboratório

No Windows:

```cmd
ipconfig
```

Observe seu endereço IPv4.

Provavelmente será algo parecido com:

```
192.168.x.x
```

Agora acesse um site que mostra seu IP público, como:

```
https://whatismyipaddress.com
```

ou

```
https://ifconfig.me
```

Compare os dois endereços.

Você perceberá que:

- O IP mostrado pelo `ipconfig` é privado.
- O IP mostrado no site é público.

Essa diferença existe por causa do NAT.

---

# Desafio

Responda:

1. O que significa NAT?
2. Onde o NAT normalmente acontece?
3. Qual é a principal função do NAT?
4. O que aconteceria se o NAT não existisse em uma rede doméstica?
5. Qual é a diferença entre NAT Estático e PAT?

---

# Próxima aula

➡️ Aula 8 — TCP x UDP

Você vai aprender a diferença entre comunicação confiável e comunicação rápida, entendendo por que jogos online utilizam UDP enquanto sites e bancos normalmente utilizam TCP.

---

#### Feito por Lucas Siqueira
