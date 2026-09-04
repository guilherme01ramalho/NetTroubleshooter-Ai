🧠 NetTroubleshooter AI
Um agente de diagnóstico de redes para Service Desk, construído com engenharia de prompts orientada por evidências
📌 Contexto e objetivo
O NetTroubleshooter AI é um agente especializado em diagnóstico de problemas de rede em ambientes Windows, desenvolvido para atuar como assistente de analistas de Service Desk.

O projeto nasceu de uma necessidade real: profissionais de suporte de nível 1 e 2 frequentemente recebem chamados de "Internet não funciona" ou "sistema não abre" sem terem um roteiro estruturado para investigação. O resultado são diagnósticos baseados em suposições, comandos executados fora de ordem e retrabalho.

O objetivo do NetTroubleshooter AI é fornecer um roteiro baseado em evidências, onde cada etapa do diagnóstico é orientada por:

Evidência observada

Hipótese formulada

Teste apropriado

Interpretação cuidadosa dos resultados

Próximo teste ou correção indicada

🎯 Problema que o projeto resolve
Problema comum no Service Desk	Como o NetTroubleshooter AI ajuda
Analista não sabe por onde começar	Fornece roteiro estruturado de investigação
Diagnóstico baseado em suposições	Exige evidências antes de concluir causas
Comandos executados sem interpretação	Explica o que cada comando demonstra e o que não demonstra
Conclusões precipitadas (ex: "169.254 é DHCP")	Ensina a diferenciar evidência, hipótese, causa provável e causa confirmada
Perda de tempo com testes errados	Prioriza testes simples, seguros e pouco invasivos
🧠 Como funciona o NetTroubleshooter AI
O agente foi projetado para atuar dentro do NotebookLM, utilizando um Caderno Temático com fontes cuidadosamente selecionadas sobre diagnóstico de redes em ambientes Windows.

O fluxo de raciocínio obrigatório do agente é:

text
Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção
Regras fundamentais do agente:
Nunca assumir a causa antes das evidências

Diferenciar claramente:

Evidência observada

Hipótese

Causa provável

Causa confirmada

Usar linguagem probabilística — "pode indicar", "sugere", "torna mais provável"

Explicar o que cada teste consegue e não consegue provar

Priorizar testes simples, seguros e pouco invasivos

Manter o escopo adequado para Service Desk

Não transformar problemas básicos em diagnósticos excessivamente avançados

📚 Curadoria das fontes de conhecimento
O conhecimento do NetTroubleshooter AI é baseado em fontes confiáveis e práticas sobre diagnóstico de redes em ambientes Windows.

Temas abordados pelas fontes
Tema	Conteúdo	Finalidade
Comandos de rede Windows	ipconfig, ping, tracert, nslookup, netstat	Base técnica para orientar testes
Metodologias de troubleshooting	Fluxos de investigação e boas práticas	Estruturação do raciocínio de diagnóstico
Abordagem para Service Desk	Diagnóstico prático para suporte nível 1 e 2	Adequação do escopo para analistas
Documentação técnica	Comportamentos de sistema e protocolos	Validação de interpretações
Critério de seleção das fontes
As fontes foram escolhidas com base em:

Relevância para diagnóstico de redes em ambientes Windows

Praticidade para aplicação em Service Desk

Confiabilidade técnica

Complementaridade entre si

🛠️ Metodologia de diagnóstico
A metodologia adotada pelo NetTroubleshooter AI segue uma hierarquia de verificação:

Camada 1 — Conectividade física e lógica básica
Verificar cabo, Wi-Fi, LEDs, status da placa de rede

Executar ipconfig /all

Validar endereço IP, máscara, gateway, DHCP, DNS

Camada 2 — Conectividade local
ping gateway

Validar comunicação com a rede local

Camada 3 — Conectividade externa
ping 8.8.8.8

tracert para identificar onde a comunicação falha

Camada 4 — Resolução de nomes
nslookup para domínios internos e externos

Verificar servidores DNS configurados

Camada 5 — Aplicação e serviços
Testar porta específica (ex: telnet ou Test-NetConnection)

Validar se o serviço está em execução

Camada 6 — Correção
Aplicar correção baseada nas evidências confirmadas

Validar após correção

🧪 Testes iniciais — Validação do agente
Antes de criarmos os prompts reutilizáveis, executamos 5 testes iniciais para validar o comportamento do agente com o prompt base.

Cenários testados
Teste	Cenário	Resultado
1	Computador com IP 169.254.1.5	Agente sugeriu verificar DHCP, mas também outras causas possíveis
2	"Internet não funciona" com Wi-Fi conectado	Agente seguiu fluxo: IP → gateway → externo → DNS
3	Ping funcionando, mas sistema não abre	Agente diferenciou ICMP de conectividade de aplicação
4	DNS externo funciona, mas interno não	Agente orientou verificar servidores DNS e resolução interna
5	"Sistema não funciona" sem evidências	Agente solicitou informações adicionais antes de diagnosticar
Principais descobertas dos testes iniciais
✅ O agente conseguia seguir um raciocínio estruturado

⚠️ Em alguns casos, o agente ainda tendia a pular etapas

⚠️ O agente ocasionalmente sugeria comandos avançados demais para Service Desk

⚠️ O agente às vezes afirmava causas sem evidências suficientes

🔥 Testes de estresse — Refinamento do agente
Após os testes iniciais, aplicamos 5 testes de estresse para expor limitações e forçar o agente a situações mais complexas.

