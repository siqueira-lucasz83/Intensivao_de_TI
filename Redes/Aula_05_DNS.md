# 🌐 Aula 5 — DNS (Domain Name System)

## 🎯 Objetivo

Compreender o que é o DNS, como ele funciona e por que ele é um dos serviços mais importantes da Internet.

---

# O que é DNS?

**DNS (Domain Name System)** é um sistema responsável por traduzir nomes de domínio em endereços IP.

Em vez de decorar um endereço IP como:

```
142.250.190.78
```

podemos simplesmente acessar:

```
www.google.com
```

O DNS faz essa tradução automaticamente.

---

# Analogia

Imagine que você quer ligar para uma pizzaria.

Você sabe apenas o nome:

```
Pizzaria do João
```

Mas não sabe o telefone.

Então você procura em uma lista telefônica.

A lista responde:

```
Pizzaria do João

↓

(11) 4002-8922
```

Agora você consegue fazer a ligação.

O DNS funciona exatamente assim.

```
www.google.com

↓

Servidor DNS

↓

142.250.xxx.xxx
```

---

# Por que o DNS existe?

Imagine se toda vez que você quisesse acessar um site precisasse decorar o endereço IP.

Por exemplo:

```
Google

↓

142.250.xxx.xxx

YouTube

↓

142.250.xxx.xxx

GitHub

↓

140.82.xxx.xxx
```

Seria praticamente impossível lembrar o endereço de milhares de sites.

O DNS resolve esse problema utilizando nomes fáceis de memorizar.

---

# Como funciona?

Imagine que você abre o navegador e digita:

```
www.google.com
```

O processo acontece da seguinte forma:

```
Você

↓

Chrome

↓

Servidor DNS

↓

"Qual é o IP do Google?"

↓

Resposta

↓

142.250.xxx.xxx

↓

Chrome conecta ao servidor

↓

Google abre.
```

Tudo isso acontece em poucos milissegundos.

---

# Quem fornece o DNS?

Normalmente o servidor DNS pode ser:

- Seu provedor de Internet.
- Google DNS.
- Cloudflare DNS.
- OpenDNS.

Você pode escolher qual deseja utilizar.

---

# DNS públicos famosos

## Google DNS

```
Primário

8.8.8.8

Secundário

8.8.4.4
```

---

## Cloudflare

```
Primário

1.1.1.1

Secundário

1.0.0.1
```

---

## OpenDNS

```
208.67.222.222

208.67.220.220
```

---

# Cache DNS

Seu computador guarda algumas consultas em memória.

Isso significa que, se você abrir o mesmo site novamente, ele provavelmente não perguntará ao servidor DNS outra vez.

Isso deixa a navegação mais rápida.

---

# Como visualizar o cache DNS

No Windows:

```cmd
ipconfig /displaydns
```

Você verá uma lista dos domínios armazenados.

---

# Como limpar o cache DNS

Às vezes o cache pode armazenar informações antigas.

Para limpá-lo:

```cmd
ipconfig /flushdns
```

Mensagem esperada:

```
Successfully flushed the DNS Resolver Cache.
```

---

# O que acontece se o DNS parar?

Imagine que o Google continua funcionando.

O servidor também continua funcionando.

Mas o DNS para.

O que acontece?

Você digita:

```
www.google.com
```

Seu computador não consegue descobrir qual é o endereço IP.

Resultado:

O site não abre.

Ou seja...

Muitas vezes a Internet está funcionando normalmente.

Quem está com problema é apenas o DNS.

---

# DNS e IPv6

O DNS também funciona com IPv6.

Ele pode responder algo como:

```
www.google.com

↓

2800:3f0:4001:xxxx...
```

Ou seja...

O DNS traduz nomes tanto para IPv4 quanto para IPv6.

---

# Curiosidade

O DNS é considerado uma das "listas telefônicas" da Internet.

Sem ele, navegar seria extremamente difícil.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| DNS | Traduz nomes de domínio em endereços IP |
| Função | Facilitar o acesso aos sites |
| Cache DNS | Armazena consultas recentes |
| Google DNS | 8.8.8.8 |
| Cloudflare DNS | 1.1.1.1 |

---

# Conceitos importantes

- DNS significa Domain Name System.
- Ele traduz nomes em endereços IP.
- Sem DNS precisaríamos decorar IPs.
- O computador utiliza cache DNS para acelerar consultas.
- O DNS funciona tanto com IPv4 quanto com IPv6.

---

# Laboratório

## 1. Descobrir o IP de um site

No Prompt de Comando:

```cmd
nslookup google.com
```

ou

```cmd
nslookup github.com
```

Observe o endereço IP retornado.

---

## 2. Verificar o cache DNS

```cmd
ipconfig /displaydns
```

---

## 3. Limpar o cache DNS

```cmd
ipconfig /flushdns
```

---

# Desafio

Responda:

1. O que significa DNS?
2. Qual é a função do DNS?
3. O que aconteceria se o DNS deixasse de funcionar?
4. Qual é o DNS público do Google?
5. Qual comando mostra o IP de um domínio?

---

# Próxima aula

➡️ Aula 6 — DHCP (Dynamic Host Configuration Protocol)

Você vai aprender como o seu computador recebe automaticamente um endereço IP quando se conecta ao Wi-Fi, sem precisar configurar tudo manualmente.

---

#### Feito por Lucas Siqueira
