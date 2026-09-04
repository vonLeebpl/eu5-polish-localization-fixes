# Zasady współpracy

## Konfiguracja jednorazowa (każda osoba na swoim komputerze)

```bash
git clone https://github.com/vonLeebpl/mod.git
cd mod
git config user.name  "Imię Nazwisko"
git config user.email "twoj@email"
```

Edytor: VS Code z wtyczką **EditorConfig for VS Code** (respektuje
`.editorconfig`). Pliki `.yml` zapisujemy jako **UTF-8 z BOM**, końce linii
**LF**. `.gitattributes` wymusza LF przy commitcie, więc nawet przy złych
ustierowanych ustawieniach Gita historia zostanie czysta.

## Model pracy — trunk-based

Mała ekipa, więc bez ceremonii:

1. `git pull --rebase` przed rozpoczęciem pracy.
2. Pracujesz nad **swoim zakresem plików** (patrz niżej) — to główny sposób
   unikania konfliktów.
3. Małe, tematyczne commity. `git pull --rebase` + `git push`.
4. Większe/ryzykowne zmiany (logika odmiany w
   `country_name_construction.txt`, pliki `.gui`) → osobna gałąź + Pull
   Request do przeglądu.

```bash
git checkout -b fix/dopelniacz-krzyzacy
# ...zmiany, commity...
git push -u origin fix/dopelniacz-krzyzacy
# PR na GitHub
```

## Podział pracy (uzupełnijcie)

Żeby nie edytować tych samych plików równolegle:

| Osoba | Zakres |
|---|---|
| vonLeebpl | `plf_*`, `country_name_construction.txt`, odmiana nazw państw |
| _(druga osoba)_ | wydarzenia (`events/`), interfejs (`interfaces_l_polish.yml`) |

## Commity

- Język: polski, tryb rozkazujący: „Popraw dopełniacz Rzeczypospolitej”.
- Zakres w prefiksie ułatwia przeglądanie historii:
  - `dop:` odmiana / dopełniacze
  - `rząd:` nazwy rządów
  - `event:` wydarzenia
  - `gui:` interfejs
  - `meta:` konfiguracja repo, metadata
- **Nie** commitujemy „WIP”. Jak musisz odłożyć pracę: `git stash` albo
  commit na własnej gałęzi.

## Pliki robocze

Kopie `.yml_copy`, `.yml_oryg`, `_mid` itp. są w `.gitignore` — trzymaj je
lokalnie, nie wrzucaj do repo.

## Konflikty w plikach .yml

Pliki lokalizacji są liniowe, więc merge zwykle działa. Przy konflikcie:
zachowaj **oba** klucze jeśli dotyczą różnych wpisów, usuń duplikat klucza
jeśli to ta sama linia. Po merge sprawdź, czy plik dalej ma BOM i czy gra
go wczytuje (konsola gry: `~`, komunikaty o błędach lokalizacji).
