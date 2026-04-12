# Fundamenty — jak działa web

To jedna z najważniejszych części nauki frontendu.  
Zanim wejdę głębiej w frameworki i bardziej złożone projekty, chcę dobrze rozumieć podstawy działania webu.

Nie chodzi tylko o umiejętność napisania komponentu.  
Chodzi o to, żeby rozumieć:

- co dzieje się po wejściu na stronę,
- jak przeglądarka pobiera i wyświetla dane,
- jak frontend komunikuje się z backendem,
- czym są requesty, API, DOM i renderowanie,
- jak debugować aplikację w przeglądarce.

Ta notatka jest moim kompendium do nauki fundamentów webu.

---

# 1. Frontend a backend

## Frontend

Frontend to wszystko to, co widzi i z czym wchodzi w interakcję użytkownik.

Przykłady:

- przyciski,
- formularze,
- menu,
- listy produktów,
- widoki,
- komunikaty błędów,
- animacje.

Frontend najczęściej buduje się przy pomocy:

- **HTML** — struktura strony,
- **CSS** — wygląd,
- **JavaScript** — logika i interakcje.

### Przykład

W sklepie internetowym frontend odpowiada za:

- wyświetlenie listy produktów,
- pokazanie ceny i zdjęcia,
- reakcję po kliknięciu „Dodaj do koszyka”,
- pokazanie informacji o sukcesie lub błędzie.

---

## Backend

Backend to część aplikacji działająca po stronie serwera.

Odpowiada za:

- logikę biznesową,
- pobieranie i zapisywanie danych,
- połączenie z bazą danych,
- autoryzację użytkownika,
- obsługę API,
- bezpieczeństwo.

### Przykład

W sklepie internetowym backend odpowiada za:

- pobranie produktów z bazy danych,
- zapisanie zamówienia,
- sprawdzenie, czy użytkownik jest zalogowany,
- przeliczenie wartości koszyka,
- zwrócenie danych do frontendu.

---

## Najprostsza różnica

- **Frontend** = to, co użytkownik widzi i klika
- **Backend** = to, co działa na serwerze i obsługuje dane oraz logikę

---

# 2. Jak frontend i backend współpracują?

Najczęściej komunikują się przez API.

### Przykładowy przepływ

1. Użytkownik otwiera stronę.
2. Frontend wyświetla interfejs.
3. Frontend wysyła request do backendu.
4. Backend pobiera dane z bazy.
5. Backend odsyła response.
6. Frontend wyświetla dane w UI.

To podstawowy model działania większości aplikacji webowych.

---

# 3. Jak działa przeglądarka?

Przeglądarka to program, który:

- pobiera zasoby z internetu,
- interpretuje HTML, CSS i JavaScript,
- buduje widok strony,
- reaguje na działania użytkownika.

Popularne przeglądarki:

- Chrome
- Firefox
- Safari
- Edge

---

## Co dzieje się po wpisaniu adresu strony?

Załóżmy, że wpisuję:

`https://example.com`

W uproszczeniu dzieje się to tak:

1. Przeglądarka odczytuje URL.
2. Sprawdza, jaki adres IP ma dana domena przy pomocy DNS.
3. Łączy się z serwerem.
4. Wysyła request HTTP.
5. Serwer odsyła response.
6. Przeglądarka pobiera HTML.
7. Następnie pobiera dodatkowe pliki:
   - CSS,
   - JavaScript,
   - obrazy,
   - fonty.
8. Buduje stronę i wyświetla ją użytkownikowi.
9. Jeśli strona zawiera JavaScript, uruchamia kod i dodaje interakcje.

---

## Rola HTML, CSS i JavaScript

### HTML

Opisuje strukturę strony.

### CSS

Nadaje stronie wygląd.

### JavaScript

Dodaje logikę i interaktywność.

### Przykład

Jeśli na stronie jest przycisk:

- HTML mówi: „tu istnieje przycisk”
- CSS mówi: „ma być niebieski i duży”
- JavaScript mówi: „po kliknięciu pobierz dane z API”

---

# 4. Request i response

To jeden z najważniejszych fundamentów webu.

