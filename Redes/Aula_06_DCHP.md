# 🌐 Aula 6 — DHCP (Dynamic Host Configuration Protocol)

## 🎯 Objetivo

Compreender o que é o DHCP, como ele funciona e por que ele permite que dispositivos obtenham automaticamente um endereço IP ao se conectarem a uma rede.

---

# O que é DHCP?

**DHCP (Dynamic Host Configuration Protocol)** é um protocolo responsável por fornecer automaticamente as configurações de rede para um dispositivo.

Quando um computador, celular ou videogame entra na rede, ele precisa de algumas informações para conseguir se comunicar.

O DHCP entrega essas informações automaticamente.

---

# O que o DHCP fornece?

Normalmente o DHCP entrega:

- Endereço IPv4
- Máscara de sub-rede
- Gateway padrão
- Servidor DNS

Ou seja, praticamente toda a configuração necessária para acessar a rede.

---

# Analogia

Imagine um hotel.

Quando um hóspede chega, a recepção entrega:

- Número do quarto
- Senha do Wi-Fi
- Horário do café
- Informações importantes

O hóspede não escolhe essas informações.

A recepção organiza tudo.

O DHCP funciona exatamente como essa recepção.

Cada novo dispositivo recebe automaticamente as informações necessárias para utilizar a rede.

---

# Como funciona?

Quando você conecta um notebook ao Wi-Fi, acontece algo parecido com isto:

```
Notebook

↓

"Existe algum servidor DHCP?"

↓

Roteador

↓

"Sim."

↓

"Tome este endereço IP."

↓

192.168.0.15
```

Depois disso, o computador já consegue acessar a Internet.

Tudo acontece em poucos segundos.

---

# Quem normalmente é o servidor DHCP?

Em redes domésticas, normalmente quem fornece o DHCP é:

```
Roteador
```

Em empresas, o DHCP pode estar em:

- Windows Server
- Linux Server
- Equipamentos de rede dedicados

---

# O processo DORA

Existe uma sequência muito famosa no DHCP chamada **DORA**.

Ela representa as quatro etapas da comunicação.

## D — Discover

O computador procura um servidor DHCP.

```
"Existe algum DHCP na rede?"
```

---

## O — Offer

O servidor responde oferecendo um endereço IP.

```
"Tenho o IP 192.168.0.20 disponível."
```

---

## R — Request

O computador responde:

```
"Quero utilizar esse endereço."
```

---

## A — Acknowledge

O servidor confirma.

```
"Perfeito.

O IP agora é seu."
```

Depois disso, o computador já está pronto para utilizar a rede.

---

# Exemplo

Imagine sua casa.

```
Notebook

↓

Conecta no Wi-Fi

↓

DHCP

↓

IP

192.168.0.15

↓

DNS

192.168.0.1

↓

Gateway

192.168.0.1

↓

Internet
```

Tudo isso foi configurado automaticamente.

---

# O que acontece se não existir DHCP?

Você precisaria configurar tudo manualmente.

Por exemplo:

```
IP

192.168.0.50

Máscara

255.255.255.0

Gateway

192.168.0.1

DNS

8.8.8.8
```

Isso funciona, mas dá muito mais trabalho.

---

# IP Dinâmico x IP Estático

## IP Dinâmico

É fornecido automaticamente pelo DHCP.

Pode mudar com o tempo.

É o mais comum em residências.

---

## IP Estático

É configurado manualmente.

Normalmente utilizado em:

- Servidores
- Impressoras
- Câmeras
- Equipamentos de infraestrutura

Esses dispositivos precisam manter sempre o mesmo endereço.

---

# Como visualizar essas informações

No Windows:

```cmd
ipconfig /all
```

Você verá:

- IPv4
- Gateway
- DNS
- DHCP Enabled

---

# Renovando o endereço IP

Liberar o IP atual:

```cmd
ipconfig /release
```

Solicitar um novo IP ao DHCP:

```cmd
ipconfig /renew
```

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| DHCP | Protocolo que fornece configurações de rede automaticamente |
| Função | Automatizar a configuração dos dispositivos |
| Servidor DHCP | Normalmente o roteador em redes domésticas |
| DORA | Discover → Offer → Request → Acknowledge |
| IP Dinâmico | Recebido automaticamente |
| IP Estático | Configurado manualmente |

---

# Conceitos importantes

- DHCP significa Dynamic Host Configuration Protocol.
- O DHCP entrega automaticamente IP, gateway, máscara e DNS.
- Em casa, normalmente o roteador é o servidor DHCP.
- O processo DORA possui quatro etapas.
- Sem DHCP seria necessário configurar cada dispositivo manualmente.

---

# Laboratório

## Verificar se o DHCP está habilitado

```cmd
ipconfig /all
```

Procure por:

```
DHCP Enabled : Yes
```

---

## Liberar o endereço IP

```cmd
ipconfig /release
```

---

## Solicitar um novo endereço

```cmd
ipconfig /renew
```

---

# Desafio

Responda:

1. O que significa DHCP?
2. Quem normalmente fornece o DHCP em uma casa?
3. O que o DHCP entrega para um computador?
4. O que significa DORA?
5. Qual é a diferença entre IP dinâmico e IP estático?

---

# Próxima aula

➡️ Aula 7 — NAT (Network Address Translation)

Você vai entender como toda a sua casa consegue acessar a Internet utilizando apenas um único IP público.

---

#### Feito por Lucas Siqueira