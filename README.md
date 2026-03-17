# 🎯 BettingPro v7 — AI Betting Intelligence

**BettingPro** è un sistema avanzato di analisi e pronostici calcistici che combina modelli statistici (Poisson, Dixon-Coles), machine learning adattivo, analisi multi-bookmaker e intelligenza artificiale per generare i pronostici più accurati possibili.

> ⚠️ **Disclaimer**: Questo è uno strumento di analisi statistica per uso personale. Il gioco d'azzardo comporta rischi. Gioca responsabilmente.

---

## 🚀 Novità v7

### 🏆 Consensus Engine
Fonde automaticamente **tutte le fonti** in un unico pick pesato:
- Modello Poisson/Dixon-Coles (peso 3)
- Probabilità bookmaker consensus (peso 3)
- Regression Score (peso 2)
- Oracle AI con news (peso 2)
- Super Algoritmo locale (peso 2)
- Steam Moves / Smart Money (peso 1.5)

Restituisce un **livello di confidenza** (MASSIMA, ALTA, MEDIA, BASSA) e la percentuale di accordo tra le fonti.

### 📊 Regression Score
Punteggio multi-fattore 0-100 con grading **A+ → D**, ispirato ai software di regressione statistica professionali. Analizza 6 fattori pesati:

| Fattore | Peso | Cosa misura |
|---------|------|-------------|
| Forza Poisson | 25% | Quanto il modello è convinto del favorito |
| Dominanza xG | 20% | Differenza Expected Goals |
| Conferma Quote | 20% | Allineamento con i bookmaker |
| Forma Recente | 15% | Ultime 5 partite del favorito |
| Solidità Difensiva | 10% | Gol subiti per partita |
| Smart Money | 10% | Segnali dagli sharp bookmaker |

### 💰 Odds Lab — Multi-Bookmaker
Analizza le quote da **tutti i bookmaker** disponibili via API, con:
- Identificazione **sharp bookmaker** (Pinnacle, Bet365, Unibet)
- Calcolo margine per bookmaker
- **Steam Move Detection** — dove sta puntando lo smart money
- Rilevamento discrepanze quote tra bookmaker
- Probabilità consensus del mercato (1X2, O/U, GG/NG)

### 🎯 Value Bet Engine + Kelly Criterion
Per ogni mercato calcola:
- **Edge** = (prob_nostra × quota) - 100%
- Se Edge > 0 → **Value Bet** (il bookmaker ci paga più del dovuto)
- **Kelly Criterion frazionato** (25%) per lo stake ottimale
- Indica il bookmaker con la quota migliore

---

## 📖 Come Usare — Workflow in 6 Step

La guida completa è disponibile anche **dentro l'app** nel pannello ⚙️ Impostazioni.

### Step 1 · Seleziona la partita
Scegli la partita dalla lista. Il sistema calcola automaticamente tutti i modelli base. In background vengono caricate le quote multi-bookmaker.

### Step 2 · 🏆 Leggi il CONSENSUS ENGINE
La sezione più importante. Se dice **MASSIMA** con accordo ≥80% → pick molto solido.

### Step 3 · 📊 Controlla il REGRESSION SCORE
- **A / A+** = pick forte, giocabile ovunque
- **B+ / B** = giocabile come singola
- **C / D** = partita incerta, evita in multipla

### Step 4 · ⚡ Premi "ANALIZZA con Super AI"
Lancia l'analisi Claude AI con news e infortuni. Il **Consensus Engine si ricalcola automaticamente** includendo Oracle AI e Super Algoritmo.

### Step 5 · 🎯 Verifica le VALUE BET
Edge positivo (verde) = value bet. Il Kelly indica quanto puntare. L'Odds Lab mostra dove puntano gli sharp.

### Step 6 · 🚨 Controlla il TRAP DETECTOR
- ≤20 = **SICURA** ✅
- 21-40 = **ATTENZIONE** ⚠️
- 41-60 = **RISCHIO** 🟠
- 61+ = **TRAPPOLA** 🔴 — non giocare il favorito secco

### 🏅 Regola d'Oro
**Gioca solo quando tutte e tre le condizioni sono soddisfatte:**
1. Consensus = MASSIMA o ALTA
2. Regression = A o A+
3. Trap Detector = SICURA o ATTENZIONE