## Request

Request to żądanie wysyłane przez klienta, najczęściej przeglądarkę, do serwera.

Przykład:

- „Daj mi listę produktów”
- „Zaloguj użytkownika”
- „Zapisz nowe zamówienie”

---

## Response

Response to odpowiedź serwera na request.

Przykład:

- „Oto lista produktów”
- „Logowanie zakończone sukcesem”
- „Nie udało się zapisać danych”

---

## Porównanie z życia

Można to porównać do restauracji:

- klient składa zamówienie → **request**
- kuchnia przygotowuje jedzenie → przetwarzanie
- kelner przynosi danie → **response**

---

## Co zwykle zawiera request?

- metodę HTTP,
- adres URL,
- nagłówki,
- czasem body z danymi.

### Przykład

```http
GET /products HTTP/1.1
Host: api.example.com
```

---

## Co zwykle zawiera response?

- status odpowiedzi,
- nagłówki,
- body z danymi.

### Przykład

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

Body:

```json
[{ "id": 1, "name": "Laptop", "price": 3999 }]
```

---

# 5. HTTP i HTTPS

## HTTP

HTTP to protokół komunikacji między klientem a serwerem.

Pełna nazwa:

**HyperText Transfer Protocol**

To zestaw zasad określających, jak mają wyglądać requesty i response.

---

## HTTPS

HTTPS to bezpieczna wersja HTTP.

Litera **S** oznacza **Secure**.

Dzięki HTTPS dane są szyfrowane w trakcie przesyłania.

---

## Dlaczego HTTPS jest ważny?

Chroni dane takie jak:

- hasła,
- tokeny,
- dane osobowe,
- dane płatnicze.

Frontend developer powinien rozumieć, że aplikacje produkcyjne powinny działać po HTTPS, a niektóre funkcje przeglądarki wymagają bezpiecznego połączenia.

---

# 6. URL

## Co to jest URL?

URL to adres zasobu w internecie.

Pełna nazwa:

**Uniform Resource Locator**

Przykład:

`https://example.com/products/12?sort=asc`

---

## Z czego składa się URL?

### `https://`

protokół

### `example.com`

domena

### `/products/12`

ścieżka

### `?sort=asc`

parametry zapytania

### `#section-2`

fragment / hash

---

## Przykłady parametrów w URL

- `?page=2`
- `?search=laptop`
- `?category=electronics&sort=price`

Parametry są często używane do filtrowania, wyszukiwania i paginacji.

---

# 7. DNS

## Co to jest DNS?

DNS to system, który tłumaczy nazwy domen na adresy IP.

Ludziom łatwiej zapamiętać:

`google.com`

niż:

`142.250.184.14`

DNS działa jak książka adresowa internetu.

---

## Jak działa DNS?

1. Wpisuję domenę, np. `example.com`
2. Przeglądarka musi ustalić adres IP serwera
3. Pyta o to DNS
4. DNS zwraca adres IP
5. Przeglądarka może połączyć się z właściwym serwerem

---

# 8. Cookies

## Co to są cookies?

Cookies to małe informacje przechowywane w przeglądarce.

Służą między innymi do:

- utrzymania sesji użytkownika,
- zapamiętywania ustawień,
- obsługi logowania,
- zapisywania zgody na cookies.

---

## Dlaczego cookies są potrzebne?

HTTP jest protokołem bezstanowym.  
To znaczy, że sam z siebie nie „pamięta”, kim był użytkownik przy poprzednim requestcie.

Cookies pomagają zachować stan między kolejnymi requestami.

---

## Przykład

Użytkownik loguje się do aplikacji.  
Serwer może zapisać cookie z identyfikatorem sesji.  
Przy kolejnych requestach przeglądarka dołącza to cookie, więc serwer wie, że to ten sam użytkownik.

---

## Ważne atrybuty cookies

### `HttpOnly`

Cookie nie jest dostępne z poziomu JavaScript.

### `Secure`

Cookie jest wysyłane tylko przez HTTPS.

### `SameSite`

Kontroluje, kiedy cookie może być wysłane między różnymi stronami.

