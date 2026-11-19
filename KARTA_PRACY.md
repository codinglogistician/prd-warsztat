# Karta pracy — sesja 5: od trzech zdań do PRD

Pracujesz na **swojej** kopii repozytorium. Po każdej fazie: 2 minuty porównania w pokoju
(jedna osoba udostępnia ekran). Checkpointy wpisujesz na **czacie głównym**. Utknięcie: słowo „pomoc”.

Agent: **Claude Code** (panel w VS Code albo terminal) — ścieżka gwarantowana.
Masz Copilota? Możesz zrobić F1 w Copilot Chat (`/plan`) i porównać z Claude w „Bez sufitu”.

---

## F0 · Gałąź (3 min)
- [ ] Wpisz swoje trzy zdania do `MOJE_TRZY_ZDANIA.md` (zapisz plik).
- [ ] Klik w nazwę gałęzi w lewym dolnym rogu → **Create new branch…** → `docs/prd-v1`.
- [ ] Sprawdź: pasek stanu pokazuje `docs/prd-v1`.

## F1 · Wywiad w trybie planu (9 min) — checkpoint `F1 + liczba pytań`
- [ ] Panel Claude Code → przełącz na **Plan mode** (Shift+Tab, aż zobaczysz „plan mode”).
- [ ] Wpisz: `/wywiad-prd`
- [ ] Odpowiadaj konkretnie: liczby, przykłady, nazwy ról. Czego nie wiesz — powiedz „nie wiem, zapisz jako otwarte pytanie”.
- [ ] Przeczytaj plan agenta. **Zanim zaakceptujesz:** czy w „poza zakresem” są co najmniej 3 rzeczy?

## F2 · Rdzeń PRD: sekcje 1–4 (8 min)
- [ ] Zaakceptuj plan → agent wypełnia sekcje 1–4 w `docs/PRD.md`.
- [ ] Przeczytaj diff. Popraw **samodzielnie** co najmniej jedno zdanie, które brzmi „jak AI”, a nie jak Twój problem.
- [ ] Commit: `docs: PRD sekcje 1-4` (Source Control → opis → Commit).

## F3 · Epiki, historie, MoSCoW (12 min) — checkpoint `F3 M:_ S:_ C:_ W:_`
- [ ] Poproś: „Zaproponuj 2–3 epiki i 6–8 historii użytkownika z kryteriami akceptacji i MoSCoW. Zapisz w sekcjach 5–6.”
- [ ] Sprawdź każdą historię *Must*: czy bez niej produkt naprawdę nie ma sensu? Przesuń co najmniej jedną w dół.
- [ ] Dopisz zależności („zależy od: US-…”) albo poproś o nie agenta.
- [ ] Commit: `docs: epiki, historie i MoSCoW`.

## F4 · Recenzja w pokoju (7 min)
- [ ] Udostępnij ekran. Partner przechodzi pytania ★ z `docs/CHECKLISTA_PRD.md`.
- [ ] Za każde NIE — jedna poprawka (ręcznie albo przez agenta). Commit.

## F5 · Pull Request i scalenie (5 min) — checkpoint `F5 scalone`
- [ ] **Publish Branch** (Source Control).
- [ ] Utwórz Pull Request: rozszerzenie *GitHub Pull Requests* → **Create Pull Request** albo na GitHubie żółty pasek **Compare & pull request**.
- [ ] Wypełnij szablon PR. Na GitHubie: **Files changed** → przeczytaj → **Squash and merge** → **Delete branch**.
- [ ] W VS Code: przejdź na `main` → **Pull**. PRD jest na `main`.

---

## Bez sufitu
- Sekcje 7–10: wymagania niefunkcjonalne, UI/UX ze stanami, ryzyka, harmonogram z wykresem `mermaid gantt` (GitHub go narysuje).
- Zgłoszenia z historii *Must*: GitHub → Issues → New issue → szablon „Historia użytkownika”; dodaj kamień milowy **Milestone: MVP**.
- Tablica projektu: GitHub → Projects → New project → Board; przeciągnij zgłoszenia do kolumn.
- Makieta: „Na podstawie sekcji 8 zrób makietę ekranu E-1 jako jeden plik `docs/makieta.html`, bez logiki”. Otwórz w przeglądarce.
- Recenzja adwersaryjna: subagent albo druga sesja z poleceniem „Jesteś sceptycznym recenzentem. Znajdź 5 miejsc, w których agent-programista źle zrozumie ten PRD”.
- Copilot Chat: `/plan` z tym samym zadaniem. Kto zadał lepsze pytania?

## Nie masz pomysłu? Trzy zapasowe projekty
1. **Kartkówka do Moodle** — generator krótkich testów z notatek wykładowych, eksport do formatu GIFT (import ręczny w Moodle).
2. **Obecności bez papieru** — prowadzący zaznacza obecność na telefonie, na koniec semestru eksport do Excela.
3. **Tematy prac dyplomowych** — katalog tematów promotora, student zgłasza zainteresowanie, promotor akceptuje.
