# Portfolio manuálního testování

Tento repozitář obsahuje ukázky **testovacích případů (Test Cases)** a **hlášení nalezených chyb (Bug Reports)**, které jsem vytvořila během manuálního testování webové aplikace pro správu osob a faktur.

Aplikace byla testována v lokálním vývojovém prostředí. Testovací případy i bug reporty byly během testování evidovány v nástroji **Jira**. Kromě testování uživatelského rozhraní (frontend) jsem ověřovala také funkčnost **REST API** pomocí nástroje **Postman**.

## Struktura repozitáře

```
.
├── README.md
├── TestCases
│   ├── TC001_PridaniNoveOsoby.md
│   ├── TC002_SmazaniOsoby.md
│   └── TC003_EditaceFaktury_API.md
├── BugReports
│   ├── BUG001_PridaniNoveOsoby.md
│   ├── BUG002_SmazaniOsoby.md
│   └── BUG003_EditaceFaktury_API.md
└── Screenshots
    └── Postman
        ├── TC003_GET_OvereniFaktury.PNG
        └── TC003_PUT_EditaceFaktury.PNG
```

## Přehled aplikace

Testovaná aplikace obsahuje dva hlavní moduly:

- **Osoby**
- **Faktury**

---

## Modul Osoby

Modul **Osoby** umožňuje:

- vytvářet nové osoby,
- zobrazovat detail osoby,
- upravovat údaje osob,
- mazat osoby,
- spravovat seznam osob.

---

## Modul Faktury

Modul **Faktury** umožňuje:

- vytvářet nové faktury,
- zobrazovat detail faktury,
- upravovat existující faktury,
- mazat faktury,
- filtrovat faktury podle zadaných kritérií,
- zobrazovat seznam faktur.

---

## Oblasti testování

Ukázky dokumentace zahrnují zejména:

- funkční testování,
- pozitivní i negativní testovací scénáře,
- validaci vstupních dat,
- CRUD operace,
- filtrování dat,
- navigaci v aplikaci,
- testování REST API pomocí Postmanu,
- evidenci nalezených chyb v Jira.

--- 

## Získané zkušenosti

- Návrh a tvorba testovacích případů (Test Cases)
- Tvorba bug reportů
- Manuální testování webové aplikace
- Testování REST API pomocí Postmanu
- Testování CRUD operací
- Pozitivní a negativní testování
- Validace formulářů
- Tvorba testovací dokumentace v Markdown
- Používání Gitu a GitHubu pro správu verzí

---

## Použité nástroje

- **Google Chrome** – testování webové aplikace
- **Jira** – evidence testovacích případů a bug reportů
- **Postman** – testování REST API
- **REST API** – testování endpointů metodami GET a PUT
- **Markdown** – tvorba dokumentace (README, Test Cases, Bug Reports)
- **Git & GitHub** – správa verzí a publikace portfolia

## Ukázky testování REST API

Součástí portfolia jsou také ukázky testování REST API vytvořené v nástroji **Postman**.

Testování zahrnovalo zejména:

- vytváření a organizaci Postman kolekcí,
- testování endpointů pomocí metod **GET**, **POST**, **PUT** a **DELETE**,
- ověřování HTTP stavových kódů,
- validaci odpovědí serveru,
- testování pozitivních i negativních scénářů.

### Editace faktury – metoda PUT

![PUT Invoice](Screenshots/Postman/TC003_PUT_EditaceFaktury.PNG)

Ukázka testování API endpointu pro editaci faktury pomocí metody **PUT**.

### Ověření změny – metoda GET

![GET Invoice](Screenshots/Postman/TC003_GET_OvereniFaktury.PNG)

Ověření provedené změny pomocí metody **GET**.

---

## Účel repozitáře

Cílem tohoto repozitáře je prezentovat ukázky mé práce v oblasti manuálního testování, tvorby QA dokumentace a testování webových aplikací.