---

# 9. localStorage i sessionStorage

To mechanizmy przechowywania danych w przeglądarce.

---

## localStorage

Dane zapisane w `localStorage` pozostają nawet po zamknięciu karty i przeglądarki.

### Przykłady użycia

- zapis motywu jasny/ciemny,
- zapis preferencji użytkownika,
- przechowywanie ustawień UI.

### Przykład

```js
localStorage.setItem("theme", "dark");
const theme = localStorage.getItem("theme");
```

---

## sessionStorage

Działa podobnie do `localStorage`, ale dane są przechowywane tylko do czasu zamknięcia danej karty.

### Przykłady użycia

- tymczasowy stan formularza,
- dane potrzebne tylko w jednej sesji.

---

## Różnica

### localStorage

- trwałe dane
- dostępne po ponownym otwarciu strony

### sessionStorage

- dane tymczasowe
- znikają po zamknięciu karty

---

## Cookies vs localStorage

### Cookies

- mogą być automatycznie wysyłane do serwera,
- często są używane do sesji i autoryzacji.

### localStorage

- działa tylko po stronie klienta,
- nie jest automatycznie wysyłane do serwera,
- nadaje się do prostych danych UI.

---

# 10. JSON

## Co to jest JSON?

JSON to bardzo popularny format zapisu danych.

Pełna nazwa:

**JavaScript Object Notation**

Jest lekki, czytelny i powszechnie używany w API.

---

## Przykład JSON

```json
{
  "id": 1,
  "name": "Anna",
  "isAdmin": false
}
```

---

## Gdzie spotykam JSON?

Najczęściej w:

- odpowiedziach API,
- plikach konfiguracyjnych,
- komunikacji frontend ↔ backend.

---

## JSON a obiekt JavaScript

Wyglądają podobnie, ale nie są tym samym.

### Obiekt JS

```js
const user = {
  name: "Anna",
};
```

### JSON

```json
{
  "name": "Anna"
}
```

JSON jest formatem tekstowym.

Najczęstsze operacje:

```js
JSON.stringify(user);
JSON.parse(jsonString);
```

---

# 11. REST API

## Co to jest API?

API to interfejs, dzięki któremu jeden system komunikuje się z drugim.

W frontendzie najczęściej oznacza to komunikację z backendem.

---

## Co to jest REST API?

REST API to popularny styl projektowania endpointów i komunikacji między klientem a serwerem.

Najczęściej operuje na zasobach, np.:

- users
- posts
- products
- orders

---

## Przykład endpointów REST

Dla zasobu `users`:

- `GET /users` — pobierz listę użytkowników
- `GET /users/1` — pobierz jednego użytkownika
- `POST /users` — utwórz użytkownika
- `PUT /users/1` — zaktualizuj użytkownika
- `DELETE /users/1` — usuń użytkownika

---

## Najczęstsze metody HTTP

### GET

Pobieranie danych

### POST

Tworzenie nowych danych

### PUT

Aktualizacja całego zasobu

### PATCH

Aktualizacja fragmentu zasobu

### DELETE

Usunięcie zasobu

---

## Przykład pobrania danych z API

```js
fetch("https://api.example.com/products")
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

## Co dzieje się w tym przykładzie?

1. Frontend wysyła request
2. Backend odbiera żądanie
3. Backend pobiera dane
4. Backend odsyła response w JSON
5. Frontend odbiera dane i może wyświetlić je w UI

---

## Najważniejsze statusy HTTP

### `200 OK`

Żądanie zakończone sukcesem

### `201 Created`

Zasób został utworzony

### `204 No Content`

Sukces, ale bez treści w odpowiedzi

### `400 Bad Request`

Błędne dane wysłane przez klienta

### `401 Unauthorized`

Brak autoryzacji

### `403 Forbidden`

Brak dostępu

### `404 Not Found`

Nie znaleziono zasobu

### `500 Internal Server Error`

Błąd po stronie serwera

---

# 12. DOM

## Co to jest DOM?

DOM to reprezentacja dokumentu HTML w postaci drzewa obiektów.

Pełna nazwa:

**Document Object Model**

Dzięki DOM JavaScript może:

- znajdować elementy,
- zmieniać tekst,
- dodawać i usuwać klasy,
- tworzyć nowe elementy,
- reagować na zdarzenia.

---

## Przykład HTML

```html
<body>
  <h1>Witaj</h1>
  <button>Kliknij</button>
