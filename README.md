# Radar de Soluções Educacionais

Vitrine institucional para comunicar iniciativas da equipe de Soluções Educacionais sem expor detalhes operacionais.

## Como atualizar
Edite somente `radar.json`.

Campos principais:
- `titulo`
- `categoria`
- `resumo`
- `impacto`
- `status`: `entregue`, `em_andamento`, `exploracao` ou `planejado`
- `publicarEm`: data em `AAAA-MM-DD`
- `destaque`: `true` ou `false`
- `tags`

## Automação por data
A página só exibe uma iniciativa quando `publicarEm` for igual ou anterior à data atual.
Assim, você pode preparar divulgações futuras antecipadamente.

## Publicação
Hospede a pasta no GitHub Pages. A página sempre lê `radar.json` sem cache para refletir atualizações.

## Comunicação recomendada
Evite cronogramas operacionais, nomes individuais, riscos internos, dependências técnicas e detalhes de execução.
Prefira: o que é, por que importa, impacto esperado e status macro.
