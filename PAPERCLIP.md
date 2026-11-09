# Paperclip per Napule Web App

Guida rapida per usare [Paperclip](https://github.com/paperclipai/paperclip) con il progetto Napule.

Paperclip è un'app open source (licenza MIT) con server Node.js e interfaccia React. Serve a gestire un team di agenti AI (Claude Code, Codex, Cursor, Gemini CLI e altri) come se fosse un'azienda: obiettivi, organigramma, task, budget, approvazioni e attività programmate (routine). Si installa sul proprio computer o server e non richiede un account Paperclip.

Per Napule la useremmo per far lavorare gli agenti sulle due sezioni di `Index.html`:

- **Calendario dei Contenuti**: pianificare i post di ogni settimana.
- **Trend e Ispirazioni**: cercare i trend di TikTok e Instagram su pizza e cucina napoletana e aggiornare le schede.

---

## 1. Requisiti

- **Node.js 24.11 o più recente** (`node -v` per controllare)
- Una chiave API per l'agente che vuoi usare, per esempio `ANTHROPIC_API_KEY` (Claude) oppure `OPENAI_API_KEY` (Codex)
- Git, se vuoi che gli agenti modifichino questo repository

## 2. Installazione

```bash
npx paperclipai@latest onboard --yes
```

Il comando configura l'istanza locale e avvia il server. I dati restano salvati sul tuo computer. Apri l'interfaccia su <http://localhost:3100>. Se la porta è occupata, Paperclip usa la prima porta libera dopo la 3100 e la mostra nel terminale.

### Solo per provarla

Avvia un'istanza di prova temporanea, che ha già un agente CEO e non installa nessun servizio:

```bash
ANTHROPIC_API_KEY=la-tua-chiave npx paperclipai test-drive
```

### Problemi con npm

Se ricevi un errore `E404` per `paperclipai`, forse il tuo npm punta a un registro privato. Forza il registro pubblico:

```bash
npx --registry https://registry.npmjs.org paperclipai@latest onboard --yes
```

## 3. Configurazione per Napule

Nell'interfaccia di Paperclip:

1. **Crea l'azienda** `Napule` e imposta l'obiettivo, per esempio:
   _"Far crescere la pizzeria su TikTok e Instagram con contenuti pubblicati ogni settimana."_
2. **Assumi gli agenti** (organigramma):
   | Ruolo | Compito |
   | --- | --- |
   | CEO | Divide l'obiettivo in progetti e assegna i task |
   | Social Media Manager | Cerca trend e idee (Pizza Flip Challenge, Mozzarella Stretch, ...) |
   | Content Planner | Prepara il calendario editoriale della settimana |
   | Web Developer | Aggiorna `Index.html` con i nuovi trend e il calendario |
3. **Collega il repository** `white94w/white94w` al progetto, così il Web Developer può lavorare su un branch e aprire una pull request da revisionare.
4. **Imposta i budget** per l'azienda e per ogni agente. Paperclip mette in pausa il lavoro quando si raggiunge il limite.
5. **Crea le routine**, cioè i task che partono da soli:
   - ogni lunedì: "Trova 3 trend nuovi su TikTok e Instagram per la pizzeria"
   - ogni venerdì: "Prepara il calendario dei contenuti della settimana prossima"
6. **Attiva le approvazioni** per controllare il lavoro prima che venga pubblicato o unito al branch principale.

## 4. Uso quotidiano

- Controlla i task e i risultati dalla dashboard, anche dal telefono.
- Commenta direttamente nei task per correggere o guidare gli agenti.
- Controlla i costi per agente e per progetto nella sezione budget.

## Link utili

- Repository: <https://github.com/paperclipai/paperclip>
- Documentazione: <https://docs.paperclip.ing>
- Guida rapida (5 minuti): <https://docs.paperclip.ing/guides/getting-started/five-minute-path/>
- Installazione: <https://docs.paperclip.ing/reference/cli/installation/>
- Routine: <https://docs.paperclip.ing/guides/projects-workflow/routines/>
- Budget: <https://docs.paperclip.ing/guides/day-to-day/costs/>
