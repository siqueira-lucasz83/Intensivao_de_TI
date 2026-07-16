# 🌐 Aula 4 — IPv6

## 🎯 Objetivo

Compreender o que é o IPv6, por que ele foi criado e quais são suas principais diferenças em relação ao IPv4.

---

## Por que o IPv6 foi criado?

O IPv4 utiliza **32 bits**, permitindo aproximadamente:

```
4.294.967.296
```

endereços diferentes.

Quando o IPv4 foi criado, essa quantidade parecia suficiente. Porém, com o crescimento da Internet e o aumento de dispositivos conectados (computadores, celulares, Smart TVs, videogames, relógios inteligentes e dispositivos IoT), essa quantidade se tornou limitada.

Para resolver esse problema, foi criado o **IPv6**.

---

## O que é IPv6?

**IPv6 (Internet Protocol Version 6)** é a versão mais recente do protocolo IP.

Seu principal objetivo é oferecer uma quantidade muito maior de endereços IP disponíveis para a Internet.

---

## IPv4 x IPv6

| IPv4 | IPv6 |
|------|------|
| 32 bits | 128 bits |
| 4 octetos | 8 grupos |
| Apenas números | Números e letras (hexadecimal) |
| Aproximadamente 4,3 bilhões de endereços | Aproximadamente 340 undecilhões de endereços |

---

## Estrutura de um IPv6

Exemplo:

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Um endereço IPv6 é composto por **8 grupos**, separados por dois pontos (`:`).

Cada grupo possui quatro caracteres em hexadecimal.

---

## O que é hexadecimal?

O IPv6 utiliza a base hexadecimal.

Em vez de utilizar apenas números de 0 a 9, ele utiliza:

```
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Onde:

```
A = 10

B = 11

C = 12

D = 13

E = 14

F = 15
```

---

## Abreviação de endereços IPv6

O IPv6 permite simplificar a escrita.

Exemplo completo:

```
2001:0db8:0000:0000:0000:0000:0000:0015
```

Forma abreviada:

```
2001:db8::15
```

Regras básicas:

- Zeros à esquerda podem ser removidos.
- Sequências contínuas de grupos compostos apenas por zeros podem ser substituídas por `::`.
- A abreviação com `::` só pode ser utilizada uma única vez em cada endereço.

---

## Endereços Link-Local

Ao executar o comando `ipconfig` no Windows, é comum encontrar um endereço semelhante a:

```
fe80::c12a:abcd:1234:5678
```

Esse endereço é chamado de **Link-Local**.

Ele permite a comunicação entre dispositivos da mesma rede local e não é utilizado para comunicação pela Internet.

---

## IPv4 e IPv6 convivem

Atualmente, grande parte da Internet ainda utiliza IPv4.

Por esse motivo, muitos dispositivos funcionam utilizando os dois protocolos simultaneamente.

Essa configuração é chamada de **Dual Stack**.

---

## Como visualizar o IPv6

### Windows

Abra o Prompt de Comando ou PowerShell.

Execute:

```cmd
ipconfig
```

Procure por linhas como:

```
Endereço IPv6

ou

Endereço IPv6 Local de Link
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

## Curiosidade

O IPv6 possui aproximadamente:

```
340.282.366.920.938.463.463.374.607.431.768.211.456
```

endereços possíveis.

Esse número é conhecido como aproximadamente **340 undecilhões** de endereços.

Na prática, é uma quantidade extremamente grande, suficiente para suportar o crescimento da Internet por muito tempo.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| IPv6 | Sexta versão do protocolo IP |
| Tamanho | 128 bits |
| Formato | 8 grupos separados por ":" |
| Base utilizada | Hexadecimal |
| Principal vantagem | Quantidade muito maior de endereços disponíveis |
| Link-Local | Endereço utilizado apenas na rede local |
| Dual Stack | Utilização simultânea de IPv4 e IPv6 |

---

# Conceitos importantes

- O IPv6 foi criado para solucionar a limitação de endereços do IPv4.
- O IPv6 utiliza 128 bits.
- Os endereços são escritos em hexadecimal.
- IPv4 e IPv6 coexistem atualmente.
- Endereços iniciados por `fe80::` são do tipo Link-Local.

---

# Laboratório

No Windows, execute:

```cmd
ipconfig
```

Responda:

1. Seu computador possui um endereço IPv6?
2. Existe algum endereço começando por `fe80::`?
3. Seu computador utiliza IPv4, IPv6 ou ambos?

---

# Próxima aula

➡️ Aula 5 — DNS (Domain Name System)

---

#### Feito por Lucas Siqueira 