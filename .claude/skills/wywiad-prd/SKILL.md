---
name: wywiad-prd
description: Przeprowadza z autorem wywiad o jego projekcie i na tej podstawie wypełnia docs/PRD.md. Używaj, gdy autor prosi o „wywiad”, „PRD”, „specyfikację” albo „dokument wymagań”.
---

# Wywiad do PRD

## Wejście
1. Przeczytaj `MOJE_TRZY_ZDANIA.md`, `docs/PRD.md` (szablon) i `CLAUDE.md`.
2. Rzuć okiem na `docs/przyklad/PRD_Dyzurka.md` — to wzór poziomu szczegółowości, nie treści.

## Wywiad (najpierw pytasz, nic nie zapisujesz)
Zadaj **najwyżej 8 pytań** w trzech blokach, ponumerowanych:
- **A · Problem i ludzie:** kto dokładnie ma problem, jak to wygląda dziś (liczby, sytuacje), kto NIE jest użytkownikiem.
- **B · Sukces i granice:** po czym poznamy sukces (miernik i wartość), czego świadomie nie robimy w pierwszej wersji.
- **C · Ograniczenia:** jakie dane (osobowe?), na jakich urządzeniach, do kiedy pierwsza wersja.

Każde pytanie ma podpowiedź w nawiasie, np. „(np. 15 maili tygodniowo)”. Zaczekaj na odpowiedzi.
Jeśli odpowiedź jest ogólnikowa („szybciej”, „łatwiej”), dopytaj raz o liczbę albo przykład.

## Plan, potem zapis
1. Przedstaw plan: jakie epiki i historie proponujesz, jak rozkładasz MoSCoW, co trafi do „Poza zakresem” i „Otwartych pytań”.
2. Po akceptacji autora wypełnij `docs/PRD.md` **sekcjami, o które prosi** (domyślnie 1–4; potem 5–6).
3. Zasady treści: historie `US-01…`, „Jako… chcę… aby…”, min. 2 kryteria „Zakładając, że… gdy… wtedy…”,
   priorytet, rozmiar S/M/L, „zależy od:”. Must ≤ ok. 60% wysiłku.
4. Czego nie wiesz — do „11. Otwarte pytania”. Nie wymyślaj faktów.
5. Na końcu: 3 punkty z `docs/CHECKLISTA_PRD.md`, które PRD jeszcze oblewa, i propozycja commita.

## Czerwone flagi (zatrzymaj się i zapytaj)
- autor prosi o integrację z USOS / Moodle / M365 przez API (polityka uczelni tego nie pozwala),
- w projekcie pojawiają się prawdziwe dane studentów,
- wszystkie historie mają priorytet Must.
