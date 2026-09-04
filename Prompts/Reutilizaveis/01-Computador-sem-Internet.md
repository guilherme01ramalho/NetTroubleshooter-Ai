# Prompt 01 — Computador sem Internet

## Quando utilizar

Quando o computador está conectado à rede (cabo ou Wi-Fi) mas o usuário não consegue acessar a Internet.

## Prompt
Atue como especialista em diagnóstico de redes para Service Desk.

O usuário relata que está conectado à rede, mas não consegue acessar a Internet.

Siga a metodologia: Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção

Investigue considerando:

IP (válido vs APIPA)

Máscara de sub-rede

Gateway (ping)

DHCP (habilitado?)

DNS (resolução de nomes)

Conectividade local (outros computadores?)

Conectividade externa (ping 8.8.8.8)

Para cada etapa, explique:

O que foi observado

O que pode indicar

O que ainda precisa ser validado

NÃO assuma a causa antes das evidências.

RELATO DO USUÁRIO:
[INSIRA O RELATO]

COMANDOS JÁ EXECUTADOS (se houver):
[INSIRA SAÍDAS]


## Exemplo de entrada
RELATO DO USUÁRIO:
"Meu computador está com Wi-Fi conectado, mas não abre nenhum site."

COMANDOS JÁ EXECUTADOS:
ipconfig /all

Saída:
Endereço IPv4: 192.168.1.25
Máscara: 255.255.255.0
Gateway: 192.168.1.1
DNS: 192.168.1.1
DHCP: Habilitado



## O que o prompt produz

Uma investigação estruturada que:
1. Valida a configuração de IP
2. Testa conectividade com gateway
3. Testa conectividade externa
4. Testa resolução de nomes
5. Identifica onde a comunicação falha
6. Sugere correção baseada em evidências