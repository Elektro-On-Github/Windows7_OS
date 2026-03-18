# ElektroOS - Windows 7 Web OS

Un sistema operativo web realista basato su Windows 7 con interfaccia Aero pura.

## Funzionalità Implementate ✨

### 1. **Minimizzazione e Taskbar Funzionale** ✓
- Le finestre si minimizzano con animazione Aero fluida
- I pulsanti delle app compaiono nella taskbar quando vengono aperte
- Clic sul pulsante taskbar alterna tra minimizzare/ripristinare
- Supporto per più finestre aperte simultaneamente

### 2. **Animazioni Aero** ✓
- **Window Minimize**: Animazione di rimpicciolimento verso la taskbar
- **Window Restore**: Animazione di espansione dal pulsante taskbar
- **Window Close**: Effetto di chiusura fluido
- **Aero Glow**: Effetto luminoso sui pulsanti taskbar attivi
- Transizioni smooth su tutti gli elementi interattivi

### 3. **Finestre in Fullscreen** ✓
- Quando massimizzate, le finestre occupano tutto lo schermo meno la taskbar (calc(100vh - 48px))
- I contenuti scrollano correttamente senza overlap con la taskbar
- Bordi arrotondati disabilitati in fullscreen per aspetto pulito

### 4. **Taskbar Realistica Windows 7** ✓
- Gradient background realistico (#c8d3e0 a #7da8d1)
- Pulsanti app con effetti hover e active
- Separatore tra pulsante Start e app pins
- Altezza corretta (48px)
- Effetti ombraatura e bordi realisti

### 5. **Desktop Icons** ✓
- Icone draggable e interattive
- Double-click per aprire le applicazioni
- Effetto hover con scala aumentata
- Icone di sistema: Internet Explorer, Start Menu

### 6. **Framework 7.css Windows 7** ✓
- Framework CSS completo per componenti Windows 7
- Pulsanti, finestre, dialog con stile autentico
- Supporto per temi Aero con trasparenza

## Struttura del Progetto 📁

```
ElektroOS/
├── index.html          # HTML principale con gestione finestre e event handling
├── style.css          # Stili custom, animazioni Aero, taskbar
├── 7.css              # Framework CSS Windows 7 (da khang-nd)
├── w7.jpg             # Wallpaper Windows 7
├── ie.png             # Icona Internet Explorer
├── start.png          # Icona Start
└── README.md          # Questo file
```

## Come Usare 🚀

1. **Serve un server locale** (HTTP):
   ```bash
   python3 -m http.server 8000
   cd /home/elektrowindows/ElektroOS
   ```

2. **Apri nel browser**:
   ```
   http://localhost:8000
   ```

3. **Interazioni**:
   - **Double-click** sulle icone desktop per aprire le app
   - **Trascinare** le finestre dalla title bar
   - **Minimizzare** con il pulsante (-) - la finestra scompare con animazione Aero
   - **Massimizzare** con il pulsante ([]) - la finestra occupa il full screen (meno taskbar)
   - **Chiudere** con il pulsante (X) - la finestra scompare con animazione
   - **Clic sulla taskbar** per minimizzare/ripristinare le app

## Specifiche Tecniche 🔧

- **Lingua**: JavaScript vanilla (nessun framework)
- **CSS**: Pure CSS3 con animazioni e transizioni
- **Browser Support**: Chrome, Firefox, Edge (moderni)
- **Responsive**: Si adatta a diverse risoluzioni
- **Performance**: Ottimizzato con transition e animation CSS

## Animazioni Implementate 🎬

| Animazione | Durata | Effetto |
|-----------|--------|--------|
| window-minimize | 300ms | Rimpicciolimento verso taskbar |
| window-restore | 300ms | Espansione dal taskbar |
| window-close | 300ms | Scomparsa scalata |
| aero-glow | 2s | Effetto luminoso infinito |

## Colori Aero 🎨

- **Taskbar**: Gradient #c8d3e0 → #7da8d1
- **Window Title**: #4580c4 (base Aero blue)
- **Glass Effect**: Blur 4px + Trasparenza
- **Glow Color**: #5dc4f0 (azzurro luminoso)

## Miglioramenti Futuri 🔮

- [ ] Menu Start completamente funzionale
- [ ] Applicazioni aggiuntive (Calculator, Notepad, etc.)
- [ ] Drag-and-drop su desktop
- [ ] Sistema di file virtuale
- [ ] Temi personalizzabili
- [ ] Volume e controlli sistema
- [ ] Clock e data nella taskbar

## Technical Stack 💻

- **HTML5**: Struttura semantica
- **CSS3**: Animazioni, gradients, filters, backdrop-filter
- **JavaScript ES6+**: Event handling, DOM manipulation
- **7.css**: Framework CSS Windows 7 di khang-nd

---

**Creato con ❤️ - ElektroOS v1.0**
