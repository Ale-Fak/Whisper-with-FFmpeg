# Guida all'Installazione e Uso di Whisper con FFmpeg

## 1. Installazione di FFmpeg

### Windows

1. Scarica FFmpeg da [questa pagina](https://www.gyan.dev/ffmpeg/builds/).
2. Scarica la versione **"ffmpeg-git-full.7z"**.
3. Estrai il file con [7-Zip](https://www.7-zip.org/) o WinRAR.
4. Sposta la cartella estratta in `C:\ffmpeg`.
5. Aggiungi `C:\ffmpeg\bin` al **PATH** di Windows:
   - Cerca **"Variabili d'ambiente"** e apri.
   - Vai su **Variabili di sistema > Path > Modifica**.
   - Clicca su **Nuovo** e inserisci `C:\ffmpeg\bin`.
   - Premi **OK** e riavvia il PC.
6. Verifica l'installazione aprendo il **Prompt dei comandi** e digitando:
   ```sh
   ffmpeg -version
   ```

### macOS

1. Apri il **Terminale**.
2. Installa Homebrew (se non lo hai già):
   ```sh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. Installa FFmpeg con:
   ```sh
   brew install ffmpeg
   ```
4. Verifica l'installazione:
   ```sh
   ffmpeg -version
   ```

### Linux (Ubuntu/Debian)

1. Apri il **Terminale**.
2. Esegui:
   ```sh
   sudo apt update && sudo apt install ffmpeg -y
   ```
3. Controlla se l'installazione è avvenuta con successo:
   ```sh
   ffmpeg -version
   ```

## 2. Installazione di Whisper

1. Installa **Python** (se non lo hai già) da [python.org](https://www.python.org/downloads/).
2. Apri il **Terminale / Prompt dei comandi**.
3. Installa Whisper e le dipendenze:
   ```sh
   pip install openai-whisper
   ```

## 3. Trascrizione di un File Audio con Whisper

1. Sposta il file audio nella cartella in cui vuoi lavorare.
2. Apri il **Terminale / Prompt dei comandi** e spostati nella cartella con:
   ```sh
   cd percorso/della/cartella
   ```
3. Esegui Whisper sul file audio:
   ```sh
   whisper nomefile.ogg --language Italian
   ```

## 4. Dove Troverai il File di Testo?

Dopo l'elaborazione, Whisper genererà più file:

- `nomefile.txt` → Contiene solo la trascrizione.
- `nomefile.srt` → Formato sottotitoli.
- `nomefile.vtt` → Formato sottotitoli WebVTT.

Questi file saranno salvati nella **stessa cartella** da cui hai eseguito il comando.

## 5. Verifica della Trascrizione

Apri il file `.txt` con un qualsiasi editor di testo per leggere la trascrizione.

## 6. Risoluzione Problemi

- **Whisper non riconosce il comando?**
  ```sh
  pip install --upgrade openai-whisper
  ```
- **FFmpeg non installato correttamente?** Verifica digitando:
  ```sh
  ffmpeg -version
  ```
  Se non funziona, reinstalla FFmpeg e verifica il PATH.

---

Ora sei pronto a trascrivere i tuoi file audio con Whisper! 🎤

