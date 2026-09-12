# Turni di Pulizia

Una pagina sola con i turni di pulizia della casa. Ogni coinquilino ha la sua
scheda con quello che gli tocca questa settimana, e tutto ruota ogni lunedì.

È tutto dentro `index.html`: niente da installare, niente da compilare.

## Come funziona la rotazione

Siamo in due squadre da tre, e ogni squadra ha tre faccende sue:

| Squadra | Faccende |
| --- | --- |
| Simone, Vittorio, Aurelio | Bagno · Cucina 1 (lun–mer) · Spazzatura (2 volte/sett.) |
| Antonio, Aran, Ali | Bagno · Cucina 2 (gio–dom) · Corridoio |

Tre persone e tre faccende per squadra, quindi:

- ognuno ha sempre qualcosa da fare, nessuna settimana libera;
- ognuno fa tutte e tre le faccende della sua squadra nel giro di tre settimane;
- nessuno ripete la stessa faccenda due settimane di fila, bagno compreso.

Il ciclo completo dura **3 settimane**, poi ricomincia uguale.

La settimana di partenza è quella **7–13 settembre 2026**, con il piano che era
già in casa: Simone bagno, Vittorio cucina 1, Aurelio spazzatura, Antonio
bagno, Aran cucina 2, Ali corridoio. Dal 14 settembre in poi si sposta tutto di
un posto a settimana.

## Come cambiare nomi o faccende

Apri `index.html` e scendi fino al blocco **DA MODIFICARE QUI**, verso il fondo.

```js
const SQUADRE = [
  {
    persone: ["Simone", "Vittorio", "Aurelio"],
    faccende: [
      { emoji: "🚽", name: "Bagno",      detail: "WC, doccia, lavandino, specchio" },
      { emoji: "🍳", name: "Cucina 1",   detail: "Da lunedì a mercoledì" },
      { emoji: "🗑️", name: "Spazzatura", detail: "2 volte a settimana" }
    ]
  },
  ...
];

const LUNEDI_DI_PARTENZA = [2026, 9, 7];
```

- **persone** — chi è in squadra, e anche l'ordine delle schede nella pagina.
- **faccende** — cosa gira dentro quella squadra. `emoji` e `detail` si possono
  lasciare vuoti con `""`.
- **Chi fa cosa nella prima settimana** lo decidono i due ordini messi insieme:
  la prima persona fa la prima faccenda, la seconda la seconda, la terza la
  terza. Per cambiare il punto di partenza basta spostare un nome nella lista.
- **LUNEDI_DI_PARTENZA** — `[anno, mese, giorno]` del lunedì da cui parte il
  conto. Non serve toccarlo.

Le squadre non devono per forza essere da tre: se aggiungi o togli gente, o
cambi il numero di faccende, la rotazione si riadatta da sola. Se in una squadra
ci sono più persone che faccende, chi avanza vede **Settimana libera**.

## Aggiornare il sito

Il sito sta su GitHub Pages. Per cambiare qualcosa: apri `index.html` su GitHub,
clicca la matita, modifica il blocco qui sopra e fai **Commit changes**. Dopo un
minuto circa il sito online è aggiornato (sui telefoni può volerci qualche
minuto in più, per via della cache).

I turni sono calcolati dalla data, quindi non c'è niente da salvare: tutti
aprono lo stesso link e vedono la stessa settimana.
