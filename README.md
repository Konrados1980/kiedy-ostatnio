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

## Gdzie są zapisywane dane

W Claude lista zapisuje się w prywatnej części bazy aplikacji, widocznej tylko dla jej właściciela, więc jest ta sama na komputerze i na telefonie. Na GitHub Pages nie ma takiej bazy: lista działa, ale znika po zamknięciu strony, o czym aplikacja informuje na górze.
