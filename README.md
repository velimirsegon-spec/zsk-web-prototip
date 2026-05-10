# ZSK web — prototip v0.1

**Datum:** 2026-05-10
**Cilj:** Statički web za Zagrebačke sunčane krovove d.o.o. čiji je primarni cilj ispunjenje obveza prema Zakonu o pravu na pristup informacijama (NN 25/13, 85/15, 69/22), uz minimalan vizualni i tehnički otisak.

## Struktura

```
2026-05-10_zsk_web-prototype/
├── index.html                      # Naslovnica
├── o-nama.html                     # O društvu, struktura, vodstvo
├── dokumenti.html                  # ZPPI obvezne objave (9 sekcija)
├── pristup-informacijama.html      # Postupak, obrasci, rokovi
├── kontakt.html                    # Sjedište, OIB, IBAN, vodstvo
├── assets/
│   ├── css/style.css               # Sve stilove drži ovaj jedan file
│   └── img/logo.svg                # Placeholder logo (zelena + žuta)
├── dokumenti/                      # Folder za PDF dokumente (trenutno prazno)
└── README.md                       # ovaj file
```

**Bez build alata, bez baze, bez JS-a (osim native `<details>` accordion-a).** Sav HTML je statičan i može se otvoriti direktnim dvoklikom u pregledniku.

## Kako pregledati lokalno

Najjednostavnije: otvori `index.html` dvoklikom — radi u svakom browseru.

Ako želiš pravi local server (radi npr. mailto-linkova ili buduće provjere):
```bash
cd "Outbox/2026-05-10_zsk_web-prototype"
python3 -m http.server 8000
# zatim http://localhost:8000
```

## Što je već gotovo

| Stranica | Status | Napomena |
|---|---|---|
| Naslovnica | ✅ Skeleton | Hero blok + 4 kartice + lista najnovijih objava |
| O nama | ✅ Skeleton | Svrha, osnovni podaci, vodstvo |
| Dokumenti | ✅ Skeleton | 9 sklopljenih sekcija (statut, pravilnici, odluke, planovi, nabava, financije, revizija, izvješća skupštini, nepravilnosti) |
| Pristup informacijama | ✅ Skeleton | Službenik, postupak, rokovi (15+15), naknada, žalba, godišnja izvješća |
| Kontakt | ✅ Skeleton | Sjedište, identifikacija, banka, vodstvo |

## Što treba dopuniti — popis za Velimira

### Faktički podaci (označeni s `DOPUNITI` u stranici)
- [ ] **OIB** Zagrebačkih sunčanih krovova d.o.o.
- [ ] **MB / MBS** (matični broj)
- [ ] **NKD** (kod djelatnosti)
- [ ] **IBAN** (žiro-račun u ZABA)
- [ ] **Iznos temeljnog kapitala** (s posljednjom dokapitalizacijom)

Svi su dostupni u `Sudski_registar/` i `Akt_o_osnivanju_i_dokapitalizacija/` folderima u SharePointu (TAJNITVO/ZAGREBAČKI SUNČANI KROVOVI d.o.o).

### PDF dokumenti za objavu (označeni s `U PRIPREMI`)

Sljedeći PDF-ovi su placeholderi — datoteke trenutno ne postoje. Treba ih kopirati iz SharePointa u `dokumenti/` folder, pri čemu prije objave svaki dokument **mora proći tvoj pregled** (osobni podaci, poslovne tajne).

Prioritet 1 — temeljni dokumenti za ZPPI compliance:
- [ ] `akt-o-osnivanju.pdf` — Akt o osnivanju (pročišćeni tekst)
- [ ] `izjava-o-osnivanju.pdf` — postoji u SP-u: `Izjava o osnivanju Zagrebački sunčani krovovi d.o.o..pdf`
- [ ] `sudski-registar-izvod.pdf` — iz SP-a `Sudski_registar/`
- [ ] `plan-poslovanja-2026.pdf` — kad bude finaliziran (trenutno `Plan poslovanja 2026_ZSK_MM.doc` u `/sites/ZSK/01_Plan_poslovanja/`)
- [ ] `plan-poslovanja-2024.pdf` — postoji `Plan_poslovanja_2024_ZSK -ispravak_version-26.3.2024._final.xlsx` (treba PDF export)
- [ ] `plan-poslovanja-2023.pdf` — postoji `Plan_poslovanja_ZSK_2023.pdf`
- [ ] `plan-nabave-2026.pdf` — iz SP-a `Plan_nabave/`
- [ ] `registar-ugovora-2025.pdf` — iz SP-a `Ugovori/`
- [ ] `obrazac-zahtjev-pristup-informacijama.docx`/`.pdf` — standardni Povjerenikov predložak
- [ ] `dokapitalizacija-2024.pdf` — iz SP-a `Dokapitalizacija_2024/`

