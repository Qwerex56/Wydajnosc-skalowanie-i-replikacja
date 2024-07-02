Wydajność, skalowanie i replikacja
==================================

Kontrola i buforowanie połączeń
-------------------------------


:Author: - Adrian Czubaty
         - Kamil Nicoś


Kontrola i buforowanie połączeń z bazą danych to kluczowe aspekty zarządzania bazami danych, które mają na celu optymalizację wydajności i zapewnienie niezawodności.

Kontrola połączeń z bazą danych:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Zarządzanie pulą połączeń: Technika ta pozwala aplikacjom na utrzymanie puli aktywnych połączeń z bazą danych, które są wielokrotnie używane. Poprzez efektywne zarządzanie pulą połączeń, aplikacje mogą minimalizować koszty związane z nawiązywaniem nowych połączeń, co przyczynia się do zwiększenia wydajności i efektywności systemu.

- Monitorowanie wydajności połączenia: Proces ten obejmuje śledzenie metryk związanych z połączeniem z bazą danych, takich jak czas odpowiedzi, błędy połączenia, ilość przesyłanych danych itp. Regularne monitorowanie tych metryk umożliwia szybkie wykrywanie problemów, co pozwala na ich natychmiastowe rozwiązanie i poprawę ogólnej wydajności systemu.

- Zarządzanie transakcjami: Kontrola nad transakcjami obejmuje precyzyjne określenie, kiedy i w jaki sposób transakcje są przetwarzane w bazie danych. Poprzez skuteczne zarządzanie transakcjami, można zapewnić spójność danych oraz uniknąć konfliktów. Przykładowo, dbając o to, aby operacje w ramach jednej transakcji były wykonywane jako jedna, niepodzielna jednostka pracy, zapewniamy integralność danych.

Buforowanie połączeń z bazą danych: 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Buforowanie zapytań: Technika ta polega na przechowywaniu wyników często używanych zapytań w pamięci podręcznej. Dzięki temu, gdy aplikacja ponownie potrzebuje wyników tego samego zapytania, może je szybko pobrać z pamięci podręcznej, co znacząco przyspiesza czas odpowiedzi i zmniejsza obciążenie bazy danych.

- Buforowanie wyników: Podobnie jak buforowanie zapytań, buforowanie wyników polega na przechowywaniu wyników kosztownych zapytań w pamięci podręcznej na przyszłe użycie. To pozwala uniknąć ponownego przetwarzania zapytań, które wymagają skomplikowanych obliczeń lub dostępu do wielu tabel, co przyczynia się do poprawy wydajności systemu.

- Inwalidacja bufora: Proces inwalidacji bufora polega na usuwaniu danych z pamięci podręcznej, gdy stają się przestarzałe lub nieaktualne. Jest to istotny aspekt zarządzania pamięcią podręczną, który zapewnia, że przechowywane dane są zawsze aktualne. Mechanizmy inwalidacji bufora mogą być zautomatyzowane (np. usuwanie danych po określonym czasie) lub sterowane manualnie przez aplikację


Indeks i klaster
----------------

- Indeks w bazie danych to struktura danych, która poprawia szybkość operacji na tabeli poprzez działanie podobne do indeksu w książce. Zamiast przeszukiwać całą tabelę, aby znaleźć konkretną informację, możemy skorzystać z indeksu, który bezpośrednio wskazuje, gdzie ta informacja się znajduje. W bazie danych indeksy są używane do szybkiego wyszukiwania i dostępu do danych w tabeli poprzez tworzenie indeksów na kolumnach tabeli.

- Klaster w bazie danych to technika przechowywania danych dwóch lub więcej powiązanych tabel w tym samym obszarze dysku. Tabele są powiązane za pomocą kluczy obcych, co umożliwia szybki dostęp do powiązanych danych. Klasterowanie może znacznie poprawić wydajność baz danych, ponieważ dane powiązane są przechowywane blisko siebie na dysku, co redukuje czas potrzebny na przeszukiwanie i dostęp do danych.


