# KrydderGutta.eb — statisk nettside

Dette repoet inneholder en enkel statisk nettside for KrydderGutta.eb. Filene ligger i branch `site`.

Filer i repo (branch `site`):
- `index.html` — hovedsiden (inkluderer skjema via Formsubmit)
- `styles.css` — styling
- `thankyou.html` — takk-side etter skjema-innsending

Hurtig: hvordan publisere (GitHub Pages)
1. Gå til: https://github.com/nickl19/Kryddergutta.eb
2. Velg fanen Settings → Pages (i venstremeny eller nederst på settings-siden).
3. Under "Source" velger du:
   - Branch: `site`
   - Folder: `/ (root)`
4. Klikk "Save" eller "Save and deploy".
5. Vent 1–10 minutter. Siden vil bli tilgjengelig på en URL som GitHub viser, vanligvis:
   `https://nickl19.github.io/Kryddergutta.eb/`

Formsubmit (kontaktskjema)
- Skjema i `index.html` sender til: `https://formsubmit.co/einar.rake@gmail.com`.
- Første gang noen sender et skjema vil Formsubmit sende en bekreftelses-e-post til `einar.rake@gmail.com`. Du må åpne den e-posten og trykke bekreftelse for å begynne å motta skjemaer.
- Når bekreftelsen er gjort blir alle fremtidige skjema-innsendelser videresendt til denne e-posten.

Bruke eget domene (anbefalt hvis du eier et domenenavn)
- GitHub Pages støtter egne domener med en gyldig TLD (f.eks. `.no`, `.com`, `.net`). Den TLD-en du forsøkte tidligere (`.eb`) er ikke en standard offentlig TLD og vil gi feilen "InvalidDomainError".

To vanlige oppsett:
1) Apex (eks: `kryddergutta.no`) — legg til disse A-records hos DNS-leverandøren din for domenets rot (ofte skrevet som @):
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153

2) Subdomene (eks: `www.kryddergutta.no`) — legg til en CNAME for `www` som peker til `nickl19.github.io`:
   - CNAME: `www` -> `nickl19.github.io`

Etter at DNS er lagt inn
- Vent på DNS-propagasjon (ofte noen minutter, av og til timer).
- Gå tilbake til Settings → Pages i repoet og trykk "Check again" eller trykk Save på nytt.
- Når GitHub verifiserer domenet blir HTTPS tilgjengelig (kryptering via GitHub). Huk av "Enforce HTTPS" for å tvinge HTTPS.

Hvordan legge til CNAME i repoet (valgfritt)
- Når du har et domene, kan jeg legge til en `CNAME`-fil i repo-roten for deg med domenet på én linje. F.eks:
  - Fil: `CNAME`
  - Innhold: `kryddergutta.no`
- Si hvilket domene du vil bruke (skriv det her), så legger jeg filen inn i branch `site`.

Testing og feilsøking
- Hvis du ser "DNS check unsuccessful" eller "InvalidDomainError":
  - Kontroller at domenet er registrert og at det bruker en gyldig TLD (ikke `.eb`).
  - Kontroller at DNS-records er lagt inn korrekt (A eller CNAME avhengig av oppsett).
  - Bruk verktøy som `dig` eller `nslookup` fra din maskin til å sjekke:
    - `dig +short A kryddergutta.no`
    - `dig +short CNAME www.kryddergutta.no`
- Eksempel (Windows): `nslookup -type=A kryddergutta.no`

Jeg kan gjøre følgende for deg i repoet
- Oppdatere README (ferdig gjort med denne committen).
- Legge til `CNAME`-fil hvis du oppgir domenet du har registrert.
- Legge til favicon / logo hvis du laster opp bilde-filen eller forteller meg URL.

Hva du må gjøre hos domeneregistratoren / DNS-leverandøren
1. Registrer et domenenavn med en gyldig TLD hvis du ikke allerede har gjort det (f.eks. kryddergutta.no).
2. Logg inn på DNS-innstillingene og legg inn A- eller CNAME-records som over.
3. Vent på propagasjon og aktiver Pages i repo-innstillingene.

Vil du at jeg nå:
- a) Legger til en `CNAME`-fil i branch `site` for et domenenavn du oppgir her, eller
- b) Bare beholder standard GitHub Pages-URL og eventuelt legger til favicon/logo?