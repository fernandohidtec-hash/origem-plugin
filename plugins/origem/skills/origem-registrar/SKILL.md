---
name: origem-registrar
description: >
  Esta habilidade deve ser usada quando o usuário disser "/origem-registrar",
  "registra no Origem", "salva isso na obra", "guarda essa ideia", "adiciona como
  contribuição" ou pedir para transformar um trecho da conversa em contribuição de
  uma obra do Origem. Prepara a contribuição, mostra a prévia e só grava com pedido explícito.
metadata:
  version: "0.2.1"
---

# Registrar contribuição no Origem

Seguir sempre o protocolo da habilidade `origem-protocolo`.

## Fluxo

1. **Identificar a obra.** Se o usuário não disse, propor a obra mais provável e confirmar. Se houver dúvida entre duas, perguntar. Confirmar o título exato com `listar_obras` ou `ler_obra`.
2. **Filtrar o essencial.** Registrar só o que muda ou explica a obra: decisões, razões de mudança, hipóteses, evidências, objeções. Não registrar conversa solta. Quando uma regra ou decisão mudar, registrar também o motivo da mudança.
3. **Ler antes de escrever.** Ler a obra e as contribuições recentes, para não repetir o que já está registrado e para ligar a nova contribuição ao que existe (citar datas de contribuições anteriores quando houver relação). Se algo já registrado ficou desatualizado, dizer isso e propor uma contribuição de atualização, sem editar a antiga.
4. **Classificar.** Escolher uma categoria aceita pela ferramenta: ideia, hipótese, objeção, decisão, questão ou fonte. Evidências e revisões entram como "ideia" ou "decisão", com o tipo explicado no texto.
5. **Redigir.** Texto autônomo, compreensível sem a conversa:
   - título curto em maiúsculas com a data;
   - o conteúdo em si;
   - de onde veio (proposto pelo usuário, pela IA ou cocriado) e o que o usuário aprovou;
   - limites e pendências, quando houver.
   Preservar as palavras do usuário quando ele ditar o texto. Até 8.000 caracteres.
6. **Definir autoria.** "humano" quando o conteúdo é do usuário; "IA" quando é só da IA; "co-criado" quando os dois contribuíram. Preencher a divisão de autoria com os nomes (ex.: humano = nome do usuário, IA = Claude).
7. **Mostrar a prévia.** Obra, categoria, autoria e texto completo.
8. **Gravar só com pedido explícito.** Se o pedido explícito já veio na mensagem atual, mostrar a prévia e gravar. Se não, esperar. "Pode", "sim", "salva" em resposta direta à prévia contam como pedido explícito.
9. **Confirmar com comprovante.** Depois que a ferramenta devolver o comprovante verificado, informar em uma frase e mostrar o link. Se falhar, dizer claramente que não foi salvo.

## Argumentos

`/origem-registrar [obra] [texto opcional]` — se o texto vier junto, usar como base preservando as palavras do usuário.