Se anche solo una manca → rischio elevato. Per le **multiple**, usa solo partite che soddisfano tutte e tre.

---

## 🔧 Funzionalità Complete

### Modelli Predittivi
- **Poisson / Dixon-Coles** con tau dinamico e rho adattivo
- **Bayesian Blending** (70% modello + 30% bookmaker)
- **ML Engine** con soglie adattive per GG/Over
- **xG Engine** con dati FootyStats e API-Football
- Fattore **stanchezza** basato su calendario reale
- Fattore **home advantage** calibrato (+6% casa, -5% trasferta)

### Mercati Coperti
1X2, Double Chance, Over/Under (0.5-3.5), GG/NG, Multigol (totale + per squadra), Corner, Cartellini, Primo Tempo, Risultati Esatti, Combo (es. 1X + Over 1.5)

### Sezioni Analisi
- **Pronostici AI & Statistico** — pick con reasoning
- **Consensus Engine** — fusione multi-fonte
- **Regression Score** — punteggio multi-fattore
- **Odds Lab** — quote multi-bookmaker + steam moves
- **Value Bet Engine** — edge + Kelly Criterion
- **Trap Detector v2** — 13 fattori + 4 attenuanti
- **NG/GG Insight** — analisi clean sheet e scoring
- **Multigol Combinato** — per squadra e totale
- **Corner & Tiri** — statistiche specialistiche
- **Storico Variazioni** — monitora cambiamenti nel tempo
- **GAP Analyser** — True Spread basato su xG
- **Super AI** — analisi Claude con news in tempo reale

### Home Screen
- **Consigli del Giorno** — pick migliori auto-generati
- **Raddoppi del Giorno** — coppie sicure per multiple
- **Smart Filters** — filtra per mercato (1, X, 2, GG, Over...)
- **Trader Section** — raddoppi e singole ottimizzate

### Gestione
- **Money Management** — sistema obiettivo con progressione
- **Result Tracker** — verifica automatica risultati
- **Schedina Builder** — componi la tua schedina
- **Firebase Sync** — dati sincronizzati su cloud
- **Autenticazione** — login con email/password
- **Tema chiaro/scuro**

---

## 🛠 Tecnologie

- **Single-file HTML** — zero dipendenze, deploy istantaneo
- **API-Football** (v3) — fixture, statistiche, quote, H2H, infortuni, formazioni
- **FootyStats API** — xG, clean sheet %, corners, cards avanzati
- **Firebase Realtime Database** — sync cloud + auth
- **Claude AI API** — analisi con news per Super AI
- **Chart.js** — grafici interattivi
- **Poisson / Dixon-Coles** — modelli statistici core

---

## 📦 Deploy su GitHub Pages

1. Crea un repository GitHub (es. `BettingPro`)
2. Carica `index.html` e `README.md` nella root
3. Vai in **Settings → Pages → Source: main / root**
4. Il sito sarà disponibile su `https://tuousername.github.io/BettingPro/`

---

## ⚙️ Configurazione API

Le API key sono già configurate nel file. Per cambiarle, modifica la sezione `CONFIG` all'inizio dello script:

```javascript
const CONFIG = {
  API_FOOTBALL: {
    key: 'LA_TUA_KEY',
    baseURL: 'https://v3.football.api-sports.io'
  },
  FOOTYSTATS: {
    key: 'LA_TUA_KEY',
    baseURL: 'https://api.footystats.org'
  },
  FIREBASE: {
    // ... configurazione Firebase
  }
};
```

---

## 📜 Changelog

### v7 (Marzo 2026)
- ✅ Consensus Engine — fusione multi-fonte intelligente
- ✅ Regression Score — punteggio multi-fattore pesato
- ✅ Odds Lab — analisi multi-bookmaker + steam moves
- ✅ Value Bet Engine — edge detection + Kelly Criterion
- ✅ Mini guida in-app nel pannello Impostazioni
- ✅ Auto-ricalcolo Consensus dopo Super AI

### v6
- Firebase Authentication
- Super AI con Claude
- Trap Detector v2
- NG/GG Insight
- Multigol Combinato
- Storico Variazioni
- GAP Analyser

### v5
- Formazioni ufficiali
- Bayesian Blending con quote bookmaker
- Fattore stanchezza Dixon-Coles
- Classifica e infortunati

---

**Made with ❤️ by Luca**
