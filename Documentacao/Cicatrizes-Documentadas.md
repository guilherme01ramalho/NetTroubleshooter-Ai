# As 6 Cicatrizes do NetTroubleshooter AI

Durante o desenvolvimento do agente, documentamos 6 momentos críticos onde o comportamento do agente precisou ser corrigido.

## Cicatriz 1 — O diagnóstico precipitado de DHCP

**Problema:** Ao ver `169.254.x.x`, o agente afirmava automaticamente "DHCP indisponível".

**Correção:** Forçamos o agente a considerar múltiplas hipóteses (cabo, switch, driver, DHCP) e solicitar mais evidências.

**Prompt relacionado:** `02-Endereco-169.254.md`

---

## Cicatriz 2 — Ping bem-sucedido = aplicação funcionando

**Problema:** O agente tratava ping bem-sucedido como prova de que a aplicação funcionava.

**Correção:** Incluímos a regra explícita de que ICMP ≠ aplicação.

**Prompt relacionado:** `06-Ping-funciona-sistema-nao.md`

---

## Cicatriz 3 — O "diagnóstico de VLAN" desnecessário

**Problema:** Em problemas simples de DNS, o agente sugeria verificar VLAN e roteamento.

**Correção:** Forçamos o agente a resolver problemas básicos antes de avançar para infraestrutura.

**Prompt relacionado:** `Prompt-Mestre.md`

---

## Cicatriz 4 — A "invenção" de evidências

**Problema:** Com relatos vagos, o agente criava informações fictícias para justificar diagnóstico.

**Correção:** Adicionamos regra: quando evidências são insuficientes, solicitar somente informações necessárias.

**Prompt relacionado:** `Prompt-Mestre.md`

---

## Cicatriz 5 — O DNS externo como prova automática

**Problema:** `nslookup 8.8.8.8` funcionando era interpretado como "DNS corporativo está errado".

**Correção:** Incluímos regra: DNS público funcionando não significa DNS interno errado.

**Prompt relacionado:** `03-Problema-DNS.md`

---

## Cicatriz 6 — A interpretação equivocada do tracert

**Problema:** Salto sem resposta no `tracert` era interpretado como "falha no equipamento".

**Correção:** Adicionamos explicação: ICMP pode ser filtrado; tracert deve ser analisado em conjunto.

**Prompt relacionado:** `09-Analise-tracert.md`

---

## Aprendizado geral

Cada cicatriz representa um refinamento importante que tornou o agente mais robusto, confiável e adequado para Service Desk.

Estas correções foram essenciais para transformar um prompt inicial com tendência a conclusões precipitadas em um agente que segue rigorosamente a metodologia:
Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção