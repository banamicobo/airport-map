# APM — Airport Map
**Kod projektu:** APM
**Repo:** https://github.com/banamicobo/airport-map

---

## Stan obecny
Mapa 40+ lotnisk świata (Leaflet.js, CartoDB dark tiles). Złote markery = A380-capable, niebieskie = standard. Hover tooltip z danymi + linki Wikipedia/Flightradar24. Kalkulator great-circle distance. Pulsująca granica Polski. Dodane WAW (Warsaw Chopin, nie-A380).

---

## /btw — Pomysły i notatki

### Funkcje do dodania
- Filtrowanie po regionie / linii lotniczej
- Wyszukiwarka lotnisk
- Tryb "moja trasa" — zapisz kilka lotów i podsumuj dystans
- Statystyki: łączny dystans wszystkich tras A380 na mapie

### Techniczne
- Zoom: aktualnie blokada górna/dolna (minZoom z wysokości ekranu), poziomo mapa się powtarza jak Google Maps
- `noWrap` usunięty celowo — user preference

---
*Ostatnia aktualizacja: 2026-04-26*
