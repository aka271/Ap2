# JavaScript (js)

- [JavaScript (js)](#javascript-js)
  - [1. Was ist JavaScript?](#1-was-ist-javascript)
  - [2. Einbindung von JavaScript in HTML](#2-einbindung-von-javascript-in-html)
    - [2.1 Externes JavaScript (empfohlen)](#21-externes-javascript-empfohlen)
    - [2.2 Internes JavaScript](#22-internes-javascript)
  - [3. Grundlegende Syntax](#3-grundlegende-syntax)
    - [3.1 Kommentare](#31-kommentare)
    - [3.2 Variablen](#32-variablen)
      - [3.2.1 `let`](#321-let)
      - [3.2.2 `const`](#322-const)
  - [4. DOM-Manipulation](#4-dom-manipulation)
    - [4.1 Elemente auswählen](#41-elemente-auswählen)
    - [4.2 Inhalte ändern](#42-inhalte-ändern)
    - [4.3 Stile ändern](#43-stile-ändern)
    - [4.4 Auf Ereignisse reagieren (Events)](#44-auf-ereignisse-reagieren-events)

## 1. Was ist JavaScript?

JavaScript ist eine Skriptsprache, die ursprünglich für die Verwendung in Webbrowsern entwickelt wurde, um Webseiten interaktiv zu gestalten. Während HTML die Struktur und CSS das Aussehen einer Webseite definieren, fügt JavaScript die **Funktionalität** hinzu.

- **Interaktivität:** JavaScript kann auf Benutzeraktionen wie Klicks, Mausbewegungen oder Tastatureingaben reagieren.
- **Dynamische Inhalte:** Es kann HTML-Inhalte und CSS-Stile zur Laufzeit ändern, ohne die Seite neu laden zu müssen.
- **Kommunikation mit Servern:** JavaScript kann Daten im Hintergrund von einem Server laden und senden (AJAX).

Zusammen mit HTML und CSS ist JavaScript eine der drei Kerntechnologien des World Wide Web.

## 2. Einbindung von JavaScript in HTML

JavaScript-Code wird mit dem `<script>`-Tag in ein HTML-Dokument eingebunden. Es gibt zwei primäre Methoden dafür.

### 2.1 Externes JavaScript (empfohlen)

Dies ist die beste Methode, um JavaScript zu organisieren. Der Code wird in einer separaten Datei mit der Endung `.js` gespeichert und dann im HTML-Dokument verknüpft.

Der `<script>`-Tag wird oft am Ende des `<body>`-Elements platziert. Dadurch wird sichergestellt, dass der gesamte HTML-Inhalt (das DOM) geladen und für JavaScript verfügbar ist, bevor das Skript ausgeführt wird.

**HTML (`index.html`):**
```html
<!DOCTYPE html>
<html lang="de">
<head>
    <title>Meine Webseite</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Hallo Welt!</h1>
    <button id="meinButton">Klick mich</button>

    <script src="script.js"></script>
</body>
</html>
```

**JavaScript (`script.js`):**
```javascript
// Code in einer externen Datei
console.log("Skript geladen!");
```

### 2.2 Internes JavaScript

JavaScript-Code kann auch direkt innerhalb eines `<script>`-Tags im HTML-Dokument geschrieben werden. Dies ist nützlich für kleine Skripte, die nur für eine einzige Seite relevant sind.

```html
<!DOCTYPE html>
<html>
<body>
    <h2>Internes JavaScript</h2>
    <p id="demo"></p>

    <script>
        document.getElementById("demo").innerHTML = "Hallo von internem JavaScript!";
    </script>
</body>
</html>
```

## 3. Grundlegende Syntax

### 3.1 Kommentare

Kommentare werden verwendet, um den Code zu erklären und ihn lesbarer zu machen. Sie werden vom JavaScript-Interpreter ignoriert.

```javascript
// Dies ist ein einzeiliger Kommentar

/*
  Dies ist ein
  mehrzeiliger
  Kommentar.
*/
```

### 3.2 Variablen

Variablen sind Container zum Speichern von Datenwerten. In modernem JavaScript werden hauptsächlich `let` und `const` verwendet.

#### 3.2.1 `let`
Deklariert eine Variable, deren Wert neu zugewiesen werden kann.
```javascript
let alter = 25;
alter = 26; // Gültig
```

#### 3.2.2 `const`
Deklariert eine Konstante – eine Variable, deren Wert nach der ersten Zuweisung nicht mehr geändert werden kann.
```javascript
const geburtsjahr = 1998;
// geburtsjahr = 1999; // Dies würde einen Fehler verursachen
```

## 4. DOM-Manipulation
Das Document Object Model (DOM) ist eine Programmierschnittstelle für HTML-Dokumente. Es stellt die Seite als eine Baumstruktur aus Objekten (Elementen) dar. JavaScript kann auf dieses Modell zugreifen, um die Struktur, den Stil und den Inhalt des Dokuments zu ändern.

### 4.1 Elemente auswählen
Bevor du ein Element manipulieren kannst, musst du es zuerst im DOM "finden" und in einer Variable speichern.

- getElementById('id'): Wählt ein Element anhand seiner eindeutigen id aus. Dies ist die schnellste Methode.
- querySelector('selector'): Wählt das erste Element aus, das mit einem bestimmten CSS-Selektor (z.B. .klasse, #id, p) übereinstimmt.
- querySelectorAll('selector'): Wählt alle Elemente aus, die mit einem CSS-Selektor übereinstimmen, und gibt eine NodeList (ähnlich einem Array) zurück.

```js
// Ein Element über seine ID auswählen
const meinButton = document.getElementById('meinButton');

// Den ersten Absatz auf der Seite auswählen
const ersterAbsatz = document.querySelector('p');

// Alle Listenelemente auswählen
const alleListenpunkte = document.querySelectorAll('li');
```

### 4.2 Inhalte ändern
Sobald ein Element ausgewählt wurde, kann seine Inhalt manipuliert werden.

- innerHTML: Liest oder setzt den gesamten HTML-Inhalt (einschließlich Tags) eines Elements. Vorsicht: Kann bei unkontrollierten Benutzereingaben zu Sicherheitslücken führen.
- textContent: Liest oder setzt den reinen Textinhalt eines Elements und seiner Nachkommen, ohne HTML-Tags zu interpretieren. Dies ist sicherer und oft schneller.

```js
const ueberschrift = document.querySelector('h1');

// HTML-Inhalt ändern
ueberschrift.innerHTML = 'Willkommen auf <em>meiner</em> Seite!';

// Nur den Textinhalt ändern
ueberschrift.textContent = 'Willkommen auf meiner Seite!';
```

### 4.3 Stile ändern
CSS-Eigenschaften können eine Element direkt über das style-Objekt ändern. Beachte, dass CSS-Eigenschaften mit Bindestrich (z.B. background-color) in JavaScript in CamelCase (z.B. backgroundColor) umgewandelt werden.

```js
const box = document.getElementById('info-box');

// Hintergrundfarbe ändern
box.style.backgroundColor = 'lightblue';

// Schriftgröße ändern
box.style.fontSize = '18px';

// Einen Rand hinzufügen
box.style.border = '2px solid navy';
```

### 4.4 Auf Ereignisse reagieren (Events)
Die wahre Interaktivität entsteht, wenn dein Code auf Benutzeraktionen reagiert. Dies geschieht über Event Listener.

- addEventListener('event-typ', funktion): Fügt einem Element einen "Zuhörer" hinzu. Dieser wartet auf ein bestimmtes Ereignis (z.B. 'click', 'mouseover') und führt dann eine angegebene Funktion (den "Callback") aus.

Beispiel:
```html
<button id="color-changer">Ändere die Hintergrundfarbe</button>
```
```javascript
const farbWechslerButton = document.getElementById('color-changer');

// Füge einen Event Listener für das 'click'-Ereignis hinzu
farbWechslerButton.addEventListener('click', function() {
  // Dieser Code wird ausgeführt, wenn der Button geklickt wird
  document.body.style.backgroundColor = '#f0f8ff'; // AliceBlue
  console.log('Hintergrundfarbe geändert!');
});
```


<a href="/" class="button-clean">Back to Dashboard</a>