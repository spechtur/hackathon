# VibeCoding — Hackathon

Eine einzelne HTML-Datei, die eine Klasse in neun Schritten durch einen
KI-Coding-Hackathon führt: von der Idee zur eigenen Web-App mit eigener Adresse.

**→ [Zur Seite](https://spechtur.github.io/hackathon/)**

Keine Installation, kein Server, keine Konten, keine externen Abhängigkeiten.
Herunterladen, im Browser öffnen, loslegen.

---

## Zwei Ansichten

| | |
|---|---|
| **Lehrperson** — die Startseite | Alle Schritte, frei navigierbar. Timer, Gruppengenerator, Werkzeugliste, Notizen. Dazu pro Schritt Moderationshinweise, die nur hier sichtbar sind. |
| **Klasse** — `#sus-1` bis `#sus-9` | Nur der aktuelle Schritt, nur lesbar. Oben ein Countdown-Balken, unten die Werkzeug-Links zum Antippen. |

Die Klasse kommt über den QR-Code im Reiter **Teilen** hinein. Der Code enthält
drei Dinge gleichzeitig: den aktuellen Schritt, den laufenden Countdown und die
Werkzeuge, die du eingestellt hast.

### Wie der Countdown auf die Geräte kommt

Es gibt keinen Server — und trotzdem läuft der Balken auf allen Tablets gleich.
Der Trick: die Uhren der Geräte sind ohnehin synchron. Übertragen wird deshalb
nur **eine Zahl**, nämlich wann Schluss ist. Balken, Halbzeit-Hinweis und
Zwei-Minuten-Warnung rechnet danach jedes Gerät für sich aus.

Wichtig: Der QR-Code enthält die Restzeit nur, solange der Timer **läuft**.
Also erst starten, dann scannen lassen.

---

## Anpassen

Zwei Wege, je nachdem wie dauerhaft es sein soll:

**Während der Lektion** — Reiter **⚙️ Einstellen**. Werkzeuge hinzufügen oder
ändern, Veröffentlichungsweg umstellen, Klassenkonto eintragen. Wirkt sofort und
reist über den QR-Code zur Klasse mit.

**Dauerhaft** — ganz oben in `index.html` steht ein Block `CONFIG`. Dort sind alle
Texte, Schritte, Werkzeuge und Leitfragen gebündelt. Text zwischen den
Anführungszeichen ersetzen, speichern, neu laden. Kommas und Klammern stehen
lassen. Der Knopf *„Als Textblock kopieren“* im Einstell-Reiter erzeugt den
passenden Abschnitt zum Einsetzen.

### Veröffentlichungsweg

Die Einstellung `veroeffentlichungsweg` bestimmt, wie die Klasse ihre Apps online
stellt — und steuert zugleich, **welche Werkzeuge überhaupt angezeigt werden**.
Das verhindert den häufigsten Fehler: mit einem Werkzeug bauen, das ein ganzes
Projekt erzeugt, und am Schluss eine einzelne Datei hochladen wollen.

| Wert | Bedeutung |
|---|---|
| `klassenkonto` | Ein GitHub-Konto der Klasse, pro Gruppe ein Ordner. Nur Werkzeuge, die eine einzelne Datei liefern. |
| `toolLink` | Jedes Team teilt den Link seines eigenen Werkzeugs. Auch Projekt-Werkzeuge sichtbar. |
| `schulcloud` | Datei in die Schul-Cloud, keine öffentliche Seite. |
| `aus` | Es wird nicht veröffentlicht. |

---

## Vor dem Einsatz prüfen

> **Die Werkzeugliste veraltet schnell.** Altersgrenzen, Anmeldepflichten und
> Gratis-Kontingente ändern sich laufend. Probiere jedes Werkzeug kurz selbst aus,
> bevor du damit vor die Klasse trittst — besonders, welcher KI-Zugang bei
> Minderjährigen für dich in Frage kommt.

Die Seite enthält an drei Stellen einen **Sicherheits-Check**, der die Klasse
auffordert, sich bei einer erwachsenen Person zu melden: beim Werkzeug-Zugang,
beim Bauen und verbindlich vor dem Veröffentlichen.

---

## Tastatur (Lehrpersonen-Ansicht)

`←` `→` Schritt · `T` Timer · `W` Werkzeuge · `F` Vollbild · `Esc` schliessen

---

## Technisches

Eine Datei, rund 110 KB, keine Abhängigkeiten. Der QR-Code wird offline erzeugt
(vollständiger Encoder nach ISO/IEC 18004, Byte-Modus, Version 1–10). Timer,
Teams und Notizen liegen nur im Browser der Lehrperson; es werden keine Daten
übertragen oder gespeichert.

Das Design folgt dem Gestaltungssystem von **ClassScreen**.

## Entstehung

Entwickelt für das CAS *Bildung im Digitalen Wandel*, Modul KI — VibeCoding.
Die Weiterbildungs-Teilnehmenden durchlaufen den Hackathon selbst in der Rolle
der Schüler:innen und nehmen die Datei anschliessend für ihre eigene Klasse mit.