Wydajność 
---------

Wydajność bazy danych to kluczowy aspekt zarządzania danymi, który ma bezpośredni wpływ na funkcjonowanie i sukces organizacji. W dobie cyfryzacji i rosnącej zależności od danych, zarządzanie wydajnością baz danych stało się nieodzownym elementem strategii IT. W tym podpunkcie opiszemy sześć kluczowych aspektów wydajności baz danych: czasy odpowiedzi, przepustowość, współbieżność, wykorzystanie zasobów, zapytania N+1 i błędy bazy danych.
Parametry wydajności baz danych są podstawowymi wskaźnikami zdrowia systemu baz danych. Monitorowanie tych parametrów i proaktywne zarządzanie nimi jest kluczowe dla utrzymania zdrowia i wydajności bazy danych. Niewidoczne lub niemonitorowane problemy mogą prowadzić do poważnych zakłóceń, takich jak spadek wydajności, potencjalna utrata danych, a nawet awaria systemu, dlatego parametry wydajności nie mogą być ignorowane.

1. Czasy odpowiedzi
~~~~~~~~~~~~~~~~~~~

Czasy odpowiedzi bazy danych są kluczowym elementem w środowiskach, gdzie szybkie decyzje mają kluczowe znaczenie, jak w usługach finansowych czy sytuacjach awaryjnych. Kilka czynników wpływa na czas odpowiedzi:
 - Architektura bazy danych: Fizyczny i logiczny projekt bazy danych, w tym partycjonowanie, indeksowanie i przechowywanie danych, mają istotny wpływ. Odpowiednie partycjonowanie i indeksowanie danych może skrócić czas wyszukiwania, a korzystanie z baz danych w pamięci może znacząco przyspieszyć operacje poprzez uniknięcie dostępu do dysku.
 - Topologia i kondycja sieci: W rozproszonych bazach danych, konfiguracja sieci, opóźnienia, przepustowość i utrata pakietów mają znaczący wpływ na czas pobierania i zwracania danych. Optymalizacja sieci i kompresja danych mogą pomóc zminimalizować opóźnienia.
 - Równoczesny dostęp i równoważenie obciążenia: Techniki takie jak łączenie połączeń, równoważenie obciążenia i replikacja odczytu mogą równomiernie rozłożyć obciążenie, co przekłada się na optymalne czasy odpowiedzi nawet przy dużym ruchu.
 
 Wydajne czasy odpowiedzi są kluczowe dla operacyjnej wydajności, zadowolenia klientów i wyników finansowych firm. Są one wskaźnikiem kondycji systemu baz danych, wpływającym na przepustowość i skalowalność infrastruktury IT. W sektorach zwiększającej się ilości danych utrzymanie szybkich czasów odpowiedzi może stanowić przewagę konkurencyjną.

2. Przepustowość
~~~~~~~~~~~~~~~~

Przepustowość bazy danych jest kluczowym wskaźnikiem efektywności systemu w obsłudze danych w określonym czasie. Wysoka przepustowość oznacza zdolność bazy danych do obsłużenia większej liczby żądań lub operacji w sposób szybki i wydajny. Wpływ na przepustowość mają różne czynniki, takie jak:
 - Współbieżność: Mechanizmy zarządzania transakcjami i blokowania odgrywają istotną rolę w zapewnieniu integralności danych i zwiększeniu wydajności. Efektywne zarządzanie transakcjami pozwala wielu użytkownikom na jednoczesne operacje bez zakłóceń, co jest istotne w środowiskach o dużym obciążeniu, jak podczas wyprzedaży online. Więcej o współbieżności w kolejnym punkcie.
 - Bazy danych NoSQL: Systemy NoSQL korzystają z podejścia opartego na ewentualnej spójności, co pozwala na szybsze operacje zapisu poprzez unikanie oczekiwania na zaktualizowanie wszystkich kopii danych we wszystkich węzłach.
 - Dystrybucja danych: Techniki takie jak sharding w NoSQL lub partycjonowanie w bazach SQL pozwalają na podział danych na wiele serwerów lub partycji, co zmniejsza obciążenie poszczególnych elementów systemu i poprawia ogólną zdolność do obsługi dużych ilości operacji.
 
 Warto zauważyć, że odpowiednie zarządzanie współbieżnością, wybór odpowiedniego typu bazy danych oraz efektywna dystrybucja danych mają kluczowe znaczenie dla osiągnięcia wysokiej przepustowości bazy danych.