</body>
```

Przeglądarka buduje z tego strukturę DOM:

- document
  - body
    - h1
    - button

---

## Przykład manipulacji DOM

```js
const button = document.querySelector("button");

button.addEventListener("click", () => {
  document.querySelector("h1").textContent = "Kliknięto!";
});
```

Po kliknięciu JavaScript zmienia treść elementu w DOM.

---

## Dlaczego DOM jest ważny?

Bo frontend to w dużej mierze:

- wyświetlanie danych,
- aktualizacja widoku,
- reagowanie na interakcje użytkownika.

Frameworki też finalnie wpływają na DOM, tylko robią to w bardziej uporządkowany sposób.

---

# 13. Renderowanie strony

Renderowanie to proces, w którym przeglądarka zamienia kod i dane na widoczny interfejs.

To moment, w którym użytkownik realnie widzi stronę.

---

## Uproszczony proces renderowania

1. Przeglądarka pobiera HTML
2. Buduje DOM
3. Pobiera CSS
4. Buduje CSSOM
5. Łączy DOM i CSSOM
6. Oblicza układ elementów
7. Rysuje elementy na ekranie
8. Wykonuje JavaScript i aktualizuje widok, jeśli trzeba

---

## Dlaczego renderowanie jest ważne?

Bo wpływa na:

- szybkość ładowania strony,
- wydajność,
- płynność działania,
- doświadczenie użytkownika,
- SEO.

---

# 14. CSR, SSR i SSG

To ważne sposoby renderowania aplikacji webowych.

---

## CSR — Client Side Rendering

Renderowanie odbywa się głównie po stronie klienta, czyli w przeglądarce.

### Jak to działa?

- serwer zwraca podstawowy HTML,
- przeglądarka pobiera JavaScript,
- JavaScript buduje widok,
- dane są często pobierane już po załadowaniu aplikacji.

### Zalety

- dobra interaktywność,
- wygodne dla aplikacji typu dashboard,
- dużo logiki po stronie klienta.

### Wady

- wolniejszy pierwszy widok,
- gorsze SEO,
- użytkownik może przez chwilę widzieć loader lub pusty ekran.

### Zastosowanie

- dashboardy,
- aplikacje po zalogowaniu,
- narzędzia wewnętrzne.

---

## SSR — Server Side Rendering

Renderowanie odbywa się na serwerze przy każdym requestcie.

### Jak to działa?

- użytkownik wchodzi na stronę,
- serwer generuje gotowy HTML,
- przeglądarka dostaje gotową stronę,
- JavaScript później dodaje interaktywność.

### Zalety

- szybszy pierwszy widok,
- lepsze SEO,
- dobre dla dynamicznych danych.

### Wady

- większe obciążenie serwera,
- bardziej złożona architektura.

### Zastosowanie

- e-commerce,
- strony z dynamiczną treścią,
- aplikacje, gdzie ważne są świeże dane i SEO.

---

## SSG — Static Site Generation

Strona jest generowana wcześniej, najczęściej podczas builda.

### Jak to działa?

- gotowe pliki HTML są tworzone wcześniej,
- użytkownik dostaje gotowy statyczny plik.

### Zalety

- bardzo szybkie ładowanie,
- świetne SEO,
- prosty hosting.

### Wady

- dane nie są zawsze świeże,
- przy dużej liczbie stron build może być cięższy.

### Zastosowanie

- blogi,
- landing pages,
- portfolio,
- dokumentacja.

---

## Jak zapamiętać różnice?

### CSR

Przeglądarka buduje widok

### SSR

Serwer buduje widok przy wejściu na stronę

### SSG

Widok został zbudowany wcześniej

---

# 15. Co dzieje się po kliknięciu przycisku?

To bardzo dobre pytanie sprawdzające rozumienie podstaw.

Załóżmy, że użytkownik klika przycisk „Pobierz użytkowników”.

---

## Możliwy przepływ

1. Użytkownik klika przycisk
2. Przeglądarka wykrywa zdarzenie `click`
3. JavaScript uruchamia odpowiednią funkcję
4. Funkcja wysyła request do API
5. Backend odbiera request
6. Backend pobiera dane z bazy
7. Backend odsyła response w formacie JSON
8. Frontend odbiera dane
9. JavaScript aktualizuje DOM lub stan aplikacji
10. Użytkownik widzi nowe dane na ekranie

---

## Przykład

```js
const button = document.querySelector("#load-users");
const list = document.querySelector("#users-list");

