# Mariana

Página web romântica — carta interativa com envelope animado e música de fundo.

## Projeto

- **`index.html`** — app completo: HTML + CSS inline + JS inline, single file.
- **`musica.mp3`** — asset único (áudio de fundo).
- **`mensagem_para_mariana.md`** — texto-fonte da carta.

Tudo estático. Sem build, sem framework, sem dependências.

## Desenvolvimento

Nenhum comando de dev/build/test/lint. Abrir `index.html` no navegador.

## Arquitetura

- Envelope fechado (`#envelopeClosed`) é exibido inicialmente.
- Ao clicar: esconde envelope com fade + mostra carta (`#letterContainer`) com `display:block`.
- Áudio (`#backgroundMusic`) começa a tocar no clique; navegador pode bloquear (autoplay policy). Volume fixo em 30%.
- Player de música (`#musicPlayer`) sai de `display:none` via classe `.show`.
- `visibilitychange` pausa/retoma música se a carta estiver visível.

## Armadilhas conhecidas

- **Animação com `display:none`**: `#musicPlayer` transita de `display:none` para `display:flex`. Animações CSS não disparam quando o elemento sai de `display:none`. Usar classe `.show` com `display:flex` + `animation` (já implementado).
- **Autoplay bloqueado**: áudio só toca em resposta a clique do usuário (já implementado). Testar em diferentes navegadores.
- **`display:none` no envelope**: a transição usa `opacity`/`transform` primeiro, depois `display:none` via `setTimeout` — ordem importa.

## Skills recomendadas

1. `brainstorming` — antes de alterar design ou adicionar interações
2. `writing-plans` — planejar mudanças
3. `frontend-design` — implementar UI
4. `verification-before-completion` — verificar antes de finalizar