3. Współbieżność
~~~~~~~~~~~~~~~~

Współbieżność w bazach danych odnosi się do zdolności systemu do obsługi wielu operacji jednocześnie, co jest kluczowe w środowiskach, gdzie wiele użytkowników lub aplikacji korzysta z bazy danych równocześnie. Parametry wydajności baz danych, takie jak transakcje na sekundę (TPS) i zapytania na sekundę (QPS), mierzą współbieżność bazy danych poprzez liczbę operacji, jakie może obsłużyć w jednostce czasu. Czynniki wpływające pozytywnie na współbieżność to:
 - Mechanizmy blokujące: Efektywne zarządzanie blokadami umożliwia uniknięcie rywalizacji między transakcjami, co przyczynia się do płynniejszego działania bazy danych.
 - Poziomy izolacji transakcji: Wybór odpowiedniego poziomu izolacji transakcji ma wpływ na dokładność danych i współbieżność. Wyższe poziomy izolacji zapewniają większą dokładność, ale mogą ograniczać współbieżność poprzez blokowanie transakcji.
 - Architektura bazy danych: Ogólny projekt bazy danych, zwłaszcza w przypadku rozproszonych baz danych, może wpłynąć na zdolność systemu do obsługi wielu równoczesnych żądań poprzez rozłożenie obciążenia na wiele węzłów.

Wyzwania dla współbieżności obejmują:
 - Zakleszczenia (Deadlocki): Sytuacje, w których transakcje blokują się nawzajem, uniemożliwiając kontynuację, co może spowolnić bazę danych.
 - Głód zasobów: Kiedy procesy zużywają zbyt dużo zasobów, ograniczając dostępność dla innych procesów i zmniejszając współbieżność.
 - Hotspoty danych: Częsty dostęp do tych samych punktów danych może tworzyć wąskie gardła, ograniczając współbieżność poprzez tworzenie kolejek dostępu do zasobów.

4. Wykorzystanie zasobów (CPU, pamięć, I/O dysku)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Wykorzystanie zasobów w środowiskach baz danych ma kluczowy wpływ na wydajność i efektywność operacji obsługi danych. Kilka kluczowych zasobów, takich jak CPU, pamięć i operacje wejścia/wyjścia na dysku, wpływa na działanie bazy danych:
 - Użycie CPU: Procesor obsługuje wszystkie obliczenia związane z bazą danych, od wykonywania zapytań po zarządzanie transakcjami. Wysokie użycie procesora może wskazywać na nadmierne obciążenie bazy danych, co może prowadzić do spowolnienia operacji i długich czasów odpowiedzi. Maksymalne obciążenie procesora może również oznaczać, że zapytania nie są zoptymalizowane.
 - Wykorzystanie pamięci: Pamięć przechowuje aktywnie używane dane, a jej odpowiednia alokacja ma kluczowe znaczenie dla wydajności bazy danych. Wyczerpanie pamięci RAM i poleganie na pamięci dyskowej może znacząco obniżyć wydajność, co często wynika z wycieków pamięci lub niewłaściwych ustawień.
 - Operacje I/O na dysku: Operacje wejścia/wyjścia na dysku obejmują odczytywanie i zapisywanie danych, co ma istotne znaczenie dla przechowywania danych na dłuższy czas. Wysoki poziom operacji I/O na dysku może być objawem nieskutecznych strategii buforowania. Optymalne przechowywanie najczęściej używanych danych w pamięci może przyspieszyć operacje i uniknąć tworzenia wąskich gardeł związanym z dostępem do dysku.
 
 Efektywne zarządzanie zasobami, takimi jak CPU, pamięć i operacje wejścia/wyjścia na dysku, jest kluczowe dla zapewnienia optymalnej wydajności bazy danych i uniknięcia spowolnień czy problemów z operacjami.

