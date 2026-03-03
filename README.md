# 🔐 Simulação de Ataques de Força Bruta com Kali Linux e Medusa

## 📌 Sobre o Projeto

Este projeto foi desenvolvido como parte de um desafio prático com foco em Segurança da Informação, utilizando Kali Linux e Medusa em conjunto com ambientes vulneráveis para simular ataques de força bruta.

O objetivo principal foi compreender técnicas ofensivas em um ambiente controlado, identificar vulnerabilidades comuns e propor medidas de mitigação.

⚠️ Todos os testes foram realizados em laboratório isolado para fins exclusivamente educacionais.

---

## 🎯 Objetivos de Aprendizagem

- Compreender ataques de força bruta em serviços FTP, Web e SMB
- Utilizar Kali Linux para auditoria de segurança
- Aplicar a ferramenta Medusa em cenários reais simulados
- Documentar processos técnicos de forma estruturada
- Reconhecer vulnerabilidades e propor medidas de mitigação
- Utilizar o GitHub como portfólio técnico

---

## 🖥️ Ambiente de Laboratório

### 🔧 Infraestrutura

- VirtualBox
- 2 Máquinas Virtuais
- Rede configurada como Host-Only

### 🐉 Máquina Atacante
- Kali Linux

### 💀 Máquina Alvo
- Metasploitable 2
- DVWA (Damn Vulnerable Web Application)

---

## 🔧 Ferramentas Utilizadas

- Medusa
- Nmap
- Wordlists personalizadas
- Terminal Linux

---

# 🚨 Cenários Testados

---

## 1️⃣ Ataque de Força Bruta em FTP

### 🔎 Enumeração de Serviço

```bash
nmap -p 21 <IP_ALVO>
```

# 🚨 Execução dos Ataques e Resultados

---

## 1️⃣ Ataque de Força Bruta em FTP

### 💣 Execução do Ataque

```bash
medusa -h <IP_ALVO> -u msfadmin -P wordlist.txt -M ftp
```

## ✅ Resultado Obtido (FTP)

- Identificação de credenciais fracas  
- Acesso ao serviço FTP validado com sucesso  

### 🛡️ Recomendações de Mitigação

- Implementação de política forte de senhas  
- Bloqueio após múltiplas tentativas falhas  
- Monitoramento contínuo de logs  
- Desativação de autenticação simples quando possível  

---

## 2️⃣ Ataque de Força Bruta em Formulário Web (DVWA)

### 🔎 Análise do Formulário

- Identificação do método HTTP (POST)  
- Captura dos parâmetros de autenticação  

### 💣 Execução do Ataque

```bash
medusa -h <IP_ALVO> -U users.txt -P passwords.txt -M http
```

## ✅ Resultado Obtido (DVWA)

- Comprometimento do login através de credenciais fracas  
- Acesso validado ao painel da aplicação  

### 🛡️ Recomendações de Mitigação

- Implementação de CAPTCHA  
- Rate limiting (limitação de tentativas)  
- Autenticação Multifator (MFA)  
- Bloqueio por IP após múltiplas falhas  
- Monitoramento de tentativas suspeitas  

---

## 3️⃣ Password Spraying em SMB

### 🔎 Enumeração de Usuários

```bash
nmap --script smb-enum-users -p 445 <IP_ALVO>
```

# ✅ Resultado Obtido

- Identificação de usuários com senha padrão  
- Acesso autenticado com sucesso  

---

# 🛡️ Recomendações de Mitigação

- Política de complexidade de senha  
- Bloqueio automático por tentativas falhas  
- Monitoramento de eventos de autenticação  
- Desativação do protocolo SMBv1  
- Auditoria periódica de credenciais  

---

# 📂 Estrutura do Repositório
/images
/wordlists
README.md
comandos-utilizados.txt


---

# 📁 Descrição das Pastas e Arquivos

- `/images` → Capturas de tela organizadas dos testes  
- `/wordlists` → Listas de senhas utilizadas nos testes  
- `README.md` → Documentação completa do projeto  
- `comandos-utilizados.txt` → Registro dos comandos executados  

---

# 📚 Principais Aprendizados

Durante o desenvolvimento deste projeto foi possível:

- Entender na prática como ataques de força bruta funcionam  
- Perceber o impacto de senhas fracas em ambientes corporativos  
- Aprender técnicas básicas de enumeração de serviços  
- Desenvolver documentação técnica clara e organizada  
- Estruturar um laboratório seguro para simulação de ataques  

---

# 🔐 Vulnerabilidades Identificadas

- Uso de senhas fracas ou padrão  
- Ausência de bloqueio após múltiplas tentativas  
- Falta de autenticação multifator  
- Serviços expostos sem monitoramento adequado  
- Configurações padrão não alteradas  

---

# 🚀 Conclusão

O projeto demonstrou que vulnerabilidades simples podem comprometer serviços críticos em poucos minutos quando não há medidas de proteção adequadas.

Mais importante do que executar os ataques foi compreender como preveni-los, reforçando boas práticas de segurança e políticas de proteção.

Este laboratório contribuiu significativamente para o fortalecimento de conhecimentos em:

- Pentest básico  
- Segurança ofensiva  
- Enumeração de serviços  
- Análise de vulnerabilidades  
- Documentação técnica  
- Estruturação de ambiente de testes  

---

# ⚠️ Aviso Legal

Este projeto foi realizado exclusivamente em ambiente controlado e com fins educacionais.

A realização de testes de invasão sem autorização formal é ilegal e pode resultar em sanções civis e criminais.
