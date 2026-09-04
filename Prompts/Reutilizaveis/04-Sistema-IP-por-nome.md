# Prompt 04 — Sistema interno acessível por IP, mas não por nome

## Quando utilizar

Em ambientes corporativos, quando o usuário não consegue acessar um sistema pelo nome (ex: \\servidor), mas consegue pelo IP.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O usuário relata que NÃO consegue acessar um sistema interno pelo nome, mas consegue pelo endereço IP.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Investigue considerando:

Resolução de nomes via DNS

FQDN (nome completo) vs nome curto

Cache DNS do cliente

Arquivo HOSTS

Configuração de sufixos DNS

Ordem de resolução de nomes

Para cada etapa, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

NÃO assuma que é problema no DNS corporativo sem testar outras possibilidades.

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS]


## Exemplo de entrada
RELATO DO USUÁRIO:
"Estou tentando acessar o sistema da empresa pelo nome \servidor-finanças, mas não funciona. Quando uso \192.168.10.50 funciona."

COMANDOS JÁ EXECUTADOS:
nslookup servidor-finanças


## O que o prompt produz

Uma investigação focada em resolução de nomes em ambientes corporativos que:
1. Verifica se o nome está registrado no DNS
2. Testa resolução com FQDN vs nome curto
3. Verifica cache DNS e arquivo HOSTS
4. Valida sufixos DNS configurados
5. Sugere correção baseada em evidências