5. Zapytania N+1
~~~~~~~~~~~~~~~~

Problemy z zapytaniami N+1 są powszechną nieefektywnością w aplikacjach korzystających z baz danych, szczególnie tych wykorzystujących narzędzia mapowania obiektowo-relacyjnego (ORM). Problem ten polega na nadmiernym wykonywaniu zapytań do bazy danych, co jest szczególnie zauważalne w przypadku, gdy aplikacja wykonuje dodatkowe zapytania dla każdego powiązanego obiektu po jednym początkowym zapytaniu. Przykładowo, jeśli aplikacja pobiera 10 użytkowników za pomocą jednego zapytania, a następnie wykonuje dodatkowe 10 zapytań dla pobrania profili każdego użytkownika, prowadzi to do łącznie 11 zapytań - co jest problemem zapytań N+1.

Przyczyny problemów z zapytaniami N+1 to:
 - Błędna konfiguracja ORM: Narzędzia ORM mają za zadanie ułatwić interakcję z bazą danych, ale nieprawidłowa konfiguracja może prowadzić do nieefektywnych strategii ładowania danych, takich jak "leniwe ładowanie", które powoduje nadmiarowe zapytania.
 - Brak zapytań łączących: Niedostateczne wykorzystanie złączeń SQL może prowadzić do problemów z zapytaniami N+1, gdzie aplikacja pobiera dane fragmentarycznie zamiast łączyć je w jednym zapytaniu.
 - Niezoptymalizowane wzorce dostępu do danych: Nieefektywne praktyki kodowania, zwłaszcza te związane z iteracyjnym dostępem do danych, mogą prowadzić do nadmiernego wykonywania zapytań do bazy danych, szczególnie w przypadku pętli, które wyzwalają nowe zapytania dla każdej iteracji.
 
 Rozwiązanie problemów z zapytaniami N+1 wymaga odpowiedniej konfiguracji ORM, wykorzystania złączeń SQL oraz optymalizacji wzorców dostępu do danych, aby uniknąć nadmiernego obciążenia bazą danych i poprawić wydajność aplikacji.

6. Błędy bazy danych
~~~~~~~~~~~~~~~~~~~~

Wskaźniki wydajności bazy danych obejmują również błędy, które mogą wpływać na operacje na bazie danych, od pobierania danych po ich przechowywanie. Błędy te mogą objawiać się jako komunikaty o błędach lub kody, sygnalizujące konkretne problemy w systemie bazy danych. Typowe rodzaje błędów bazy danych to:
 - Błędy połączenia: Pojawiają się, gdy aplikacja nie może nawiązać połączenia z bazą danych, co może być spowodowane problemami sieciowymi, błędami w ciągach połączeń lub awarią serwera bazy danych.
 - Błędy składni w zapytaniach: Występują, gdy polecenie SQL zawiera błędy składniowe, co powoduje odrzucenie go przez bazę danych, szczególnie w przypadku złożonych zapytań SQL.
 - Naruszenia ograniczeń: Bazy danych mają reguły, takie jak klucze obce i unikalne ograniczenia, które mają na celu utrzymanie integralności danych. Naruszenie tych ograniczeń, na przykład próba wstawienia duplikatu w miejscu, gdzie powinny być tylko unikalne wpisy, spowoduje zgłoszenie błędu przez bazę danych.
 - Błędy limitu zasobów: Pojawiają się, gdy baza danych przekracza limity dostępnych zasobów, takie jak brak miejsca na dysku, przeciążenie procesora czy brak pamięci. Te błędy mogą znacząco spowolnić lub nawet zatrzymać działanie systemu.
 - Błędy uprawnień i zabezpieczeń: Próba wykonania operacji bez odpowiednich uprawnień spowoduje błędy, na przykład brak dostępu do tabeli lub wykonywanie operacji bez wymaganych uprawnień.
 
 Rozpoznanie i rozwiązanie tych błędów jest kluczowe dla zapewnienia stabilności i wydajności bazy danych oraz uniknięcia problemów podczas operacji na danych.


