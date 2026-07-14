# TC-002 – Smazání osoby

## Description

Testovací případ ověřuje, zda lze existující osobu úspěšně smazat a že se již neobjeví v seznamu osob.

## Preconditions

- V systému existuje alespoň jedna osoba se správně vyplněnými daty.
- Uživatel se nachází na obrazovce **„Osoby“**.

## Test steps

### Pozitivní scénář

1. Uživatel klikne v menu na **„Osoby“**.
2. Vybere existující osobu.
3. Klikne na tlačítko **„Odstranit“**.
4. Ověří, že se osoba již nezobrazuje v seznamu osob.
5. **Očekávaný výsledek:** Osoba byla úspěšně smazána a zmizela ze seznamu osob.

### Negativní scénář

1. Uživatel klikne v menu na **„Osoby“**.
2. Vybere existující osobu.
3. Klikne na tlačítko **„Odstranit“**.
4. **Chyba:** Osoba zůstane v seznamu osob i po pokusu o smazání.
5. **Očekávaný výsledek:** Osoba by měla být odstraněna ze seznamu osob.

## Expected Result

- Osoba je smazána a již se nezobrazuje v seznamu osob na stránce **„Osoby“**.
- Po smazání není možné osobu zobrazit ani upravovat.

## Acceptance Criteria

- Osoba musí být odstraněna ze seznamu osob po kliknutí na **„Odstranit“**.
- Pokud osoba zůstane v seznamu, jedná se o chybu a test je neúspěšný.
- Po smazání nesmí být osoba dohledatelná ani přes vyhledávání.

## Actual Result

### Pozitivní scénář

Testování selhalo. Po kliknutí na tlačítko **„Odstranit“** osoba zmizí ze seznamu osob. Po obnovení stránky se zde však znovu objeví.

### Negativní scénář

Osoba zůstane v seznamu osob.

---

## Linked work items

- [**BUG-002** – Osoba není trvale odstraněna po kliknutí na tlačítko **„Odstranit“**](../BugReports.md/BUG002_SmazaniOsoby.md)