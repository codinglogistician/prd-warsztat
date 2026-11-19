# Ściąga: git i GitHub w VS Code

Zasada: **`main` zawsze działa. Każda zmiana powstaje na gałęzi i wraca na `main` przez Pull Request.**

## Cykl jednej zmiany (GitHub Flow)

```
main ──●────────────────────────────●──  (po scaleniu)
        \                          /
         ●──●──●  docs/prd-v1  ──PR
```

1. Aktualny `main` → 2. nowa gałąź → 3. małe commity → 4. publikacja gałęzi → 5. Pull Request →
6. recenzja („Files changed”) → 7. scalenie → 8. powrót na `main`, pobranie zmian, usunięcie gałęzi.

## Kliknięcia w VS Code ↔ polecenia w terminalu

| Co chcę zrobić | VS Code (klik) | Terminal |
|---|---|---|
| Pobrać najnowsze zmiany | Source Control (Ctrl+Shift+G) → ⋯ → Pull | `git pull` |
| Zobaczyć, na jakiej gałęzi jestem | nazwa gałęzi w lewym dolnym rogu (pasek stanu) | `git status` |
| Utworzyć gałąź i na nią przejść | klik w nazwę gałęzi → **Create new branch…** | `git switch -c docs/prd-v1` |
| Przełączyć gałąź | klik w nazwę gałęzi → wybierz z listy | `git switch main` |
| Zobaczyć zmiany | Source Control → klik w plik (diff) | `git diff` |
| Dodać zmiany do commita | **+** przy pliku (Stage Changes) | `git add docs/PRD.md` |
| Zapisać migawkę (commit) | wpisz opis → **Commit** | `git commit -m "docs: PRD sekcje 1-4"` |
| Wysłać nową gałąź na GitHub | **Publish Branch** | `git push -u origin docs/prd-v1` |
| Wysłać kolejne commity | **Sync Changes** / ikona strzałek na pasku stanu | `git push` |
| Utworzyć Pull Request | rozszerzenie *GitHub Pull Requests* → **Create Pull Request** (albo przycisk na GitHubie) | `gh pr create` (opcjonalne GitHub CLI) |
| Scalić gałąź lokalnie | przejdź na `main` → Paleta (Ctrl+Shift+P) → **Git: Merge…** | `git merge docs/prd-v1` |
| Usunąć gałąź lokalną | Paleta → **Git: Delete Branch** | `git branch -d docs/prd-v1` |
| Zobaczyć historię i gałęzie | **Source Control Graph** | `git log --oneline --graph` |

## Nazwy gałęzi

| Prefiks | Kiedy | Przykład |
|---|---|---|
| `feature/` | nowa funkcja (jedna historia) | `feature/US-03-zapis` |
| `fix/` | poprawka błędu | `fix/podwojna-rezerwacja` |
| `docs/` | dokumentacja | `docs/prd-v1` |

## Opisy commitów (konwencja)

`typ: co zmieniono` — po polsku, w trybie „co robi ten commit”.
`feat:` nowa funkcja · `fix:` poprawka · `docs:` dokumentacja · `test:` testy · `refactor:` porządki bez zmiany działania.
Przykład: `docs: dodaj epiki E1–E3 i MoSCoW`.

## Trzy sposoby scalania PR na GitHubie

| Przycisk | Efekt | Kiedy |
|---|---|---|
| **Create a merge commit** | cała historia gałęzi + commit scalający | zespół chce widzieć każdy krok |
| **Squash and merge** | wszystkie commity gałęzi → jeden commit na `main` | domyślnie u nas: czysta historia |
| **Rebase and merge** | commity „przeklejone” na koniec `main` | dla zaawansowanych |

## Gdy git protestuje

- *„Your local changes would be overwritten”* — najpierw commit (albo `git stash`), potem przełączanie gałęzi.
- *Konflikt scalania* — VS Code pokaże **Accept Current / Accept Incoming / Accept Both** albo edytor scalania 3-stronnego. Zdecyduj, zapisz, commit.
- *„rejected — fetch first”* — ktoś (albo agent w chmurze) wypchnął zmiany: `git pull`, potem `git push`.
- Nie wiesz, co się dzieje? Wklej komunikat agentowi: „Wyjaśnij, co się stało i co proponujesz. Nic nie zmieniaj”.