Skalowanie
----------

Bazy danych SQL nie są tak kosztowne w rozbudowie, jak się powszechnie sądzi. Możliwe jest skalowanie ich wszerz, co przynosi wiele korzyści, zwłaszcza w kontekście analizy danych biznesowych. Firmy coraz bardziej interesują się analizą danych klientów pochodzących z różnych źródeł, co wymaga platform skalowalnych wszerz do przetwarzania dużych ilości danych w czasie rzeczywistym. Istnieje kilka opcji, takich jak bazy NoSQL, NewSQL czy platforma Hadoop, które mogą rozwiązać różne wyzwania związane z przetwarzaniem danych. Wdrożenie rozwiązania skalowalnego wszerz z odpowiednim balansem między pamięcią RAM a nośnikami flash może przynieść istotne korzyści, a nowa generacja skalowalnych baz SQL, takie jak InfiniSQL, ClustrixDB czy F1, pokazuje, że bazy SQL mogą być skalowalne wszerz.

Analityka czasu rzeczywistego:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Analityka czasu rzeczywistego w branży Big Data skupia się obecnie na analizie danych w czasie rzeczywistym, co pozwala firmom uzyskać przewagę konkurencyjną i korzyści biznesowe. Istotnym elementem są skalowalne bazy danych SQL, które umożliwiają przetwarzanie danych operacyjnych w czasie rzeczywistym. Wykorzystanie metod przetwarzania kwerend w pamięci operacyjnej i macierzy dyskowych opartych na nośnikach SSD pozwala osiągnąć wysoką wydajność bez konieczności stosowania specjalistycznych rozwiązań. Firmy takie jak Google czy Facebook udowodniły, że bazy danych SQL są skutecznym narzędziem do przetwarzania danych, co może przyczynić się do ograniczenia kosztów zatrudniania specjalistów. Przykładowo, Google wykorzystuje bazę F1 SQL do usługi Adwords, co ułatwia tworzenie aplikacji do zadań OLTP i OLAP. Facebook również podkreśla znaczenie relacyjnych baz danych w analityce, co przekonało wielu do promowania rozszerzeń Hadoopa umożliwiających integrację z bazami SQL.

Łatwa rozbudowa:
~~~~~~~~~~~~~~~~
Bazy danych SQL typu scale out umożliwiają łatwą liniową skalowalność poprzez dodawanie nowych węzłów do klastra, nawet w trakcie intensywnego użytkowania. Ta operacja nie wymaga zmian w kodzie, aktualizacji bazy danych ani wymiany sprzętu obsługującego aplikację. Każdy nowy węzeł może przyjmować i przetwarzać transakcje wraz z rozszerzaniem klastra. Istotną cechą tych baz SQL jest możliwość przenoszenia kodu bazy danych do węzłów przechowujących dane, zamiast przenoszenia samych danych. Dzięki temu ogranicza się ilość danych przesyłanych wewnątrz klastra, co prowadzi do zmniejszenia nadmiernego ruchu w klastrze i umożliwia liniową skalowalność bazy danych. Ponadto zapewnia to, że tylko jeden węzeł jest odpowiedzialny za zapis danych w określonym zbiorze, co eliminuje problem konkurencyjnego dostępu do tych samych zasobów. W tradycyjnych bazach danych każde zadanie blokuje obszary danych, co przy dużej liczbie zadań konkurencyjnych prowadzi do spadku wydajności.