Cenários de estresse
Teste	Cenário	Objetivo
1	Computador com vários adaptadores e IPs conflitantes	Verificar capacidade de lidar com múltiplas interfaces
2	"Internet lenta" com resultados contraditórios	Testar priorização de hipóteses
3	Relato vago sem evidências	Forçar solicitação de informações
4	Infraestrutura complexa com VLAN e VPN	Testar manutenção de escopo Service Desk
5	Múltiplos problemas simultâneos	Verificar capacidade de separar problemas
Principais aprendizados dos testes de estresse
🔴 O agente frequentemente tentava diagnosticar causas avançadas (VLAN, MTU, roteamento) antes de validar o básico

🔴 Em relatos vagos, o agente às vezes "inventava" evidências

🔴 O agente ocasionalmente confundia "provável" com "confirmado"

🟢 Após refinamentos, o agente melhorou significativamente a solicitação de informações antes de diagnosticar

🩹 Engenharia de Prompts — As cicatrizes do NetTroubleshooter AI
Durante o desenvolvimento do NetTroubleshooter AI, documentamos 6 "cicatrizes" — momentos em que o agente apresentou comportamentos indesejados que exigiram correção no prompt.

Cicatriz 1 — O diagnóstico precipitado de DHCP
Problema: Ao ver 169.254.x.x, o agente afirmava automaticamente "DHCP indisponível".

Correção: Forçamos o agente a considerar múltiplas hipóteses (cabo, switch, driver, DHCP) e solicitar mais evidências.

Prompt relacionado: 02-Endereco-169.254.md

Cicatriz 2 — Ping bem-sucedido = aplicação funcionando
Problema: O agente tratava ping bem-sucedido como prova de que a aplicação funcionava.

Correção: Incluímos a regra explícita de que ICMP ≠ aplicação.

Prompt relacionado: 06-Ping-funciona-sistema-nao.md

Cicatriz 3 — O "diagnóstico de VLAN" desnecessário
Problema: Em problemas simples de DNS, o agente sugeria verificar VLAN e roteamento.

Correção: Forçamos o agente a resolver problemas básicos antes de avançar para infraestrutura.

Prompt relacionado: Prompt-Mestre.md

Cicatriz 4 — A "invenção" de evidências
Problema: Com relatos vagos, o agente criava informações fictícias para justificar diagnóstico.

Correção: Adicionamos regra: quando evidências são insuficientes, solicitar somente informações necessárias.

Prompt relacionado: Prompt-Mestre.md

Cicatriz 5 — O DNS externo como prova automática
Problema: nslookup 8.8.8.8 funcionando era interpretado como "DNS corporativo está errado".

Correção: Incluímos regra: DNS público funcionando não significa DNS interno errado.

Prompt relacionado: 03-Problema-DNS.md

Cicatriz 6 — A interpretação equivocada do tracert
Problema: Salto sem resposta no tracert era interpretado como "falha no equipamento".

Correção: Adicionamos explicação: ICMP pode ser filtrado; tracert deve ser analisado em conjunto.

Prompt relacionado: 09-Analise-tracert.md

📊 Resultados e evolução do agente
Evolução do NetTroubleshooter AI
Versão	Características	Limitações
v1.0 (Prompt inicial)	Diagnóstico básico com ipconfig, ping, nslookup	Conclusões precipitadas, diagnóstico avançado demais
v1.1 (Após testes iniciais)	Melhor estruturação do raciocínio	Ainda tendia a pular etapas
v1.2 (Após testes de estresse)	Solicitação de informações adicionais	Ocasionalmente "inventava" evidências
v2.0 (Com cicatrizes documentadas)	Regras explícitas de diferenciação	Pronto para uso em Service Desk
Métricas de qualidade
Critério	Antes	Depois
Conclusões precipitadas	Frequente	Raro
Diagnóstico avançado	Comum	Controlado
Diferenciação ICMP × aplicação	Não existia	Claramente definida
Solicitação de evidências	Ocasional	Obrigatória
Uso de linguagem probabilística	Raro	Padrão
🎓 Aprendizados
Aprendizados sobre engenharia de prompts
Especificidade é tudo — Prompts vagos geram respostas vagas. É necessário dizer explicitamente o que o agente deve e não deve fazer.

Regras negativas são tão importantes quanto positivas — Dizer "não assuma" é tão eficaz quanto dizer "siga este fluxo".

Cicatrizes documentadas são valiosas — Cada erro corrigido fortalece o prompt e serve como aprendizado para projetos futuros.

Testes de estresse expõem limitações — Situações extremas revelam problemas que não aparecem em testes simples.

A fonte define o escopo — O agente só pode diagnosticar o que está nas fontes. Uma curadoria cuidadosa é fundamental.

Aprendizados sobre diagnóstico de redes para Service Desk
O básico resolve a maioria dos problemas — Muitos diagnósticos avançados são desnecessários se o básico for verificado primeiro.

Evidência não é interpretação — Um fato observado (ex: IP 169.254) é diferente de sua interpretação (ex: DHCP falhou).

Testes têm limitações — Um teste bem-sucedido não prova tudo; um teste mal-sucedido não prova nada.

A comunicação com o usuário é parte do diagnóstico — Muitas vezes, a informação mais valiosa vem do relato do usuário, não de comandos.

🚀 Possíveis melhorias futuras
O NetTroubleshooter AI pode ser expandido nas seguintes direções:

Expansão de escopo
Inclusão de diagnósticos para ambientes Linux/macOS

Suporte a problemas de VPN e proxy

Diagnóstico de Wi-Fi (interferência, sinal, autenticação)

Problemas de impressão em rede

Aprimoramento do agente
Versão com suporte a múltiplos comandos simultâneos

Integração com ferramentas de monitoramento

Geração automática de relatórios de diagnóstico

Formas de disponibilização
Versão para ChatGPT (GPTs)

Bot no Teams/Slack para suporte interno

Interface web para analistas

