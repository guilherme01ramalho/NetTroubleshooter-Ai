# Prompts do NetTroubleshooter AI

Este diretório contém todos os prompts desenvolvidos para o agente de diagnóstico de redes.

## Estrutura

- **Prompt-Mestre.md**: Prompt universal para qualquer diagnóstico de rede
- **Reutilizaveis/**: 10 prompts para cenários específicos de Service Desk

## Como usar

1. Copie o prompt desejado
2. Cole no NotebookLM (ou outra IA com suporte a cadernos temáticos)
3. Substitua o relato do usuário e as evidências
4. Execute o diagnóstico

## Metodologia

Todos os prompts seguem:
Evidência → Hipótese → Teste → Resultado → Interpretação → Próximo teste → Correção


## Regras fundamentais

- Não assumir causas sem evidências
- Diferenciar evidência, hipótese, causa provável e causa confirmada
- Usar linguagem probabilística
- Explicar o que cada teste prova e não prova
- Priorizar testes simples para Service Desk