Eliminacja wąskich gardeł:
~~~~~~~~~~~~~~~~~~~~~~~~~~
W skalowalnych bazach danych SQL rozwiązano problem logu transakcyjnego, który często stanowił wąskie gardło. W tradycyjnych bazach danych wszystkie przetwarzane rekordy są zapisywane w logu transakcyjnym przed zakończeniem kwerendy. W przypadku błędnej konfiguracji lub awarii może to spowodować nadmierny wzrost logu transakcyjnego, który może przekroczyć rozmiar samej bazy danych. To z kolei prowadzi do spowolnienia operacji zapisu w bazie, nawet w przypadku użycia nośników SSD.

Wysoka dostępność w chmurze:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Organizacje oczekują, że ich aplikacje produkcyjne będą zawsze dostępne, co zapewni ciągłość procesów biznesowych. W przypadku awarii chmury, która może się zdarzyć, istotne jest, aby firma mogła szybko przywrócić działanie bazy danych bez utraty danych. Skalowalne bazy danych SQL posiadają wbudowane funkcje wysokiej dostępności, które zapewniają przechowywanie kilku kopii danych, co minimalizuje ryzyko ich utraty.


Replikacja
----------
Replikacja danych to metoda duplikowania informacji pomiędzy różnymi serwerami baz danych. 
Dzięki replikacji możemy:
- Zwiększyć skalowalność – obciążenie można rozdzielić między wiele serwerów. Operacje takie jak zapisywanie i aktualizowanie rekordów są wykonywane na jednym serwerze, podczas gdy pobieranie i przeszukiwanie danych są realizowane na innym.
- Poprawić bezpieczeństwo – poprzez replikację tworzymy kopię istniejącej bazy danych produkcyjnej. Choć nie zabezpieczy nas to przed operacjami typu DROP TABLE, może to być pomocne w przypadku awarii sprzętowej głównego serwera.
- Ułatwić analizę – złożone operacje analityczne, różne przeliczenia i analizy statystyczne mogą być przeprowadzane na dedykowanym serwerze, bez obciążania głównej bazy danych.
- Zapewnić separację – możemy udostępnić kopię bazy danych produkcyjnej dla programistów lub testerów, umożliwiając im pracę na kopii bazy.

Mechanizmy replikacji
~~~~~~~~~~~~~~~~~~~~~
Replikacja w bazach danych odnosi się do procesu kopiowania i dystrybucji danych i obiektów z jednej bazy danych do innej, a następnie synchronizacji obu baz danych w celu utrzymania ich spójności.
Proces ten jest dość prosty. Główny serwer (master) prowadzi dziennik operacji, wykorzystując do tego pliki binarne zwane bin-logami, które zawierają instrukcje wykonane przez mastera. Te pliki są następnie odczytywane przez serwer zapasowy (slave), który wykonuje zapytania zawarte w bin-logach, co skutkuje dodawaniem nowych rekordów do bazy danych. W efekcie powstają dwie identyczne bazy danych. Po ustawieniu replikacji na serwerze master, uruchamiany jest dodatkowy wątek, który ma za zadanie wysyłać bin-logi do serwerów slave. Serwer zapasowy z kolei uruchamia dwa wątki: jeden do odczytu bin-logów i drugi do ich wykonania.
- Wątek I/O (Input/Output) - zajmuje się odbieraniem dziennika od serwera głównego i zapisywaniem go w plikach tymczasowych relay-log.
- Wątek SQL - parsuje te pliki i wykonuje zapytania do bazy danych.
W skrócie, mechanizm replikacji MySQL polega na tym, że serwer główny rejestruje swoje działania, a serwer zapasowy odtwarza te działania, tworząc kopię bazy danych.

