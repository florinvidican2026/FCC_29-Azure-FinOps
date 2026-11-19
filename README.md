# FCC_29 – Gestionarea și optimizarea costurilor în Azure

**Disciplina:** Fundamentele Cloud Computing  
**Student:** VIDICAN ADRIAN FLORIN  
**Grupa:** 301  
**Platforma:** Microsoft Azure  
**Abonament:** Azure for Students

## 1. Descrierea proiectului

Proiectul FCC_29 urmărește implementarea unor mecanisme de monitorizare, control și optimizare a costurilor serviciilor cloud utilizând platforma Microsoft Azure.

Scopul principal este gestionarea eficientă a resurselor cloud, prin aplicarea etichetelor, configurarea bugetelor, monitorizarea consumului și identificarea oportunităților de reducere a costurilor.

## 2. Obiectivele proiectului

1. Aplicarea etichetelor (tags) pentru organizarea resurselor.
2. Configurarea unui buget lunar și a alertelor la 50%, 80% și 100%.
3. Analiza costurilor utilizând Azure Cost Management.
4. Verificarea recomandărilor Azure Advisor.
5. Estimarea costurilor cu Azure Pricing Calculator și compararea cu valorile reale.

## 3. Infrastructura Azure

Resursele au fost configurate în abonamentul Azure for Students.

| Componentă | Configurație |
|---|---|
| Resource Group | rg-cloud-finops |
| Storage Account | stcloudfinops2026 |
| Regiune | Sweden Central |
| Tip cont | StorageV2 |
| Performanță | Standard |
| Redundanță | LRS |
| Access tier | Hot |
| Blob Container | container-cloud-finops |
| Acces container | Private |

Configurația infrastructurii este disponibilă în fișierul `template.json`, exportat din Azure Portal în format ARM (Azure Resource Manager).

## 4. Etichetarea resurselor

Au fost aplicate următoarele etichete pe Resource Group și Storage Account:

| Etichetă | Valoare |
|---|---|
| proiect | CloudFinOps |
| mediu | Test |
| proprietar | Student |

Aceste etichete permit identificarea și gruparea resurselor pentru analiza costurilor.

## 5. Configurarea bugetului

A fost creat bugetul `budget-cloud-finops`, cu valoarea de **10 EUR/lună**.

Au fost configurate următoarele praguri de notificare:

- 50% – 5 EUR
- 80% – 8 EUR
- 100% – 10 EUR

Bugetul permite monitorizarea cheltuielilor, dar nu oprește automat resursele atunci când este depășit.

## 6. Analiza costurilor

Analiza a fost realizată în Azure Cost Management, la nivelul Resource Group `rg-cloud-finops`.

Au fost utilizate:
- Gruparea după eticheta `proiect`.
- Filtrarea după `proiect = cloudfinops`.
- Vizualizarea costurilor pentru noiembrie 2026.

La momentul verificării, costul real acumulat era sub **0,01 EUR**.

Vizualizarea filtrată a fost salvată în Azure Portal.

## 7. Azure Advisor

Azure Advisor a fost utilizat pentru verificarea recomandărilor de optimizare a costurilor.

Nu au fost identificate recomandări active pentru infrastructura existentă.

Optimizările pentru mașini virtuale, precum redimensionarea (right-sizing) și oprirea programată, sunt analizate teoretic. Nu au fost aplicate deoarece proiectul nu include mașini virtuale.

## 8. Azure Pricing Calculator

A fost realizată o estimare pentru serviciul Azure Storage, folosind următoarele caracteristici:

- Regiune: Sweden Central
- Performanță: Standard
- Tip: General Purpose V2
- Redundanță: LRS
- Access tier: Hot
- Capacitate estimată: 1 GB

**Cost lunar estimat: 0,02 USD.**

Costul real acumulat în Azure era sub 0,01 EUR la momentul verificării.

Valorile nu sunt direct comparabile deoarece sunt exprimate în monede diferite și acoperă perioade diferite. Unele componente de tarifare nu au fost disponibile în calculator.

## 9. Securitate

Au fost utilizate următoarele setări:

- Transfer securizat HTTPS.
- Versiune TLS minimă 1.2.
- Acces anonim la blob-uri dezactivat.
- Container privat.
- Protecție la ștergere pentru 7 zile.

## 10. Concluzii

Proiectul demonstrează utilizarea instrumentelor Azure pentru organizarea resurselor, controlul bugetului, monitorizarea costurilor și estimarea cheltuielilor cloud.

Au fost configurate și verificate mecanismele de etichetare, bugetare și analiză a costurilor. Azure Advisor nu a generat recomandări active, iar optimizările VM au rămas la nivel teoretic.

## 11. Fișierele proiectului

- `README.md` – documentația generală.
- `template.json` – configurația ARM exportată din Azure.

Capturile de ecran și documentația suplimentară vor fi adăugate ulterior.

## 12. Referințe

- [Microsoft Azure Cost Management](https://learn.microsoft.com/en-us/azure/cost-management-billing/)
- [Microsoft Azure Advisor](https://learn.microsoft.com/en-us/azure/advisor/)
- [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- [Azure Resource Manager Templates](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview)
