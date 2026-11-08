# xrk-reader-for-Mychron-5S

App: https://gabrielecapodanno.github.io/xrk-reader-for-Mychron-5S/


Web app per analizzare i file `.xrk` / `.xrz` del MyChron dall'iPhone.
Tutto gira nel browser: i file di telemetria non vengono mai inviati a nessun server.

## Pubblicare su GitHub Pages

1. Su github.com crea un nuovo repository, per esempio `telemetria-kart` (pubblico; privato solo con GitHub Pro).
2. Nel repository: **Add file → Upload files**, trascina **tutti** i file di questa cartella (compreso `.nojekyll`) e premi **Commit changes**.
   - Se il file nascosto `.nojekyll` non si vede nel Finder, premi Cmd+Maiusc+. per mostrarlo. Non è indispensabile.
3. **Settings → Pages** → in *Build and deployment* scegli *Source: Deploy from a branch*, *Branch: main*, cartella `/ (root)` → **Save**.
4. Dopo un minuto circa l'app è su `https://<tuo-utente>.github.io/telemetria-kart/`.

## Installarla sull'iPhone

1. Apri l'indirizzo in **Safari**.
2. Tocca **Condividi → Aggiungi alla schermata Home**.
3. Da quel momento si apre a schermo intero e funziona anche senza rete (aprila una volta online, così salva tutto in cache).

## Aprire una sessione

1. Nell'app RaceStudio scarica la sessione dal MyChron ed esportala/salvala in **File**.
2. In Telemetria Kart tocca **Apri .xrk** e scegli il file. Le sessioni aperte restano salvate sul telefono.

## Aggiornare l'app

Carica il nuovo `index.html` sul repository. Se l'aggiornamento non compare, cambia `VERSION` in `sw.js` (es. `tk-v2`) e caricalo anche lui: alla seconda apertura l'iPhone prende la nuova versione.

## File

| File | A cosa serve |
|---|---|
| `index.html` | l'app (parser .xrk, grafici, analisi) |
| `sw.js` | service worker: uso offline |
| `manifest.webmanifest`, `icon-*.png` | nome e icona sulla schermata Home |
| `sample.xrz` | sessione di prova (CloseTrackDB_Split) |

Il parser del formato XRK si basa sul lavoro di libxrk (licenza MIT).
