---
name: origem-genealogia
description: >
  Esta habilidade deve ser usada quando o usuário disser "/origem-genealogia",
  "de onde veio essa ideia", "mostra a genealogia", "como essa obra evoluiu",
  "quem contribuiu com o quê" ou "quais obras estão ligadas". Mostra a origem,
  as derivações, as relações entre obras e os créditos registrados no Origem.
metadata:
  version: "0.2.0"
---

# Genealogia de uma obra do Origem

Seguir sempre o protocolo da habilidade `origem-protocolo`. Esta habilidade só lê; não grava nada.

## Fluxo

1. **Identificar a obra** (ou a ideia específica, se o usuário perguntar sobre uma).
2. **Ler** com `ler_genealogia` e `ler_obra`. Para rastrear uma ideia, usar também `buscar_contribuicoes` com termos dela.
3. **Apresentar:**
   - **Origem** — a semente e quem a propôs, com data.
   - **Marcos** — em ordem, com o impacto de cada um.
   - **Derivações e relações** — obras que nasceram desta ou se ligam a ela, e como.
   - **Créditos** — o papel do humano e de cada IA, conforme registrado. Nunca atribuir autoria que não esteja registrada.
4. Quando ajudar, desenhar uma linha do tempo ou um diagrama simples das relações.
5. Se a genealogia estiver vazia ou incompleta, dizer isso exatamente, sem preencher lacunas.

## Argumentos

`/origem-genealogia [obra ou ideia]`
