# BUG-002 – Smazání osoby – osoba po pokusu o smazání stále zůstává v seznamu osob

## Description

Po pokusu o smazání osoby zůstává osoba i nadále zobrazena v seznamu osob. Po obnovení stránky není změna provedena.

**Testovací zařízení**

- Desktop
- Windows 10 Pro
- Verze 10.0.19045
- Build 19045

**Prohlížeč**

- Google Chrome
- Verze 146.0.7680.177

**Oblast**

Stránka se seznamem osob.

**Povaha chyby**

Funkční (front-end)

**Priority**

Medium – chyba neblokuje práci s aplikací, ale neumožňuje úspěšně dokončit operaci mazání.

**Impact**

Osoba se stále zobrazuje, což vede k neaktuálním datům.

**Severity**

Low – chyba neomezuje běh aplikace, ale ovlivňuje správnost zobrazených dat.

## Steps to reproduce

1. Uživatel se nachází na obrazovce **Osoby**.
2. U osoby **Milan Houžvička** klikne na tlačítko **„Smazat“**.
3. Provede obnovu (refresh) stránky.

## Expected Result

Osoba se nezobrazuje v seznamu osob a není dohledatelná ani pomocí vyhledávání.

## Actual Result

Osoba se po obnovení stránky stále zobrazuje v seznamu osob.

## Frequency

Chyba se vyskytuje vždy při testování mazání osob.

---

## Linked work items

- [**TC-002** – Smazání osoby](../TestCases.md/TC002_SmazaniOsoby.md)