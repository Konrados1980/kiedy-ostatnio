# Kiedy ostatnio

Dodatkowe zadanie z mentoringu „Po prostu koduj” (Paul Crow): przeczytać *Shape Up* Ryana Singera i opisać oraz zbudować własną aplikację w stałym budżecie czasu.

Rzadkie, powtarzalne sprawy w jednym miejscu. Jednym spojrzeniem widać, co już dojrzało do zrobienia, zanim zrobi się pilne.

**Aplikacja online:** https://konrados1980.github.io/kiedy-ostatnio/

## Opis w stylu Shape Up

| Pole | Opis |
|---|---|
| **Problem** | Rzadkie, powtarzalne sprawy (filtr, olej w aucie, dentysta) wpisuję do kalendarza, który się przez to przeładowuje i przypomina mi o nich dopiero w ostatniej chwili. |
| **Czas** | 2 godziny łącznie, a jeśli się nie zmieszczę, wycinam funkcje, a nie dokładam czasu. |
| **Pierwsza wersja** | Dodanie rzeczy z informacją, co ile ją robić, przycisk „Zrobione dziś” zerujący licznik i lista posortowana od najbardziej zaległych, z napisem „minęło X dni”. |
| **Do sprawdzenia** | Czy zapisane rzeczy przetrwają zamknięcie strony i będą widoczne zarówno na komputerze, jak i na telefonie. |
| **Poza projektem** | Powiadomienia i połączenie z kalendarzem, historia wszystkich wykonań, wspólna lista dla domowników. |

### Dlaczego tak

- **Problem opisuje frustrację, a nie funkcję.** Kalendarz przypomina w ostatniej chwili, więc nie budujemy kolejnego przypominacza, tylko miejsce, w którym stan widać od razu.
- **„Co ile” jest w pierwszej wersji**, bo bez tego „minęło 47 dni” nic nie znaczy: dla kwiatów to katastrofa, dla przeglądu auta to nic.
- **Zapis danych to jedyna rzecz, która mogła zablokować projekt** (w poprzedniej aplikacji niczego nie trzeba było pamiętać), więc sprawdziliśmy go jako pierwszy.
- **Powiadomienia są świadomie poza projektem**, bo to właśnie ten kalendarz, który męczył.

## Co działa w pierwszej wersji

- **Lista od najpilniejszych rzeczy**, z paskiem pokazującym, ile minęło z okresu: „W porządku”, „Za 3 dni” (od 80% okresu) albo „7 dni po terminie”.
- **„Zrobione dziś”** zeruje licznik, z możliwością cofnięcia przez 6 sekund.
- **Dodawanie z podpowiedziami.** Pusta data oznacza „nie pamiętam” i rzecz trafia na górę jako do zrobienia.
- **Usuwanie z potwierdzeniem.**
- **Zwijana sekcja „W porządku (N)”** (dodana po pierwszym dniu używania): na górze zostaje tylko to, co wymaga uwagi, a reszta czeka zwinięta. Każde urządzenie pamięta, czy sekcja ma być rozwinięta.

## Gdzie są zapisywane dane

W Claude lista zapisuje się w prywatnej części bazy aplikacji, widocznej tylko dla jej właściciela, więc jest ta sama na komputerze i na telefonie. Na GitHub Pages nie ma takiej bazy: lista działa, ale znika po zamknięciu strony, o czym aplikacja informuje na górze.

## Wynik

| | |
|---|---|
| **Niewiadoma** | Sprawdzona. Lista zapisuje się, przetrwa zamknięcie strony i jest ta sama na komputerze i na telefonie, gdzie działa równie dobrze. |
| **Czas** | Około 20 minut budowania z 2 godzin budżetu. |
| **Decyzja** | Kończymy na pierwszej wersji. Po pierwszym użyciu nic nie trzeba poprawiać, a porównanie z punktem wyjścia (przeładowany kalendarz) wypada dobrze. Pozycje z „Poza projektem” zostają tam, gdzie są. |

Zgodnie z rozdziałem *Decide When to Stop*: wynik porównujemy z punktem wyjścia, a nie z wersją idealną.

## Projekt 2: poranne podsumowanie

Pomysł wrócił zaraz po zakończeniu pierwszej wersji (*Important ideas come back*), więc dostał własny opis i własny budżet, zamiast trafić do zamkniętego projektu.

| Pole | Opis |
|---|---|
| **Problem** | Gdy nie otworzę aplikacji, nie wiem, że coś minęło, a nie chcę osobnego alarmu dla każdej rzeczy jak w kalendarzu. |
| **Czas** | 1 godzina. |
| **Pierwsza wersja** | Codzienne sprawdzenie listy o 8:00, jedno zbiorcze powiadomienie na telefon tylko wtedy, gdy coś jest po terminie albo zostały do niego najwyżej 3 dni, i cisza, gdy wszystko jest w porządku. |
| **Do sprawdzenia** | Czy zaplanowane zadanie w Claude ma dostęp do mojej prywatnej listy. |
| **Poza projektem** | Wybór godziny w aplikacji, osobne alarmy dla każdej rzeczy, przypomnienia e-mailem. |

### Jak to działa

Zaplanowane zadanie w Claude uruchamia się codziennie o 7:57 (żeby powiadomienie zdążyło przed 8:00). Czyta prywatną listę, liczy dla każdej rzeczy, ile zostało do terminu, i wysyła jedno powiadomienie, np. „Kiedy ostatnio: 2 rzeczy. Wizyta u dentysty (247 dni po terminie), …”. Jeśli nic nie wymaga uwagi, nie wysyła niczego. Zadanie tylko czyta listę i nigdy jej nie zmienia.

**Dlaczego 3 dni, a nie 80% okresu jak w aplikacji:** przy rzeczach robionych raz w roku 80% to około dwóch miesięcy przed terminem, czyli o wiele za wcześnie na powiadomienie.

### Wynik

| | |
|---|---|
| **Niewiadoma** | Sprawdzona na początku próbnym zadaniem, które przeczytało listę i zostawiło na niej znak (potem usunięty). |
| **Próba końcowa** | Powiadomienie przyszło na telefon z dwiema rzeczami po terminie, zgodnie z ręcznym wyliczeniem. Dźwięk wymagał przestawienia powiadomień Claude w Androidzie z „cichych” na domyślne. |
| **Czas** | Około 20 minut z 1 godziny. |
