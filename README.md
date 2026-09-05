# digitalvalut.github.io

La radice del sito. Esiste per una ragione sola, e conviene dirla subito.

## `.well-known/assetlinks.json`

E' un **biglietto di autorizzazione** che Android va a leggere qui. Dice, in
sostanza: *«io, questo sito, autorizzo l'applicazione Android che ha questa
esatta impronta di firma ad aprire i miei link»*.

Senza questo file, un invito di **DigitalValut Logos** toccato dentro WhatsApp o
in una email si apre nel **browser** invece che nell'app — e l'app e la pagina
web hanno identita' e indirizzi **separati**, quindi l'invito arriva a un "te"
diverso da quello che le persone hanno in rubrica. Il difetto e' silenzioso da
entrambe le parti: nessuno dei due ha modo di accorgersene.

L'impronta nel file (`42:3E:30:94:…`) e' quella della chiave con cui sono
firmati i pacchetti pubblicati, ed e' verificabile su qualsiasi APK con:

```
apksigner verify --print-certs DigitalValut-Logos.apk
```

Se un giorno F-Droid firmasse l'app con una chiave propria, la sua impronta va
**aggiunta** all'elenco, non sostituita: altrimenti chi ha installato da GitHub
smette di funzionare.

## `.nojekyll`

Necessario, non decorativo: senza, GitHub Pages scarta ogni cartella che
inizia con un punto — compresa `.well-known/`, cioe' l'unica cosa che questo
repository serve a pubblicare.

## Il progetto

Il codice di Logos non sta qui. Sta in
**[logos-protocol](https://github.com/digitalvalut/logos-protocol)**, licenza
Apache 2.0.

---

© 2026 **Associazione di Promozione Sociale DigitalValut** (Ente del Terzo Settore)
