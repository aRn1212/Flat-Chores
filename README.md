# Turni di Pulizia

Una pagina sola con i turni di pulizia della casa. Ogni coinquilino ha la sua
scheda con quello che gli tocca questa settimana, e tutto ruota ogni lunedì.

È tutto dentro `index.html`: niente da installare, niente da compilare.

## Come funziona la rotazione

Siamo in sei e i lavori sono cinque, perché i bagni sono due:

- **I due bagni** girano ognuno dentro la propria squadra di tre:
  - bagno 1 → Aran, Ali, Antonio
  - bagno 2 → Aurelio, Salvatore, Simone
  - Con tre persone per squadra, il bagno torna una settimana ogni tre: nessuno
    lo fa due settimane di fila.
- **Cucina, spazzatura e corridoio** girano tra i quattro che quella settimana
  non hanno il bagno.
- Chi resta senza niente ha la **settimana libera**.

Il ciclo completo dura **12 settimane**. In quelle 12 settimane ognuno fa
esattamente: 4 volte il bagno, 2 la cucina, 2 la spazzatura, 2 il corridoio e
2 settimane libere. Uguale per tutti e sei.

## Come cambiare nomi o faccende

Apri `index.html` e scendi fino al blocco **DA MODIFICARE QUI**, verso il fondo.

```js
const BAGNI = [
  {
    emoji: "🚿",
    name: "Bagno",
    detail: "WC, doccia, lavandino, specchio",
    squadra: ["Aran", "Ali", "Antonio"]
  },
  ...
];

const ALTRE_FACCENDE = [
  { emoji: "🍳", name: "Cucina", detail: "Piano cottura, lavello, superfici" },
  ...
];

const SETTIMANA_LIBERA = { emoji: "😎", text: "Settimana libera" };

const LUNEDI_DI_PARTENZA = [2026, 1, 5];
```

- **BAGNI** — un blocco per bagno. `squadra` è la lista di chi lo fa a turno;
  i nomi lì dentro sono anche l'ordine delle schede nella pagina. Chi è nella
  squadra di un bagno non finisce mai nell'altro.
- **ALTRE_FACCENDE** — una riga per faccenda. `emoji` e `detail` si possono
  lasciare vuoti con `""`.
- **SETTIMANA_LIBERA** — cosa vede chi quella settimana non ha niente.
- **LUNEDI_DI_PARTENZA** — `[anno, mese, giorno]` del lunedì da cui parte il
  conto. Cambialo per spostare chi comincia con cosa.

Se aggiungi o togli gente, la rotazione si riadatta da sola: basta che ogni
persona stia nella `squadra` di un bagno.

## Aggiornare il sito

Il sito sta su GitHub Pages. Per cambiare qualcosa: apri `index.html` su GitHub,
clicca la matita, modifica il blocco qui sopra e fai **Commit changes**. Dopo un
minuto circa il sito online è aggiornato.

I turni sono calcolati dalla data, quindi non c'è niente da salvare: tutti
aprono lo stesso link e vedono la stessa settimana.
