# CLAUDE.md — Projekt Kreski.pl

> Plik kontekstowy dla Claude Code. Czytaj przed każdą sesją.

---

## 1. Kim jesteś i z kim pracujesz

Pracujesz z **Piotrem** (Collytics, piotr@collytics.io) — wykonawcą projektu.
Klient: **Marcin Maksymiuk** (marcin.maksymiuk@kreski.pl) — Kreski Sp. Jawna.

---

## 2. Repozytorium i podgląd

- **Repo:** https://github.com/colly23421/kreski-wireframe.git
- **Live:** https://kreski-wireframe.vercel.app
- **Git config:** user.email "piotr@collytics.io" / user.name "Collytics"
- **GitHub token:** zapisany lokalnie w git credentials (nie wklejaj tu — GitHub blokuje push)
- **Deployment:** Vercel — auto-deploy po każdym push na `main`

---

## 3. Co to za projekt

Redesign sklepu B2B **kreski.pl** — sprzedaż sprzętu Auto ID (Zebra, Honeywell, Datalogic).
Zakres prac:
- Etap I: Low-Fi wireframe (5 widoków HTML) ← **jesteśmy tutaj**
- Etap II: Projekt graficzny na bazie wireframe (bez oddzielnego etapu Hi-Fi — Marcin chce przejść prosto do dev)
- Etap III: Wdrożenie na szablonie ThemeForest (~$100), głęboka modyfikacja

**Ważne:** Marcin nie wie że to będzie szablon ThemeForest. To zostaje między nami.

---

## 4. Umowa i finanse

- Podpisana: 02.03.2026 | Zaliczka: 03.03.2026
- Etap I (Low-Fi makiety): deadline był 12.03.2026
- Stawka za prace dodatkowe: **200 zł netto/h**
- Kara umowna: 500 zł/dzień opóźnienia (max 30% wartości brutto)
- Wartość projektu: ~17 200 zł

**Zakres Low-Fi wg umowy (załącznik):**
1. Strona Główna
2. Kategoria
3. Subkategoria
4. Karta produktu
5. Kontakt

---

## 5. Struktura plików wireframe

```
index.html          → Strona główna
kategoria.html      → Widok kategorii (AUTO ID)
subkategoria.html   → Listing z filtrami sidebar + grid produktów
produkt.html        → Karta produktu (omawiana osobno z Marcinem)
kontakt.html        → Strona kontaktowa z formularzem
```

**Zasada budowy plików:**
- Każdy plik = pełna strona (header + breadcrumb + content + footer)
- Shared header: nav z mega-menu (wyciągnięty z index.html do ~wiersza 17920)
- Shared footer: stopka (tylko stopka, BEZ contentu innych stron!)
- Na dole każdej strony: czarny pasek nawigacyjny z linkami do wszystkich 5 widoków (Wireframe v4)
- **UWAGA:** Nie wrzucaj hero/contentu strony głównej jako "shared header" — to był częsty błąd w tej sesji

---

## 6. Design System

