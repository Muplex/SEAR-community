# SEAR

**Sound-Estimation & Auto-Refinement** — get a recorded guitar tone on your FM3 or FM9.

[![Donate with PayPal](https://img.shields.io/badge/Donate-PayPal-0070BA?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/Muplex)

```
        __     ♫
       |oo|           ╔════════════════════════════════════════════╗
       |oo|  ♪        ║   S . E . A . R .                          ║
       |oo|           ║   listen · measure · tweak · repeat        ║
        ||            ║   ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁▁▂▃▅▇▅▃▂▁             ║
        ||            ╚══════════════════════╤═════════════════════╝
        ||                                   |  USB
        ||                                   |
       _||_           .----------------------+--------------------------.
      /    \          |  FM3                   [ Deluxe Tweed Jumped ]  |
     |  ::  |         |  PRESET 042 · SCENE 2           TUNER  E  >|<   |
      \ -- /  ~~~=[>  |   (o)    (o)    (o)    (o)    (o)               |
     /  ==  \  JACK   |-------------------------------------------------|
    |   ()   |        |      [ 1 ]            [ 2 ]            [ 3 ]    |
     \______/         '-------------------------------------------------'
                                             | OUT1 XLR/JACK
                                             v
                          .----------------------------------------.
                          | VOLUME 1 2 3 4 5 6 7 8 9 10 [11]  \m/  |
                          |========================================|
    ______                |         .-----.        .-----.         |     ♪
    \    /                |         (  o  )        (  o  )         |   ♫
     \  /                 |         '-----'        '-----'         |        ♪
      \/                  |         .-----.        .-----.         |     ♫
                          |         (  o  )        (  o  )         |
                          |         '-----'        '-----'         |
                          '----------------------------------------'
```

You play the part over the record; SEAR separates the record's guitar, tries candidate rigs on **your own FM3**, tunes
their knobs by measuring the real sound against the record, and leaves the result in the working preset for you to save.
It can also measure a rig *you* built and tell you how close it is.

This repository is SEAR's **public home**: downloads (Releases), release notes, bug reports, ideas and questions.
SEAR's source code is not here. SEAR is free.

> 🇮🇹 Più sotto c'è un riassunto in italiano.

> **Status: SEAR 1.1.0, Windows only — an FM3 with firmware 13.00 or an FM9 with firmware 12.00.** SEAR reads the
> firmware and refuses a version it has not been validated on. It is tested on one FM3 and one FM9 so far: please report
> what goes wrong. On the FM9, the extra blocks (wah, pitch, filter, compressor, talk box, modulations) and preset / scene
> names are not available yet.

## What SEAR does

- **Your songs, your takes.** Add a song from your PC (MP3, WAV, FLAC, M4A). Record your DI inside SEAR while the record
  plays: SEAR measures the latency and places every take exactly in the song. You can change the record's key and speed to
  practise. Every record starts at the same volume, set from its own loudness, and the file itself is never changed.
- **The right 6 seconds.** SEAR tunes on a 6-second window of each section. It reads your take and proposes a window that
  holds the ways you play in it: palm mutes, low notes, high notes, soft playing. Drag the window elsewhere and it tells
  you what is left out.
- **The rig research, with your own AI.** SEAR writes the question (the song, the rules it learned, the exact FM3 model
  names). You paste the answer back and SEAR checks it.
- **Tone match on your FM3.** SEAR screens the candidate rigs and all 2048 factory cabs (once measured on your FM3), then
  tunes the knobs until no move is audibly better, and adds a final EQ. Clean, crunch and high-gain parts are handled
  differently, and a rig more distorted than the record is never chosen. You watch it live and can stop it at any time.
- **Continue instead of starting over.** A part that already has a good run continues from it: no new screening, about 4-6
  minutes. This is the default for one part and for every part of a whole song.
- **A whole song in one preset.** One scene per section (clean, rhythm, lead), each matched and leveled against the
  others. **⟲ Recall** rebuilds it on the FM3 in about a minute and leaves alone the scenes that are already right.
- **👂 Tweak by ear.** *Boxy*, *fizzy*, *thin*, *boomy*, *more gain*, *too wet*, *too quiet*… SEAR plays two ready-made
  corrections on your FM3 for you to compare with the record. The one you keep stays with that run, and every recall applies
  it again.
- **🎸 Play along.** The record, or the record **without its guitar**, plays from the FM3 while you play through your song
  preset, and SEAR **switches the scenes** at the points you marked on a coloured scene bar.
- **🎛 Your own rig.** SEAR measures a preset you built yourself against the record, without writing anything into it.
- **Tidy.** SEAR keeps only the files it needs. *Settings → Disk space* deletes the runs you don't use.

## What you need

- **Windows 10 or 11, 64-bit**, about 3 GB of free disk space (5 GB with the optional RoFormer separator).
- **An FM3 with firmware 13.00 or an FM9 with firmware 12.00**, connected by USB, with its USB audio driver — it is
  installed with **FM3-Edit** / **FM9-Edit** (free, from the maker's site).
- **Open FM3-Edit (FM9-Edit for an FM9) once with the device connected before SEAR's first start**, and let it read the
  device. SEAR reads its parameter tables from the editor's data on your PC (they are not included in SEAR). After a
  firmware update, do it again.
- **FM3-Edit / FM9-Edit closed** while SEAR talks to the device.
- **Your own AI chat** (Claude or ChatGPT, with web search) for the rig research: SEAR writes the question, you paste it,
  and SEAR checks the answer.

## Install

1. Download the newest `SEAR-<version>.zip` from [Releases](../../releases).
2. Extract the **whole folder** anywhere you like, for example in Documents. The path must not contain `%` or `^`.
3. Double-click **SEAR.exe** (the squirrel). SEAR opens in your browser, and its icon appears next to the clock: click it to
   open SEAR again, right-click it → **Quit SEAR** to close it.

**Windows SmartScreen** may say *"Windows protected your PC"*: SEAR is not signed with a paid certificate yet. Click
**More info** → **Run anyway**. Everything SEAR writes stays inside its folder (`data\`); to uninstall, delete the folder.

**Before SEAR builds a rig, load an EMPTY preset on the FM3.** SEAR never saves to the FM3 by itself: you save the result
when you like it. Back up your presets first (FM3-Edit or the FM3's own backup).

## Updates

SEAR updates itself. At start (and every few hours while it is open) it checks [`latest.json`](latest.json) here; when a
newer version is out it downloads it, checks the author's signature and every file's checksum, and the page shows
**"Restart to update"**. Nothing is installed until you press it, never while the FM3 is in use, and your songs, runs and
settings are kept. What changed in each version: [CHANGELOG.md](CHANGELOG.md).

## Reporting a problem

1. **From SEAR (best):** press **🐞 Report** on a failed job, or ⚙ Settings → "Something wrong?". SEAR prepares the report
   with the log, the version and the settings — your paths and user name removed — and sends nothing by itself. It also
   looks here for the same error (its `E-xxxxxxxx` code in the title): if it is already reported, add yours as a
   **comment**.
2. **By hand:** [open an issue](../../issues/new/choose) with the **Bug** form.
3. **Without a GitHub account:** "Save the report" in SEAR's report window, then e-mail the file to
   **sear.beta.reports@gmail.com**.

## Ideas and questions

- An idea or a missing feature: an issue with the **Idea** form.
- "How do I…?" or "Is this normal?": [Discussions](../../discussions).

## Privacy

SEAR runs on your PC and its page is only on your own computer. It goes online only to check for and download updates
(here, on GitHub), to look for an already-reported error, for band / album pictures (Wikipedia, MusicBrainz — on by
default, off in ⚙ Settings) and, only if you ask for it, to install the optional RoFormer separator. No telemetry, no account. Details: the `EULA.md`
in SEAR's folder.

## Support SEAR

SEAR is free. If it helps your tone, a voluntary donation helps keep it growing:

[![Donate with PayPal](https://img.shields.io/badge/Donate-PayPal-0070BA?logo=paypal&logoColor=white&style=for-the-badge)](https://paypal.me/Muplex)

[paypal.me/Muplex](https://paypal.me/Muplex) — nothing in the app changes whether you donate or not.

## In italiano

**SEAR** è un'app gratuita per Windows che ti aiuta a ottenere sull'FM3 o sull'FM9 il suono di chitarra di un disco: suoni la parte
sopra il disco, SEAR separa la chitarra del disco, prova dei rig sul **tuo** FM3, ne regola le manopole misurando il suono
e lascia il risultato nel preset di lavoro, che salvi tu. Questo repository è la casa pubblica di SEAR (download nelle
Releases, note di versione, segnalazioni, idee, domande); il codice non è qui.

- **Cosa fa:**
  - registri la tua DI sopra il disco (MP3, WAV, FLAC, M4A, ognuno allo stesso volume);
  - SEAR propone i 6 secondi che contengono i tuoi modi di suonare (palm-mute, note gravi e acute, parti piano);
  - fa la ricerca del rig con la tua AI, poi lo screening dei rig e dei 2048 cab di fabbrica e la taratura delle manopole sul tuo FM3;
  - un run già buono si continua invece di ripartire da zero;
  - mette una canzone intera in un preset (una scena per sezione) con ⟲ Richiama;
  - 👂 ritocchi a orecchio (*inscatolato*, *zanzaroso*, *magro*, *più gain*…);
  - 🎸 **Suona con il brano**: il disco, anche senza la sua chitarra, esce dall'FM3 e SEAR cambia le scene nei punti che hai segnato;
  - 🎛 misura un rig fatto da te.
- **Serve:** Windows 10/11 a 64 bit, un FM3 con firmware 13.00 o un FM9 con firmware 12.00 collegato via USB,
  **FM3-Edit (FM9-Edit per l'FM9) aperto una volta con il dispositivo collegato prima del primo avvio** (SEAR legge da lì
  le tabelle dei parametri), l'editor chiuso mentre SEAR lavora, una tua chat AI (Claude o ChatGPT) per la ricerca del
  rig. Sull'FM9 non ci sono ancora i blocchi extra (wah, pitch, filtro, compressore, talk box, modulazioni) e i nomi di
  preset e scene.
- **Installazione:** scarica lo zip dalle [Releases](../../releases), estrai tutta la cartella, doppio clic su
  **SEAR.exe**. Se Windows dice *"PC protetto"*: **Ulteriori informazioni** → **Esegui comunque** (SEAR non è ancora
  firmato con un certificato a pagamento). Per disinstallare basta cancellare la cartella.
- **Aggiornamenti:** automatici; SEAR scarica la versione nuova, ne controlla la firma e ti propone **"Riavvia per
  aggiornare"**. Canzoni, run e impostazioni restano.
- **Problemi:** **🐞 Segnala** dentro SEAR; senza account GitHub "Salva il rapporto" e invia il file a
  **sear.beta.reports@gmail.com**. **Idee:** una issue con il modulo *Idea*. **Domande:** le
  [Discussions](../../discussions).

---

SEAR is an independent project, not affiliated with, endorsed or sponsored by Fractal Audio Systems. FM3, FM9, FM3-Edit,
FM9-Edit and Axe-Fx are trademarks of Fractal Audio Systems, named here only to identify the hardware SEAR works with. Windows is a
trademark of Microsoft; ASIO is a trademark of Steinberg Media Technologies GmbH.


```
.........................:#@%%@%=...................                   ...-####-..                  
.........................@@@@@@@+:..................                   ..-+*###...                  
.......................:=#*@%@#**=-.................                  ..:*+###:..                   
........................:%%@%@@#::..................                 ..:+####+.                     
.......................:=##@%@##---.................                 ..:**###*....                  
.........................@%@@%%#:-..................                 ..-++###%+...                  
.......................--%%%%%@+::..................                 .:#+#%##%*...                  
.........................-#@@%=.....................               ..:+###%%%#-...                  
.........................:***+......................               ...+*%#%%=.....                  
.........................-%%%*......................                 ..*%##+...                     
.........................-%%%*......................                 ..+*##=...                     
.........................-%%%#......................                 ..+*#*=...                     
.........................-###*......................                 ..+*#*=...                     
.........................=*=+#......................                 ..****=...                     
.........................=%%%#......................                 ..****+...                     
.........................=%%%#......................                 ..****=...                     
.........................=*==#:.....................                 ..*###+...                     
.........................+%%%%:.....................                 ..**##+...                     
.........................+####:.....................                 ..*+**+...                     
.........................+***%:.....................                 ..**##+...                     
.........................*%%%%:.....................                 ..**#*+...                     
.........................*+++#:.....................                 ..****+...                     
.........................*####:.....................                 ..****+...                     
.........................*####:.....................                 ..###**...                     
.........................*#**#:.....................                 ..#*#**...                     
.........................*####:.....................          ...    .:#*#**:..                     
.........................*####:.....................        ...--..  .:**#**:..                     
.........................*+++*-.....................      ...*@@%... .:#*#**:..                     
.....................==..#%%%%-.....................      ..#@@@%..  .:#*#**:..                     
..................:+##%%%*****-.....................      .:@@@@%-.  .-#****:..                     
.................*####%%##+++*+.....................      .=@%%@@%:...-*****+..    .......          
................=###+#%%###**#=*.....:=*............      .-@@%%@@@+-+#******:.    ..+=...          
................+%%%##%%######==+=-=#%%*:...........      ..%@%%%%%@%%##****#-.  ...%%@#..          
................-###**#=---------:*%%%%*:...........      ..+@@%%%%%=-=*+*+***....:#%-#%=.          
.................:##*+*-----:::+-::#%%*+............      ...%@%%%%%+-=*****+@@%@@%-:-%#:.          
..................-%*++-========:::=%#%.............        ..%@%%%%+---------::-:---*%*..          
...................*+++++++*+**:::::#*=.............        ..=@%%%%+----:--:---:-:-+%%:..          
..................-*+==++++*+**::::::*%:............         .-@%%%%=--:----:-=-::-=@%:.            
.................=*+==-=+++++++-:::-:=*#-...........        ..+@%%%#-:---:--:-=:::-+%#.             
...............-#*+====-----:-:=::::::*%+#..........        .:@@%%%:-:--------+-::-=@#..            
..............*#+=====+-----:---:::::::*%%+*........      ..-@@%@@+-::-----::-+-::+:*%%...          
.............##+=====+++++**********+==**#%*#.......      .-@@%%%%-:----------=-::--:+%*..          
............=#+-----=++=+++++*+++***++++**#%+=......    ..-@@%%%%%-::-#%%@%%%=---::-=-+%%:.         
............*#=-----=++++++**+*++++++****+#%#*......   ...*@%%%%%%+---=-----==-:::---::+@#..        
............**=-----+*===-----+=+#*#*+****##%#......   ..:##%%%%%%%%##+**+*+**##+=----::%%#..       
............+*=-----=+=++++++*+++++++*****##%*......   ..:@%+%%#%%%%%#++++=*=-#%%@@%=-:-=%%:.       
............-#*=---=+*+++++++*++***++****+#%*=......   ...%@%+*%%%%%%%%%#####%%%%%%%##+=*@*-        
.............=#*+=++++++++++++*++********###+.......   ...-@@%#+%%%%%%%%%#%%%#%%%%%%###%%@#-.       
..............-#**++++++++++**++***##****%#-........      .:%@%%+#%%%%%%%%%%%%%%%%%%##%%@@*.        
................+##*++++++++*********##%%=:.........       ..+@@%#*%%%%%%%%%%%%%%%%%%%%@@+..        
..................:+###***********####*:............         ..-#@@*%@@@@@@%%@@%@@@@@@@*..          
........................-=+**#**+=:.................          .......:-=+*%**###**=-....            
```
