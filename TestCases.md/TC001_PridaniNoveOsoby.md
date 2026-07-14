# TC-001 – Přidání nové osoby

## Description

Testovací případ ověřuje, zda uživatel může úspěšně přidat novou osobu v aplikaci.

## Preconditions

Uživatel se nachází na obrazovce **„Osoby“**.

## Test steps

### Pozitivní scénář

1. Uživatel klikne v menu na **Osoby**.
2. Klikne na tlačítko **„Nová osoba“**.
3. Vyplní všechna pole.
4. Klikne na tlačítko **„Uložit“**.
5. **Očekávaný výsledek:** Osoba se uloží a zobrazí se v seznamu osob.

### Negativní scénář

1. Uživatel klikne v menu na **Osoby**.
2. Klikne na tlačítko **„Nová osoba“**.
3. Uživatel vyplní všechna pole kromě pole **IČO**.
4. Klikne na tlačítko **„Uložit“**.
5. **Očekávaný výsledek:** U pole se zobrazí chybová hláška **„Vyplňte prosím toto pole.“**

## Expected Results

- Osoba se uloží pouze v případě, že jsou vyplněna všechna povinná pole.
- Pokud chybí některé povinné pole (například **IČO**), aplikace zobrazí chybovou hlášku **„Vyplňte prosím toto pole.“**

## Acceptance Criteria

- Uživatel musí být schopen přidat osobu pouze při vyplnění všech povinných polí.
- Pokud pole **IČO** není vyplněno, aplikace nesmí umožnit uložení osoby.
- Po úspěšném uložení musí být osoba zobrazena v seznamu osob.

## Actual Result

### Pozitivní scénář

Testování proběhlo úspěšně. Po vyplnění všech polí se osoba uložila a zobrazila v seznamu osob.

### Negativní scénář

Testování selhalo. Po vyplnění všech polí kromě **IČO** se osoba uložila a zobrazila v seznamu osob.

Aplikace nezobrazila chybovou hlášku **„Vyplňte prosím toto pole.“**

Osoba bez vyplněného **IČO** se zobrazí v seznamu osob.  
## Linked work items

- **BUG-001** – Chybí validace pole **IČO** při vytváření osoby.