| Element | Wartość |
|---------|---------|
| Czerwień | `#e30613` (z logo, nie #CC0000) |
| Czerń | `#1a1a1a` |
| Tło | `#ffffff` (białe) |
| Akcenty | Czerń i czerwień TYLKO jako akcenty, nie dominujące tło |
| Font UI | `sans-serif` (nie Courier — Courier tylko w `.ptitle` etykiecie wireframe) |

**Styl:** Business Professional, B2B, industrial/tech. NIE dark, NIE agresywny.

---

## 7. Struktura nawigacji (mega-menu 3 poziomy)

### L1 (navbar):
Produkty | Usługi | Serwis | Centrum wiedzy | O firmie | Kontakt

### Produkty → L2 → L3:
1. **AUTO ID** → Czytniki kodów, Drukarki etykiet, Drukarki kart, Terminale przenośne, Terminale wózkowe, Weryfikatory kodów, Weryfikatory cen, Aplikatory etykiet, Wearables, RFID, Systemy wizyjne
2. **Akcesoria** → Baterie i ładowarki, Futerały, Stacje dokujące, Uchwyty, Przewody
3. **Materiały eksploatacyjne** → Etykiety, Taśmy, Ribbony, Karty plastikowe
4. **Rozwiązania dla przemysłu** → Tablety, Komputery przemysłowe, Notebooki, Kioski, ATEX, Systemy kontrolno-pomiarowe
5. **Oprogramowanie** → (9 pozycji: etykiety, MDM, aplikacje mobilne, dedykowane, Migracja z WiNG, bezpieczeństwo)
6. **Infrastruktura IT** → Sieci, Switche, Access Pointy, Serwery, UPS
7. **Monitoring i kontrola dostępu** → Kamery IP, Kontrola dostępu
8. **Bezpieczeństwo IT** → NGFW, IPS, DLP, Email Security, Web Security, Backup, Zarządzanie IT, SSE

### Serwis (osobny L1):
Zgłoszenie naprawy (CTA), Gwarancja i ochrona, Serwis mobilny, Sprzedaż części, FAQ

### Usługi:
Wdrożenia i integracje | Wsparcie i szkolenia

### Centrum wiedzy:
Artykuły, Pliki do pobrania, Realizacje

### O firmie:
O nas, Nasi partnerzy (kafelki ~17 brandów), Kariera

---

## 8. Ustalenia UX z meetingu z Marcinem

- **Kafelki = klikalne całą powierzchnią** — bez osobnych buttonów wewnątrz
- **Hero:** kontrast na mobile do poprawy
- **3. poziom menu:** URL-based (nie onclick)
- **Layout strony głównej:** 9 kafelków oferty → zdjęcie (przełamanie) → branże → partnerzy na dole
- **Responsywność:** poprawki na monitorach 15–17" (layout za szeroki)
- **Warianty/part numbery:** jeden produkt, wiele SKU, bez osobnych URL-i
- **Filtry i SKU:** edytowalne w CMS
- **Floating menu kontaktowe:** do dodania
- **Karta produktu:** musi mieć zakładkę SKU/Warianty

---

## 9. Karta produktu — szczegóły (produkt.html)

Ten plik był omawiany osobno z Marcinem przed integracją z resztą.
Zakładki (`.tabs-nav`):
1. Opis produktu
2. **SKU / Warianty** ← obowiązkowa, tabela part numberów z radio buttons
3. Specyfikacja techniczna
4. Pliki do pobrania

**SKU module:** tabela (Part Number, Interfejs, Kolor, W zestawie, Uwagi) + nota że warianty nie generują osobnych URL-i.

---

## 10. Skala projektu (etap wdrożenia)

- ~1000 produktów do migracji z obecnego CMS
- ~3500 URLi do przekierowania (301) pod SEO
- Plik z crawlem: `Crawl_kreski_pl.xlsx` (~6000 URLi, wiele duplikatów)
- Plik ze strukturą kategorii: `Kategorie__subkategorie_-_description.xlsx` (997 wierszy, meta title/description/frazy)
- ~280 stron bez tytułu i meta description
- Migracja SEO: przekierowania tematycznie spójne (kategoria→kategoria, produkt→produkt)
- Obecny CMS Kreski: własny (nie WordPress), URL-e kończą się na `.html`

---

## 11. Partnerzy / Producenci

50+ brandów: Zebra, Honeywell, Datalogic, Toshiba, SICK, GoDEX, Newland, TSC, Citizen, Intermec, CipherLab, Champtek, i in.
Osobna podstrona `/partnerzy` — nie element mega-menu.

---

## 12. Polecenia git dla tego projektu

```bash
# Standard commit i push
git add -A
git commit -m "opis zmian"
git push origin main

# Sprawdź status
git log --oneline -5
```

Vercel automatycznie deployuje po push na `main`. Podgląd live za ~30s.

---

## 13. Rzeczy do zrobienia (backlog)

- [ ] Poprawki responsywności na 15–17" monitorach
- [ ] Floating contact menu
- [ ] Potwierdzić z Marcinem które dokładnie 4 strony były w oryginalnym zakresie
- [ ] Kupić szablon ThemeForest (~$100) i zainstalować na `dev.kreski.pl`
- [ ] Subdomena dev.kreski.pl na OVH (rekord A → ten sam IP co kreski.pl)
- [ ] Eksport produktów z obecnego CMS Marcina (status nieznany)
- [ ] Skrypt mapowania URLi do przekierowań 301
- [ ] Potwierdzić podsumowanie Fireflies od Mateusza

---

## 14. Inne projekty Piotra (kontekst)

- **Collytics** (collytics.io) — własna firma Piotra, marketing AI
  - Repo: https://github.com/colly23421/collytics-static.git
  - Aktywna kampania Meta Ads "Audyt AI | LPV | PL | 2026-03"
- **ILT** (kancelarialt.pl + iltksiegowosc.pl) — GTM → Stape → Meta CAPI (niestabilne)