Oprogramowanie i zaimplementowane mechanizmy replikacji
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Replikacja oparta na zapisie (Write-Ahead Logging): Ten mechanizm jest powszechnie stosowany w systemach baz danych, takich jak PostgreSQL. Polega na rejestrowaniu transakcji w dzienniku zapisu przed ich zastosowaniem, a następnie replikacji dziennika na serwery repliki.
- Replikacja oparta na zrzutach (Snapshot-Based Replication): Systemy, takie jak Apache Cassandra, wykorzystują replikację opartą na zrzutach. Polega to na tworzeniu zrzutów stanu bazy danych w określonych odstępach czasu i replikacji ich na serwery repliki.
- Replikacja oparta na transakcjach (Transaction-Based Replication): W tym modelu każda transakcja jest replikowana na serwery repliki, co jest przydatne w systemach wymagających silnej spójności, np. Google Spanner.
- Replikacja asynchroniczna i synchroniczna: W replikacji asynchronicznej dane są najpierw zapisywane do głównej bazy danych, a następnie replikowane na serwery repliki. W replikacji synchronicznej dane są zapisywane jednocześnie do głównej bazy danych i serwerów repliki.
- Replikacja dwukierunkowa (Bi-Directional Replication): Pozwala na wprowadzanie zmian na dowolnym serwerze repliki, które są następnie replikowane na pozostałe serwery, co jest przydatne w przypadku wysokiej dostępności i tolerancji na awarie.

PostgreSQL oferuje różne typy replikacji, w tym replikację opartą na zapisie (Write-Ahead Logging), replikację asynchroniczną i synchroniczną oraz replikację logiczną. Replikacja oparta na zapisie (WAL) gwarantuje odporność na awarie poprzez zapisywanie zmian w bazie danych do dziennika zapisu przed ich zastosowaniem, który jest replikowany na serwery repliki. PostgreSQL obsługuje zarówno replikację asynchroniczną, gdzie dane są najpierw zapisywane do głównej bazy danych, a następnie replikowane, jak i replikację synchroniczną, gdzie dane są zapisywane jednocześnie do głównej bazy danych i serwerów repliki. Dodatkowo, replikacja logiczna pozwala na replikację wybranych tabel lub baz danych zamiast całego klastra, co jest przydatne zwłaszcza w przypadku dużych baz danych, gdzie replikacja całego klastra byłaby nieefektywna.

Plusy i minusy replikacji
~~~~~~~~~~~~~~~~~~~~~~~~~
Plusy:

- Poprawa wydajności i dostępności: Replikacja danych pozwala na dystrybucję obciążenia zapytań pomiędzy wiele serwerów, co zwiększa wydajność systemu. Użytkownicy mogą wysyłać zapytania do najbliższego serwera repliki, co skraca czas odpowiedzi. Ponadto, jeśli jeden serwer ulegnie awarii, inne serwery repliki mogą nadal obsługiwać zapytania, co zwiększa dostępność systemu.
- Bezpieczeństwo danych: Replikacja jest również kluczowym elementem strategii tworzenia kopii zapasowych i odzyskiwania danych. Jeśli główna baza danych ulegnie awarii, replika może zostać użyta do przywrócenia danych.
- Dystrybucja danych: Replikacja umożliwia dystrybucję danych do oddzielnych lokalizacji geograficznych. Na przykład, globalna firma może chcieć replikować dane między swoimi lokalizacjami w różnych krajach, aby lokalni użytkownicy mogli szybko i łatwo uzyskać dostęp do potrzebnych informacji.
- Analiza i raportowanie: Repliki danych mogą być używane do celów analitycznych i raportowych. Dzięki temu operacje te nie wpływają na wydajność głównej bazy danych obsługującej transakcje.

Minusy:

- Nie daje nam pewności, że po przeprowadzeniu operacji, dane z serwera głównego będą poprawnie przeniesione na serwer zapasowy
- Nie zapewnia ochrony przed operacjami niosącymi poważne konsekwencje - takimi jak DROP TABLE


