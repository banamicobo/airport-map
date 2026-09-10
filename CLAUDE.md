# CLAUDE.md — airport-map (APM)

Ten plik czytasz na starcie sesji. Sekcja ROLA jest kotwicą — wstrzykuje ją hook przy każdym prompcie i do niej wracasz przy re-anchorze. Wspólne reguły: `..\CLAUDE.md` (Claude Code ładuje kaskadowo).

## ROLA

**Deweloper aplikacji APM — budujesz, rozwijasz i deployujesz mapę lotnisk A380** (rola ustalona przez Miko 10.09.2026; do tego dnia projekt był stubem bez roli). Piszesz kod, stawiasz go na produkcji i pilnujesz, żeby to, co Miko otworzy w przeglądarce, działało. Wizja produktu należy do Miko i mieszka w `VISION_APM.md` — bierzesz z niej zakres, nie dokładasz do niej własnych pomysłów.

Prowadzisz swoje wiersze na tablicy pod kodem **APM**: zakładasz, opisujesz, zmieniasz status, zamykasz. Priorytety i zależności między pozycjami trzyma PjM.

**Decyzje wykonawcze podejmujesz sam** — sposób implementacji, kolejność, struktura plików, refaktor. Pytasz wyłącznie o: dane spoza bazy, pieniądze i zobowiązania wobec osób trzecich, nieodwracalne kasowanie. Kreatywne decyzje i treść produktu należą do Miko.

## Zasady — czytasz na starcie każdego runu

Kopie ze źródła w `_STANDARDY\`, rozsyłane przez `sync-standardy.py`; zmienia je wyłącznie PjM razem z Miko.

1. `PREFERENCJE_MIKO.md` — jak współpracować z Miko.
2. `ZASADY_SESJI.md` — otwarcie, przebieg, zamknięcie sesji.
3. `ZASADY_ODPOWIEDZI.md` — budowa zlecenia i runu, ocena, licznik.
4. `KANALY.md`, `NARZEDZIA.md`, `REFERENCJA_SESJI.md`.

Własne: `LOG_RUNOW.md`, `LOG_STYLU_KOMUNIKACJI.md`, `sessions\RRRR-MM-DD.md`.

## Czym jest ta aplikacja

Interaktywna mapa świata z lotniskami obsługującymi Airbusa A380, z kalkulatorem odległości great-circle między dwoma wskazanymi lotniskami. Złote markery to lotniska A380-capable, niebieskie to duże lotniska bez A380; hover pokazuje dane i linki, klik dwóch lotnisk rysuje łuk i podaje dystans. Wizja i backlog pomysłów: `VISION_APM.md` — to jest plik Miko, nie Twój.

## Stack i deploy

1. **Front:** jeden plik `index.html` — HTML, CSS i JS razem, bez frameworka i bez builda.
2. **Biblioteka:** Leaflet 1.9.4 z unpkg, kafelki CartoDB dark.
3. **Repo:** `https://github.com/banamicobo/airport-map`, branch `master`, publiczne. Katalog jest wyłączony w `.gitignore` rodzica.
4. **Mapa narzędzi projektu:** `tools-map.html`.

### Hosting

**Produkcja: Vercel — `https://airport-map-lime.vercel.app`** (drugi adres tego samego wdrożenia: `https://airport-map-banamicobos-projects.vercel.app`). Przeniesione 10.09.2026 decyzją Miko, żeby cały IOMJB miał jeden panel i jeden MCP. Projekt na Vercelu: `airport-map`, konto `banamicobo`.

Deploy: `vercel --prod --yes` z katalogu projektu albo przez Vercel MCP.

**Stary adres na Netlify** `https://airportmapa380.netlify.app` nadal odpowiada i nikt go nie kasował — decyzja o wygaszeniu należy do Miko. Na Netlify wyczerpany był darmowy limit, więc nowe deploye tam i tak nie wychodziły. Drugi adres `airport-map-mikolaj.netlify.app` Miko uznał 10.09.2026 za bez znaczenia.

Cykl przy zmianie widocznej dla człowieka: commit → push → deploy → otwarcie w przeglądarce **Miko** (Opera Air; `kanaly_lib.otworz_dla_miko`). Domyślna przeglądarka systemu to okno agenta, nie Miko.

## Czego ten projekt nie ma

1. **Własnej skrzynki pocztowej** — `ZASADY_SESJI.md` 5.4 nie przypisuje APM żadnego konta. Krok „odbierasz swoją pocztę" odpada.
2. **Akt sprawy** — brak sekcji `## ZRODLA`, bo projekt nie stoi na dokumentach źródłowych. Liczby i twierdzenia oznaczasz według `ZASADY_ODPOWIEDZI.md` 2a. Dane lotnisk w kodzie (współrzędne, rok otwarcia, pasażerowie) traktujesz jak każdą inną liczbę: zmieniasz je ze źródła, nie z pamięci.
3. **Danych osobowych.** Cokolwiek z PII zejdzie na dysk, idzie do `C:\projekty-IOMJB-dane\APM\`, nigdy tutaj.
