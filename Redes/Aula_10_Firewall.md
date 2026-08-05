# 🌐 Aula 10 — Firewall

## 🎯 Objetivo

Compreender o que é um firewall, como ele funciona e como ele protege dispositivos e redes contra acessos não autorizados.

---

# O que é um Firewall?

Um **Firewall** é um sistema de segurança que controla o tráfego de rede.

Ele analisa as conexões que entram e saem de um dispositivo ou de uma rede e decide se elas serão:

- Permitidas ✅
- Bloqueadas ❌

Em outras palavras, o firewall funciona como um porteiro.

---

# Analogia

Imagine um condomínio.

Na entrada existe um porteiro.

Quando alguém chega, ele verifica:

- Quem é?
- Está autorizado?
- Pode entrar?

Se estiver autorizado:

```
Entrada liberada ✅
```

Caso contrário:

```
Acesso negado ❌
```

O firewall faz exatamente isso com os dados da rede.

---

# Onde existe um Firewall?

Firewalls podem estar em vários lugares:

- Computador (Windows Defender Firewall)
- Roteador
- Servidores
- Empresas
- Data Centers
- Ambientes em Cloud (AWS, Azure, Google Cloud)

Na prática, uma empresa costuma utilizar vários firewalls ao mesmo tempo.

---

# Como funciona?

Imagine que um computador tenta acessar seu servidor.

```
Internet

↓

Firewall

↓

Servidor
```

O firewall verifica as regras.

Se a conexão estiver permitida:

```
Conexão aceita.
```

Caso contrário:

```
Conexão bloqueada.
```

---

# Regras

Um firewall trabalha utilizando regras.

Exemplo:

```
Permitir

HTTPS

Porta 443
```

ou

```
Bloquear

FTP

Porta 21
```

Cada organização cria regras conforme suas necessidades.

---

# O que um Firewall pode analisar?

Dependendo do tipo de firewall, ele pode verificar:

- Endereço IP
- Porta
- Protocolo (TCP ou UDP)
- Origem
- Destino
- Aplicação

Com base nessas informações ele toma uma decisão.

---

# Firewall de Entrada e Saída

## Entrada (Inbound)

Controla conexões que tentam entrar no computador.

Exemplo:

```
Internet

↓

Seu computador
```

O firewall decide se essa conexão será aceita.

---

## Saída (Outbound)

Controla conexões iniciadas pelo próprio computador.

Exemplo:

```
Seu computador

↓

Internet
```

Também é possível impedir que determinados programas acessem a Internet.

---

# Exemplo prático

Você abre o navegador.

```
Chrome

↓

HTTPS

↓

Firewall

↓

Internet

↓

Servidor
```

Como a porta 443 normalmente está liberada, a conexão acontece normalmente.

Agora imagine um programa desconhecido tentando abrir uma conexão.

O firewall pode bloquear essa tentativa automaticamente.

---

# Firewall no Windows

O Windows possui um firewall integrado chamado:

```
Microsoft Defender Firewall
```

Ele já vem habilitado por padrão e protege o computador contra conexões não autorizadas.

---

# Firewall em empresas

Em empresas, é comum existirem firewalls dedicados.

Eles podem:

- Bloquear sites.
- Permitir apenas determinados serviços.
- Registrar acessos.
- Detectar atividades suspeitas.
- Impedir ataques.

---

# Firewall ≠ Antivírus

Muitas pessoas confundem os dois.

## Firewall

Controla o tráfego de rede.

Decide quais conexões podem entrar ou sair.

---

## Antivírus

Analisa arquivos e programas em busca de ameaças.

Detecta:

- Vírus
- Trojans
- Ransomware
- Malware

Os dois trabalham juntos.

---

# Exemplo

Imagine um ladrão.

O firewall é o porteiro.

O antivírus é o segurança dentro do prédio.

Cada um possui uma função diferente.

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| Firewall | Controla o tráfego de rede |
| Função | Permitir ou bloquear conexões |
| Analisa | IP, porta, protocolo e regras |
| Inbound | Conexões que entram |
| Outbound | Conexões que saem |

---

# Conceitos importantes

- Firewall é uma barreira de segurança.
- Trabalha utilizando regras.
- Pode bloquear ou permitir conexões.
- Existe em computadores, roteadores e servidores.
- Firewall não substitui um antivírus.

---

# Laboratório

## Verificar o estado do Firewall no Windows

Abra o Prompt de Comando:

```cmd
netsh advfirewall show allprofiles
```

Observe se o firewall está:

```
State

ON
```

---

## Abrir o Firewall do Windows

Pressione:

```
Windows + R
```

Digite:

```
wf.msc
```

Será aberta a ferramenta **Firewall do Windows com Segurança Avançada**.

Observe:

- Regras de Entrada.
- Regras de Saída.
- Perfis de rede.

**Não altere nenhuma regra**, apenas explore a interface.

---

# Desafio

Responda:

1. O que é um Firewall?
2. Qual é sua principal função?
3. O que significa uma regra de Entrada (Inbound)?
4. O que significa uma regra de Saída (Outbound)?
5. Qual é a diferença entre Firewall e Antivírus?
6. O Firewall do Windows vem ativado por padrão?

---

# Próxima aula

➡️ Aula 11 — VLAN (Virtual Local Area Network)

Você vai aprender como dividir uma única rede física em várias redes virtuais, aumentando a organização, a segurança e o desempenho das redes.

---

#### Feito por Lucas Siqueira 