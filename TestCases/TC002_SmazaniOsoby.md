# TC-002 – Smazání osoby

## Description

Testovací případ ověřuje, zda lze existující osobu úspěšně smazat a že se již neobjeví v seznamu osob.

## Preconditions

- V systému existuje alespoň jedna osoba se správně vyplněnými daty.
- Uživatel se nachází na obrazovce **„Osoby“**.

## Test steps

### Pozitivní scénář

1. Uživatel klikne v menu na **„Osoby“**.
2. Uživatel vybere existující osobu a klikne u ní na tlačítko **„Odstranit“**.
4. Systém zobrazí potvrzovací dialog pro smazání.
5. Uživatel potvrdí akci.
6. Uživatel ověří, že se osoba již nezobrazuje v seznamu osob.
7. **Očekávaný výsledek:** Osoba se již nezobrazuje v seznamu osob.

### Negativní scénář

1. Uživatel klikne v menu na **„Osoby“**.
2. Vybere existující osobu.
3. Klikne na tlačítko **„Odstranit“**.
4. Systém zobrazí potvrzovací dialog pro smazání.
5. Uživatel akci zruší (např. kliknutím na "Zrušit").
6. Uživatel ověří, že osoba zůstává v seznamu osob.
8. **Očekávaný výsledek:** Osoba se stále zobrazuje v seznamu osob.  

## Acceptance Criteria

- Osoba musí být odstraněna ze seznamu osob po kliknutí na **„Odstranit“** a potvrzení akce.
- Pokud osoba zůstane v seznamu, jedná se o chybu a test je neúspěšný.
- Po smazání nesmí být osoba dohledatelná ani přes vyhledávání.

## Actual Result

### Pozitivní scénář

Testování selhalo.
- Po kliknutí na tlačítko **„Odstranit“** osoba zmizí ze seznamu osob. Po obnovení stránky se zde však znovu objeví.

### Negativní scénář

Testování bylo úspěšné. 
- Osoba zůstane v seznamu osob.

---

## Linked work items

- [**BUG-002** – Osoba není trvale odstraněna po kliknutí na tlačítko **„Odstranit“**](../BugReports/BUG002_SmazaniOsoby.md)