Prioritet 2 — pravilnici (svaki treba pregled prije objave):
- [ ] `pravilnik-o-radu.pdf`
- [ ] `pravilnik-jednostavna-nabava.pdf` (postoji u SP-u, retroaktivno potpisana 23.6.2025.)
- [ ] `pravilnik-sukob-interesa.pdf`
- [ ] `pravilnik-zastita-podataka.pdf`
- [ ] `pravilnik-zastita-prijavitelja.pdf`
- [ ] `pravilnik-arhiviranje.pdf`

Prioritet 3 — financije i revizija (objaviti tek nakon usvajanja od skupštine):
- [ ] `fi-godisnje-2025.pdf`
- [ ] `fi-godisnje-2024.pdf`
- [ ] `fi-godisnje-2023.pdf`
- [ ] `revizija-2025.pdf`
- [ ] `revizija-2024.pdf`
- [ ] `izvjesce-skupstina-gz-2025.pdf` (Burićev draft od 8.5.2026.)
- [ ] `izvjesce-nepravilnosti-2025.pdf`
- [ ] `zppi-izvjesce-2025.pdf` — Izvješće Povjereniku (rok 31.1. za prethodnu godinu — ovo je već trebalo biti)

### Vizualni elementi koje treba zamijeniti

- [ ] **Logo** — trenutno je placeholder SVG s 4 kvadrata. Pravi logo treba izvući iz Burićevog email-potpisa (postoji u inline atachmentu — mogu dohvatiti kasnije) ili iz SP-a `ZSK.zip`.
- [ ] **Boje** — trenutno `#F2C200` (žuta) + `#4FA340` (zelena). Mogu se ugoditi prema točnim brand-bojama kad ih budemo imali.
- [ ] **(Opcionalno)** Generička fotografija sunčane elektrane na hero-bloku naslovnice — sada nema slike, samo tekst.

## Otvorena pitanja koja čekaju tvoju odluku

1. **Logo — pravi fajl.** Mogu ga izvući iz Burićevog potpisa kad budeš spreman, ili sam radije pogledaš `ZSK.zip` na SharePointu pa kopiraš PNG/SVG?
2. **Imenovanje službenika za informiranje.** Sada si v.d. (vršitelj dužnosti). Hoćeš li u slijedu donijeti formalnu odluku o imenovanju? Nije nužno za prototip, ali jest za pravnu cjelovitost objave. Predložak odluke mogu pripremiti.
3. **Domena `zagrebackisuncanikrovovi.hr`.** Istekla 19.4. — obnoviti ju i napraviti 301 redirect na `zsk.hr`, ili pustiti? (Sugestija: obnovi i preusmjeri, jer postoji eksterna upućivanja na nju u nekim ranijim dokumentima.)
4. **Hosting.** Najjednostavnije: GitHub Pages (besplatno, HTTPS automatski). Alternativno: Netlify, ili neki postojeći REGEA hosting. Trebaju li ti detaljne upute kad budemo na tom koraku?
5. **Analytics i kolačići.** Prijedlog: bez analytics-a → bez kolačića → bez cookie banner-a. Ako ti treba broj posjeta, koristit ćemo server-side log na hostingu. Slažeš li se?
6. **Politika privatnosti.** Trenutno nije dodana stranica. Ako se odlučimo za bez-kolačića pristup, dovoljan je kratki paragraf na dnu stranice „Pristup informacijama" + kontakt voditelja obrade. Da to dodam u sljedećoj iteraciji?

## Što ostaje za sljedeću iteraciju

1. Pregledat ćeš ovaj prototip u browseru, javit ćeš komentare na strukturu, jezik i izgled.
2. Dopunit ću faktičke podatke (OIB, MB itd.) izravno u HTML-u kad ih izvučemo iz SP-a.
3. Zamijenit ćemo placeholder logo s pravim, eventualno doraditi paletu.
4. Kopirat ćemo PDF-ove koje si potvrdio za objavu u `dokumenti/` folder.
5. Dodati politiku privatnosti / cookie napomenu (po potrebi).
6. Pripremit ću upute za hosting + (po želji) postaviti GitHub repo.

## Tehničke napomene

- **HTML5 semantika:** `<header>`, `<nav>`, `<main>`, `<footer>`, `<details>`/`<summary>`, ARIA labels.
- **Accessibility:** skip-link, fokus-stilovi, kontrast prema WCAG 2.1 AA, alt text na svim slikama.
- **Responsive:** prelama se na mobitel ispod 640&nbsp;px.
- **Bez vanjskih ovisnosti:** ne koristi Google Fonts, CDN-ove, jQuery, ništa. Sve je inline ili lokalno.
- **Veličina:** ukupno cca 30 KB HTML + CSS, brza naslovnica i bez ikakvog build koraka.
