# Testes: regras dos avisos

**Data:** 14/11/2026
**Skill:** [`skills/regras-dos-avisos`](../skills/regras-dos-avisos/SKILL.md)
**Onde:** planilha (abas `Registros` e `Painel`), com respostas fictícias enviadas pelo Google Forms
**Resultado:** 7 de 7 casos passaram ✅

| # | Caso | Dados usados | Esperado | Resultado |
|---|---|---|---|---|
| 1 | Dor forte | Carla, dor forte no joelho | Destaque no painel | ✅ Linha vermelha |
| 2 | Dor moderada | Rafa, dor moderada na panturrilha | Destaque no painel | ✅ Linha vermelha |
| 3 | Dor leve | Gabi, dor leve no pé | Sem destaque | ✅ Sem cor |
| 4 | Primeiro registro | Primeiro registro de cada aluno (ex.: Bia, 6 min) | Sem recorde | ✅ Coluna Recorde vazia |
| 5 | Novo recorde | Bia: 6 min → 8 min | Recorde de tempo | ✅ Linha verde, "Tempo" |
| 6 | Empate | Bia: 8 min → 8 min | Sem recorde | ✅ Coluna Recorde vazia |
| 7 | Primeira distância | Davi: 10 min; depois 9 min e 2 km | Sem recorde | ✅ Coluna Recorde vazia |

## Observações

- O caso 7 usou 2 km em vez dos 1,5 km da skill, para evitar diferença entre vírgula e ponto na planilha. A regra testada é a mesma.
- Os alertas no Telegram dos casos 1 e 2 serão testados na Etapa 4, com o n8n.
