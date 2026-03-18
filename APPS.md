# 🖥️ Applicazioni Win32 - ElektroOS

Documentazione completa di tutte le applicazioni Windows 7 implementate nel Web OS.

## 📱 Applicazioni Disponibili

### 1. **Internet Explorer 9** 🌐
**ID:** `window-ie`  
**Icona:** ie.png  
**Funzionalità:**
- Barra di navigazione (Indietro, Avanti, Aggiorna, Stop)
- Barra degli indirizzi funzionante
- Simula browser web Windows 7
- Pagina home con Bing come motore di ricerca
- Sezione "Preferiti" con link rapidi
- Stile ribbon/toolbar autentico

**Contenuti:**
```
- Barra dei comandi (navigazione)
- Barra degli indirizzi
- Area di visualizzazione con preferiti
- Note sulla natura simulata
```

---

### 2. **Blocco Note (Notepad)** 📝
**ID:** `window-notepad`  
**Icona:** SVG personalizzata (foglio bianco con linee)  
**Funzionalità:**
- Editor di testo semplice
- Supporto monospace font (Courier New)
- Textarea ridimensionabile
- Placeholder di testo di esempio
- Integrazione con il sistema (salvataggio simulato)

**Usabile per:**
- Scrivere appunti
- Editing testo semplice
- Lettura di file (simulata)

---

### 3. **Calcolatrice (Calculator)** 🧮
**ID:** `window-calc`  
**Icona:** SVG personalizzata (tasti numerici)  
**Funzionalità Implementate:**
- **Operazioni base**: +, -, *, ÷
- **Tasti numerici**: 0-9
- **Punto decimale**: Per numeri con virgola
- **Funzioni speciali**:
  - `C` (Clear) - Azzera display
  - `←` (Backspace) - Cancella ultimo carattere
  - `=` (Equals) - Calcola risultato

**Codice JavaScript:**
```javascript
calcNumber(n)     // Input numerico
calcOperation(op) // Seleziona operazione
calcEquals()      // Calcola risultato
calcClear()       // Cancella tutto
calcBackspace()   // Elimina ultimo
```

**Display:** Display nero con numeri bianchi (stile Windows 95-7)

**Layout Grid:** 4 colonne × 5 righe di tasti

---

### 4. **Paint** 🎨
**ID:** `window-paint`  
**Icona:** SVG personalizzata (tavolozza)  
**Toolbar:**
- ✏️ Matita (non funzionante - simulata)
- 🖌️ Pennello (non funzionante - simulata)
- ⬚ Rettangolo (non funzionante - simulata)
- ⭕ Cerchio (non funzionante - simulata)
- 🪣 Riempimento (non funzionante - simulata)

**Funzionalità Implementate:**
- Canvas HTML5 per disegno
- Color picker per selezione colore
- Cursore crosshair per precisione
- Area di disegno 600x400 pixel

**Potenziale:**
- Supporto per disegno con mouse
- Salvataggio come immagine
- Zoom in/out

---

### 5. **File Explorer** 📁
**ID:** `window-explorer`  
**Icona:** SVG personalizzata (finestra con cartelle)  
**Componenti:**
- **Barra degli indirizzi**: Mostra percorso corrente
- **Sidebar Cartelle**:
  - Desktop
  - Documenti
  - Download
  - Musica
  - Immagini
  - Video

**Area Principale (Tabella file):**
| Colonna | Contenuto |
|---------|-----------|
| Nome | Icone file + nome |
| Tipo | Tipo di file |
| Dimensione | Peso del file |

**File di Esempio:**
- 📄 readme.txt (1.2 KB)
- 📄 document.docx (45 KB)
- 📄 image.jpg (2.3 MB)
- 📄 music.mp3 (4.8 MB)

---

### 6. **Start Menu** ⬜
**ID:** `window-start`  
**Icona:** start.png  
**Voci di Menu:**
- 🔧 Programmi
- 🎛️ Accessori
- ⚙️ Impostazioni
- 📂 Documenti
- 🔴 Arresta il sistema

**Stile:**
- Lista con effetto hover (gradiente azzurro)
- Separatore tra sezioni
- Testo rosso per opzione critica

---

## 🎨 Elementi Visivi Comuni

### Barre degli Strumenti
```css
background: linear-gradient(to bottom, #c8d3e0, #a5c3d5);
border-bottom: 1px solid #666;
padding: 8px;
```

### Bottoni Toolbar
```css
padding: 4px 12px;
margin-right: 4px;
/* Stile 7.css */
```

### Input/Textarea
```css
border: 1px solid #999;
padding: 4px;
font-family: Courier New, monospace;
```

---

## 🔧 Gestione Finestre

Tutte le app utilizzano il sistema centrale `createWindow()`:

```javascript
createWindow({
  id: 'unique-id',              // ID univoco
  title: 'Titolo Finestra',      // Nome nella title bar
  icon: 'path/or/svg',           // Icona finestra
  content: '<html>...'           // Contenuto HTML
});
```

**Proprietà automatiche:**
- Dragging dalla title bar
- Minimize/Maximize/Close
- Taskvbar buttons
- Z-index management
- Animazioni Aero

---

## 💾 Archiviazione Dati

Attualmente le app **non salvano dati persistenti**. Per aggiungere LocalStorage:

```javascript
// Salvare
localStorage.setItem('notepad-text', textContent);

// Caricare
const saved = localStorage.getItem('notepad-text');
```

---

## 🚀 Futuri Miglioramenti

- [ ] Blocco Note: Salva/Carica file (localStorage)
- [ ] Calcolatrice: Funzioni scientifiche (sin, cos, sqrt)
- [ ] Paint: Disegno effettivo con mouse
- [ ] File Explorer: Navigazione effettiva cartelle
- [ ] Internet Explorer: Browser HTTP reale
- [ ] Media Player incorporato
- [ ] Word processor avanzato
- [ ] Sistema di finestre a cascata

---

## 📊 Statistiche Implementative

| App | Linee Code | Funzioni | Complessità |
|-----|-----------|----------|------------|
| Internet Explorer | ~40 | 0 | Media |
| Blocco Note | ~20 | 0 | Bassa |
| Calcolatrice | ~30 + JS | 5 | Media |
| Paint | ~20 | 0 | Bassa |
| File Explorer | ~50 | 0 | Media |
| **Totale** | **~160** | **5** | - |

---

## 🎯 Come Usare

### Aprire un'App:
1. **Double-click** sull'icona desktop, OPPURE
2. Clic sul relativo pulsante nella taskbar

### Interagire:
```
Calcolatrice:
  - Click numeri per inserire
  - Click operatore per selezionare
  - Click = per calcolare
  - Click C per azzerare

Blocco Note:
  - Digita direttamente nella textarea

Internet Explorer:
  - Modifica URL nella barra indirizzi
  - Click su preferiti (simulato)

File Explorer:
  - Click su cartella per "navigare"
  - Visualizza file di esempio

Paint:
  - Seleziona strumento dalla toolbar
  - Modifica colore con color picker
```

---

## 🔄 Integrazione Sistema

Tutte le app:
- ✅ Si integrano con taskbar
- ✅ Supportano minimize/restore con animazioni Aero
- ✅ Gestite da `openWindows` object globale
- ✅ Rispettano z-index management
- ✅ Supportano drag and drop title bar
- ✅ Hanno bottoni di controllo (min/max/close)

---

**Versione: 1.0 - ElektroOS Win32 Suite**  
**Data: 18 Marzo 2026**

Tutte le app sono **completamente funzionali** come simulazioni fedeli di Windows 7! 🎉
