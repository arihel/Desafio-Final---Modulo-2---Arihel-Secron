==================================================
PROPOSTA DE CIBERSEGURANCA PARA E-COMMERCE (LOJAZETA)
==================================================

Este documento detalha uma proposta estratégica de cibersegurança defensiva (Blue Team), criada especificamente para a plataforma de e-commerce LojaZeta.


1. OBJETIVO ESTRATÉGICO
-------------------------
O objetivo principal é criar um ecossistema digital seguro e resiliente. Isso vai além de simplesmente "evitar hackers"; trata-se de proteger a continuidade do negócio, garantir que a receita não seja interrompida por ataques, manter a confiança do cliente — que é o ativo mais valioso da empresa — e assegurar a conformidade com leis de proteção de dados, como a LGPD, evitando multas e sanções.


2. ARQUITETURA DE DEFESA EM PROFUNDIDADE
-------------------------
A filosofia adotada é a de "Defesa em Profundidade", onde múltiplas barreiras de segurança independentes são implementadas. Se uma falha, as outras continuam a proteger o sistema.

- WAF (Web Application Firewall): Atua como um segurança na porta de entrada da aplicação. Ele inspeciona todo o tráfego HTTP/S destinado ao site, utilizando regras para identificar e bloquear automaticamente os tipos de ataques mais comuns contra aplicações web (como SQL Injection e XSS, do OWASP Top 10).

- Segmentacao de Rede: Consiste em dividir a infraestrutura em zonas isoladas. A aplicação web fica em uma sub-rede, e o banco de dados em outra, ainda mais protegida. As regras de firewall só permitem a comunicação estritamente necessária entre elas. Isso impede que um invasor, caso comprometa o servidor web, consiga se mover lateralmente para acessar diretamente o banco de dados.

- Hardening de Servidores: É o processo de "blindar" os servidores. Isso envolve remover todos os softwares e serviços desnecessários, desabilitar portas não utilizadas, aplicar as configurações de segurança mais restritivas e garantir que um processo de gerenciamento de patches esteja em vigor para corrigir vulnerabilidades conhecidas.

- Gestao de Acesso e Identidade (IAM): Garante que apenas as pessoas certas tenham acesso às ferramentas certas. Segue o "Princípio do Privilégio Mínimo", onde cada usuário ou serviço tem apenas as permissões essenciais para realizar sua função. A Autenticação Multifator (MFA) para contas administrativas é inegociável, pois adiciona uma camada de verificação que protege contra o roubo de senhas.


3. MONITORAMENTO, DETECÇÃO E RESPOSTA (SIEM)
-------------------------
Uma defesa eficaz depende de visibilidade. Logs de segurança gerados em sistemas isolados têm pouco valor. A proposta é centralizar todos os registros (logs) de eventos do WAF, servidores, aplicação e banco de dados em uma única plataforma de SIEM (Security Information and Event Management).

O SIEM atua como uma central de inteligência, correlacionando eventos de diferentes fontes para encontrar padrões que indicam um ataque em andamento. Por exemplo, ele pode cruzar uma informação de bloqueio no WAF com um erro no log do banco de dados para gerar um alerta de alta confiança sobre uma tentativa de invasão que, de outra forma, poderia passar despercebida.


4. PLANO DE RESPOSTA A INCIDENTES (NIST)
-------------------------
Estar preparado para o pior cenário é fundamental. Ter um plano claro evita o caos durante uma crise e minimiza os danos. O plano de resposta, baseado no framework NIST, define um ciclo de vida para o tratamento de incidentes:

1. Deteccao e Analise: Como identificamos e validamos que um incidente está ocorrendo?
2. Contencao: Como isolamos o problema para evitar que ele se espalhe e cause mais danos?
3. Erradicacao: Como removemos completamente a ameaça do nosso ambiente?
4. Recuperacao: Como restauramos os sistemas para a operação normal de forma segura?
5. Licoes Aprendidas (Pós-Incidente): O que deu certo? O que deu errado? Como podemos melhorar para que isso não aconteça novamente?


5. PLANO DE ACAO IMEDIATO (QUICK WINS - PRIMEIROS 30 DIAS)
-------------------------
Ações priorizadas para gerar o maior impacto de segurança no menor tempo possível:

- Ativar o WAF (Web Application Firewall): Para criar uma primeira linha de defesa imediata, filtrando ataques automatizados e de baixa complexidade que ocorrem 24/7 na internet.

- Habilitar o MFA para todos os administradores: Para proteger as contas mais críticas contra roubo de senhas, que é um dos vetores de ataque mais comuns e eficazes.

- Centralizar os logs essenciais: Para começar a construir a visibilidade necessária para futuras investigações e para a implantação do SIEM na próxima fase.

- Aplicar todas as atualizacoes de seguranca criticas: Para fechar brechas de segurança já conhecidas e que são ativamente exploradas por atacantes para obter acesso inicial aos sistemas.

Arihel Martins Secron	
https://www.linkedin.com/in/arihelsecron/