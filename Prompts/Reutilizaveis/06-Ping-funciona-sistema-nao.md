# Prompt 06 — Ping funciona, mas sistema não abre

## Quando utilizar

Quando o servidor responde ao ping, mas o sistema/aplicação não funciona.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O usuário relata: "O servidor responde ao ping, mas o sistema não abre."

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Deixe EXPLÍCITO que:

Ping bem-sucedido demonstra resposta ICMP (camada 3 - rede)

Ping NÃO confirma que a aplicação, serviço ou porta utilizada pelo sistema esteja funcionando (camada 7 - aplicação)

Diferencie:

Conectividade de rede (IP, roteamento)

Conectividade de aplicação (porta, serviço, firewall)

Investigue:

Porta do serviço (telnet ou Test-NetConnection)

Serviço em execução no servidor

Firewall local

Firewall de rede

Configuração da aplicação

Para cada etapa, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS]


## Exemplo de entrada
RELATO DO USUÁRIO:
"O sistema ERP não abre. Quando tento acessar, dá erro de conexão."

COMANDOS JÁ EXECUTADOS:
ping servidor-erp

Saída:
Resposta de 192.168.10.100: bytes=32 tempo=1ms TTL=128

## O que o prompt produz

Uma investigação que:
1. Explica claramente a diferença entre ICMP e aplicação
2. Testa conectividade na porta específica
3. Verifica se o serviço está rodando
4. Verifica firewalls
5. Sugere correção baseada em evidências