Limity systemu oraz ograniczanie dostępu użytkowników
-----------------------------------------------------
Limity systemu w zarządzaniu bazami danych odnoszą się do maksymalnej liczby zasobów, które system może obsłużyć. Te limity są zwykle określane przez system zarządzania bazą danych (DBMS) i są zdefiniowane na podstawie dostępnych zasobów sprzętowych i ustawień konfiguracyjnych. Na przykład, w Azure SQL Database istnieją specyficzne limity zasobów dla różnych poziomów cenowych dla pojedynczych baz danych. W MySQL, efektywny maksymalny rozmiar tabeli dla baz danych MySQL jest zazwyczaj określany przez ograniczenia systemu operacyjnego na rozmiary plików, a nie przez wewnętrzne limity MySQL.
Ograniczanie dostępu użytkowników w DBMS odnosi się do mechanizmu, który umożliwia lub zabrania użytkownikom dostęp do danych. Składa się z dwóch głównych komponentów: uwierzytelniania i autoryzacji. Uwierzytelnianie to sposób potwierdzenia tożsamości osoby, która próbuje uzyskać dostęp do bazy danych. Autoryzacja natomiast określa, czy poziom dostępu użytkownika jest odpowiedni. Istnieją różne modele kontroli dostępu, takie jak Kontrola Dostępu Uzależniona (DAC), Kontrola Dostępu Obowiązkowa (MAC), Kontrola Dostępu na Podstawie Roli (RBAC) i Kontrola Dostępu na Podstawie Atrybutów (ABAC).
W PostgreSQL również istnieją mechanizmy do zarządzania limitami systemu oraz ograniczania dostępu użytkowników. PostgreSQL umożliwia administratorom określenie różnych parametrów konfiguracyjnych, takich jak maksymalna ilość połączeń, pamięć dostępna dla zapytań, maksymalny rozmiar pliku danych, czy maksymalny rozmiar tabeli. Te limity mogą być dostosowywane do potrzeb konkretnego środowiska i obciążenia.
W kwestii ograniczania dostępu użytkowników, PostgreSQL oferuje zaawansowane mechanizmy uwierzytelniania i autoryzacji. Można definiować różne role użytkowników, nadawać im odpowiednie uprawnienia do baz danych, schematów, tabel czy nawet poszczególnych kolumn. PostgreSQL obsługuje zarówno uwierzytelnianie oparte na hasłach, jak i uwierzytelnianie oparte na certyfikatach SSL.
Dzięki tym funkcjom, administratorzy baz danych mogą skutecznie kontrolować dostęp do danych, zapewniając bezpieczeństwo i poufność informacji przechowywanych w PostgreSQL.


Testy wydajności sprzętu (pamięć, procesor, dyski) na poziomie systemu operacyjnego
-----------------------------------------------------------------------------------
Testy wydajności sprzętu na poziomie systemu operacyjnego są kluczowe dla optymalizacji wydajności baz danych. Obejmują one testy pamięci (RAM), procesora (CPU) oraz dysków (HDD/SSD), które są kluczowymi komponentami sprzętowymi wpływającymi na wydajność systemu.

Testy pamięci (RAM) oceniają szybkość i efektywność pamięci RAM komputera, co ma bezpośredni wpływ na wydajność bazy danych. Narzędzia takie jak MemTest86 mogą być używane do przeprowadzania tych testów.

Testy procesora (CPU) oceniają wydajność jednostki centralnej procesora, która jest kluczowa dla szybkości przetwarzania zapytań do bazy danych. Narzędzia takie jak Cinebench R23 mogą być używane do przeprowadzania tych testów.

Testy dysków (HDD/SSD) oceniają szybkość odczytu i zapisu na dyskach, co ma istotne znaczenie dla wydajności bazy danych, ponieważ dane są przechowywane na dyskach. Narzędzia takie jak CrystalDiskMark 8 i Acronis Drive Monitor mogą być używane do przeprowadzania tych testów.

Wyniki tych testów na poziomie systemu operacyjnego mogą pomóc zidentyfikować obszary, które wymagają ulepszeń sprzętowych, aby zwiększyć wydajność bazy danych, niezależnie od konkretnego oprogramowania bazy danych.
