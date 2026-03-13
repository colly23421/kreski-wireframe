# CLAUDE.md — Kreski Wireframe

> Kontekst techniczny projektu. Dane biznesowe i umowy → ~/.claude/CLAUDE.md (globalny, poza repo).

---

## Repo i podgląd

- **Repo:** https://github.com/colly23421/kreski-wireframe.git
- **Live:** https://kreski-wireframe.vercel.app
- **Git:** user.email "piotr@collytics.io" / user.name "Collytics"
- **Deploy:** Vercel auto-deploy po push na `main`

---

## Struktura plików

```
index.html          → Strona główna
kategoria.html      → Widok kategorii (AUTO ID)
subkategoria.html   → Listing z filtrami sidebar + grid produktów
produkt.html        → Karta produktu
kontakt.html        → Strona kontaktowa z formularzem
```

**Zasada budowy:**
- Każdy plik = pełna strona (header nav + breadcrumb + content + footer)
- Shared header = tylko nav z mega-menu (BEZ hero/contentu strony głównej!)
- Shared footer = tylko stopka (BEZ contentu innych stron!)
- Czarny pasek nawigacyjny na dole każdej strony (Wireframe v4)

---

## Design System

| Element | Wartość |
|---------|---------|
| Czerwień | `#e30613` (z logo) |
| Czerń | `#1a1a1a` |
| Tło | `#ffffff` |
| Akcenty | Czerń i czerwień TYLKO jako akcenty |
| Font UI | `sans-serif` (Courier tylko w `.ptitle`) |

Styl: Business Professional, B2B, industrial/tech. NIE dark, NIE agresywny.

---

## Nawigacja (mega-menu 3 poziomy)

**L1:** Produkty | Usługi | Serwis | Centrum wiedzy | O firmie | Kontakt

**Produkty → L2:**
1. AUTO ID (11 subkategorii)
2. Akcesoria
3. Materiały eksploatacyjne
4. Rozwiązania dla przemysłu
5. Oprogramowanie
6. Infrastruktura IT
7. Monitoring i kontrola dostępu
8. Bezpieczeństwo IT

**Serwis** = osobny L1 (nie pod Produkty).
Pełna struktura L3 → plik `Kategorie__subkategorie_-_description.xlsx`.

---

## Ustalenia UX z meetingu

- Kafelki = klikalne całą powierzchnią (bez osobnych buttonów)
- 3. poziom menu: URL-based, nie onclick
- Layout strony głównej: 9 kafelków → zdjęcie → branże → partnerzy na dole
- Responsywność: poprawki na monitorach 15–17"
- Warianty/part numbery: jeden produkt, wiele SKU, bez osobnych URL-i
- Filtry i SKU edytowalne w CMS
- Floating contact menu: do dodania

---

## Karta produktu (produkt.html)

Zakładki:
1. Opis produktu
2. **SKU / Warianty** ← obowiązkowa, tabela part numerów z radio buttons
3. Specyfikacja techniczna
4. Pliki do pobrania

---

## Skala projektu (etap wdrożenia)

- ~1000 produktów do migracji
- ~3500 URLi do przekierowań 301
- `Crawl_kreski_pl.xlsx` — ~6000 URLi z obecnego serwisu
- `Kategorie__subkategorie_-_description.xlsx` — 997 wierszy, meta/frazy
- Obecny CMS: własny (nie WP), URL-e kończą się na `.html`
- Docelowy: szablon ThemeForest + modyfikacje

---

## Backlog

- [ ] Responsywność 15–17" monitorów
- [ ] Floating contact menu
- [ ] Eksport produktów z CMS Marcina
- [ ] Skrypt mapowania URLi → 301
- [x] dev.kreski.pl na OVH (rekord A) ✓
- [x] Zakup szablonu ThemeForest ✓

---

## Git workflow

```bash
git add -A && git commit -m "opis" && git push origin main
# Vercel deploy automatycznie za ~30s
```
