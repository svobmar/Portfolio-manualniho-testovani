# BUG-003 – Editace faktury – po editaci faktury zůstává číslo faktury beze změny

## Description

**Příčina**

Při odeslání požadavku na editaci faktury server sice vrátí odpověď **200 OK**, ale editace pole **invoiceNumber** se neprovede a číslo faktury zůstane beze změny.

**Testovací zařízení**

- Desktop
- Windows 10 Pro
- Verze 10.0.19045
- Build 19045

**Prohlížeč**

- Google Chrome
- Verze 146.0.7680.177

**Oblast**

API endpoint `/api/invoices/{invoice_id}` – úprava faktury.

**Povaha chyby**

Funkční chyba – nesprávná aktualizace dat na back-endu.

**Priority**

High – chyba ovlivňuje správnost dat v databázi a výsledky zobrazené uživateli.

**Impact**

Uživatel může být mylně přesvědčen, že faktura byla úspěšně aktualizována, přestože data zůstala nezměněna. To může vést k nesprávným fakturačním údajům.

**Severity**

High – data se neaktualizují správně, což narušuje integritu faktur v systému.

## Steps to reproduce

1. Vyberte existující fakturu k editaci (např. **invoiceNumber 25001**, **id: 1**).
2. Zvolte metodu **PUT** na endpoint:

   `http://localhost:8000/api/invoices/1`

3. Do těla požadavku změňte hodnotu **invoiceNumber** na **98765**. Ostatní údaje ponechte beze změny.
4. Odešlete požadavek a ověřte, že systém vrátí odpověď **200 OK**.
5. Pomocí požadavku **GET** na endpoint

   `http://localhost:8000/api/invoices/1`

   ověřte změnu hodnoty **invoiceNumber**.

## Expected Result

- Systém vrátí odpověď **200 OK**.
- Číslo faktury (**invoiceNumber**) bude změněno na **98765**.

## Actual Result

- Systém vrátil odpověď **200 OK**.
- Hodnota **invoiceNumber** zůstala původní (**25001**).

## Frequency

Chyba se vyskytuje při každém pokusu o editaci faktury. Hodnota **invoiceNumber** zůstává původní (**25001**).

---

## Linked work items

- [**TC-003** – Editace faktury (API)](../TestCases/TC003_EditaceFaktury_API.md)