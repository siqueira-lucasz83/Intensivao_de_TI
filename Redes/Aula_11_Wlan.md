# 🌐 Aula 11 — VLAN (Virtual Local Area Network)

## 🎯 Objetivo

Compreender o que é uma VLAN, por que ela é utilizada e como ela melhora a organização e a segurança das redes.

---

# O que é uma VLAN?

**VLAN (Virtual Local Area Network)** é uma tecnologia que permite dividir uma única rede física em várias redes virtuais independentes.

Mesmo utilizando o mesmo switch e os mesmos cabos, os dispositivos podem ficar separados em redes diferentes.

---

# Por que usar VLAN?

Imagine uma empresa com:

- Financeiro
- RH
- TI
- Visitantes (Wi-Fi)

Sem VLAN, todos estariam na mesma rede.

Isso significa que qualquer computador poderia, em teoria, tentar se comunicar com qualquer outro.

Isso não é ideal.

---

# Analogia

Imagine um prédio.

Existe apenas um prédio, mas vários apartamentos.

```
Prédio

↓

Apartamento 101

Apartamento 102

Apartamento 103
```

Todos utilizam o mesmo prédio.

Mas cada apartamento é separado dos demais.

A VLAN funciona da mesma forma.

Existe apenas uma infraestrutura física, mas várias redes virtuais.

---

# Exemplo

Sem VLAN:

```
Internet

↓

Roteador

↓

Switch

├── PC Financeiro
├── PC RH
├── PC TI
└── Notebook Visitante
```

Todos pertencem à mesma rede.

---

Com VLAN:

```
Internet

↓

Roteador

↓

Switch

├── VLAN 10 → Financeiro
├── VLAN 20 → RH
├── VLAN 30 → TI
└── VLAN 40 → Visitantes
```

Agora cada departamento possui sua própria rede.

---

# O que muda?

O computador do Financeiro não consegue conversar diretamente com o computador do RH apenas por estarem ligados ao mesmo switch.

Isso aumenta:

- Segurança
- Organização
- Controle

---

# Identificação

Cada VLAN possui um número chamado **VLAN ID**.

Exemplo:

| Departamento | VLAN |
|--------------|-----:|
| Financeiro | 10 |
| RH | 20 |
| TI | 30 |
| Visitantes | 40 |

Esses números podem variar conforme o projeto da rede.

---

# Comunicação entre VLANs

Pergunta:

O computador da VLAN 10 consegue acessar a VLAN 20?

Resposta:

**Não diretamente.**

Para que isso aconteça é necessário um equipamento de camada 3 (como um roteador ou um switch Layer 3).

Esse processo é chamado de:

```
Inter-VLAN Routing
```

---

# VLAN aumenta a segurança?

Sim.

Imagine que um computador de visitantes seja infectado por malware.

Como ele está em uma VLAN separada, fica muito mais difícil que esse problema afete computadores do Financeiro ou da TI.

---

# VLAN melhora o desempenho?

Também.

Como cada VLAN possui seu próprio domínio de broadcast, há menos tráfego desnecessário circulando pela rede.

Isso torna a comunicação mais eficiente.

---

# O que é Broadcast?

Broadcast é uma mensagem enviada para **todos os dispositivos da mesma rede**.

Exemplo:

```
"Quem possui o IP 192.168.0.10?"
```

Todos recebem essa mensagem.

Com VLANs, esse broadcast fica limitado aos dispositivos daquela VLAN.

Isso reduz o tráfego da rede.

---

# Onde as VLANs são configuradas?

Normalmente em switches gerenciáveis.

Exemplos:

- Cisco
- HP Aruba
- TP-Link Omada
- MikroTik
- Ubiquiti

Switches simples (não gerenciáveis) normalmente não suportam VLAN.

---

# Portas Access e Trunk

## Porta Access

Transporta apenas uma VLAN.

Exemplo:

```
PC

↓

Switch

(VLAN 10)
```

É o tipo de porta normalmente utilizado para computadores, impressoras e telefones IP.

---

## Porta Trunk

Transporta várias VLANs ao mesmo tempo.

Exemplo:

```
Switch A

⇅

Switch B
```

ou

```
Switch

↓

Roteador
```

Uma única conexão pode carregar o tráfego de diversas VLANs.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| VLAN | Rede Local Virtual |
| Objetivo | Separar uma rede física em várias redes virtuais |
| VLAN ID | Número que identifica uma VLAN |
| Access | Porta para uma única VLAN |
| Trunk | Porta que transporta várias VLANs |
| Inter-VLAN Routing | Comunicação entre VLANs através de um roteador ou switch Layer 3 |

---

# Conceitos importantes

- VLAN significa **Virtual Local Area Network**.
- Uma VLAN separa dispositivos logicamente.
- VLANs aumentam segurança e organização.
- Cada VLAN possui um identificador chamado VLAN ID.
- Broadcasts ficam limitados à VLAN correspondente.
- A comunicação entre VLANs exige um equipamento de camada 3.

---

# Laboratório (teórico)

Imagine uma empresa com os seguintes setores:

- Financeiro
- RH
- TI
- Visitantes

Proponha uma divisão de VLANs.

Exemplo:

| Setor | VLAN |
|--------|-----:|
| Financeiro | 10 |
| RH | 20 |
| TI | 30 |
| Visitantes | 40 |

Agora responda:

1. O notebook dos visitantes deveria acessar os computadores do Financeiro?
2. Qual seria a vantagem de separar esses setores em VLANs?

---

# Desafio

Responda:

1. O que significa VLAN?
2. Qual é a principal função de uma VLAN?
3. O que é um VLAN ID?
4. Qual é a diferença entre uma porta Access e uma porta Trunk?
5. O que é Inter-VLAN Routing?
6. Por que as VLANs melhoram a segurança da rede?

---

# Próxima aula

➡️ Aula 12 — Wireshark

Você aprenderá a capturar e analisar pacotes de rede em tempo real, observando protocolos como DNS, DHCP, TCP, UDP, HTTP e HTTPS em funcionamento.

---

#### Feito por Lucas Siqueira 