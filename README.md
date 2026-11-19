# prd-warsztat — od trzech zdań do PRD

Repozytorium ćwiczeniowe kursu **„Od promptu do produktu”**, sesja 5.
Tu nie powstaje kod. Powstaje **dokument wymagań produktu (PRD)** Twojego projektu przewodniego —
umowa między Tobą a agentem, którą od sesji 6 będziemy realizować.

## Start
1. **Use this template → Create a new repository** → nazwa np. `projekt-przewodni` → **Private**.
2. VS Code → Terminal → `git clone https://github.com/TWOJ-LOGIN/projekt-przewodni.git` → File → Open Folder.
3. Instrukcja krok po kroku: [KARTA_PRACY.md](KARTA_PRACY.md).

## Co jest w środku

| Plik | Do czego |
|---|---|
| `MOJE_TRZY_ZDANIA.md` | Twoje wejście: kto, jaki problem, po czym poznasz sukces |
| `docs/PRD.md` | szablon PRD (12 sekcji, podpowiedzi w komentarzach) |
| `docs/przyklad/PRD_Dyzurka.md` | wzorcowy, wypełniony PRD |
| `docs/CHECKLISTA_PRD.md` | czy PRD jest gotowy dla agenta? |
| `docs/INVEST.md` | sześć pytań do każdej historii + prompt do recenzji z agentem |
| `docs/SCIAGA_GIT.md` | gałęzie, commity, Pull Requesty: klik ↔ polecenie |
| `CLAUDE.md`, `.github/copilot-instructions.md` | te same zasady dla dwóch agentów |
| `.claude/skills/wywiad-prd/`, `.github/prompts/wywiad-prd.prompt.md` | wywiad do PRD: skill Claude i prompt file Copilota |
| `.github/pull_request_template.md`, `.github/ISSUE_TEMPLATE/` | szablony PR i historii użytkownika |

## Zasady
- `main` zawsze w porządku; pracujesz na gałęzi, scalasz przez Pull Request.
- Zero prawdziwych danych studentów i dokumentów uczelni w repozytorium.
