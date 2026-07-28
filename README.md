# Astrolancer — Segui la rotta

Esperienza audiovisiva interattiva: dieci dita controllano dieci stem musicali
(tracking mani via webcam), mentre una navicella naviga nello spazio profondo.
La musica è il propulsore — più il brano sale, più la nave accelera — e quando
l'energia trabocca la nave **salta di dimensione**: nebulosa, pianeti, colori
e HUD cambiano settore (ciano → magenta → ambra → smeraldo).

## Avvio

```bash
npx serve
# oppure
python -m http.server 8000
```

Apri `http://localhost:8000/` (l'app è `index.html`).

- **Entra** — carica gli stem (WAV/MP3/M4A) scaricati da [MobyGratis](https://mobygratis.com)
  con Ctrl/Cmd+click multiplo. Il mix viene mescolato a caso a ogni sessione,
  il silenzio iniziale tagliato automaticamente.
- **Solo scena (demo)** — vola subito senza webcam né stem, con beat sintetico.
- **Tasto W** — forza il salto dimensionale.

## Struttura

```
index.html                        pagina unica: UI, audio (Tone.js), tracking (MediaPipe), scena (three.js)
three-fluid-fx.es.js              simulazione fluida + compositing pass
stems/manifest.json               esempio di manifest per il catalogo online
```

## Controlli in volo

| Gesto | Effetto |
|---|---|
| Stendere/piegare un dito | Volume dello stem assegnato |
| Altezza del polpastrello | Apertura del filtro |
| Posizione orizzontale | Pan stereo |
| Alzare il polso | Mandata riverbero |
| Indici (posizione media) | Rotta della navicella |

Brand: [astrolancer.it](https://astrolancer.it) — font Bricolage Grotesque, titolo "Segui la rotta".

## Online

Il sito è pubblicato con GitHub Pages: **https://monesi96.github.io/astrospacemusic/**
(serve HTTPS, quindi la webcam funziona direttamente dal browser, senza server locale).
