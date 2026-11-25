---
name: origem-retomar
description: >
  Esta habilidade deve ser usada quando o usuário disser "/origem-retomar",
  "retoma a obra", "onde paramos no livro", "continua de onde parou",
  "me atualiza sobre a obra" ou quiser recomeçar o trabalho numa obra do Origem
  em uma conversa nova. Reconstrói o estado atual da obra a partir do que está registrado.
metadata:
  version: "0.2.1"
---

# Retomar uma obra do Origem

Seguir sempre o protocolo da habilidade `origem-protocolo`. Esta habilidade só lê; não grava nada.

## Fluxo

1. **Identificar a obra.** Se o usuário não disse, listar as obras com `listar_obras` e perguntar qual.
2. **Ler.** Chamar `ler_obra`, `ler_contexto_atual` e `buscar_contribuicoes` para a obra. Para obras muito grandes, priorizar a forma atual, os marcos, as decisões, as questões abertas e as contribuições mais recentes; declarar o que ficou sem ler.
3. **Apresentar o ponto de retomada**, curto e em linguagem simples:
   - **Do que se trata** — uma ou duas frases na linguagem da própria obra.
   - **Onde está** — forma atual e último marco.
   - **Decisões em vigor** — somente decisões: os itens do campo de decisões da obra e as contribuições da categoria "decisão". Se uma decisão antiga foi superada, mostrar a vigente junto com o motivo da mudança. Guardar as razões, e não só as conclusões, é o que impede uma IA nova de voltar a uma regra superada. Se não houver decisão além das automáticas do sistema (como "a semente inicial foi preservada"), dizer "nenhuma decisão registrada ainda".
   - **Ideias e hipóteses registradas** — contribuições das categorias "ideia", "hipótese" e "fonte", em ordem da mais recente para a mais antiga, cada uma em uma linha. Nunca colocá-las entre as decisões.
   - **Objeções e questões em aberto** — contribuições das categorias "objeção" e "questão" e as questões abertas da obra; as mais relevantes.
   - **Próximo passo registrado** — se existir; se não existir, dizer isso e sugerir um, marcado como sugestão nova.
4. **Separar** o que está registrado (a), conhecimento externo (b) e interpretações novas (c).
5. **Perguntar** por onde o usuário quer continuar.

## Argumentos

`/origem-retomar [obra]`