button.addEventListener("click", async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");
  const users = await response.json();

  list.innerHTML = users.map((user) => `<li>${user.name}</li>`).join("");
});
```

---

# 16. Jak pobrać dane z API i wyświetlić je w UI?

To jeden z absolutnych fundamentów frontendu.

## Przykład

```js
async function loadPosts() {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts");
  const posts = await response.json();

  const container = document.querySelector("#posts");

  container.innerHTML = posts
    .slice(0, 5)
    .map(
      (post) => `
        <article>
          <h2>${post.title}</h2>
          <p>${post.body}</p>
        </article>
      `,
    )
    .join("");
}

loadPosts();
```

---

## Co się tutaj dzieje?

- `fetch()` wysyła request,
- `await` czeka na odpowiedź,
- `response.json()` zamienia odpowiedź na dane,
- dane są mapowane na HTML,
- HTML trafia do DOM.

---

## O czym trzeba pamiętać w praktyce?

W realnej aplikacji trzeba obsłużyć:

- loading,
- błędy,
- puste dane.

### Lepsza wersja

```js
async function loadPosts() {
  const container = document.querySelector("#posts");
  container.textContent = "Ładowanie...";

  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");

    if (!response.ok) {
      throw new Error("Błąd pobierania danych");
    }

    const posts = await response.json();

    container.innerHTML = posts
      .slice(0, 5)
      .map(
        (post) => `
          <article>
            <h2>${post.title}</h2>
            <p>${post.body}</p>
          </article>
        `,
      )
      .join("");
  } catch (error) {
    container.textContent = "Nie udało się pobrać danych.";
  }
}
```

---

# 17. DevTools w przeglądarce

DevTools to podstawowe narzędzie pracy frontend developera.

Najczęściej uruchamia się je przez:

- `F12`
- `Ctrl + Shift + I`

---

## Najważniejsze zakładki

## Elements

Pozwala oglądać i edytować HTML oraz CSS.

Przydaje się do:

- sprawdzania struktury DOM,
- debugowania stylów,
- testowania zmian wizualnych.

---

## Console

Pokazuje:

- błędy JavaScript,
- ostrzeżenia,
- logi z `console.log()`.

Przydaje się do debugowania kodu.

---

## Network

Jedna z najważniejszych zakładek.

Pokazuje:

- requesty,
- response,
- statusy HTTP,
- czas ładowania,
- nagłówki,
- payload.

Przydaje się do:

- sprawdzania, czy API działa,
- analizy błędów `404` i `500`,
- sprawdzania, jakie dane przychodzą z backendu.

---

## Application

Tutaj można sprawdzić między innymi:

- cookies,
- localStorage,
- sessionStorage.

---

## Sources

Pozwala analizować pliki JavaScript, ustawiać breakpointy i debugować kod krok po kroku.

---

# 18. Jak używać DevTools w praktyce?

## Gdy coś nie działa

### 1. Sprawdzam Console

Czy pojawił się błąd JavaScript?

### 2. Sprawdzam Network

Czy request został wysłany?  
Jaki ma status?  
Czy response zawiera poprawne dane?

### 3. Sprawdzam Elements

Czy element istnieje w DOM?  
Czy nie został ukryty przez CSS?

### 4. Sprawdzam Application

Czy localStorage, sessionStorage albo cookies mają oczekiwane wartości?

---

## Typowy przykład problemu

Lista produktów się nie wyświetla.

Sprawdzam wtedy:

- czy skrypt się uruchomił,
- czy `fetch` został wykonany,
- czy response ma status `200`,
- czy dane mają taki kształt, jak zakładam,
- czy poprawnie renderuję dane do DOM,
- czy kontener docelowy istnieje na stronie.

---

# 19. Najważniejsze pojęcia dodatkowe

## Klient

Najczęściej przeglądarka użytkownika.

## Serwer

Aplikacja lub maszyna obsługująca requesty.

## Baza danych

Miejsce przechowywania danych aplikacji.

## Endpoint

Konkretny adres API, np. `/users` albo `/posts/1`.

## Payload

Dane wysyłane w request albo response.

## Header

Dodatkowe informacje o request albo response.

## Body

Główna treść requestu albo odpowiedzi.

## Status code

Kod określający wynik operacji.

---

# 20. Jak to wszystko łączy się w całość?

Przykład: aplikacja do zarządzania zadaniami.

### Frontend

- pokazuje listę zadań,
- wyświetla formularz,
- reaguje na kliknięcie „Dodaj zadanie”.

### Backend

- przechowuje zadania,
- zapisuje nowe zadania,
- zwraca listę zadań do frontendu.

### Przepływ

1. Użytkownik otwiera stronę
2. Przeglądarka pobiera aplikację
3. Frontend wysyła request po listę zadań
4. Backend odsyła JSON
5. Frontend renderuje listę
6. Użytkownik dodaje zadanie
7. Frontend wysyła `POST` do API
8. Backend zapisuje dane
9. Frontend odświeża widok

To jest praktyczne działanie webu.

---

# 21. Co powinienem umieć po przerobieniu tej notatki?

Powinienem umieć własnymi słowami wyjaśnić:

- czym różni się frontend od backendu,
- jak działa przeglądarka po wejściu na stronę,
- czym są request i response,
- czym różni się HTTP od HTTPS,
- z czego składa się URL,
- czym jest DNS,
- do czego służą cookies,
- czym różni się localStorage od sessionStorage,
- czym jest JSON,
- czym jest REST API,
- czym jest DOM,
- jak działa renderowanie strony,
- czym różni się CSR, SSR i SSG,
- jak używać DevTools do sprawdzania błędów.

---

# 22. Mini checklista

## Teoria

- [ ] umiem wyjaśnić różnicę między frontendem a backendem
- [ ] wiem, jak działa przeglądarka po wejściu na stronę
- [ ] rozumiem request i response
- [ ] znam podstawy HTTP i HTTPS
- [ ] wiem, z czego składa się URL
- [ ] rozumiem, czym jest DNS
- [ ] wiem, czym są cookies
- [ ] rozumiem różnicę między localStorage i sessionStorage
- [ ] wiem, czym jest JSON
- [ ] rozumiem podstawy REST API
- [ ] wiem, czym jest DOM
- [ ] rozumiem, czym jest renderowanie strony
- [ ] znam różnice między CSR, SSR i SSG
- [ ] umiem korzystać z podstawowych zakładek DevTools

## Praktyka

- [ ] potrafię pobrać dane z API przez `fetch`
- [ ] potrafię sparsować odpowiedź JSON
- [ ] potrafię wyrenderować dane w UI
- [ ] potrafię obsłużyć loading i error state
- [ ] potrafię sprawdzić request w zakładce Network
- [ ] potrafię znaleźć błąd w Console
- [ ] potrafię podejrzeć localStorage, sessionStorage i cookies
- [ ] potrafię wyjaśnić krok po kroku, co dzieje się po kliknięciu przycisku

---

# Podsumowanie

Fundamenty webu są bazą całego frontendu.

Bez nich można nauczyć się składni frameworka, ale trudno będzie:

- dobrze debugować,
- świadomie budować aplikacje,
- rozumieć integrację z API,
- tłumaczyć swoje decyzje techniczne,
- rozwijać się dalej jako frontend developer.

Dlatego ten temat traktuję jako obowiązkowy fundament przed głębszym wejściem w React, Next.js i bardziej zaawansowane projekty.
