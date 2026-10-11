# SEAR community

**SEAR** (Sound-Estimation & Auto-Refinement) is a Windows app that helps you get a recorded guitar tone on the FM3:
you play the part over the record, SEAR separates the record's guitar, tries rigs on your FM3, tunes their knobs by
measuring the sound and leaves the result in the working preset for you to save.

This repository is the **public meeting point of the SEAR beta**: bug reports, ideas, questions, release notes and
the testers' guides. **SEAR's source code is not here.**

> 🇮🇹 Più sotto c'è un riassunto in italiano.

## Status

Private beta, Windows only. The test builds go to invited testers. If you'd like to try SEAR, open a
[Discussion](../../discussions).

## Reporting a problem

1. **From SEAR (best):** press **🐞 Report** on the failed job, or in ⚙ Settings → "Something wrong?". SEAR prepares
   the report with the log, your version and settings. Personal paths and your user name are removed, and SEAR
   sends nothing by itself. It also looks here for the same error (its `E-xxxxxxxx` code in the title): if it is
   already reported, add yours as a **comment** instead of a new issue.
2. **By hand:** [open an issue](../../issues/new/choose) with the bug template.
3. **Without a GitHub account:** use "Save the report" in SEAR and send the file by e-mail to the address in the
   beta's read-me.

## Ideas and questions

- An idea or a missing feature: an issue with the **Idea** template.
- "How do I…?" or "Is this normal?": [Discussions](../../discussions).

## What you need

- An FM3 (firmware 13.00), connected by USB, with its USB / ASIO driver (installed with FM3-Edit).
- Windows 10 / 11, 64-bit; about 3 GB of disk space (5 GB with the optional RoFormer separator).
- FM3-Edit **closed** while SEAR talks to the FM3.
- Your own AI chat (Claude or ChatGPT) for the rig research: SEAR prepares the question and checks the answer.

## In italiano

**SEAR** è un'app per Windows che ti aiuta a ottenere sull'FM3 il suono di chitarra di un disco. Suoni la parte sopra
il disco; SEAR separa la chitarra del disco, prova dei rig sul tuo FM3, ne regola le manopole misurando il suono e
lascia il risultato nel preset di lavoro, che salvi tu. Questo repository è il punto d'incontro pubblico della beta:
segnalazioni, idee, domande, note di versione e guide per i tester. **Il codice di SEAR non è qui.**

- **Segnalare un problema:** dentro SEAR premi **🐞 Segnala**. SEAR prepara la segnalazione senza i tuoi percorsi né
  il tuo nome utente, e da solo non invia nulla. Se l'errore è già segnalato, aggiungi la tua come commento. Senza
  account GitHub: "Salva il rapporto" e invialo via email.
- **Idee:** una issue con il modello *Idea*. **Domande:** le [Discussions](../../discussions).

---

SEAR is not affiliated with or endorsed by Fractal Audio Systems. FM3, FM3-Edit and Axe-Fx are trademarks of Fractal
Audio Systems, used here only to identify the hardware.
