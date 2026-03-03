🔐 Projeto: Simulação de Ataques de Força Bruta com Kali Linux e Medusa
📌 Sobre o Projeto
Este projeto foi desenvolvido como parte do desafio prático da DIO, com o objetivo de implementar e documentar ataques de força bruta em ambiente controlado utilizando Kali Linux, Medusa e máquinas vulneráveis como Metasploitable 2 e DVWA.
O foco foi compreender técnicas ofensivas para, posteriormente, aplicar medidas defensivas e boas práticas de segurança.
⚠️ Todos os testes foram realizados em ambiente virtual isolado (laboratório controlado), exclusivamente para fins educacionais.
🎯 Objetivos do Projeto
Compreender ataques de força bruta em diferentes serviços
Utilizar Kali Linux para auditoria de segurança
Aplicar a ferramenta Medusa em cenários reais simulados
Documentar processos técnicos de forma clara
Identificar vulnerabilidades e propor mitigação
🖥️ Ambiente de Laboratório
🔧 Infraestrutura
2 Máquinas Virtuais no VirtualBox
Rede: Host-Only
Sistema atacante:
🐉 Kali Linux
Sistema alvo:
💀 Metasploitable 2
🌐 Damn Vulnerable Web Application (DVWA)
🔍 Ferramentas Utilizadas
Medusa
Nmap
Wordlists personalizadas
Terminal Linux
🚨 Cenários Testados
1️⃣ Ataque de Força Bruta em FTP
🎯 Objetivo
Obter acesso ao serviço FTP explorando credenciais fracas.
🔎 Enumeração
nmap -p 21 <IP_ALVO>
💣 Ataque com Medusa
medusa -h <IP_ALVO> -u msfadmin -P wordlist.txt -M ftp
✅ Resultado
Credenciais fracas identificadas
Acesso FTP validado com sucesso
🛡️ Mitigações
Política forte de senhas
Bloqueio após múltiplas tentativas
Desativar autenticação simples
Monitoramento de logs
2️⃣ Ataque de Força Bruta em Formulário Web (DVWA)
🎯 Objetivo
Automatizar tentativas de login no formulário da DVWA.
🔎 Identificação do formulário
Análise do método POST
Captura de parâmetros
💣 Execução do ataque
medusa -h <IP_ALVO> -U users.txt -P passwords.txt -M http
✅ Resultado
Login comprometido via credenciais fracas
Validação de acesso no painel
🛡️ Mitigações
Implementar CAPTCHA
Rate limiting
MFA (Autenticação Multifator)
Bloqueio por IP
3️⃣ Password Spraying em SMB
🎯 Objetivo
Testar uma mesma senha para múltiplos usuários no serviço SMB.
🔎 Enumeração de usuários
nmap --script smb-enum-users -p 445 <IP_ALVO>
💣 Execução do ataque
medusa -h <IP_ALVO> -U usuarios.txt -p senha123 -M smbnt
✅ Resultado
Usuários com senha padrão identificados
Acesso validado com sucesso
🛡️ Mitigações
Política de complexidade de senha
Bloqueio por tentativas falhas
Monitoramento de autenticação
Desativar SMBv1
📂 Estrutura do Repositório
/images
/wordlists
README.md
comandos-utilizados.txt
📚 Aprendizados
Durante o desenvolvimento deste projeto, foi possível:
Entender como ataques de força bruta funcionam na prática
Compreender a importância de políticas de senha fortes
Praticar enumeração de serviços
Melhorar a documentação técnica
Estruturar um laboratório seguro para testes
Este projeto reforça que falhas simples de configuração podem comprometer sistemas inteiros.
🔐 Principais Vulnerabilidades Observadas
Senhas fracas ou padrão
Ausência de bloqueio por tentativa
Falta de autenticação multifator
Serviços expostos sem monitoramento
🚀 Conclusão
A prática em laboratório demonstrou como ataques automatizados podem comprometer serviços rapidamente quando não há medidas de proteção adequadas.
Mais importante do que explorar vulnerabilidades, foi compreender como preveni-las.
Este projeto fortaleceu meus conhecimentos em:
Pentest básico
Segurança ofensiva
Análise de serviços
Documentação técnica
Uso do GitHub como portfólio
⚠️ Aviso Legal
Este projeto foi realizado exclusivamente em ambiente controlado para fins educacionais.
A execução de testes em sistemas sem autorização é ilegal.
