# SEAR

**Sound-Estimation & Auto-Refinement** — get a recorded guitar tone on your FM3.

```
        __     ♫
       |oo|           ╔════════════════════════════════════════════╗
       |oo|  ♪        ║   S . E . A . R .                          ║
       |oo|           ║   listen · measure · tweak · repeat        ║
        ||            ║   ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁▁▂▃▅▇▅▃▂▁             ║
        ||            ╚══════════════════════╤═════════════════════╝
        ||                                   |  USB
       _||_           .----------------------+--------------------------.
      /    \          |  FM3                   [ Deluxe Tweed Jumped ]  |
     |  ::  |         |  PRESET 042 · SCENE 2           TUNER  E  >|<   |
      \ -- /  ~~~=[>  |   (o)    (o)    (o)    (o)    (o)               |
     /  ==  \  JACK   '-------------------------------------------------'
    |   ()   |
     \______/
```

You play the part over the record; SEAR separates the record's guitar, tries candidate rigs on **your own FM3**, tunes
their knobs by measuring the real sound against the record, and leaves the result in the working preset for you to save.
It can also measure a rig *you* built and tell you how close it is.

This repository is SEAR's **public home**: downloads (Releases), release notes, bug reports, ideas and questions.
SEAR's source code is not here. SEAR is free.

> 🇮🇹 Più sotto c'è un riassunto in italiano.

> **Status: beta, Windows only, FM3 firmware 13.00 only.** SEAR reads the firmware and refuses a version it has not been
> validated on. It is tested on one FM3 so far: please report what goes wrong.

## What you need

- **Windows 10 or 11, 64-bit**, about 3 GB of free disk space (5 GB with the optional RoFormer separator).
- **An FM3 with firmware 13.00**, connected by USB, with its USB audio driver — it is installed with **FM3-Edit** (free,
  from the maker's site).
- **Open FM3-Edit once with the FM3 connected before SEAR's first start**, and let it read the FM3. SEAR reads the FM3's
  parameter tables from FM3-Edit's data on your PC (they are not included in SEAR). After an FM3 firmware update, do it
  again.
- **FM3-Edit closed** while SEAR talks to the FM3.
- **Your own AI chat** (Claude or ChatGPT, with web search) for the rig research: SEAR writes the question, you paste it,
  and SEAR checks the answer.

## Install

1. Download the newest `SEAR-<version>.zip` from [Releases](../../releases) (a release appears there when it is out).
2. Extract the **whole folder** anywhere you like, for example in Documents. The path must not contain `%` or `^`.
3. Double-click **SEAR.exe** (the squirrel). A window opens — keep it open while you use SEAR — and SEAR opens in your
   browser.

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
(here, on GitHub), to look for an already-reported error, and — only if you turn them on — for band / album pictures
(Wikipedia, MusicBrainz) or to install the optional RoFormer separator. No telemetry, no account. Details: the `EULA.md`
in SEAR's folder.

## Support SEAR

SEAR is free. If it helps your tone, a voluntary donation helps keep it growing:
[paypal.me/Muplex](https://paypal.me/Muplex). Nothing in the app changes whether you donate or not.

## In italiano

**SEAR** è un'app gratuita per Windows che ti aiuta a ottenere sull'FM3 il suono di chitarra di un disco: suoni la parte
sopra il disco, SEAR separa la chitarra del disco, prova dei rig sul **tuo** FM3, ne regola le manopole misurando il suono
e lascia il risultato nel preset di lavoro, che salvi tu. Questo repository è la casa pubblica di SEAR (download nelle
Releases, note di versione, segnalazioni, idee, domande); il codice non è qui.

- **Serve:** Windows 10/11 a 64 bit, un FM3 con firmware 13.00 collegato via USB, **FM3-Edit aperto una volta con l'FM3
  collegato prima del primo avvio** (SEAR legge da lì le tabelle dei parametri dell'FM3), FM3-Edit chiuso mentre SEAR
  lavora, una tua chat AI (Claude o ChatGPT) per la ricerca del rig.
- **Installazione:** scarica lo zip dalle [Releases](../../releases), estrai tutta la cartella, doppio clic su
  **SEAR.exe**. Se Windows dice *"PC protetto"*: **Ulteriori informazioni** → **Esegui comunque** (SEAR non è ancora
  firmato con un certificato a pagamento). Per disinstallare basta cancellare la cartella.
- **Aggiornamenti:** automatici; SEAR scarica la versione nuova, ne controlla la firma e ti propone **"Riavvia per
  aggiornare"**. Canzoni, run e impostazioni restano.
- **Problemi:** **🐞 Segnala** dentro SEAR; senza account GitHub "Salva il rapporto" e invia il file a
  **sear.beta.reports@gmail.com**. **Idee:** una issue con il modulo *Idea*. **Domande:** le
  [Discussions](../../discussions).

---

SEAR is an independent project, not affiliated with, endorsed or sponsored by Fractal Audio Systems. FM3, FM3-Edit and
Axe-Fx are trademarks of Fractal Audio Systems, named here only to identify the hardware SEAR works with. Windows is a
trademark of Microsoft; ASIO is a trademark of Steinberg Media Technologies GmbH.
