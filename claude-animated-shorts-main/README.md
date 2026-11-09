# Shorts Animados com o Claude

Skill gratuita para o Claude Code que cria **shorts verticais de 55-70 s** no estilo "personagens 2D chapados num
mundo 3D colorido": contorno de tinta, cidade pintada, desfoque de lente, câmera deslizando, trilha e efeitos
sonoros. Tudo é renderizado com three.js dentro do Remotion, **no seu próprio computador**. Não usa gerador de
vídeo de IA.

Exemplo feito com ela: **José no Egito**, um short de 70 s sobre o prisioneiro que salvou o Egito da falência
(roteiro e notas em `exemplos/jose-no-egito/`).

## Crédito
Baseada em **claude-animated-shorts**, de **Mr omi**: https://github.com/mromidev/claude-animated-shorts
(licença MIT, veja `LICENSE`). Todo o pipeline, as regras de estilo, os relatórios de medição e o código do exemplo
"The Bridge That Fell for a Song" são do projeto original. O README original, em inglês, está em `README.en.md`.

## O que tem aqui
| Pasta / arquivo | O que é |
|---|---|
| `SKILL.md` | A skill: o processo completo, todas as regras, todas as correções e os valores finais do visual |
| `templates/bridge/` | O código completo de um short pronto: mundo, personagens, contorno, desfoque, cor, câmera |
| `templates/audio/` | O som sintetizado: efeitos, trilha e a mixagem com volume certo |
| `templates/scripts/` | Stills, folhas lado a lado, junção de cenas e checagem quadro a quadro |
| `references/STYLE_BIBLE.md` | A fórmula de roteiro e de visual medida em 20 shorts de referência |
| `references/reports/` | Sete relatórios com números: movimento, profundidade, texturas, personagens, luz, contorno, cor |
| `exemplos/jose-no-egito/` | Roteiros em inglês e português (com fatos e fontes) e as notas de produção |

`SKILL.md` e os relatórios estão em inglês porque são as instruções que o Claude lê. Ele funciona normalmente
quando você conversa em português.

## O que mudou em relação ao original
- **Correções de render** em `templates/bridge/Bridge.tsx` e `templates/scripts/bridge-stills.mjs`, feitas
  durante a produção do José no Egito.
- **Exemplo novo** em `exemplos/jose-no-egito/`.
- **Removido:** `references/frames/` e `references/sheets/`, que são quadros de vídeos de um canal de terceiros.
  As medições em texto continuam. Para comparar os seus quadros com uma referência, monte as suas próprias folhas
  de quadros a partir dos vídeos que você estudar (os scripts em `templates/scripts/` fazem isso).

## Como instalar
1. Instale **Node.js**, **Python 3** e **ffmpeg**.
2. Copie esta pasta para `~/.claude/skills/cartoon-3d-short/` (clone o repositório ali ou baixe o ZIP em
   **Code → Download ZIP**).
3. Crie uma pasta para o projeto, abra no app do Claude no computador e peça para ele rodar `npm install` (isso
   instala o Remotion com `@remotion/three`).
4. No Claude Code, diga: *"Use a skill de cartoon short e faça um short sobre …"*.

O Claude segue o `SKILL.md`: tema e fatos, roteiro, voz, plano de cenas em `story.ts`, stills e render. No fim
você recebe o render em 2K e a mixagem de som.

## Dicas do José no Egito
- **Render no seu PC:** o render 2K de 69 s levou cerca de 12 min (≈4 fps), com `--scale 1.3333 --concurrency=3`.
- **Placa de vídeo:** no Windows, em Configurações › Sistema › Tela › Gráficos, coloque o Chrome do Remotion em
  "Alto desempenho" (placa dedicada).
- **Disco:** defina `REMOTION_TMP` numa unidade com espaço. Cada bundle copia a pasta `public/` (~1,3 GB).
- **Versão em português:** a mesma imagem do vídeo em inglês, com a narração em `en-US-AndrewMultilingualNeural`
  (edge-tts, +25 a +30%) e legendas geradas a partir do tempo de cada palavra.
- **Conteúdo próprio:** história, personagens e voz devem ser sempre seus. Use as referências para o visual, não
  para o conteúdo.

## Licença
Código e documentação sob licença MIT (veja `LICENSE`), mantendo o aviso de copyright do autor original.
