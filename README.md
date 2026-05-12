# Calorie Notebook translations

To repozytorium trzyma zdalne pakiety tłumaczeń dla aplikacji
`Calorie Notebook`.

W aplikacji lokalnie zostają tylko:

- tłumaczenie interfejsu z `language.dart`,
- angielskie treści ekranów,
- angielskie nazwy produktów dla baz wbudowanych do aplikacji.

Reszta może być pobierana dopiero wtedy, gdy użytkownik wybierze inny język.

## Struktura

```text
manifest.json
info/
  ar.json
  de.json
  es.json
  fi.json
  fr.json
  hi.json
  it.json
  pl.json
  pt.json
  sz.json
product_names/
  fi_fi.json
  fi_sz.json
  pl_fi.json
  pl_sz.json
  sz_fi.json
  sz_sz.json
```

## Jak to działa

- `manifest.json` mówi aplikacji, które paczki istnieją i z jaką wersją
  aplikacji są zgodne
- `info/<lang>.json` trzyma długie treści ekranów
- `product_names/<lang>_<base>.json` trzyma tłumaczenia nazw produktów dla
  konkretnej bazy danych

## Jak aktualizować tłumaczenia

Jeśli poprawiasz tylko treść:

1. edytujesz odpowiedni plik JSON
2. podbijasz `contentVersion` dla tej paczki w `manifest.json`
3. robisz commit i push

Nie trzeba wtedy wydawać nowej wersji aplikacji, o ile nie zmienił się format
danych.

## Jak dodać nowy język

1. najpierw dodajesz tłumaczenie interfejsu do `language.dart`
2. dodajesz `info/<lang>.json`, jeśli masz przetłumaczone treści ekranów
3. dodajesz `product_names/<lang>_<base>.json` dla baz, które mają już
   angielską podstawę w aplikacji
4. dopisujesz nowe wpisy do `manifest.json`

## Jak dodać nową bazę produktów

Każda nowa baza produktów musi najpierw wejść do aplikacji po angielsku.
Dopiero potem dodajesz dla niej zdalne tłumaczenia do tego repozytorium.

## Ważna uwaga o zgodności

`contractVersion` zmieniasz tylko wtedy, gdy aplikacja zaczyna oczekiwać innej
struktury danych.

Przy zwykłych poprawkach treści wystarczy podbić `contentVersion`.
