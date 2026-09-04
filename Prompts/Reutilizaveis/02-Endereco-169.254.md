# Prompt 02 — Endereço 169.254.x.x

## Quando utilizar

Quando o ipconfig mostra um endereço IPv4 na faixa 169.254.x.x.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O ipconfig mostra que o computador recebeu um endereço IPv4 na faixa 169.254.x.x.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Investigue SEM afirmar automaticamente que o DHCP é a causa raiz.

Considere:

Cabo de rede / Wi-Fi (conexão física)

Switch / porta de rede

Driver da placa de rede

Serviço DHCP no cliente (está em execução?)

Servidor DHCP (está funcionando?)

Roteador / gateway

Para cada etapa, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

NUNCA afirme que a causa é DHCP apenas com base no endereço APIPA.

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS, especialmente ipconfig /all]


## Exemplo de entrada
RELATO DO USUÁRIO:
"Meu computador não está pegando Internet."

COMANDOS JÁ EXECUTADOS:
ipconfig /all

Saída (parte relevante):
Endereço IPv4: 169.254.137.42
Máscara: 255.255.0.0
Gateway: (em branco)
DHCP: Habilitado


## O que o prompt produz

Uma investigação que:
1. Não assume DHCP como causa automática
2. Verifica camada física (cabo, Wi-Fi, switch)
3. Verifica se o serviço DHCP está rodando
4. Verifica se o servidor DHCP está acessível
5. Somente depois de excluir outras causas, sugere correção DHCP