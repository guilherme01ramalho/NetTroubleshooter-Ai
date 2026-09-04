# Prompt 05 — Internet lenta

## Quando utilizar

Quando o usuário relata que a Internet está lenta, mas ainda funciona.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O usuário relata que a Internet está lenta ("demora para abrir páginas", "arquivos demoram para baixar").

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Separe a investigação em:

Problema no computador (recursos, processos, malware)

Problema na rede local (congestionamento, Wi-Fi, switch)

Problema na conexão externa (operadora, roteamento)

Problema de resolução de nomes (DNS lento)

NÃO assuma automaticamente que lentidão é causada por DNS.

Para cada etapa, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

Priorize testes que diferenciam cada categoria de problema.

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS]


## Exemplo de entrada
RELATO DO USUÁRIO:
"A Internet está muito lenta hoje. As páginas demoram para abrir e o sistema da empresa também está lento."

COMANDOS JÁ EXECUTADOS:
ping google.com


## O que o prompt produz

Uma investigação estruturada que:
1. Separa as categorias de possíveis causas
2. Testa cada categoria com comandos específicos
3. Interpreta os resultados
4. Identifica onde está o gargalo
5. Sugere correção baseada em evidências