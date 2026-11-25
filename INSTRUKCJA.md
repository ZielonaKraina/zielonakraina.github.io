# Zielona Kraina – instrukcja

Ten plik nie pojawia się na blogu. To ściąga do prowadzenia strony.

---

## 1. Publikacja bloga (jednorazowo)

1. Wejdź na **github.com/new**.
2. W polu **Repository name** wpisz dokładnie `zielonakraina.github.io`.
3. Zaznacz **Public** i kliknij **Create repository**.
4. Na stronie pustego repozytorium kliknij link **uploading an existing file**.
5. Rozpakuj pobraną paczkę na komputerze. Otwórz folder `zielonakraina`, zaznacz wszystko w środku (Ctrl+A) i **przeciągnij** na stronę GitHuba. Foldery trzeba przeciągnąć, przycisk „choose your files” ich nie wgra.
6. Poczekaj, aż wszystkie pliki się wczytają, i kliknij **Commit changes**.
7. Wejdź w **Settings → Pages**. W sekcji **Build and deployment** ustaw **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)** i kliknij **Save**.
8. Po 1–3 minutach blog będzie pod adresem **https://zielonakraina.github.io**. Postęp widać w zakładce **Actions**.

---

## 2. Nowy artykuł

1. W repozytorium kliknij **Add file → Create new file**.
2. W polu nazwy wpisz `_posts/` (folder utworzy się sam), a potem nazwę pliku w formacie:

   `RRRR-MM-DD-adres-artykulu.md`

   Przykład: `2026-12-01-jak-podlewac-monstere.md`

   Adres artykułu będzie wtedy taki: `zielonakraina.github.io/jak-podlewac-monstere/`
   W nazwie pliku używaj małych liter, myślników i **bez polskich znaków**.

3. Wklej na górę pliku ten szablon i uzupełnij:

```
---
title: "Tytuł widoczny na stronie (H1)"
seo_title: "Meta title do ok. 60 znaków"
description: "Meta description do ok. 155 znaków"
category: Pielęgnacja
image: /assets/img/nazwa-zdjecia.jpg
image_alt: "Opis zdjęcia dla Google i czytników ekranu"
---

Tu zaczyna się wstęp artykułu.

## Nagłówek H2

Tekst.
```

4. Kliknij **Commit changes**. Artykuł pojawi się na blogu po 1–2 minutach.

**Ważne**
- Wartości w szablonie zostaw w cudzysłowach.
- `seo_title`, `image` i `image_alt` są opcjonalne. Jeśli nie ma `seo_title`, meta title to tytuł + nazwa bloga.
- Kategorię wpisuj zawsze tak samo, np. Pielęgnacja, Problemy i choroby, Gatunki roślin. Na dole artykułu pokazują się inne teksty z tej samej kategorii.
- Data w nazwie pliku nie może być z przyszłości, bo wtedy artykuł się nie pokaże.
- Po aktualizacji starego tekstu dopisz w szablonie linię `last_modified_at: 2026-12-15`. Data aktualizacji pokaże się pod tytułem i trafi do danych dla Google.

---

## 3. Formatowanie tekstu (Markdown)

| Co | Jak wpisać |
|---|---|
| Nagłówek H2 | `## Nagłówek` |
| Nagłówek H3 | `### Nagłówek` |
| Pogrubienie | `**tekst**` |
| Link | `[tekst linku](https://adres.pl)` |
| Link wewnętrzny | `[tekst linku](/adres-artykulu/)` |
| Lista | `- punkt` w każdej linii |
| Lista numerowana | `1. punkt` |
| Wskazówka w zielonej ramce | `> tekst wskazówki` |
| Zdjęcie | `![opis zdjęcia](/assets/img/nazwa.jpg)` |

**Spis treści** generuje się sam z nagłówków. Wklej w miejscu, gdzie ma się pojawić:

```
* Spis treści
{:toc}
```

**Tabela**

```
| Roślina | Podlewanie |
|---|---|
| Nazwa | Opis |
```

H1 robi się sam z `title`, więc w treści zaczynaj od `##`.

---

## 4. Zdjęcia

1. Wejdź do folderu `assets/img` w repozytorium.
2. Kliknij **Add file → Upload files** i wgraj zdjęcie.
3. Przed wgraniem zmniejsz zdjęcie do ok. 1200 px szerokości i skompresuj, np. na squoosh.app (format WebP albo JPG).
4. Nazwa pliku małymi literami, bez polskich znaków, opisowa, np. `monstera-zolte-liscie.webp`.
5. Używaj własnych zdjęć albo zdjęć z darmowych banków z licencją do użytku komercyjnego, np. Unsplash, Pexels.

---

## 5. Google Search Console

1. Wejdź na **search.google.com/search-console** i kliknij **Dodaj usługę**.
2. Wybierz **Prefiks URL** i wpisz `https://zielonakraina.github.io/`.
3. Jako metodę weryfikacji wybierz **Tag HTML**. Skopiuj tylko wartość z `content="..."`, bez cudzysłowów.
4. W repozytorium otwórz plik `_config.yml` i kliknij ikonę ołówka (edycja).
5. Znajdź te linie:
   ```
   # webmaster_verifications:
   #   google: TU_WKLEJ_KOD
   ```
   Usuń `# ` z początku obu linii (druga linia musi zaczynać się od dwóch spacji) i wklej kod w miejsce `TU_WKLEJ_KOD`.
6. Kliknij **Commit changes**, poczekaj 2–3 minuty i kliknij **Zweryfikuj** w GSC.
7. W GSC wejdź w **Mapy witryn**, wpisz `sitemap.xml` i kliknij **Prześlij**.

---

## 6. Google Analytics 4

1. Wejdź na **analytics.google.com** i utwórz konto oraz usługę dla bloga.
2. Dodaj strumień danych **Sieć** z adresem `https://zielonakraina.github.io`.
3. Skopiuj **Identyfikator pomiaru** (zaczyna się od `G-`).
4. W `_config.yml` znajdź linię `# google_analytics: G-XXXXXXXXXX`, usuń `# ` i wpisz swój identyfikator.
5. Zapisz zmiany. Na blogu pojawi się baner zgody na cookies. GA4 zbiera dane tylko od osób, które klikną „Akceptuję”.

---

## 7. Do uzupełnienia na start

- `o-blogu.md` – tekst o blogu w miejscu nawiasów kwadratowych.
- `polityka-prywatnosci.md` – kontakt. Najlepiej załóż osobny e-mail dla bloga.
- `_config.yml` – opis bloga (`description`), jeśli chcesz go zmienić.

## Co jest już ustawione pod SEO

- meta title i meta description dla każdej strony
- tagi Open Graph i Twitter (podgląd linku w social mediach)
- dane strukturalne BlogPosting i BreadcrumbList (schema.org)
- automatyczna mapa witryny `sitemap.xml` i plik `robots.txt`
- adresy kanoniczne (canonical)
- przyjazne adresy URL bez dat
- ścieżka nawigacji (breadcrumbs) i powiązane artykuły z tej samej kategorii
- kanał RSS `feed.xml`
- szybkie ładowanie bez zewnętrznych czcionek i bibliotek
- wersja mobilna
