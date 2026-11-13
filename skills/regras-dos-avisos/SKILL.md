---
name: regras-dos-avisos
description: Regras e casos de teste dos fatos que geram aviso ou destaque (dor e recorde). Use ao criar ou alterar fórmulas da planilha, o painel do treinador ou os alertas do n8n.
---

# Regras dos avisos

Na versão 1, só **fatos** geram aviso ou destaque. Nenhuma regra avalia se o treino foi adequado: isso é do treinador. Estas regras são calculadas **sem IA**, por fórmulas na planilha ou condições no n8n.

## Avisos e destaques

| Fato | Regra | O que acontece |
|---|---|---|
| **Dor** | `Sentiu dor?` = "Moderada" ou "Forte" | Alerta imediato ao treinador no Telegram, com o apelido e o local da dor; destaque no painel |
| **Dor leve** | `Sentiu dor?` = "Leve" | Só aparece no painel e no resumo semanal |
| **Recorde** | O valor do registro é **maior** que todos os registros anteriores do mesmo aluno, na mesma medida | Destaque no painel e menção no resumo semanal e na mensagem semanal do aluno |

## Recordes

* São duas medidas separadas: **tempo correndo sem parar (min)** e **distância corrida sem parar (km)**.
* O **primeiro registro** de cada medida é o ponto de partida: não conta como recorde.
* Empatar com o recorde anterior **não** é recorde.
* O recorde não gera mensagem imediata, para não encher o aluno de notificações. Ele entra na mensagem semanal.
* Metas de 1, 3 e 5 km são batidas em provas, não nos treinos, e ficam fora da versão 1.

## Casos de teste (dados inventados)

| # | Entrada | Resultado esperado |
|---|---|---|
| 1 | Dor forte no joelho | Alerta imediato ao treinador + destaque no painel |
| 2 | Dor moderada na panturrilha | Alerta imediato ao treinador |
| 3 | Dor leve no pé | Sem alerta; aparece no painel e no resumo |
| 4 | Primeiro registro do aluno: 4 min sem parar | Sem recorde (ponto de partida) |
| 5 | Recorde anterior 6 min; hoje 8 min | Recorde |
| 6 | Recorde anterior 8 min; hoje 8 min | Sem recorde (empate) |
| 7 | Recorde de tempo 10 min; primeiro treino por distância, 1,5 km | Sem recorde de distância (ponto de partida) |
