# Prompt 07 — Análise de ipconfig /all

## Quando utilizar

Quando o analista possui a saída completa do comando ipconfig /all e precisa de interpretação estruturada.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O analista forneceu a saída do comando "ipconfig /all" e precisa de uma interpretação estruturada.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Identifique informações relevantes como:

Endereço IPv4 (válido ou APIPA?)

Máscara de sub-rede

Gateway padrão (configurado? responde a ping?)

Servidores DNS (configurados? resolvem?)

DHCP (habilitado? servidor acessível?)

Endereços APIPA (169.254.x.x)

Para cada observação, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

NÃO declare causa raiz apenas com base no ipconfig /all.

SAÍDA DO ipconfig /all:
[COLE A SAÍDA COMPLETA AQUI]


## Exemplo de entrada
SAÍDA DO ipconfig /all:

Adaptador Ethernet Ethernet:
Endereço IPv4: 169.254.137.42
Máscara: 255.255.0.0
Gateway: (em branco)
DHCP: Habilitado
Servidor DHCP: (não disponível)
Servidores DNS: (em branco)


## O que o prompt produz

Uma interpretação estruturada que:
1. Identifica todas as configurações relevantes
2. Explica o significado de cada uma
3. Não conclui causas apenas com base no ipconfig
4. Sugere próximos testes baseados nas observações