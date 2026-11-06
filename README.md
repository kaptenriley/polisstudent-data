# polisstudent-data

Filer som appen **Inte Moodle** hämtar från GitHub Pages (`https://kaptenriley.github.io/polisstudent-data/`).

| Fil | Vad |
|---|---|
| `data.json` | Krypterad studentdata (klasslista, handledningar, förberedelser). Skapas med `tools/kryptera.py` i repot inte-moodle. Redigera inte för hand. |
| `popup.json` | Pop-up-rutor som visas i appen (t.ex. Polisplugg och Poliscase). Får redigeras direkt här. |

## Skicka ut en pop-up

1. Öppna `popup.json` här på github.com och tryck på pennan (**Edit this file**).
2. Ändra eller lägg till ett meddelande (se fälten nedan). Sätt `"aktiv": true`.
3. Tryck **Commit changes…** → **Commit changes**.
4. Efter några minuter (GitHub Pages) visas rutan för alla som öppnar appen. Appen kollar varje gång den öppnas.

Varje person ser ett meddelande **en gång** (eller en gång per dag med `"visa": "varje dag"`).
Vill du att samma meddelande ska visas igen för alla: byt `id`.
Visas flera aktiva meddelanden samtidigt kommer de ett i taget, i den ordning de står i filen.

### Fält

| Fält | Krävs | Exempel | Förklaring |
|---|---|---|---|
| `id` | ja | `"polisplugg-1"` | Unikt namn. Nytt id = visas igen för alla. |
| `aktiv` | nej | `true` | `false` = utkast, visas inte. |
| `titel` | ja | `"Plugga smartare"` | Rubrik. |
| `text` | ja | `"…"` | Brödtext, några rader. |
| `knapp` | nej | `"Läs mer"` | Text på knappen. |
| `lank` | nej | `"https://…"` | Webbsida eller App Store-länk som knappen öppnar. Utan länk visas bara OK. |
| `ikon` | nej | `"book.fill"` | Symbol från SF Symbols när ingen bild finns. |
| `bild` | nej | `"https://…/bild.jpg"` | Bild överst i rutan (lägg t.ex. bilden i det här repot). |
| `fran` / `till` | nej | `"2026-11-10"` | Första och sista dagen den visas. |
| `visa` | nej | `"en gång"` | `"en gång"` eller `"varje dag"`. |
| `klasser` | nej | `["P3A", "P3C"]` | Bara för vissa klasser. Utelämna = alla. |

Kommatecken mellan meddelanden och citattecken runt text är viktiga – en felaktig fil gör att inga rutor visas
(appen fungerar annars som vanligt). Kontrollera gärna filen på jsonlint.com innan du sparar.
