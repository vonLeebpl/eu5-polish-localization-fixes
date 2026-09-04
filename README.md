# Polish localization fixes — EU5

Mod do *Europa Universalis V* poprawiający polską lokalizację gry:
odmiana nazw państw przez przypadki (dopełniacz), nazwy rządów, teksty
interfejsu, wydarzeń, tooltipów itd.

- **Mod ID:** `vonleebpl.polish_localization_fixes`
- **Wspierana wersja gry:** patrz `.metadata/metadata.json`

## Struktura

| Katalog | Zawartość |
|---|---|
| `.metadata/` | deskryptor moda (`metadata.json`) |
| `main_menu/localization/polish/` | właściwe tłumaczenia (pliki `*_l_polish.yml`) |
| `main_menu/localization/english/` | klucze `l_english` nadpisywane przez mod |
| `in_game/common/customizable_localization/` | logika odmiany nazw (`country_name_construction.txt` itp.) |
| `in_game/gui/` | nadpisania plików interfejsu `.gui` |

## Instalacja do testów

Sklonuj repo bezpośrednio do katalogu modów EU5 albo zrób dowiązanie
symboliczne folderu repo do:

```
Documents/Paradox Interactive/Europa Universalis V/mod/
```

Plik `.metadata/metadata.json` musi znaleźć się w katalogu moda, żeby gra
go wykryła.

## Współpraca

Zasady pracy w repo: [CONTRIBUTING.md](CONTRIBUTING.md).
Ustalone tłumaczenia terminów: [GLOSARIUSZ.md](GLOSARIUSZ.md).
