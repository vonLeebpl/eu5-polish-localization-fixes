# CLAUDE.md

Mod do EU5 poprawiający polską lokalizację. Szczegóły w [README.md](README.md),
zasady pracy w [CONTRIBUTING.md](CONTRIBUTING.md).

## Pliki bazowe gry (referencja, tylko do odczytu)

`C:\SteamLibrary\steamapps\common\Europa Universalis V\game`

Układ taki sam jak w modzie: `game\main_menu\localization\polish\`,
`game\in_game\common\customizable_localization\country_name_construction.txt` itd.
Służą do sprawdzania nazw kluczy i waniliowych tłumaczeń. **Nie kopiować do repo**
(prawa autorskie Paradoksu).

## Format plików — krytyczne

- Pliki `*_l_polish.yml`, `.txt`, `.gui`: **UTF-8 z BOM**, końce linii **LF**.
  Nigdy nie zapisuj bez BOM — gra przestanie wczytywać plik.
- Nie przycinaj trailing whitespace w `.yml`/`.txt` (psuje wcięcia Paradoksa).
- Składnia wpisu `.yml`: ` KLUCZ: "wartość"` (spacja na początku linii). Zachowuj
  istniejący styl pliku — część plików Paradoksa używa `KLUCZ:0 "wartość"`.

## Struktura

- `main_menu/localization/polish/` — tłumaczenia
- `main_menu/localization/english/` — nadpisania kluczy `l_english`
- `in_game/common/customizable_localization/country_name_construction.txt` — logika odmiany nazw państw
- `plf_*` — pliki własne moda (prefiks `plf` = "polish localization fixes")
- `in_game/gui/` — nadpisania interfejsu

## Konwencje

- Commity po polsku, z prefiksem zakresu (`dop:`, `rząd:`, `event:`, `gui:`, `meta:`).
- Bez commitów „WIP”.
- Pliki robocze (`*.yml_copy`, `*.yml_oryg`, `_mid`) są ignorowane — nie dodawaj ich.
- Nowe formy dopełniacza → `plf_country_names_dop_l_polish.yml`, alfabetycznie wg taga.
- Spójność terminów: [GLOSARIUSZ.md](GLOSARIUSZ.md).
