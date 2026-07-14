# BUG-001 – Chybí validace pole IČO při vytváření osoby

## Description

**Příčina**  
Pole **IČO** přijímá prázdnou hodnotu, i když by mělo být pole povinné.

**Testovací zařízení**

- Desktop
- Windows 10 Pro
- Verze 10.0.19045
- Build 19045

**Prohlížeč**

- Google Chrome
- Verze 146.0.7680.177

**Oblast**

Formulář pro vytváření osoby.

**Povaha chyby**

Funkční (front-end)

**Priority**

Medium – chyba neblokuje celý proces, ale může vést k nekonzistentním datům.

**Impact**

Uživatel může uložit neplatná data, což vede k problémům v databázi.

**Severity**

Medium – chyba může ovlivnit kvalitu dat, ale aplikace je stále funkční.

## Steps to reproduce

1. Uživatel se nachází na obrazovce **Osoby**.
2. Uživatel klikne na tlačítko **„Nová osoba“**.
3. Vyplní všechny povinné údaje kromě pole **IČO**.
4. Klikne na tlačítko **„Uložit“**.
5. U vytvořené osoby v seznamu osob klikne na **„Zobrazit“**.
6. V detailu osoby je vidět, že **IČO** chybí, nebylo uloženo.

## Expected Result

Aplikace by při pokusu o uložení osoby měla zobrazit hlášku, že pole je povinné.

## Actual Result

Aplikace umožní uložení osoby i s prázdným polem **IČO**.

## Frequency

Chyba se vyskytuje vždy při vytváření nové osoby.

---

## Linked work items

- [**TC-001** – Přidání nové osoby](../TestCases/TC001_PridaniNoveOsoby.md)