# Inżynieria Systemów dla Fizyków – Projekt I.
Celem projektu było stworzenie programu w języku C++, który będzie składać się z kilku plików, umieszczonych w odpowiednich katalogach. Dodatkowo do projektu należało dołączyć makefile, umożliwiający automatyzację procesu kompilacji oraz budowanie programu.

## Informacje ogólne
Na potrzeby projektu stworzyliśmy serwer webowy, który akceptuje klientów za pomocą wątku, następnie przyjmuje wiadomość w postaci requestu webowego i odsyła odpowiednie dane.  
Projekt został podzielony na cztery katalogi: 
* bin (serwer oraz  przykładowa strona), 
* include (pliki .h), 
* lib (pliki .o),
* src (pliki .cpp).

**Najważniejsze wykorzystane funkcje systemowe:**
* socket() - tworzenie gniazda komunikacyjnego
* memset() - wypełnianie wskazanej przestrzeni/struktury daną wartością
* bind() - przypisywanie gniazdu nazwy
* listen() - przekształcanie nazwy
* send() - wysyłanie danych na określony adres (w przypadku gniazd skojarzonych z adresem zdalnym)
* recv() - odbieranie danych (w przypadku gniazd skojarzonych z adresem zdalnym)
* accept() - pobieranie pierwszych połączeń z kolejki połączeń oczekujących i tworzenie nowych gniazd komunikacyjnych
* htons() - konwertowanie wartości hostshort typu unsigned short integer z lokalnego na sieciowy porządek bajtów

**Najważniejsze wykorzystane parametry:**
* SOCK_STREAM – gniazdo strumieniowe (TCP)
* PF_INET – protokoły IPv4
* INADDR_ANY – adres nieokreślony

**Najważniejsze zmienne strukturalne:**
* sockaddr_in – struktura przechowująca informacje adresowe dla protokołu IPv4
* sockaddr – ogólna struktura gniazdowa
* socklen_t – zmienna strukturalna świadcząca o rozmiarze struktury

## Uruchamianie
W celu uruchomienia projektu należy najpierw zbudować kod, wpisując w terminalu polecenie `make`. Następnie należy uruchomić serwer poleceniem `./`. Wówczas można uruchomić załączoną, przykładową stronę internetową z katalogu bin -> www, spisując w przeglądarce `localhost:1233`. Template strony pochodzi z [https://bootstrapmade.com]. Serwer wyłączamy kombinacją klawiszy Ctrl+c.



## Informacje dodatkowe 
* Port ustawiony został „na sztywno”
* Klientów oraz ich żądania obsługuje pętla while
* Gdy request nie jest webowy, zwracana jest informacja aby stworzyć go przez stronę
* Pliki są obsługiwane przez filehandler (wczytywanie i zwracanie)
