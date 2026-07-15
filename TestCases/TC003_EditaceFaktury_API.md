# TC-003 – Editace faktury (API)

## Description

Testovací případ ověřuje, zda server umožňuje editovat fakturu přes API endpoint a ověřuje validaci povinných polí.

## Preconditions

Endpoint pro editaci faktury:

`http://localhost:8000/api/invoices/{invoice_id}`

## Test Steps

### Positive test scenario

1. Zvolte metodu **PUT** na endpoint `/api/invoices/1`.
2. Do těla požadavku vložte následující JSON s platnými daty:

```json
{
  "invoiceNumber": "98765",
  "seller": 1,
  "buyer": 2,
  "issued": "2024-01-10",
  "dueDate": "2024-02-10",
  "product": "Aktualizovaný produkt",
  "price": 1500.00,
  "vat": 21
}
```

3. Odešlete požadavek na server.

**Očekávaný výsledek:**

- Server vrátí odpověď s kódem **200 OK**.
- Tělo odpovědi obsahuje aktualizovaná data faktury.
- Faktura je aktualizována v databázi.

---

### Negative test scenatio

1. Odešlete **PUT** požadavek na endpoint `/api/invoices/1` s chybějícím polem **invoiceNumber**:

```json
{
  "seller": 1,
  "buyer": 2,
  "issued": "2024-01-10",
  "dueDate": "2024-02-10",
  "product": "Aktualizovaný produkt",
  "price": 1500.00,
  "vat": 21
}
```

2. Odešlete požadavek.

**Očekávaný výsledek:**

- Server vrátí odpověď s kódem **400 Bad Request**.
- Tělo odpovědi obsahuje chybovou hlášku:

```json
{
  "invoiceNumber": [
    "This field is required."
  ]
}
```

## Acceptance Criteria

- Uživatel musí být schopen editovat fakturu pouze při vyplnění všech povinných polí.
- Chybová hláška musí být jasná a odpovídat specifikaci API.
- Po úspěšné editaci musí být faktura aktualizována a dostupná přes endpoint **GET** `/api/invoices/{invoice_id}` se správně aktualizovanými údaji.

## Actual Result

### Positive test scenario

Testování selhalo.

- Server sice vrátí kód **200 OK**, ale neproběhne změna čísla faktury. Pole **invoiceNumber** zůstane původní. Ostatní položky jsou upraveny dle zadání.

### Negative test scenatio

Testování proběhlo úspěšně.

- Server vrátí odpověď s kódem **400 Bad Request**.
- Tělo odpovědi obsahuje chybovou hlášku:

```json
{
  "invoiceNumber": [
    "This field is required."
  ]
}
```  
## Linked work items

- [**BUG-003** – Editace faktury přes API](../BugReports/BUG003_EditaceFaktury_API.md)  

## Přílohy

### Postman – PUT požadavek

![PUT Editace faktury](../Screenshots/Postman/TC003_PUT_EditaceFaktury.PNG)

### Postman – GET ověření

![GET Ověření faktury](../Screenshots/Postman/TC003_GET_OvereniFaktury.PNG)
---

