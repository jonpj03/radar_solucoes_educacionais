# Radar de Soluções Educacionais — Tela Única

Esta versão foi pensada para ficar aberta em uma única tela, TV, monitor ou navegador.

## O que o público vê
- uma iniciativa principal em destaque;
- resumo simples;
- impacto para outras áreas;
- status macro;
- tags;
- lista lateral das principais iniciativas;
- rotação automática das notícias;
- indicadores gerais;
- tema Automático, Claro ou Escuro.

Nenhuma instrução de manutenção aparece no `index.html`.

## Como a equipe atualiza
Edite apenas o arquivo `radar.json`.

Cada item usa esta estrutura:

```json
{
  "id": "nome-unico",
  "titulo": "Nome da iniciativa",
  "categoria": "Categoria macro",
  "resumo": "Explique em uma frase o que está sendo criado.",
  "impacto": "Explique em uma frase por que isso importa para outras áreas.",
  "status": "em_andamento",
  "publicarEm": "2026-09-25",
  "destaque": true,
  "icone": "✦",
  "tags": ["Tecnologia", "Experiência", "Dados"]
}
```

### Status aceitos
- `entregue`
- `em_andamento`
- `exploracao`
- `planejado`

### Publicação automática
O campo `publicarEm` controla quando a notícia aparece.
Uma iniciativa com data futura só entra no Radar quando essa data chegar.

### Ordem das notícias
Primeiro aparecem os itens com `destaque: true`.
Depois, os demais são organizados pela data `publicarEm`, do mais recente para o mais antigo.

### Tempo de rotação
No `index.html`, a constante:

```js
const INTERVAL=9000;
```

define o tempo de cada notícia em milissegundos.
`9000` = 9 segundos.

## Recomendações de conteúdo
Para evitar ruído entre áreas, publique apenas:
- o que é;
- por que importa;
- impacto esperado;
- status macro.

Evite:
- nomes de responsáveis;
- tarefas operacionais;
- riscos internos;
- dependências técnicas;
- datas de execução não confirmadas;
- detalhes de bastidores.


## Mini dashboards
A lateral agora inclui indicadores macro calculados automaticamente a partir do `radar.json`:
- iniciativas visíveis;
- entregues;
- em movimento;
- quantidade de áreas/categorias;
- percentual entregue;
- distribuição entre entregue, andamento e exploração.

Não é necessário preencher esses indicadores manualmente. Eles são recalculados sempre que o `radar.json` é carregado.


## Atualização automática sem F5
A página relê o `radar.json` automaticamente a cada 60 segundos.

Isso significa que, se uma iniciativa estiver com:

```json
"publicarEm": "2026-10-05"
```

e o Radar permanecer aberto continuamente em uma TV ou monitor, a iniciativa passa a aparecer sozinha após a data ser atingida, sem necessidade de atualizar manualmente a página.

O intervalo pode ser alterado no `index.html` pela constante:

```js
const DATA_REFRESH_INTERVAL=60000;
```

`60000` = 60 segundos.
