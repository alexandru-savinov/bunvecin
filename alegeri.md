# Alegerile

Aici stau soluțiile cântărite, cu motivul scris. O alegere fără motiv scris nu e
alegere, e obicei.

Grila e cea din README: **există deja · nu cere date personale · poate fi luată
și dusă mai departe · costă cât suportă o asociație · poate fi refuzată.**

Fiecare rând poartă și **cât de tare e verificat**. „După documentația
proiectului" nu e același lucru cu „citit în cod". Nimic de aici n-a fost auditat
în cod.

---

## Ce am căutat și n-am găsit (28 august 2026)

Am căutat software liber pentru asociații de proprietari în cinci limbi —
engleză, spaniolă (*administración de fincas*), italiană (*amministratore di
condominio*), rusă (*ЖКХ, ТСЖ*), poloneză (*wspólnota mieszkaniowa*).

**Nu există nimic care să publice AGREGAT prin construcție.** Tot ce am găsit e
registru pe apartament: numele omului, numărul apartamentului, cât a plătit
fiecare. Unde există publicare, ea e un raport SCOS din registrul pe apartament —
niciodată o poartă care are dreptul să spună nu.

Motivul e structural, și merită spus: **produsele astea se vând
ADMINISTRATORULUI**, iar treaba administratorului e factura pe apartament. Cine
plătește hotărăște modelul de date. Nimeni nu construiește agregat-întâi fiindcă
cine ar avea de câștigat — locatarii — nu e clientul. Golul ăsta nu se închide
singur.

De-aia **banii la vedere** a trebuit scris. Până acum era o presupunere; acum e
verificat pe patru comunități lingvistice, fără contraexemplu.

| Ce e | Licență | Server? | Date personale? | Verdict |
|---|---|---|---|---|
| **KondoManager** | AGPL-3.0 | da, auto-găzduit (Laravel/Vue/MySQL) | **DA** — nume, apartamente, plăți per unitate | pică pe regula 1. Cel mai apropiat pe „poate fi dus mai departe" (AGPL, explicit anti-abonament), dar arhitectura e registru-întâi |
| **Condo** (open-condo-software) | MIT | da, stivă grea (Postgres/Redis/Node/Python) | **DA** — contacte, plăți per apartament, tichete | pică pe regula 1 și pe „fără om de IT" |
| ТСЖ/ЖКХ rusești (Контур, ДомУчет, GKH365) | comerciale | serviciu | DA | pică pe tot |
| programa-comunidades | **neverificat** | ? | ? | găsit, nedeschis — nu ghicesc |

---

## Ce se poate lua gata

| Ce e | Pentru ce | Licență | Server? | Cere identitate? | Verdict |
|---|---|---|---|---|---|
| **Frictionless / Fiscal Data Package** | validarea tabelelor, forma canonică a datelor fiscale | MIT (cod) | **nu** — specificație + unealtă locală | nu | **intră.** Stratul de validare de sub documentul lunar. Fără server, licență curată |
| **Microsoft Presidio** | găsește date personale în text liber | MIT *(după descrierea depozitului, nedeschis)* | nu — bibliotecă locală | nu | **intră, dar mărginit** — vezi mai jos |
| **Decidim** | decizii, adunări, buget participativ | AGPLv3 | **da**, Rails | da, iar votul cere identitate | licență potrivită, greutate nepotrivită. Un bloc nu ține un Rails în picioare fără om de IT |
| **Consul Democracy** | idem, din Madrid | AGPLv3 | **da**, Rails/Postgres/Redis | **votul cere identitate verificată** | idem |
| **Loomio** | discuție + decizie, mai ușor | liber, dar și SaaS | auto-găzduit sau la ei | cont pentru fiecare participant | cel mai ușor din cele trei. Rămâne de verificat dacă merge cu conturi ne-identificatoare |

### Unde e locul lui Presidio, exact

Presidio **caută** date personale după ce au fost scrise. Poarta noastră face
altceva: **nu le lasă să existe.** Dacă modelul de date nu are niciodată sume pe
apartament, nu are ce găsi niciun detector.

Deci Presidio nu e paznicul. E **a doua opinie**, și numai pe câmpurile de text
liber (notele), unde un om poate scrie din greșeală un nume. Propria lui
documentație spune că nu garantează că le găsește pe toate — deci a-l pune ca
singură apărare ar fi exact greșeala pe care regula 1 o interzice.

**Construcția bate detecția.** Detecția e centura de siguranță, nu frâna.

---

## Cum intră ceva aici

Modelul e luat de la registrul **Digital Public Goods Alliance**, care are trei
însușiri de copiat:

1. **Criteriile sunt scrise ÎNAINTE de candidați.** Ale noastre sunt în README,
   scrise înainte să fi cântărit ceva.
2. **Propunerea e deschisă oricui** — la noi, prin Issues.
3. **Cine judecă nu e cine propune.**

**A treia n-o avem, și n-o ascund:** azi propunătorul și judecătorul sunt același
om. La o asociație și un proiect de o zi, e firesc. Dar e o slăbiciune cunoscută,
scrisă aici ca să nu treacă drept virtute.

## Ce nu s-a verificat

`programa-comunidades` (licență, model de date) · Loomio (efortul de
auto-găzduire, dacă suportă conturi ne-identificatoare) · licența Presidio, citită
din descriere, nu din depozit · criteriile de achiziție ale FSFE „Public Money?
Public Code!" · mecanica listelor `awesome-*` și a stivelor municipale.
