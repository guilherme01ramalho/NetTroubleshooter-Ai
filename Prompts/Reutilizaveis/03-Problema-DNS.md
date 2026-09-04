# Prompt 03 — Problema de DNS

## Quando utilizar

Quando o usuário consegue acessar a Internet por IP, mas não por nome de domínio.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O usuário consegue acessar a Internet usando endereços IP, mas NÃO consegue acessar sites por nome de domínio.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Utilize, quando apropriado:

ipconfig /all (para ver servidores DNS configurados)

nslookup (para testar resolução de nomes)

ipconfig /flushdns (para limpar cache DNS)

Para cada teste, explique:

O que o teste demonstra

O que o teste NÃO demonstra sozinho

Como interpretar resultados de sucesso e falha

NÃO assuma que DNS público funcionando significa DNS corporativo errado.

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS]


## Exemplo de entrada
RELATO DO USUÁRIO:
"Consigo acessar o Google pelo IP 142.250.217.78, mas não consigo acessar www.google.com."

COMANDOS JÁ EXECUTADOS:
nslookup www.google.com


## O que o prompt produz

Uma investigação focada em resolução de nomes que:
1. Verifica quais servidores DNS estão configurados
2. Testa resolução para domínios internos e externos
3. Verifica cache DNS local
4. Diferencia problemas de cliente DNS de problemas de servidor DNS
5. Sugere correção baseada em evidências