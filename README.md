# ukw-bipg-thesis

Szablon Typst pracy licencjackiej i magisterskiej dla kierunku **Badanie i Projektowanie Gier**
(Wydział Nauk o Kulturze, Uniwersytet Kazimierza Wielkiego w Bydgoszczy), zgodny z
*Regulaminem dyplomowania* zatwierdzonym przez Radę Kolegium I 27 stycznia 2026 r.

## Szybki start

```bash
typst init @preview/ukw-bipg-thesis:0.1.0 moja-praca
cd moja-praca
typst watch main.typ
```

## Co szablon robi automatycznie

| Wymóg regulaminu | Realizacja |
|---|---|
| §2 ust. 1 — język polski albo angielski | `lang: "pl"` / `"en"` (przełącza też nazwy spisów) |
| §2 ust. 2 — A4, Times New Roman 12 pkt, interlinia 1½, marginesy 2,5 cm, justowanie | ustawienia `page` / `text` / `par` |
| §2 ust. 3 — wydruk dwustronny | układ dwustronny; `draft: true` na czas pisania |
| §2 ust. 4 — jednolita numeracja, ciągłe przypisy, rozdziały od strony nieparzystej | `heading` + `pagebreak(to: "odd")`, `footnote` z numeracją ciągłą |
| §2 ust. 5a — strona tytułowa (zał. 2) | generowana z metadanych |
| §2 ust. 5b — spis treści | `outline` |
| §2 ust. 5d — spis literatury | `bibliography-file` (BibTeX/Hayagriva) |
| §2 ust. 5e — spisy rysunków, tabel, wykresów | `list-of-figures`, `list-of-tables` |
| §2 ust. 5f — streszczenie i słowa kluczowe (zał. 3) | `abstract`, `keywords` + licznik 1000 znaków |
| §2 ust. 5g — oświadczenie autora (zał. 1) | generowane z metadanych |

Numery kontrolne wydruku (§2 ust. 3a) pochodzą z systemu APD — dodaje się je do pliku
pobranego z APD, a nie w Typście.

## Parametry `ukw-thesis`

`title`, `subtitle`, `author`, `album`, `supervisor`, `field`, `study-type`,
`degree` (`"bachelor"` | `"master"`), `year`, `lang`, `abstract`, `keywords`,
`bibliography-file`, `bibliography-style`, `list-of-figures`, `list-of-tables`, `draft`.

## Uwagi praktyczne

- **Czcionka**: jeśli w systemie nie ma Times New Roman, szablon użyje TeX Gyre Termes
  (metrycznie zgodny). Do wydruku warto skompilować z zainstalowanym TNR:
  `typst compile --font-path ./fonts main.typ`.
- **Wydruk**: przed oddaniem ustaw `draft: false`, aby rozdziały zaczynały się od strony
  nieparzystej, a puste strony wersa były poprawnie wstawione.
- **AI**: wykorzystanie narzędzi sztucznej inteligencji regulują odrębne przepisy UKW
  (Zarządzenie Nr 34/2025/2026 Rektora UKW) — szablon niczego tu nie przesądza.
- **Załączniki**: `#zalacznik(1, "Tytuł")[treść]`.

## Publikacja w Typst Universe

Zawartość katalogu skopiuj do `packages/preview/ukw-bipg-thesis/0.1.0/` w forku repozytorium
[`typst/packages`](https://github.com/typst/packages), uzupełnij `repository` w `typst.toml`,
dodaj `thumbnail.png` (pierwsza strona przykładu, ≤ 1 MB, format PNG) i złóż pull request.

Licencja: MIT-0.
