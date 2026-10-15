---
name: create-glossary
description: Adds a Glossary slide with an Acronym and Definition table built from every acronym in the deck.
---

## Definitions

All three kinds go in the glossary.

- **Defined acronym**: an acronym that appears somewhere in the deck beside its expansion, in either order: `Harbor Logistics (HL)` or `HL (Harbor Logistics)`. Its definition is the expansion as written in the deck.
- **Bare acronym**: an acronym used in the deck with no expansion anywhere. Its definition is the standard expansion that fits the deck's subject. When the expansion cannot be determined with confidence, the Definition cell reads `[to confirm]`.
- **Code**: a country code, currency code, ticker or unit (`US`, `USD`, `kWh`). Its definition is the standard expansion, or the expansion written in the deck when one exists.

## Steps

### 1. Read every slide

Go through every slide in order and read all on-slide text. Speaker notes are excluded. If a slide titled "Glossary" already exists, stop and ask the user whether to replace it or add a second one. Exclude that slide from the read.

Done when: the count of slides read equals the deck's slide count minus any existing Glossary slide.

### 2. Collect acronyms

Record every token of two or more characters with at least two capitals (`HL`, `PPA`, `kWh`, `USD`).

- Plurals merge into the singular: `PPAs` records as `PPA`.
- Write each definition with the first letter capitalised.
- The same acronym with two different definitions in the deck becomes two rows, one per definition.
- Sort rows alphabetically by acronym. Rows sharing an acronym follow the order their definitions first appear in the deck.

Done when: each acronym-and-definition pair in the deck appears exactly once in the list, and every row has a definition or `[to confirm]`.

### 3. Build the slide

1. Add one new slide at the end of the deck, using the slide master of the last slide. Choose its layout in this order: a layout named "Title Only"; otherwise any layout with a title placeholder, then delete that new slide's empty non-title placeholders.
2. Set the title placeholder text to `Glossary`. Leave its font, size and colour as the layout gives them.
3. Add two tables side by side, a left table and a right table. Each has two columns and one header row, header cells `Acronym` and `Definition`.
   - Split the rows in alphabetical order: the left table takes the first half, the right table takes the rest. With an odd number of rows, the left table takes the extra row.
   - Pass only rows, columns, values, position and size. Leave style, fill, borders, font and font size unset so PowerPoint applies the theme's default table style and default text formatting.
   - Position: both tables share a top edge just below the title placeholder. The left table's left edge aligns with the title placeholder's left edge, and the right table's right edge aligns with the title placeholder's right edge. Each table is 48% of the title placeholder's width, leaving a 4% gap between them.
   - Column widths in each table: Acronym about 25% of the table width, Definition the remainder.
4. Overflow: each table holds at most 14 rows, so each slide holds at most 28. When there are more, fill each slide with 14 rows per table and add further slides built the same way, each titled `Glossary`, placed directly after the first Glossary slide. The last slide splits its remaining rows between its two tables by the rule in 3.

Done when: every Glossary slide has the title `Glossary` and two tables, the data row count across all tables equals the number of rows in the list, every table has its own header row, and no formatting beyond position and size was set.

### 4. Reply

Reply with one word: `Completed.`

## Example

"Harbor Logistics (HL) signed a PPA (power purchase agreement) in 2024. Two further PPAs are planned, tracked against KPIs in USD." gives:

| Acronym | Definition |
|---|---|
| HL | Harbor Logistics |
| KPI | Key performance indicator |
| PPA | Power purchase agreement |
| USD | United States dollar |

The left table holds `HL` and `KPI`; the right table holds `PPA` and `USD`.
