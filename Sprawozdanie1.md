# Sprawozdanie 1
# Adam Gawieńczuk

Podczas tworzenia bota na portalu azure można wybrać dwie opcje: aplikacja Echo Bot oraz bot podstawowy. Samodzielnie bot mógłby tylko odpowiadać na konkretne polecenia, ale za pomocą dodatkowych serwisów można sprawić, że będzie on bardziej responsywny.

Serwisy wykorzystywane do budowania bota:
 - Azure Content Moderator
 - Language Understanding Intelligent Service (LUIS)
 - Text Analytics API
 
Cena zależy od wybranego pakietu. Darmowy umożliwia przetworzenie nielimitowanej ilości standardowych wiadomości i 10000 wiadomości premium, natomiast pakiet S1 ceni wiadomości premium $0.50 za 1000.


# Azure Content Moderator
Jest to serwis wykorzystujący sztuczną inteligencję, służy do wykrywania niepożądanych słów, zdjęć oraz materiałów wideo.

Może zostać wykorzystany w aplikacjach by uniemożliwić wysyłanie albo wycinanie fragmentów wiadomości zawierających wulgarne treści oraz zdjęć z nieprzyzwoitą zawartością. Innym przykładem może być ukrywanie treści wrażliwych dla użytkownika, takich jak mail czy adres IP.

Ten serwis tworzy się w aplikacji internetowej Microsoft Azure, dodając go jako zasób do wybranego projektu. Niepożądane słowa zapisuje się w pliku JSON zachowując odpowiedni format. Przetworzony tekst może zostać podzielony na 3 różne kategorie, w zależności, jak serwis go zinterpretuje. Działanie utworzonego serwisu można testować za pomocą strony moderatora zawartości: https://northeurope.dev.cognitive.microsoft.com/docs/services/57cf753a3f9b070c105bd2c1/operations/57cf753a3f9b070868a1f66e/console podając klucz subskrypcji w wymaganym polu.

Cena zależy od wybranej subskrypcji. Wersja darmowa nic nie kosztuje i pozwala na weryfikowanie 5000 wiadomości w ciągu miesiąca. W wersjach standardowych cena zależy od wybranego planu:

0-1M transakcji - $1 za 1,000 transakcji

1M-5M transakcji - $0.75 za 1,000 transakcji

5M-10M transakcji - $0.60 za 1,000 transakcji

10M+ transakcji - $0.40 za 1,000 transakcji


# Language Understanding Intelligent Service (LUIS)
Celem serwisu jest umożliwienie zrozumienia przez bota wysyłanych wiadomości. Przetwarza on otrzymane wiadomości i wyszukuje odpowiedni sens, jeśli treść mogłaby być dwuznaczna przy domyślnym tłumaczeniu.

Można go wykorzystać, by bot mógł zrozumieć w jakim kontekście zostało napisane dane zdanie lub słowo, kiedy ma ono wiele znaczeń, np. zamek.

Tworzy się go w aplikacji internetowej Microsoft Azure, dodając go jako zasób do wybranego projektu. Można zbudować z niego aplikację na stronie internetowej https://eu.luis.ai/. Dodaje się do niej intent (zamiary) i przykładowe wyrażenia jakimi może posłużyć się użytkownik. Następnie tworzy się entity (podmioty), które zostaną nauczone za pomocą uczenia maszynowego, jak rozpoznawać sens treści użytkowników, jako przykłady podając zdania tworzone w intent. 

Cena zależy od wybranego pakietu. Darmowy oferuje nielimitowaną ilość transakcji, ale z prędkością 5 transakcji na sekundę. Standardowy umożliwia porównywanie z prędkością 50 na sekundę i koszt transakcji wynosi $1.50 za 1000 wiadomości tekstowych i $5.50 za 1000 wiadomości głosowych.

# Text Analytics API
Celem serwisu jest analiza nastrojów, wyodrębnianie kluczowych fraz, wykrywanie języka i inne podobne funkcje. Wykorzystuje on uczenie maszynowe, by rozpoznawać wiadomości przesłane przez użytkowników i wyodrębniać zamiary i słowa klucze.

Przykładowym użyciem może być analizowanie komentarzy, co ludzie sądzą na konkretny temat. Za pomocą serwisu analiza przebiega szybciej niż gdyby ręcznie sprawdzało się każdy komentarz i wyodrębnienie najistotniejszych.

Serwis ten tworzy się w aplikacji internetowej Microsoft Azure, dodając go jako zasób do wybranego projektu. Za pomocą klucza można uzyskać dostęp do testowania serwisu na stronie https://northeurope.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0. Odpowiednio nauczony serwis jest w stanie rozpoznać pożądane informacje o przesłanych wiadomościach. Rozpoznane wiadomości można kategoryzować, by ułatwić posortowanie i późniejsze wykorzystanie wiadomości. By umożliwić wykorzystanie serwisu w tworzonym programie, koniecznie jest utworzenie aplikacji, za pomocą której będzie działał ten serwis. Dodaje się do niej funkcje, które będą wywoływanie przez odpowiednie wywoływacze.

Cena zależy od wybranego pakietu, które posiadają też różne funkcjonalności.

 - Darmowy: 
 
5000 transakcji na miesiąc

 - Standardowy:
 
0-500,000 wiadomości — $2 za 1,000 wiadomości

0.5M-2.5M wiadomości — $1 za 1,000 wiadomości

2.5M-10.0M wiadomości — $0.50 za 1,000 wiadomości

10M+ wiadomości — $0.25 za 1,000 wiadomości

 - S0
 
$74.71 miesięcznie Do 25,000 transakcji 

 - S1
 
$249.86 miesięcznie Do 100,000 transakcji 

 - S2
 
$999.75 miesięcznie Do 500,000 transakcji 

 - S3
 
$2,499.84 miesięcznie Do 2,500,000 transakcji 

 - S4
 
$4,999.99 miesięcznie Do 10,000,000 transakcji 

