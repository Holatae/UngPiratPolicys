---
title: Instruktion över att skriva styrdokument
type: Instruktion
---
Detta dokument beskriver riktlinjerna för att skriva styrdokument i Markdown, samt processen för att generera DOCX-versioner av dessa dokument. Genom att följa instruktionerna kan du enkelt skapa strukturerade dokument som kan konverteras till DOCX-format via ett anpassat program. När du har filerna i DOCX-format kan du göra lämpliga redigeringar

## Förberedelser och Systemkrav

För att kunna generera DOCX-filer från Markdown-filer krävs följande:

1. **Java 17**: Programmet som omvandlar Markdown-filer till DOCX är utvecklat i Kotlin och kräver Java 17 för att fungera. Installera Java 17 om det inte redan finns på ditt system.
2. **Pandoc**: Programmet använder Pandoc för att konvertera Markdown till DOCX. Installera Pandoc från [pandoc.org](https://pandoc.org).
3. **Mallar**: DOCX-mallfiler krävs för att styra formatet i de genererade dokumenten. En nedladdningslänk till mallarna kommer att tillhandahållas i framtiden.
4. _valfritt ordbehandlingsprogram_: **Rekomenderat: Microsoft Word**. Detta är för att du ska enkelt kunna redigera den slutgivna filen du får i DOCX-format för att redigera enklare grejer såsom viss formatering, samt för att skapa en PDF-variant av dokumentet

## Struktur för Markdown-filer

Varje styrdokument bör börja med ett metadata-block som specificerar dokumentets titel och typ. Detta block skrivs i YAML-syntax och omges av tre bindestreck (`---`) i början och slutet. Metadata används av programmet för att tillämpa rätt mall och organisera dokument.

### Exempel på Metadata

```
---
title: Intruktioner över att skriva styrdokument
type: Instruktioner
---
```
Fältet `title` anger dokumentets titel, och `type` anger dokumentets typ (t.ex., Policy, Instruktioner, eller Rutin). Typen avgör vilken mall som används under konverteringen.

## Grundläggande Markdown-syntax

Markdown är ett enkelt markeringsspråk som är lätt att lära sig. Här är några grundläggande element:

* **Rubriker**: Använd `#` för att skapa rubriker. Fler `#` betyder en lägre rubriknivå.

  * `# Rubrik 1` för huvudrubriker
  * `## Rubrik 2` för underrubriker

* **Listor**:

  * Punktlistor skapas med `-` eller `*`.
  * Numrerade listor skrivs med siffror följda av punkt: `1. Första punkt`

* **Fetstil och kursiv**:

  * **Fetstil**: Omslut text med två stjärnor, `**fetstil**`.
  * _Kursiv_: Omslut text med en stjärna, `*kursiv*`.

* **Länkar**: `[Text för länken](URL)`

### Exempel på ett enkelt dokument
```markdown
---
title: Exempel på styrdokument
type: Policy
---

# Exempelpolicy

Denna policy beskriver riktlinjerna för [exempelprocessen](https://exempel.se).

## Mål och syfte

- Att säkerställa enhetlighet
- Att främja effektivitet

```

## Att Köra Programmet för DOCX-konvertering

När Java 17, Pandoc, och mallarna har installerats kan programmet köras för att generera DOCX-filer. Gör så här:

1. Placera dina Markdown-filer i den mapp som specificeras som input-mapp i `config.ini`-filen (t.ex., `styrdokument`).
2. Kör programmet genom att exekvera följande kommando:
```bash
java -jar MarkdownToDocx-1.0-SNAPSHOT.jar
```
3. Programmet skapar en mapp för `output` med samma mappstruktur som input och sparar DOCX-filerna där.

När du följer dessa steg skapar du DOCX-filer från dina Markdown-styrdokument.
