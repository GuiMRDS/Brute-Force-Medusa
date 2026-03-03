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
