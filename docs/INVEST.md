# INVEST: sześć pytań do każdej historii użytkownika

Lista kontrolna Billa Wake'a (2003, „INVEST in Good Stories, and SMART Tasks”). To nie definicja, tylko sześć pytań.
Historia nie musi być idealna w każdej literze, ale każde „NIE” to sygnał do poprawki.

**Dlaczego to ważne przy agencie:** programista przy niejasnej historii przyjdzie i dopyta. Agent zgadnie.
Każda litera chroni przed innym rodzajem zgadywania.

| Litera | Znaczy | Pytanie kontrolne |
|---|---|---|
| **I** · Independent — niezależna | da się ją zrobić, pokazać i sprawdzić bez czekania na inne | Czy mogę zrobić ją jako pierwszą albo jedyną i coś pokazać? |
| **N** · Negotiable — negocjowalna | opisuje cel i efekt, nie implementację | Czy da się to zrobić na dwa sposoby i oba byłyby OK? |
| **V** · Valuable — wartościowa | ktoś konkretny coś zyskuje (część „aby…”) | Co się stanie, jeśli tego nie zrobimy? |
| **E** · Estimable — szacowalna | wiadomo mniej więcej, ile to pracy (S / M / L) | Czy dwie osoby dałyby jej ten sam rozmiar? |
| **S** · Small — mała | jeden PR, którego diff przeczytasz za jednym podejściem | Czy recenzja zajmie mniej niż kwadrans? |
| **T** · Testable — testowalna | ma kryteria, które zdaje albo oblewa | Czy osoba spoza projektu sprawdzi to bez pytania mnie? |

## Litera po literze

### I — niezależna
- Pełna niezależność bywa niemożliwa (US-03 zapis zawsze wymaga US-01 dyżur). Wtedy **zapisz zależność jawnie** („zależy od: US-01”).
- Nie twórz zależności sztucznych. Najczęstsza: podział warstwami („najpierw baza, potem formularz, potem lista”) — żadna część osobno nic nie daje.
- Lepiej **cienki plaster przez wszystkie warstwy**: „zapis na slot na przykładowych danych” — uproszczony, ale kompletny.

### N — negocjowalna
- Historia to zaproszenie do rozmowy o celu, nie umowa szczegółów (Ron Jeffries: karta, rozmowa, potwierdzenie). Przy agencie tą rozmową jest wywiad w trybie planu.
- Źle: „Dodaj rozwijaną listę z 8 pozycjami i granatowy przycisk po prawej”. Odbierasz agentowi miejsce na lepsze rozwiązanie.
- Treść historii jest elastyczna, **kryteria akceptacji są twarde**. Szczegóły należą do kryteriów.

### V — wartościowa
- Wartość to część „aby…”. Bez niej agent dostarczy funkcję, nie rozwiązanie problemu.
- Pułapka: „Jako programista chcę mieć bazę danych” to **zadanie**, nie historia. Jego wartość widać w historii użytkownika, której służy.
- Wartość decyduje o priorytecie MoSCoW: historia bez wartości nie może być Must.

### E — szacowalna
Gdy nie da się oszacować, powód jest zwykle jeden z trzech:
1. brak wiedzy dziedzinowej → dopytaj (albo zapisz w „Otwartych pytaniach”),
2. brak wiedzy technicznej → krótkie rozpoznanie (*spike*), np. „sprawdź, czy Moodle przyjmie taki plik GIFT”,
3. historia za duża → podziel (litera S).

Przy agencie szacujemy głównie **czas Twojej recenzji i testowania**, nie czas pisania kodu — agent pisze szybko.

### S — mała
Sygnały, że historia jest za duża:
- spójnik „i”: „zapisuję się **i** dostaję przypomnienie **i** mogę zmienić termin”,
- więcej niż ok. 5 kryteriów akceptacji,
- słowa „zarządzać”, „obsługiwać” (zwykle kryją: dodaj, edytuj, usuń, przeglądaj naraz).

Duża historia = duży diff = recenzja „po łebkach” = błędy na `main`. Agent przy dużych zadaniach częściej dryfuje od specyfikacji.

**Jak dzielić (SPIDR, Mike Cohn):**

| Litera | Sposób | Przykład z Dyżurki |
|---|---|---|
| **S** · Spike | krótkie rozpoznanie, gdy czegoś nie wiemy | „sprawdź, gdzie mogą mieszkać wspólne zapisy” |
| **P** · Paths | ścieżki: najpierw szczęśliwa, potem błędy | zapis na wolny slot → potem „slot właśnie zajęty” |
| **I** · Interfaces | interfejs: najpierw najprostszy | lista slotów jako tekst → potem siatka przycisków |
| **D** · Data | dane: najpierw jeden typ | dyżur jednorazowy → potem cykliczny |
| **R** · Rules | reguły: najpierw bez reguły biznesowej | zapis bez limitu → potem „max 1 zapis na tydzień” |

„Zarządzam dyżurami” → definiuję jeden dyżur · definiuję dyżur cykliczny · odwołuję dyżur · edytuję dyżur.

### T — testowalna
- Słowa-pułapki: *intuicyjny, szybki, przyjazny, nowoczesny, łatwy, odpowiedni*. Każde zamień na liczbę albo obserwowalne zachowanie: „szybki” → „lista pojawia się w mniej niż 1 s”.
- Z testowalnych kryteriów agent sam napisze testy automatyczne. Kryterium nietestowalne agent uzna za spełnione.

## Napięcia między literami

| Napięcie | Co się dzieje | Rozwiązanie |
|---|---|---|
| **S ↔ V** | dzielenie za drobno daje kawałki bez wartości | dziel pionowo; każda część ma swoje „aby” |
| **S ↔ I** | więcej małych historii = więcej zależności | szukaj równowagi; zależności zapisuj jawnie |
| **N ↔ T** | ogólny cel kontra konkretne kryteria | cel w zdaniu historii, konkret w kryteriach |

## Przykład: historia przed i po

**Przed:** „Jako prowadzący chcę zarządzać konsultacjami w nowoczesnym, intuicyjnym systemie.”

| I | N | V | E | S | T |
|---|---|---|---|---|---|
| TAK (formalnie) | TAK | **NIE** — brak „aby” | **NIE** | **NIE** — „zarządzać” to kilka historii | **NIE** — „nowoczesny”, „intuicyjny” |

**Po:** trzy historie z [przykładowego PRD](przyklad/PRD_Dyzurka.md) — US-01 *Definiuję termin dyżuru*, US-02 *Odwołuję dyżur*,
US-05 *Widzę listę zapisanych* — każda z własnym „aby”, rozmiarem i kryteriami „Zakładając, że… gdy… wtedy…”.

## Prompt: recenzja INVEST z agentem

> Oceń każdą historię w sekcji 5 pliku docs/PRD.md według INVEST (docs/INVEST.md).
> Dla każdej litery napisz TAK albo NIE i jedno zdanie uzasadnienia. Dla każdego NIE zaproponuj
> poprawkę. Niczego nie zmieniaj w pliku.

Potem sam(a) zdecyduj, które poprawki przyjmujesz, i poproś o ich wprowadzenie albo popraw ręcznie.
