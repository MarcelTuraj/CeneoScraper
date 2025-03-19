# CeneoScraper

## Kod produktu, o którym będą pobierane opinie 

## Algorytm pobierania opinii o pojedynczym produkcie  serwisu Ceneo.pl

 1. Wysłanie zapytania o dostęp do strony z opiniami o produkcie
 2. Jeśli operacja zakończy się suckesem i otrzymamy kod strony, wyodrębniamy z kodu strony fragmenty odpowiadające poszczególnym opinionm.
 3. Dla każdej z opinii wydobywamy z kodu HTML poszczególnych składowych i zapisanie ich w postaci struktur danych.
 4. Jeżeli istnieje kolejna strona z opiniami, to przechodzimy na kolejną i poowtórzenie procesu 1-4.
 5. Zapisanie wszystkich opinii w bazie danych

 ## Struktura opinii w serwisie Ceneo.pl
  |składowa|zmienna|selektor|
  |--------|-------|--------|
  |opinia|review|.js_product-review|
  |identyfikator opinii|review_id|['data-entry_id']|
  |autor|author|.user-post__author-name|
  |rekomendacja|recommendation|.user-post__author-recomendation > em|
  |liczba gwiazdek|stars|.user-post__score-count|
  |data wystawienia opinii|publish_date|.user-post__published >time:nth-child(1)['datatime']|
  |data zakupu produktu|buy_date|.user-post__published >time:nth-child(2)['datatime']|
  |ile osób uznało opinię za przydatną|likes|button.vote-yes > span|
  |ile osób uznało opinię za nieprzydatną|dislikes|button.vote-no > span|
  |treść opinii|content|.user-post__text|
  |lista wad|cons|.review-feature__item--negative|
  |lista zalet|pros|.review-feature__item--positive|
  
 