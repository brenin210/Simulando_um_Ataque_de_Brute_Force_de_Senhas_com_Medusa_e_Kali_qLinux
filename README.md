Simulação de Ataque de Força Bruta com Medusa no Kali Linux

Este repositório reúne anotações, conceitos e explicações referentes à aula “Simulando um Ataque de Brute Force de Senhas com Medusa e Kali Linux”, utilizando o ambiente vulnerável Metasploitable 2. O conteúdo tem caráter educacional e ético, destinado ao estudo de Segurança da Informação, Auditoria de Senhas e Pentest em ambientes controlados.

📌 Conteúdo

Principais tipos de ataques a autenticação Diferença entre Password Spraying e Credential Stuffing Conceitos sobre Hydra, Medusa, Ncrack, John, WPScan e Patator O que são wordlists Visão geral de um ataque simulado usando Medusa + Metasploitable 2 Como testar acessos SMB utilizando smbclient

🔐 1. Principais tipos de ataques a senhas

Brute Force (Força Bruta): Testa todas as combinações possíveis de senhas até encontrar a correta.
Ataque por Dicionário: Usa listas de palavras/senhas prováveis (wordlists). Mais rápido que brute force puro.
Password Spraying: Testa poucas senhas muito comuns contra muitos usuários, evitando bloqueios por tentativas.
Credential Stuffing: Testa usuário + senha reais obtidos em vazamentos em outros serviços, explorando a reutilização de credenciais.
Ataques a Hashes: Quebra ou tenta descobrir senhas a partir de hashes capturados.
Engenharia Social: Engana pessoas para obter informações de autenticação (phishing, pretexting etc.).
🔄 2. Password Spraying vs Credential Stuffing Password Spraying

Poucas senhas → muitos usuários
Minimiza bloqueio de conta
Útil quando só se conhece a lista de usuários
Credential Stuffing

Combinações reais de credenciais vazadas
Alta taxa de sucesso quando usuários reutilizam senhas
Usado quando se tem pares usuário/senha
🛠️ 3. Ferramentas do Kali Linux para auditoria de senhas Hydra Ferramenta rápida para testar autenticação em múltiplos protocolos (SSH, FTP, HTTP, SMB etc.).

Medusa Ferramenta voltada para testes de força bruta em paralelo, eficiente em diversos hosts simultaneamente.

Ncrack Do time do Nmap, ideal para auditoria de autenticação em rede com alto desempenho.

John the Ripper Especializado em quebrar hashes de senhas. Um dos mais populares no mundo.

WPScan Scanner para WordPress, identifica vulnerabilidades, plugins e pode realizar auditoria de senhas.

Patator Ferramenta modular e flexível para testar autenticação em inúmeros protocolos com alto controle de erros.

📚 4. O que são Wordlists Wordlists são listas de senhas prováveis usadas em auditorias. Podem conter:

senhas mais utilizadas
padrões comuns
combinações geradas automaticamente
credenciais vazadas
listas temáticas
O Kali inclui várias por padrão em:

/usr/share/wordlists/

A mais conhecida é rockyou.txt.

🎯 5. Visão geral da simulação com Medusa + Metasploitable 2 Esta simulação demonstra como falhas de políticas de senha permitem que ferramentas automatizadas encontrem credenciais válidas.

Fluxo conceitual:

Configuração do ambiente
Kali Linux (atacante)
Metasploitable 2 (alvo vulnerável)
Mapeamento de serviços Identificação de serviços de login (SSH, FTP, Telnet etc.).
Escolha do serviço alvo Seleciona-se um protocolo vulnerável do Metasploitable 2.
Configuração do Medusa
lista de usuários
lista de senhas (wordlist)
serviço/protocolo
Execução da auditoria O Medusa testa credenciais de forma rápida e paralela.
Validação das credenciais encontradas Apenas para fins de demonstração dentro do ambiente controlado.
📁 6. Testando acessos SMB com smbclient smbclient é um utilitário do Samba usado para acessar compartilhamentos SMB/CIFS, comum em servidores Windows ou Linux com Samba.

Em auditorias, ele permite:

validar se um usuário e senha funcionam
listar pastas e permissões
identificar compartilhamentos expostos
confirmar acessos indevidos
É muito útil para demonstrar o impacto de credenciais fracas ou permissões mal configuradas.

⚠️ Aviso de Uso Ético Este repositório não fornece comandos operacionais. Todo o conteúdo é exclusivamente para ensino, estudo e simulações em ambientes autorizados. Ataques reais sem permissão são ilegais.
