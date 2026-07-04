# AdLevel Preisrechner

Interaktiver Preisrechner fürs Verkaufsgespräch (Autohaus-Anfragen-System).
Statische Web-App, kein Build nötig. Datei: `index.html`.

## Was der Rechner kann
- Paket wählen (Basis / Wachstum / Premium)
- Zusatzleistungen monatlich & einmalig dazuklicken
- AutoFox (Basic/Premium) getrennt, mit echter Mengen-Staffelung
- Rechnet live: Einmalig (Setup), Monatlich, Rechnung Monat 1, AutoFox extern
- Fertiger Vorlese-Satz für den Kunden

## Lokal öffnen
`index.html` doppelklicken. Läuft im Browser, auch offline.

## Online stellen über Vercel (einmalig einrichten)

Du brauchst zwei kostenlose Accounts: **GitHub** (Code) und **Vercel** (Hosting).

1. Account bei https://github.com anlegen.
2. Account bei https://vercel.com anlegen ("Continue with GitHub" wählen, dann sind beide verbunden).
3. Auf GitHub ein neues, leeres Repository anlegen (Name z.B. `adlevel-preisrechner`, "Private").
4. Diesen Ordner hochladen (zwei Wege):
   - **Einfach (ohne Terminal):** auf der GitHub-Repo-Seite "uploading an existing file" klicken und `index.html` per Drag & Drop reinziehen, dann "Commit".
   - **Oder per Terminal:** siehe unten.
5. In Vercel: "Add New… → Project" → das GitHub-Repo importieren → "Deploy". Fertig, die Seite ist online (z.B. `adlevel-preisrechner.vercel.app`).
6. Optional: eigene Domain verbinden (z.B. `angebot.adlevel.de`) unter Vercel → Settings → Domains.

Ab dann gilt: jede Änderung an `index.html` (die Claude macht) einfach committen/hochladen, Vercel aktualisiert die Seite automatisch.

### Terminal-Variante für Schritt 4 (falls gewünscht)
```
cd "~/Documents/AdLevel-Software/adlevel-preisrechner"
git remote add origin https://github.com/<DEIN-NAME>/adlevel-preisrechner.git
git branch -M main
git push -u origin main
```

## Preise pflegen
Alle Preise stehen oben in `index.html` im `<script>`-Block (Arrays `packages`, `mon`, `once`, `foxTable`). Claude passt sie auf Zuruf an.
