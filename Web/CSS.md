# Cascading Style Sheets (CSS)

- [Cascading Style Sheets (CSS)](#cascading-style-sheets-css)
  - [1. Was ist CSS?](#1-was-ist-css)
  - [2. CSS-Syntax](#2-css-syntax)
  - [3. Einbindung von CSS in HTML](#3-einbindung-von-css-in-html)
    - [3.1 Externe Stylesheets (empfohlen)](#31-externe-stylesheets-empfohlen)
    - [3.2 Interne Stylesheets](#32-interne-stylesheets)
    - [3.3 Inline-Styles](#33-inline-styles)
  - [4. CSS-Selektoren](#4-css-selektoren)
    - [4.1 Element-Selektor](#41-element-selektor)
    - [4.2 Klassen-Selektor](#42-klassen-selektor)
    - [4.3 ID-Selektor](#43-id-selektor)

## 1. Was ist CSS?

CSS steht für **Cascading Style Sheets**. Es ist eine Stylesheet-Sprache, die verwendet wird, um das Aussehen und die Formatierung von Dokumenten zu beschreiben, die in einer Auszeichnungssprache wie HTML geschrieben sind.

- **Trennung von Inhalt und Design:** CSS ermöglicht es, den Inhalt (HTML) von der Darstellung (Styling) zu trennen. Dies macht den Code übersichtlicher und einfacher zu warten.
- **Wiederverwendbarkeit:** Ein einziges Stylesheet kann für mehrere Webseiten verwendet werden, um ein einheitliches Erscheinungsbild zu gewährleisten.
- **Kontrolle über das Layout:** CSS bietet leistungsstarke Werkzeuge zur Steuerung des Layouts, der Farben, Schriftarten und vieler anderer visueller Aspekte einer Webseite.

## 2. CSS-Syntax

Eine CSS-Regel besteht aus einem **Selektor** und einem **Deklarationsblock**.

- **Selektor:** Zielt auf das HTML-Element, das Sie formatieren möchten (z.B. `h1`, `.menu`, `#header`).
- **Deklarationsblock:** Enthält eine oder mehrere Deklarationen, die durch Semikolons getrennt sind. Jede Deklaration besteht aus einem Eigenschaftsnamen und einem Wert (z.B. `color: blue;`).

```css
/* Ein Kommentar in CSS */
selektor {
  eigenschaft: wert;
  andere-eigenschaft: anderer-wert;
}
```

**Beispiel:**
```css
p {
  color: red;
  font-size: 16px;
}
```
Diese Regel wählt alle `<p>`-Elemente auf der Seite aus und setzt ihre Textfarbe auf Rot und ihre Schriftgröße auf 16 Pixel.

## 3. Einbindung von CSS in HTML

Es gibt drei Möglichkeiten, CSS in ein HTML-Dokument einzubinden.

### 3.1 Externe Stylesheets (empfohlen)

Dies ist die gebräuchlichste und empfohlene Methode. Das CSS wird in einer separaten `.css`-Datei gespeichert und im `<head>`-Bereich des HTML-Dokuments mit einem `<link>`-Element verknüpft.

**HTML (`index.html`):**
```html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Meine Webseite</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Hallo Welt!</h1>
    <p>Dies ist ein Absatz.</p>
</body>
</html>
```

**CSS (`style.css`):**
```css
body {
  font-family: sans-serif;
}

h1 {
  color: navy;
}
```

### 3.2 Interne Stylesheets

CSS-Regeln können direkt im `<head>`-Bereich eines HTML-Dokuments innerhalb eines `<style>`-Elements platziert werden. Dies ist nützlich für Stile, die nur für eine einzelne Seite gelten.

```html
<!DOCTYPE html>
<html lang="de">
<head>
    <style>
        body {
            background-color: #f0f0f0;
        }
        p {
            color: green;
        }
    </style>
</head>
<body>
    <p>Dieser Absatz hat einen grünen Text.</p>
</body>
</html>
```

### 3.3 Inline-Styles

Stile können direkt auf ein einzelnes HTML-Element mit dem `style`-Attribut angewendet werden. Diese Methode sollte sparsam verwendet werden, da sie die Trennung von Inhalt und Design aufhebt und die Wartung erschwert.

```html
<p style="color: blue; font-size: 20px;">Dieser Absatz ist blau und hat eine Schriftgröße von 20px.</p>
```

## 4. CSS-Selektoren

Selektoren sind Muster, die verwendet werden, um die Elemente auszuwählen, die Sie formatieren möchten. Sie haben bereits die Klassen- (`.`) und ID-Selektoren (`#`) im HTML-Dokument gesehen.

### 4.1 Element-Selektor
Wählt alle Elemente eines bestimmten Typs aus.
```css
/* Wählt alle <p>-Elemente aus */
p {
  line-height: 1.5;
}
```

### 4.2 Klassen-Selektor
Wählt alle Elemente aus, die ein bestimmtes `class`-Attribut haben. Um Elemente mit einer bestimmten Klasse auszuwählen, schreiben Sie ein Punkt-Zeichen (`.`), gefolgt vom Klassennamen.

```css
/* Wählt alle Elemente mit class="wichtig" aus */
.wichtig {
  font-weight: bold;
  color: firebrick;
}
```

### 4.3 ID-Selektor
Wählt ein Element basierend auf dem Wert seines `id`-Attributs aus. Da IDs auf einer Seite einzigartig sein müssen, wird dieser Selektor verwendet, um ein einzelnes, eindeutiges Element auszuwählen. Um ein Element mit einer bestimmten ID auszuwählen, schreiben Sie ein Raute-Zeichen (`#`), gefolgt von der ID des Elements.

```css
/* Wählt das Element mit id="kopfzeile" aus */
#kopfzeile {
  background-color: lightblue;
  padding: 20px;
}
```
```
