# José no Egito — notas de produção

Short de 70 s feito com esta skill: um prisioneiro que salvou o Egito da falência guardando um quinto da colheita
(Gênesis 41). Roteiros com fatos e fontes: `SCRIPT_EN.md` e `SCRIPT_PT.md`.

## Como foi feito
- **Composição:** `JosephShort` no projeto Remotion (`src/videos/joseph/`: story.ts, egyptset.ts, world.ts, cast.ts,
  toon.ts, lights.ts com luz noturna, de sonho e de poeira). Partiu do template `templates/bridge/`.
- **Voz:** edge-tts `en-US-AndrewNeural` +25% (inglês, 68,3 s) → `voice.wav` + `words.json` (tempo de cada palavra).
- **Som:** efeitos sintetizados e trilha (`templates/audio/`), mix final em -15 LUFS e -1,2 dBTP.
- **Rodadas de imagem:** 8 rodadas de stills (r1 a r8) até o estilo bater. Problemas reais que apareceram:
  personagem cortado e cena torta (r1), câmera mirando no lugar errado com a cena vazia (r3), um plano em que o
  monte de grãos crescendo ficava fora do quadro, e o pôr do sol do final saindo roxo em vez de dourado.
- **Final:** render 2K (1440x2560, `--scale 1.3333`, `--concurrency=3`), cerca de 12 min no PC, 69,17 s,
  oscilação média de brilho entre quadros de 0,21 %.

## Versão em português
- A mesma imagem do inglês, remapeada para o tempo da fala em português (`ptmap.ts`), mais uma montagem no hook.
- Voz: `en-US-AndrewMultilingualNeural` +25% falando português (70,0 s).
- Legendas queimadas no vídeo, geradas a partir dos tempos de cada palavra (blocos de 1-3 palavras).
