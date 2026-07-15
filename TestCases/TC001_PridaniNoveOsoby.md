# TC-001 – Přidání nové osoby

## Description

Testovací případ ověřuje, zda uživatel může úspěšně přidat novou osobu v aplikaci.

## Preconditions

Uživatel se nachází na obrazovce **„Osoby“**.

## Test steps

### Positive test scenario

1. Uživatel klikne v menu na **Osoby**.
2. Klikne na tlačítko **„Nová osoba“**.
3. Uživatel vyplní všechna pole platnými daty.
4. Klikne na tlačítko **„Uložit“**.
5. **Očekávaný výsledek:** Osoba se uloží a zobrazí se v seznamu osob.

### Negative test scenario

1. Uživatel klikne v menu na **Osoby**.
2. Klikne na tlačítko **„Nová osoba“**.
3. Uživatel vyplní všechna pole kromě pole **IČO**.
4. Klikne na tlačítko **„Uložit“**.
5. **Očekávaný výsledek:** U pole **IČO** se zobrazí chybová hláška **„Vyplňte prosím toto pole.“**  

## Acceptance Criteria

- Uživatel musí být schopen přidat osobu pouze při vyplnění všech povinných polí.
- Pokud pole **IČO** není vyplněno, aplikace nesmí umožnit uložení osoby.
- Po úspěšném uložení musí být osoba zobrazena v seznamu osob.

## Actual Result

### Positive test scenario

Testování proběhlo úspěšně. 
- Po vyplnění všech polí se osoba uložila a zobrazila v seznamu osob.

### Negative test scenario

Testování selhalo. 
- Po vyplnění všech polí kromě **IČO** se osoba uložila a zobrazila v seznamu osob.
- Aplikace nezobrazila chybovou hlášku **„Vyplňte prosím toto pole.“**
  
## Linked work items

- [**BUG-001** – Chybí validace pole **IČO** při vytváření osoby](../BugReports/BUG001_PridaniNoveOsoby.md)
