# 🌐 Aula 9 — HTTP x HTTPS

## 🎯 Objetivo

Compreender o que são HTTP e HTTPS, como eles funcionam e por que o HTTPS é essencial para a segurança na Internet.

---

# O que é HTTP?

**HTTP (HyperText Transfer Protocol)** é um protocolo responsável pela comunicação entre um navegador (cliente) e um servidor web.

Sempre que você acessa um site, o navegador envia uma requisição ao servidor utilizando HTTP ou HTTPS.

Exemplo:

```
Você

↓

Chrome

↓

Servidor

↓

Resposta

↓

Página carregada
```

---

# Como funciona?

Imagine que você acessa:

```
https://github.com
```

O navegador envia uma requisição como:

```
"Olá servidor!

Envie a página inicial do GitHub."
```

O servidor responde:

```
"Aqui está a página."
```

O navegador então exibe o conteúdo para você.

---

# O que é HTTPS?

HTTPS significa:

**HyperText Transfer Protocol Secure**

Ele funciona da mesma forma que o HTTP.

A diferença é que a comunicação é protegida por criptografia.

---

# Analogia

Imagine duas situações.

## HTTP

Você envia uma carta sem envelope.

Qualquer pessoa no caminho pode ler seu conteúdo.

---

## HTTPS

Agora imagine que a carta está dentro de um cofre trancado.

Somente quem possui a chave consegue abrir.

É exatamente isso que a criptografia faz.

---

# O que é criptografia?

Criptografia é uma técnica utilizada para transformar informações legíveis em dados codificados.

Exemplo:

```
Senha

123456
```

Durante a transmissão ela fica protegida.

Mesmo que alguém intercepte os dados, não conseguirá entender seu conteúdo.

---

# O cadeado 🔒

Quando você acessa um site e vê um cadeado ao lado do endereço, significa que a conexão utiliza HTTPS.

Exemplo:

```
https://github.com

🔒
```

Isso indica que a comunicação está criptografada.

---

# HTTP x HTTPS

| HTTP | HTTPS |
|------|-------|
| Não utiliza criptografia | Utiliza criptografia |
| Menos seguro | Muito mais seguro |
| Porta 80 | Porta 443 |
| Dados podem ser interceptados | Dados protegidos |

---

# O que pode acontecer usando HTTP?

Imagine que você está utilizando um Wi-Fi público.

Se um site utilizar apenas HTTP, uma pessoa mal-intencionada pode interceptar os dados transmitidos.

Isso pode expor:

- Usuário
- Senha
- Informações pessoais

Por isso, atualmente praticamente todos os sites importantes utilizam HTTPS.

---

# Certificados Digitais

Como o navegador sabe que um site é realmente quem diz ser?

Através de um **Certificado Digital**.

Esse certificado comprova a identidade do servidor.

É por isso que, às vezes, o navegador mostra mensagens como:

```
Sua conexão não é particular.
```

Isso pode indicar que o certificado é inválido, expirou ou não é confiável.

---

# Fluxo completo de uma conexão

Imagine que você acessa:

```
https://github.com
```

O processo acontece assim:

```
Notebook

↓

DHCP

↓

Recebe IP

↓

DNS

↓

Descobre o IP do GitHub

↓

TCP

↓

Cria uma conexão

↓

HTTPS

↓

Comunicação criptografada

↓

Servidor

↓

Resposta

↓

Página carregada
```

Perceba que praticamente todas as aulas estudadas até agora participam desse processo.

---

# Portas

| Serviço | Porta |
|----------|------:|
| HTTP | 80 |
| HTTPS | 443 |

---

# Como identificar um site seguro?

Observe:

```
https://
```

Além disso, procure pelo cadeado no navegador.

Isso indica que a comunicação utiliza HTTPS.

---

# Curiosidade

Mesmo utilizando HTTPS, ainda é possível saber qual site você acessou em alguns cenários.

O que fica protegido é o conteúdo da comunicação, como:

- Senhas
- Mensagens
- Dados enviados
- Informações pessoais

---

# Resumo

| Conceito | Explicação |
|----------|------------|
| HTTP | Comunicação entre navegador e servidor |
| HTTPS | HTTP com criptografia |
| Porta HTTP | 80 |
| Porta HTTPS | 443 |
| Certificado Digital | Comprova a identidade do servidor |

---

# Conceitos importantes

- HTTP significa **HyperText Transfer Protocol**.
- HTTPS significa **HyperText Transfer Protocol Secure**.
- HTTPS utiliza criptografia.
- Sites seguros utilizam certificados digitais.
- Atualmente, praticamente todos os serviços importantes utilizam HTTPS.

---

# Laboratório

## Verificar se um site utiliza HTTPS

Acesse alguns sites:

```
https://github.com

https://google.com

https://openai.com
```

Observe o cadeado ao lado da URL.

---

## Testar HTTP

Experimente acessar:

```
http://example.com
```

Observe se o navegador redireciona automaticamente para HTTPS.

Muitos sites fazem isso para aumentar a segurança.

---

# Desafio

Responda:

1. O que significa HTTP?
2. O que significa HTTPS?
3. Qual utiliza criptografia?
4. Qual utiliza a porta 80?
5. Qual utiliza a porta 443?
6. Para que serve um certificado digital?
7. Por que praticamente todos os bancos utilizam HTTPS?

---

# Próxima aula

➡️ Aula 10 — Firewall

Você vai entender como computadores e roteadores decidem quais conexões podem entrar ou sair da rede e como um firewall ajuda a proteger sistemas contra acessos não autorizados.

---

#### Feito por Lucas Siqueira
