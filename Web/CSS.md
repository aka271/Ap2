<style>
    /* General Styles */
    .example-container-combined {
        font-family: sans-serif;
        color: #333;
    }
    .example-container-combined .box {
        width: 120px;
        height: 100px;
        color: white;
        padding: 10px;
        text-align: center;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 10px;
    }
    .example-container-combined h2 {
        color: #0056b3;
        border-bottom: 2px solid #f0f0f0;
        padding-bottom: 5px;
    }

    /* 1. Static */
    .example-container-combined .static-box { background-color: #6c757d; }

    /* 2. Relative */
    .example-container-combined .relative-box-1, .example-container-combined .relative-box-3 { background-color: #17a2b8; }
    .example-container-combined .relative-box-2 {
        position: relative;
        top: 20px;
        left: 30px;
        background-color: #007bff;
    }

    /* 3. Absolute */
    .example-container-combined .absolute-container {
        position: relative; /* Context for the child */
        height: 150px;
        border: 2px dashed #dc3545;
        padding: 10px;
    }
    .example-container-combined .absolute-box {
        position: absolute;
        top: 10px;
        right: 10px;
        background-color: #dc3545;
    }

    /* 4. Fixed */
    .example-container-combined .fixed-box {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background-color: #28a745;
        z-index: 100;
    }

    /* 5. Sticky */
    .example-container-combined .sticky-container {
        height: 200px;
        overflow-y: scroll;
        border: 2px dashed #ffc107;
    }
    .example-container-combined .sticky-header {
        position: sticky;
        top: 0;
        background-color: #ffc107;
        color: #333;
        padding: 8px;
        text-align: center;
    }
    .example-container-combined .sticky-container p { padding: 0 15px; }
</style>

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
  - [5. Das Boxmodell](#5-das-boxmodell)
  - [6. Positionierung](#6-positionierung)
    - [6.1 static (Standardwert)](#61-static-standardwert)
    - [6.2 relative](#62-relative)
    - [6.3 absolute](#63-absolute)
    - [6.4 fixed](#64-fixed)
    - [6.5 sticky](#65-sticky)

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
        p {
            color: green;
            background: #000000ff;
        }
    </style>
</head>
<body>
    <p>Dieser Absatz hat einen grünen Text.</p>
</body>
</html>
```

<p style="color: green; background: #000000ff;">Dieser Absatz hat einen grünen Text.</p>

### 3.3 Inline-Styles

Stile können direkt auf ein einzelnes HTML-Element mit dem `style`-Attribut angewendet werden. Diese Methode sollte sparsam verwendet werden, da sie die Trennung von Inhalt und Design aufhebt und die Wartung erschwert.

```html
<p style="color: blue; font-size: 20px;">Dieser Absatz ist blau und hat eine Schriftgröße von 20px.</p>
```

<p style="color: blue; font-size: 20px;">Dieser Absatz ist blau und hat eine Schriftgröße von 20px.</p>

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

## 5. Das Boxmodell

<style>
    /* General Body Styling */

    /* Main container for the widget */
    .container {
        width: 100%;
        max-width: 32rem; /* 512px */
    }

    /* Main title */
    .title {
        font-size: 1.5rem; /* 24px */
        font-weight: 700;
        text-align: center;
        margin-bottom: 1.5rem; /* 24px */
    }

    /* Box Model Visualization Styles */
    .margin-box {
        background-color: rgba(255, 237, 213, 0.7);
        padding: 2rem; /* 32px */
        border-radius: 0.5rem; /* 8px */
        border: 2px dashed #fdba74;
        position: relative;
    }

    .border-box {
        background-color: #bbf7d0;
        border-radius: 0.375rem; /* 6px */
        padding: 2rem; /* 32px */
        border: 8px solid #22c55e;
        position: relative;
    }

    .padding-box {
        background-color: #bfdbfe;
        border-radius: 0.125rem; /* 2px */
        padding: 2rem; /* 32px */
        position: relative;
    }

    .content-box {
        background-color: #60a5fa;
        color: white;
        padding: 1rem; /* 16px */
        border-radius: 0.125rem; /* 2px */
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 100px;
        transition: all 300ms cubic-bezier(0.4, 0, 0.2, 1);
    }
    
    .content-box h2 {
        font-weight: 700;
        font-size: 1.125rem; /* 18px */
    }

    .box-label {
        position: absolute;
        top: 8px;
        left: 8px;
        font-size: 0.75rem; /* 12px */
        font-weight: 500;
    }
    .label-margin { color: #9a3412; }
    .label-border { color: #15803d; }
    .label-padding { color: #1e40af; }


    /* Controls and Explanation Styles */
    .controls {
        background-color: white;
        padding: 1.5rem; /* 24px */
        border-radius: 0.5rem; /* 8px */
        box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
        margin-top: 2rem; /* 32px */
    }

    .controls-header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin-bottom: 1rem; /* 16px */
    }
    
    .controls-header h3 {
        font-size: 1.125rem; /* 18px */
        font-weight: 600;
    }

    .button-group {
        display: flex;
        align-items: center;
        gap: 0.5rem; /* 8px */
        background-color: #f1f5f9;
        padding: 0.25rem; /* 4px */
        border-radius: 0.5rem; /* 8px */
    }

    .button-group button {
        border: none;
        padding: 0.25rem 0.75rem; /* 4px 12px */
        border-radius: 0.375rem; /* 6px */
        font-size: 0.875rem; /* 14px */
        font-weight: 500;
        cursor: pointer;
        transition: all 150ms ease-in-out;
    }

    .button-active {
        background-color: white;
        color: #1e293b;
        box-shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
    }

    .button-inactive {
        background-color: transparent;
        color: #475569;
    }

    .explanation {
        font-size: 0.875rem; /* 14px */
        color: #475569;
        margin-bottom: 1rem; /* 16px */
    }

    .code-display {
        background-color: #f8fafc;
        padding: 1rem; /* 16px */
        border-radius: 0.5rem; /* 8px */
    }

    .code-display p {
        font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
        font-size: 0.875rem; /* 14px */
    }
    
    .code-display hr {
        margin: 0.75rem 0;
        border-color: #e2e8f0;
    }

    .result-display {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .result-display .label {
        font-size: 0.875rem; /* 14px */
        font-weight: 500;
    }

    .result-display .value {
        font-size: 1.125rem; /* 18px */
        font-weight: 700;
        color: #4f46e5;
    }

</style>
<div class="container">
    <h1 class="title">Das CSS Boxmodell</h1>
    <!-- Visuelle Darstellung des Boxmodells -->
    <div class="margin-box">
         <span class="box-label label-margin">Margin (Außenabstand)</span>
        <div class="border-box">
             <span class="box-label label-border">Border (Rahmen)</span>
            <div class="padding-box">
                 <span class="box-label label-padding">Padding (Innenabstand)</span>
                <div id="content-box" class="content-box">
                    <h2>Inhalt</h2>
                    <p>(width & height)</p>
                </div>
            </div>
        </div>
    </div>
    <!-- Steuerung und Erklärung -->
    <div class="controls">
        <div class="controls-header">
            <h3>Box Sizing</h3>
            <div class="button-group">
                <button id="btn-content-box">content-box</button>
                <button id="btn-border-box">border-box</button>
            </div>
        </div>
         <p class="explanation" id="explanation">
            Standard: `width` und `height` gelten nur für den **Inhalt**. Padding und Border werden addiert.
        </p>
        <div class="code-display">
            <p>#content-box {<br>
            &nbsp;&nbsp;width: 200px;<br>
            &nbsp;&nbsp;padding: 32px;<br>
            &nbsp;&nbsp;border: 8px;<br>
            }</p>
            <hr>
            <div class="result-display">
                <span class="label">Berechnete Gesamtbreite:</span>
                <span id="total-width" class="value">280px</span>
            </div>
        </div>
    </div>
</div>
<script>
    document.addEventListener('DOMContentLoaded', function() {
        const contentBox = document.getElementById('content-box');
        const btnContentBox = document.getElementById('btn-content-box');
        const btnBorderBox = document.getElementById('btn-border-box');
        const totalWidthLabel = document.getElementById('total-width');
        const explanation = document.getElementById('explanation');
        if (!contentBox || !btnContentBox || !btnBorderBox || !totalWidthLabel || !explanation) {
            console.error("Ein oder mehrere Elemente für das Boxmodell-Widget wurden nicht gefunden.");
            return;
        }
        function updateStyles(boxSizing) {
            contentBox.style.boxSizing = boxSizing;
            contentBox.style.width = '200px';
            if (boxSizing === 'border-box') {
                btnContentBox.className = 'button-inactive';
                btnBorderBox.className = 'button-active';
                explanation.innerHTML = "`width` und `height` beinhalten **Padding und Border**. Die Box ist exakt `200px` breit.";
                totalWidthLabel.textContent = '200px';
            } else { // content-box
                btnBorderBox.className = 'button-inactive';
                btnContentBox.className = 'button-active';
                explanation.innerHTML = "Standard: `width` und `height` gelten nur für den **Inhalt**. Padding und Border werden addiert.";
                totalWidthLabel.textContent = '280px';
            }
        }
        btnContentBox.addEventListener('click', () => updateStyles('content-box'));
        btnBorderBox.addEventListener('click', () => updateStyles('border-box'));
        // Initial state
        updateStyles('content-box');
    });
</script>



## 6. Positionierung
Die `position`-Eigenschaft in CSS legt fest, wie ein Element in einem Dokument positioniert wird. Zusammen mit den Eigenschaften `top`, `right`, `bottom` und `left` ermöglicht sie eine präzise Steuerung des Layouts.

### 6.1 static (Standardwert)
Jedes HTML-Element ist standardmäßig `static` positioniert. Das bedeutet, es folgt dem normalen Fluss der Seite. Die Eigenschaften `top`, `right`, `bottom`, `left` und `z-index` haben keine Wirkung.

```css
.box {
  position: static;
}
```

<div class="example-container-combined">
  <h2>Static-Example</h2>
      <div class="box static-box">Static Box</div>
      <p>This box is in the normal document flow.</p>
</div>


### 6.2 relative
Ein relativ positioniertes Element wird relativ zu seiner *normalen* Position im Dokumentenfluss verschoben. Der Platz, den das Element ursprünglich eingenommen hätte, bleibt leer. Es dient oft als Positionierungskontext für absolut positionierte Kind-Elemente.

```css
.box-relative {
  position: relative;
  left: 30px; /* Verschiebt das Element 30px vom linken Rand seiner normalen Position weg */
  top: 10px;  /* Verschiebt es 10px vom oberen Rand weg */
}
```
<div class="example-container-combined">
    <h2>Relative-Example</h2>
    <div class="box relative-box-1">Box 1</div>
    <div class="box relative-box-2">Box 2 (Relative)</div>
    <div class="box relative-box-3">Box 3</div>
    <p>Box 2 is shifted, but its original space is preserved.</p>
</div>


### 6.3 absolute
Ein absolut positioniertes Element wird vollständig aus dem normalen Dokumentenfluss entfernt. Es wird relativ zum nächsten Vorfahrenelement positioniert, das eine andere Position als `static` hat. Wenn kein solches Element vorhanden ist, wird es relativ zum `<html>`-Element positioniert.

```css
.container {
  position: relative; /* Dies wird zum Bezugspunkt für das absolute Kind */
  width: 200px;
  height: 200px;
  border: 1px solid black;
}

.box-absolute {
  position: absolute;
  top: 10px;
  right: 10px;
}
```

<div class="example-container-combined">
    <h2>Absolute-Example</h2>
    <div class="absolute-container">
        Container (position: relative)
        <div class="box absolute-box">Absolute Box</div>
    </div>
    <p>The red box is positioned relative to its container.</p>
</div>

### 6.4 fixed
Ein Element mit `position: fixed` wird relativ zum Ansichtsfenster (dem Browserfenster) positioniert. Es bleibt an derselben Stelle, auch wenn die Seite gescrollt wird. Es wird ebenfalls aus dem normalen Dokumentenfluss entfernt. Typische Anwendungsfälle sind fixierte Kopfzeilen oder "Zum Seitenanfang"-Buttons.

```css
.fixed-header {
  position: fixed;
  top: 0;
  width: 100%;
}
```

<div class="example-container-combined">
    <h2>Fixed-Example</h2>
    <div class="box fixed-box">Fixed Box</div>
    <p>This box stays in place when you scroll the page.</p>

### 6.5 sticky
Ein "klebrig" positioniertes Element ist eine Mischung aus `relative` und `fixed`. Es verhält sich wie ein relativ positioniertes Element, bis ein bestimmter Scroll-Punkt erreicht ist. Dann "klebt" es an dieser Stelle (wie `fixed`), aber nur innerhalb seines übergeordneten Containers.

```css
.sticky-element {
  position: sticky;
  top: 0; /* Klebt am oberen Rand des Viewports, wenn man dorthin scrollt */
}
```

<div class="example-container-combined">
    <h2>Sticky-Example</h2>
    <div class="sticky-container">
        <div class="sticky-header">Sticky Header</div>
        <p>Scroll <b>inside this container</b> to see the effect.</p>
        <p>Some content to create scrolling...</p>
        <p>More content here...</p>
        <p>Even more content to ensure scrolling is possible...</p>
    </div>
</div>