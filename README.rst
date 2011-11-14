=============================
Repozytorium z testami z MRJP 
=============================

Wstęp
=====

Repozytorium to zawiera testy do programu zaliczeniowego
z MRJP. Testy te zostały stworzone przez różnych autorów.

Zgoda na wymienianie się takimi testami została udzielona
przez prowadzącego przedmiot i znajduje się w pliku
`PODSTAWA_PRAWNA`.

Repozytorium nie zawiera testów przygotowanych przez 
wykładowcę. Można je znaleźć pod adresem:
http://www.mimuw.edu.pl/~ben/Zajecia/Mrj2011/Latte/

Organizacja testów
==================

Występuje następująca organizacja testów:

- *good* - testy poprawne

  - *basic* - testy które powinna przechodzić każda implementacja
  - *hardcore* - testy teoretycznie da się przejść, ale na chwile obecną są uważane za trudne (mogą zostać później przeniesione)

- *bad* - testy, na których powinien zostać zgłoszony błąd

  - *lexer* - błąd powinien zostać wykryty przez lexer
  - *syntax* - błąd powinien zostać wykryty przez parser
  - *semantic* - błąd powinien zostać wykryty przez analizator semantyczny
  - *semantic_or_runtime* - błąd może zależnie od implementacji zostać wykryty w dwóch miejscach (np. `if(1/0 == 0)`)
  - *runtime* - błąd, który może być wykryty tylko w runtime
  - *overflow* - programy, które mają na celu się wysypać (przepełnienie stosu itp.), ale nie zawierają błędu
  - *infinite_loop* - programy, które są poprawne, ale się zapętlają

Wraz z postępem zadania zostaną dodane kolejne kategorie (np. na rozszerzenia).

Jak dodać swój test
===================

Test można dodać za pomocą githubowego `pull request` lub wysyłając do mnie maila (tw277696) z plikami testu oraz informacją w której kategorii powinien się znaleźć.

**Uwaga:** test powinien w **pierwszej linii pliku \*.lat** zawierać dane autora, np.

    // Author: Tomasz Wysocki 277696

Jeżeli z jakiegoś powodu taki komentarz nie może znajdować się w pliku, powinien zostać utworzony dodatkowy plik z rozszerzeniem .author.

Jest to wymaganie prowadzącego i testy nie spełniające go, nie zostaną wpuszczone do repo.

Jak wygląda test
================

Test składa się z trzech plików z poniższymi rozszerzeniami:

- *.lat* - kod programu użytego do testu
- *.input* - dane wejściowe dla programu, plik ten jest wymagany tylko jeśli program jest poprawny i dojdzie do uruchomienia
- *.output* - oczekiwane dane wyjściowe dla programu, plik ten jest wymagany tylko jeśli program jest poprawny i dojdzie do zakończenia programu
