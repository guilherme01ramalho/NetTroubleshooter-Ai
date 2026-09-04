# Prompt 08 — Análise de nslookup

## Quando utilizar

Quando o analista possui a saída do comando nslookup e precisa de interpretação.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O analista forneceu o resultado do comando "nslookup domínio" e precisa de interpretação.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Ajude a interpretar:

Sucesso (resolução retornou IP)

Timeout (sem resposta do servidor DNS)

Servidor DNS utilizado (qual foi consultado)

Endereço retornado (IP correto?)

Possíveis diferenças entre resolução interna e externa

Para cada observação, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

NÃO considere automaticamente um resultado de nslookup como prova definitiva da causa.

SAÍDA DO nslookup:
[COLE A SAÍDA COMPLETA AQUI]


## Exemplo de entrada
SAÍDA DO nslookup:

Servidor: DNS-Interno.corporativo.local
Address: 192.168.1.10

Nome: servidor-erp.corporativo.local
Address: 192.168.10.100


## O que o prompt produz

Uma interpretação estruturada que:
1. Identifica o servidor DNS consultado
2. Analisa a resposta obtida
3. Verifica se o IP retornado está correto
4. Não conclui causas apenas com base no nslookup
5. Sugere próximos testes baseados nas observações