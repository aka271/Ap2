# Java

- [Java](#java)
  - [1. Programmiersprachen](#1-programmiersprachen)
    - [1.1 Compiler vs. Interpreter](#11-compiler-vs-interpreter)
    - [1.2 Besonderheiten und Vorteile von Java](#12-besonderheiten-und-vorteile-von-java)
  - [2. Java Grundlagen](#2-java-grundlagen)
    - [2.1 Hello World](#21-hello-world)
    - [2.2 Kompilieren und Ausführen](#22-kompilieren-und-ausführen)
      - [2.2.1 Kompilieren von Programmen](#221-kompilieren-von-programmen)
      - [2.2.2 Ausführen von Programmen](#222-ausführen-von-programmen)
    - [2.3 Variablen und Datentypen](#23-variablen-und-datentypen)
      - [2.3.1 Operatoren](#231-operatoren)
    - [2.4 Zahlendarstellung in Java](#24-zahlendarstellung-in-java)
      - [2.4.1 Datentypen für ganze Zahlen](#241-datentypen-für-ganze-zahlen)
      - [2.4.2 Datentypen für Dezimalzahlen](#242-datentypen-für-dezimalzahlen)
    - [2.5 Ein- und Ausgabe](#25-ein--und-ausgabe)
    - [2.6 Strings](#26-strings)
    - [2.7 Verzweigungen](#27-verzweigungen)
    - [2.8 Schleifen](#28-schleifen)
  - [3. Arrays und Listen](#3-arrays-und-listen)


## 1. Programmiersprachen
Programme werden in **Hochsprachen** wie Java, Python oder C++ geschrieben. Diese Sprachen sind für Menschen gut lesbar und verständlich. Der Quelltext, also das in Textform geschriebene Programm, kann jedoch nicht direkt von der Computer-Hardware ausgeführt werden.

Computer verstehen ausschließlich **Maschinensprache**, eine sehr hardwarenahe Sprache. Daher muss der Quelltext einer Hochsprache in die für das jeweilige Betriebssystem (z.B. Windows oder Linux) verständliche Maschinensprache übersetzt werden.

### 1.1 Compiler vs. Interpreter

Für diese Übersetzung gibt es zwei Arten von Programmen:
- **Compiler**: Ein Compiler übersetzt den gesamten Quelltext vor der Ausführung des Programms in Maschinensprache. Das Ergebnis ist eine direkt ausführbare Datei.
- **Interpreter**: Ein Interpreter übersetzt den Quelltext Zeile für Zeile während das Programm läuft.

Zusammenfassend lässt sich sagen, dass Compiler und Interpreter als "Übersetzer" fungieren, die die Brücke zwischen der vom Menschen geschriebenen Hochsprache und der von der Maschine verstandenen Maschinensprache schlagen.

### 1.2 Besonderheiten und Vorteile von Java
Java verfolgt einen besonderen Ansatz bei der Übersetzung von Quelltext. Im Gegensatz zu vielen anderen Sprachen übersetzt der **Java-Compiler** den Code nicht direkt in Maschinensprache, sondern in einen Zwischencode, den sogenannten **Bytecode**. Diese kompilierten Java-Dateien erkennen Sie an der Endung `.class.`

Der entscheidende Vorteil von Bytecode ist seine **Plattformunabhängigkeit**. Das bedeutet, er ist auf jedem Betriebssystem identisch. Allerdings kann er nicht direkt von der CPU des Computers ausgeführt werden.

An dieser Stelle kommt die **Java Virtual Machine (JVM)** ins Spiel. Die JVM ist eine spezielle Laufzeitumgebung, die als "virtueller Computer" fungiert und für verschiedene Betriebssysteme (wie Windows, Linux oder macOS) verfügbar ist. Sie nimmt den plattformunabhängigen Bytecode entgegen und interpretiert ihn, also übersetzt ihn in die spezifische Maschinensprache, die der lokale Computer versteht. Dieser zweistufige Prozess macht Java-Anwendungen extrem portabel: Einmal kompiliert, können sie auf jedem System laufen, auf dem eine JVM installiert ist.


## 2. Java Grundlagen

### 2.1 Hello World
Beispiel Programm Java Hello World.

```java
//HelloWorld.java
public class HelloWorld{
    public static void main(String[] args){
        System.out.println("Hello World");
    }
}
```

### 2.2 Kompilieren und Ausführen

#### 2.2.1 Kompilieren von Programmen
Um das Programm zu kompilieren kann über die Konsole foglender Befehl ausgeführt werden.
```bash
javac HelloWorld.java
```

#### 2.2.2 Ausführen von Programmen
Um das Programm auszuführen, kann über die Konsole folgender Befehl ausgeführt werden.
```bash
java HelloWorld
```

### 2.3 Variablen und Datentypen
Variablen sind ein grundlegender Teil der Programmierung. Man kann sie sich als Container oder benannte Speicherplätze vorstellen, in denen Daten während der Laufzeit eines Programms abgelegt werden. Jede Variable hat einen **Datentyp**, der festlegt, welche Art von Daten sie speichern kann, und einen eindeutigen **Namen**.

Die wichtigsten primitiven Datentypen in Java sind:
- **int**: Für ganze Zahlen (z.B. 10, -42, 1500).
- **double**: Für Kommazahlen (z.B. 3.14, -2.5).
- **boolean**: Für Wahrheitswerte, kann nur true oder false sein.
- **char**: Für einzelne Zeichen, in einfachen Anführungszeichen (z.B. 'A', '!').
- **String**: (technisch gesehen kein primitiver Typ, aber genauso fundamental) Für Zeichenketten, in doppelten Anführungszeichen (z.B. "Hallo").

Beispiel für die Deklaration und Initialisierung von Variablen:
```java
public class VariablenBeispiel {
    public static void main(String[] args) {
        String name = "Ada Lovelace"; // Eine Variable vom Typ String
        int alter = 36;              // Eine Variable vom Typ int
        double pi = 3.14159;         // Eine Variable vom Typ double
        boolean istProgrammiererin = true; // Eine Variable vom Typ boolean
    }
}
```

#### 2.3.1 Operatoren
Operatoren sind spezielle Symbole, die eine oder mehrere Aktionen oder Prozesse ausführen. Sie werden verwendet, um Variablen und Werte zu manipulieren.

**Arithmetische Operatoren**:\
Werden für mathematische Berechnungen verwendet.
- `+` (Addition)
- `-` (Subtraktion)
- `*` (Multiplikation)
- `/` (Division)
- `%` (Modulo, gibt den Rest einer Division zurück)

```java
int a = 10;
int b = 3;
System.out.println(a + b); // 13
System.out.println(a % b); // 1
```

**Zuweisungsoperatoren**:\
Weisen einer Variable einen Wert zu.

- `=` (Einfache Zuweisung)
- `+=`, `-=`, `*=`, `/=`, `%=` (Kombinierte Zuweisung)

```java
int x = 10;
x += 5; // entspricht x = x + 5; -> x ist jetzt 15
```

**Vergleichsoperatoren**:\
Vergleichen zwei Werte und geben einen boolean-Wert (true oder false) zurück.

- `==` (Gleich)
- `!=` (Ungleich)
- `>` (Größer als)
- `<` (Kleiner als)
- `>=` (Größer oder gleich)
- `<=` (Kleiner oder gleich)

```java
int alter = 18;
boolean istVolljaehrig = alter >= 18; // true
```

**Logische Operatoren**:\
Werden verwendet, um boolean-Werte zu verknüpfen.

- `&&` (Logisches UND: true, wenn beide Ausdrücke true sind)
- `||` (Logisches ODER: true, wenn mindestens ein Ausdruck true ist)
- `!` (Logisches NICHT: Kehrt den boolean-Wert um)

```java
boolean hatFuehrerschein = true;
boolean hatAuto = false;
boolean darfFahren = hatFuehrerschein && hatAuto; // false
```

**Inkrement- und Dekrement-Operatoren**:\
Erhöhen oder verringern den Wert einer Variable um eins.

- `++` (Inkrement)
- `--` (Dekrement)

```java
int anzahl = 5;
anzahl++; // anzahl ist jetzt 6
```

### 2.4 Zahlendarstellung in Java
#### 2.4.1 Datentypen für ganze Zahlen
Typ | Größe im Speicher | Wertebereich |
--- | --- | --- |
`byte` | 1 Byte | -128 bis +127 |
`short` | 2 Bytes | -32.768 bis +32.767 | 
`int` | 4 Bytes | -2.147.483.648  bis +2.147.483.647 |
`long` | 8 Bytes | -9.223.372.036.854.775.808 bis +9.223.372.036.854.775.807 |
`BigInteger` | mind. 24 Bytes | Beliebig groß |


**Kodierung negativer Zahlen – Zweierkomplement**

Negative Zahlen werden in der **Zweierkomplementdarstellung** gespeichert. So wird die Zahl -23 mit einem Byte gespeichert:

1. **Positive Zahl binär aufschreiben**: +23 entspricht 0001 0111.
2. **Binäre Zahl invertieren**: Jedes Bit wird umgedreht zu 1110 1000.
3. **Eins hinzuaddieren**: 1110 1000 + 0000 0001 = 1110 1001.
4. Der Wert 1110 1001 entspricht nun der -23 im Zweierkomplement.

Teste folgenden Code, um einen Überlauf zu sehen:
```java
System.out.println((byte)(127 + 1)); // Ausgabe: -128
```

#### 2.4.2 Datentypen für Dezimalzahlen
Man unterscheidet zwischen Gleitkommazahlen und Festkommazahlen.

**Gleitkommazahlen**\
Hier ist die Anzahl der Vor- und Nachkommastellen variabel. Das Komma "gleitet", was bei sehr großen Zahlen zu Ungenauigkeiten führen kann.

Typ | Größe im Speicher | Wertebereich |
--- | --- | --- |
`float` | 4 Bytes | -3,4 * 10³⁸ bis +3,4 * 10³⁸ |
`double` | 8 Bytes | -1,7 * 10³⁰⁸ bis +1,7 * 10³⁰⁸ |

Gleitkommazahlen bestehen aus einem Vorzeichenbit, einer Mantisse (Ziffern) und einem Exponenten (Kommaverschiebung). Wegen möglicher Rundungsfehler sollten sie **nicht für Geldbeträge** verwendet werden.

Teste folgenden Code, um die Ungenauigkeit zu sehen:
```java
System.out.println(0.1 + 0.2); // Ausgabe: 0.30000000000000004
```

**Festkommazahlen**\
Hier ist die Position des Kommas fest, was sie sehr präzise macht. Java bietet dafür den Datentyp `BigDecimal`. Er kann beliebig große Zahlen mit beliebiger Genauigkeit darstellen, bis der Hauptspeicher voll ist. Dies ist die zwingend empfohlene Wahl für Finanzberechnungen.


### 2.5 Ein- und Ausgabe
Um Werte von Variablen oder einfachen Text auf dem Bildschirm (in der Konsole) auszugeben, wird der Befehl `System.out.println()` verwendet. Der Inhalt, der in den Klammern steht, wird ausgegeben, gefolgt von einem Zeilenumbruch.
Man kann festen Text (in Anführungszeichen) und Variablen miteinander kombinieren, indem man sie mit einem `+`-Zeichen verbindet.

Beispiel für die Ausgabe von Variablen:
```java
public class AusgabeBeispiel {
    public static void main(String[] args) {
        String name = "Ada Lovelace";
        int alter = 36;
        
        // Ausgabe von reinem Text
        System.out.println("Informationen zur Person:");
        
        // Ausgabe des Werts der Variable 'name'
        System.out.println(name); 
        
        // Kombination von Text und Variablen
        System.out.println("Name: " + name);
        System.out.println("Alter: " + alter);
        System.out.println(name + " war " + alter + " Jahre alt.");
    }
}
```

Konsolenausgabe dieses Programms:

```bash
Informationen zur Person:
Ada Lovelace
Name: Ada Lovelace
Alter: 36
Ada Lovelace war 36 Jahre alt.
```

### 2.6 Strings
Ein `String` in Java ist kein primitiver Datentyp, sondern ein Objekt, das eine Zeichenkette (eine Sequenz von Zeichen) darstellt. Strings werden in doppelten Anführungszeichen " geschrieben.

**Deklaration und Initialisierung**:

```java
String gruss = "Hallo Welt!";
String name = "Ada";
```

**String-Verkettung (Konkatenation)**:\
Strings können mit dem `+` Operator verbunden werden.

```java
String satz = gruss + " Ich bin " + name + ".";
System.out.println(satz); // Ausgabe: Hallo Welt! Ich bin Ada.
```

**Wichtige String-Methoden**:\
Da Strings Objekte sind, stellen sie nützliche Methoden (Funktionen) zur Verfügung.

- `length()`: Gibt die Anzahl der Zeichen im String zurück.
- `toUpperCase()`: Wandelt alle Zeichen in Großbuchstaben um.
- `toLowerCase()`: Wandelt alle Zeichen in Kleinbuchstaben um.
- `charAt(index)`: Gibt das Zeichen an einer bestimmten Position zurück (Zählung beginnt bei 0).
- `equals(anotherString)`: Vergleicht zwei Strings auf inhaltliche Gleichheit. Wichtig: Verwenden Sie equals() und nicht == zum Vergleichen von String-Inhalten!

**Beispiel für Methoden**:
```java
String text = "Java ist super";

int laenge = text.length(); // 14
String gross = text.toUpperCase(); // "JAVA IST SUPER"
char zeichen = text.charAt(0); // 'J'
boolean istGleich = text.equals("java ist super"); // false (Groß/Kleinschreibung)

System.out.println("Länge: " + laenge);
System.out.println("Großbuchstaben: " + gross);
System.out.println("Erstes Zeichen: " + zeichen);
System.out.println("Ist gleich? " + istGleich);
```

### 2.7 Verzweigungen
Verzweigungen, auch Kontrollstrukturen genannt, ermöglichen es einem Programm, Entscheidungen zu treffen und unterschiedliche Code-Blöcke auszuführen, je nachdem, ob eine bestimmte Bedingung erfüllt ist oder nicht.

`if-else`**-Anweisung**\
Die `if-else`-Anweisung ist die grundlegendste Form der Verzweigung.

- Der `if`-Block wird ausgeführt, wenn die Bedingung in den runden Klammern `true` (wahr) ist.
- Optional kann ein `else`-Block angehängt werden, der ausgeführt wird, wenn die Bedingung `false` (falsch) ist.
- Mit `else if` können weitere Bedingungen geprüft werden.

**Syntax**:
```java
if (bedingung) {
    // Code, der ausgeführt wird, wenn die Bedingung wahr ist
} else if (andere_bedingung) {
    // Code, der ausgeführt wird, wenn die erste Bedingung falsch,
    // aber die andere_bedingung wahr ist
} else {
    // Code, der ausgeführt wird, wenn alle vorherigen Bedingungen falsch sind
}
```
**Beispiel**:
```java
int alter = 20;

if (alter >= 18) {
    System.out.println("Die Person ist volljährig.");
} else {
    System.out.println("Die Person ist minderjährig.");
}
```

`switch`**-Anweisung**\
Die `switch`-Anweisung ist nützlich, wenn eine einzelne Variable mit mehreren möglichen Werten verglichen werden soll. Sie ist oft lesbarer als eine lange Kette von `if-else if`-Anweisungen.

- Der Wert der Variable in den `switch`-Klammern wird mit den `case`-Werten verglichen.
- `break`; ist wichtig, um aus dem `switch`-Block auszuspringen, sobald ein passender Fall gefunden wurde. Ohne `break` würden auch alle nachfolgenden `case`-Blöcke ausgeführt werden ("fall-through").
- Der `default`-Block ist optional und wird ausgeführt, wenn keiner der `case`-Werte zutrifft.

**Beispiel**:
```java
int wochentag = 3;
String tag;

switch (wochentag) {
    case 1:
        tag = "Montag";
        break;
    case 2:
        tag = "Dienstag";
        break;
    case 3:
        tag = "Mittwoch";
        break;
    case 4:
        tag = "Donnerstag";
        break;
    case 5:
        tag = "Freitag";
        break;
    default:
        tag = "Wochenende";
        break;
}
System.out.println("Heute ist " + tag); // Ausgabe: Heute ist Mittwoch
```

### 2.8 Schleifen
Schleifen werden verwendet, um einen Code-Block mehrfach zu wiederholen, solange eine bestimmte Bedingung erfüllt ist.

`while`**-Schleife**\
Die `while`-Schleife ist eine kopfgesteuerte Schleife. Das bedeutet, die Bedingung wird vor jeder Ausführung des Schleifenkörpers geprüft. Ist die Bedingung von Anfang an `false`, wird der Code-Block gar nicht erst ausgeführt.

**Beispiel**:
```java
int i = 1;
while (i <= 5) {
    System.out.println("Durchlauf Nummer " + i);
    i++; // Wichtig: Zählervariable verändern, um eine Endlosschleife zu vermeiden!
}
// Ausgabe:
// Durchlauf Nummer 1
// Durchlauf Nummer 2
// Durchlauf Nummer 3
// Durchlauf Nummer 4
// Durchlauf Nummer 5
```

`do-while`**-Schleife**\
Die `do-while`-Schleife ist eine fußgesteuerte Schleife. Der Schleifenkörper wird mindestens einmal ausgeführt, da die Bedingung erst nach dem ersten Durchlauf geprüft wird.

**Beispiel**:
```java
int i = 6;
do {
    System.out.println("Dieser Text wird mindestens einmal ausgegeben.");
    System.out.println("i ist jetzt: " + i);
    i++;
} while (i <= 5);
// Ausgabe:
// Dieser Text wird mindestens einmal ausgegeben.
// i ist jetzt: 6
```

`for`**-Schleife**\
Die `for`-Schleife ist ideal, wenn die Anzahl der Wiederholungen im Voraus bekannt ist. Sie kombiniert Initialisierung, Bedingung und Inkrementierung/Dekrementierung in einer Zeile.

**Syntax**:
```java
for (Initialisierung; Bedingung; Inkrement/Dekrement) { ... }
```
**Beispiel**:
```java
for (int i = 1; i <= 5; i++) {
    System.out.println("For-Schleifen Durchlauf: " + i);
}
// Ausgabe ist identisch zur while-Schleife oben.
```

## 3. Arrays und Listen