# 🔑 Ataque de Brute Force de Senhas com Medusa e Kali Linux

> ⚠️ **Aviso Legal:** Este projeto foi desenvolvido **exclusivamente para fins educacionais**, em ambiente controlado e isolado. Nenhum código, comando ou técnica aqui descrita deve ser utilizada contra sistemas reais sem autorização explícita. O objetivo é compreender como ataques de força bruta funcionam para **fortalecer a segurança de sistemas e autenticações**.

Projeto de **Cibersegurança** focado na simulação de ataques de força bruta contra serviços de autenticação (**SSH, FTP e HTTP**), utilizando **Kali Linux** e a ferramenta **Medusa**. O projeto também documenta as principais **contramedidas e boas práticas** de defesa contra esse tipo de ataque.

---

## 🎯 Objetivo

Demonstrar na prática como ataques de força bruta exploram senhas fracas em serviços de autenticação amplamente utilizados, e como administradores de sistemas podem detectar, bloquear e prevenir esse tipo de ataque.

---

## 🗂️ Estrutura do Projeto

```
Ataque-de-Brute-Force-de-Senhas-com-Medusa-e-Kali-Linux/
├── commands/
│   ├── ssh_bruteforce.sh         # Comandos para ataque via SSH
│   ├── ftp_bruteforce.sh         # Comandos para ataque via FTP
│   └── http_bruteforce.sh        # Comandos para ataque via HTTP (painel web)
├── wordlist/
│   └── passwords.txt             # Wordlist de senhas utilizada nos testes
├── docs/
│   └── relatorio.pdf             # Relatório técnico com evidências e análise
└── README.md
```

---

## ⚔️ Protocolos Testados

### 🔴 SSH — Secure Shell

Simulação de ataque de força bruta contra o serviço de acesso remoto SSH, um dos alvos mais comuns em servidores expostos na internet.

```bash
medusa -h <TARGET_IP> -u <USER> -P wordlist/passwords.txt -M ssh
```

---

### 🔴 FTP — File Transfer Protocol

Simulação de ataque contra serviços FTP, frequentemente expostos com credenciais padrão ou fracas.

```bash
medusa -h <TARGET_IP> -u <USER> -P wordlist/passwords.txt -M ftp
```

---

### 🔴 HTTP — Painel Web

Simulação de ataque de força bruta contra formulários de login em painéis web, explorando autenticações sem proteção contra múltiplas tentativas.

```bash
medusa -h <TARGET_IP> -u <USER> -P wordlist/passwords.txt -M http -m DIR:/<LOGIN_PATH>
```

---

## 🛡️ Defesa e Mitigação

Para cada serviço testado, o projeto documenta as principais contramedidas:

| Vetor de Ataque | Contramedidas Recomendadas |
|---|---|
| SSH | Desabilitar login por senha, usar chaves SSH, alterar porta padrão, configurar `fail2ban` |
| FTP | Desabilitar FTP anônimo, usar SFTP, limitar tentativas de login |
| HTTP | Implementar bloqueio por tentativas, CAPTCHA, autenticação multifator (MFA) |
| Geral | Senhas longas e complexas, monitoramento de logs, alertas de acesso, rate limiting |

### Ferramentas de defesa citadas

- **Fail2ban** — bloqueia IPs após N tentativas falhas
- **UFW / iptables** — firewall para restringir acesso por IP e porta
- **Autenticação multifator (MFA)** — segunda camada de verificação
- **Monitoramento de logs** — `/var/log/auth.log` para SSH e FTP

---

## 🛠️ Tecnologias e Ferramentas

| Ferramenta | Uso |
|---|---|
| Kali Linux | Sistema operacional para testes de segurança |
| Medusa | Ferramenta de força bruta para múltiplos protocolos |
| SSH / FTP / HTTP | Protocolos alvo dos testes |
| Wordlist | Lista de senhas para os ataques simulados |
| Git / GitHub | Versionamento e documentação |

---

## 🚀 Como Reproduzir (Ambiente Controlado)

### Pré-requisitos

- Kali Linux instalado (físico ou em VM)
- Medusa instalado:
```bash
sudo apt update && sudo apt install medusa -y
```
- Ambiente de laboratório isolado (ex: máquina virtual alvo com serviços habilitados)

### Executando os testes

```bash
# Clone o repositório
git clone https://github.com/GuiMRDS/Ataque-de-Brute-Force-de-Senhas-com-Medusa-e-Kali-Linux.git

# Acesse a pasta
cd Ataque-de-Brute-Force-de-Senhas-com-Medusa-e-Kali-Linux

# Execute o script desejado (exemplo SSH)
bash commands/ssh_bruteforce.sh
```

> 🔒 **Obrigatório:** Use exclusivamente em redes e máquinas próprias ou em ambientes de laboratório criados para este fim. Nunca execute contra sistemas de terceiros.

---

## 📚 O que foi Aprendido

- Como ataques de força bruta exploram autenticações sem proteção
- Diferenças de comportamento entre os protocolos SSH, FTP e HTTP sob ataque
- Uso prático da ferramenta **Medusa** para testes de penetração
- Como wordlists influenciam a eficiência do ataque
- Configuração de ferramentas de defesa como **Fail2ban** e firewall
- Boas práticas de hardening de serviços de autenticação

---

## 🎓 Contexto Acadêmico

> Projeto desenvolvido durante o **Bootcamp Riachuelo – Cibersegurança**, promovido pela **Digital Innovation One (DIO)** em parceria com **Lojas Riachuelo S.A.**
>
> **Carga horária:** 40 horas
> **Tópicos do bootcamp:** Segurança da Informação · Linux básico e intermediário · Kali Linux · Análise de vulnerabilidades · Hacking ético · Automação com Python

---

## 👨‍💻 Autor

**Guilherme Marinho**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-guilherme--marinho04-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/guilherme-marinho04/)
[![GitHub](https://img.shields.io/badge/GitHub-GuiMRDS-black?style=flat&logo=github)](https://github.com/GuiMRDS)
[![Email](https://img.shields.io/badge/Email-guimars22%40gmail.com-red?style=flat&logo=gmail)](mailto:guimars22@gmail.com)

---

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais. O uso das técnicas aqui descritas contra sistemas sem autorização é crime previsto na **Lei nº 12.737/2012 (Lei Carolina Dieckmann)** e no **Marco Civil da Internet**. Use com responsabilidade.
