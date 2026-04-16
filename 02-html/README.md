# HTML — kompletna notatka do nauki

## Czym jest HTML

**HTML** (_HyperText Markup Language_) to język znaczników służący do opisywania struktury strony internetowej.

HTML:

- nie odpowiada za wygląd strony jak CSS,
- nie odpowiada za logikę jak JavaScript,
- odpowiada za **strukturę, znaczenie i organizację treści**.

To dzięki HTML przeglądarka wie:

- co jest nagłówkiem,
- co jest akapitem,
- co jest linkiem,
- co jest obrazem,
- co jest formularzem,
- co jest tabelą,
- co jest główną treścią strony.

HTML to fundament frontendu.

---

## 1. Podstawowa struktura dokumentu HTML

Każda strona HTML powinna mieć poprawny szkielet:

```html
<!DOCTYPE html>
<html lang="pl">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Tytuł strony</title>
  </head>
  <body>
    <h1>Witaj na stronie</h1>
    <p>To jest przykładowy dokument HTML.</p>
  </body>
</html>
```

### Omówienie

#### `<!DOCTYPE html>`

Informuje przeglądarkę, że dokument jest napisany w HTML5.

#### `<html>`

Główny element dokumentu. Zawiera całą stronę.

#### `lang="pl"`

Określa język dokumentu.  
To ważne dla:

- czytników ekranu,
- tłumaczeń,
- SEO,
- poprawnej interpretacji treści.

#### `<head>`

Zawiera metadane dokumentu, czyli informacje o stronie niewidoczne bezpośrednio jako treść.

Najczęściej znajdują się tam:

- `meta charset`,
- `meta viewport`,
- `title`,
- linki do CSS,
- favicon,
- meta tagi SEO.

#### `<meta charset="UTF-8" />`

Ustawia kodowanie znaków. Dzięki temu polskie litery wyświetlają się poprawnie.

#### `<meta name="viewport" content="width=device-width, initial-scale=1.0" />`

Bardzo ważne dla urządzeń mobilnych. Umożliwia poprawne skalowanie strony.

#### `<title>`

Tytuł strony widoczny w karcie przeglądarki i używany przez wyszukiwarki.

#### `<body>`

Zawiera treść widoczną dla użytkownika.

---

## 2. Elementy blokowe i liniowe

### Elementy blokowe

Zajmują całą dostępną szerokość i zaczynają się od nowej linii.

Przykłady:

- `div`
- `p`
- `h1-h6`
- `section`
- `article`
- `main`
- `header`
- `footer`
- `ul`
- `ol`
- `li`

### Elementy liniowe

Układają się w linii i zajmują tylko tyle miejsca, ile potrzebują.

Przykłady:

- `span`
- `a`
- `strong`
- `em`
- `img`
- `label`

### Przykład

```html
<p>To jest <strong>ważny</strong> fragment tekstu.</p>
```

Tutaj:

- `p` jest elementem blokowym,
- `strong` jest elementem liniowym.

---

## 3. Semantyczny HTML

### Co to znaczy „semantyczny HTML”

Semantyka oznacza, że tag opisuje **znaczenie elementu**, a nie tylko jego wygląd.

Przykład słabego podejścia:

```html
<div>Menu</div>
<div>Treść artykułu</div>
<div>Stopka</div>
```

To działa, ale nie mówi, czym są te elementy.

Lepsza wersja:

```html
<nav>Menu</nav>
<main>Treść artykułu</main>
<footer>Stopka</footer>
```

Tutaj kod od razu komunikuje znaczenie elementów.

### Dlaczego semantyczny HTML jest ważny

#### 1. Dostępność

Czytniki ekranu lepiej rozumieją strukturę strony.

#### 2. SEO

Wyszukiwarki lepiej rozumieją zawartość.

#### 3. Czytelność kodu

Kod jest bardziej zrozumiały dla innych developerów.

#### 4. Utrzymanie projektu

Kod łatwiej rozwijać i poprawiać.

---

## 4. Najważniejsze semantyczne tagi

### `header`

Nagłówek strony lub sekcji.

```html
<header>
  <h1>Moja strona</h1>
  <nav>
    <a href="/">Start</a>
    <a href="/o-mnie">O mnie</a>
  </nav>
</header>
```

Może być używany:

- jako nagłówek całej strony,
- jako nagłówek artykułu,
- jako nagłówek sekcji.

### `main`

Główna treść strony.

```html
<main>
  <h2>Aktualności</h2>
  <p>To jest główna zawartość strony.</p>
</main>
```

Na stronie zazwyczaj powinien występować jeden element `main`.

### `section`

Sekcja tematyczna, zwykle posiadająca własny nagłówek.

```html
<section>
  <h2>Oferta</h2>
  <p>Opis oferty...</p>
</section>
```

Używaj `section`, gdy treść tworzy logiczną część dokumentu.

### `article`

Samodzielna, niezależna treść.

Przykłady:

- wpis blogowy,
- news,
- karta artykułu,
- komentarz,
- post.

```html
<article>
  <h2>Jak uczyć się HTML</h2>
  <p>Artykuł o podstawach HTML...</p>
</article>
```

### `nav`

Sekcja nawigacyjna z linkami.

```html
<nav>
  <ul>
    <li><a href="/">Start</a></li>
    <li><a href="/blog">Blog</a></li>
    <li><a href="/kontakt">Kontakt</a></li>
  </ul>
</nav>
```

Nie każdy zestaw linków to `nav`.  
Używamy go dla ważnych bloków nawigacyjnych.

### `aside`

Treść poboczna, dodatkowa.

Przykłady:

- sidebar,
- powiązane artykuły,
- box z dodatkowymi informacjami,
- reklama.

```html
<aside>
  <h2>Powiązane wpisy</h2>
  <ul>
    <li><a href="#">HTML semantic</a></li>
    <li><a href="#">Formularze</a></li>
  </ul>
</aside>
```

### `footer`

Stopka strony lub sekcji.

```html
<footer>
  <p>&copy; 2026 Moja strona</p>
</footer>
```

---

## 5. Tekst i struktura treści

### Nagłówki `h1`–`h6`

Nagłówki tworzą hierarchię treści.

- `h1` — główny tytuł strony lub dokumentu,
- `h2` — główne sekcje,
- `h3` — podsekcje,
- kolejne poziomy rozwijają strukturę.

### Dobre praktyki

- Używaj nagłówków w logicznej kolejności.
- Nie wybieraj nagłówka ze względu na jego wielkość wizualną.
- Zazwyczaj strona powinna mieć jedno `h1`.

### Przykład

```html
<h1>Kurs HTML</h1>
<h2>Podstawy</h2>
<h3>Struktura dokumentu</h3>
<h2>Formularze</h2>
```

### `p`

Akapit tekstu.

```html
<p>HTML służy do budowania struktury strony internetowej.</p>
```

### `span`

Neutralny semantycznie element liniowy. Najczęściej używany do stylowania fragmentu tekstu lub pomocniczej logiki.

```html
<p>Cena: <span>99 zł</span></p>
```

### `strong`

Oznacza ważność treści.

```html
<p><strong>Uwaga:</strong> formularz musi być poprawnie oznaczony.</p>
```

### `em`

Oznacza nacisk lub akcent.

```html
<p>To jest <em>naprawdę</em> istotne.</p>
```

### Różnica między `strong` a `b`, `em` a `i`

- `strong` i `em` mają znaczenie semantyczne,
- `b` i `i` są bardziej prezentacyjne.

W praktyce zwykle lepiej używać:

- `strong` zamiast `b`,
- `em` zamiast `i`.

---

## 6. Listy

### Lista nieuporządkowana `ul`

Gdy kolejność elementów nie ma znaczenia.

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

### Lista uporządkowana `ol`

Gdy kolejność ma znaczenie.

```html
<ol>
  <li>Otwórz edytor</li>
  <li>Utwórz plik index.html</li>
  <li>Dodaj strukturę dokumentu</li>
</ol>
```

### `li`

Pojedynczy element listy.

### Dobre praktyki

- Nie używaj `div` tam, gdzie lista opisuje zbiór elementów.
- Menu, kroki instrukcji, cechy produktu często warto modelować jako listy.

---

## 7. Linki

### `a`

Tag służący do tworzenia linków.

```html
<a href="https://developer.mozilla.org/">MDN</a>
```

### Najważniejsze atrybuty linku

#### `href`

Adres docelowy.

### Link wewnętrzny

```html
<a href="/kontakt">Kontakt</a>
```

### Link zewnętrzny

```html
<a href="https://github.com/">GitHub</a>
```

### Link do sekcji na stronie

```html
<a href="#formularz">Przejdź do formularza</a>

<section id="formularz">
  <h2>Formularz</h2>
</section>
```

### `target="_blank"`

Otwiera link w nowej karcie.

```html
<a href="https://github.com/" target="_blank" rel="noopener noreferrer">
  GitHub
</a>
```

Przy `target="_blank"` dodawaj `rel="noopener noreferrer"`.

### Kiedy używać `a`, a kiedy `button`

To bardzo ważna różnica.

#### Użyj `a`, gdy:

- przechodzisz do innej strony,
- przechodzisz do sekcji,
- otwierasz dokument,
- wykonujesz nawigację.

#### Użyj `button`, gdy:

- otwierasz modal,
- wysyłasz formularz,
- usuwasz element,
- zmieniasz stan interfejsu,
- uruchamiasz akcję JavaScript.

### Błędnie

```html
<a href="#" onclick="openModal()">Otwórz modal</a>
```

### Poprawnie

```html
<button type="button">Otwórz modal</button>
```

**Zasada:**  
`a` = nawigacja  
`button` = akcja

---

## 8. Obrazy i media

### `img`

Wyświetla obraz.

```html
<img src="avatar.jpg" alt="Zdjęcie profilowe Jana Kowalskiego" />
```

### Najważniejsze atrybuty

#### `src`

Ścieżka do pliku.

#### `alt`

Tekst alternatywny.

Jest ważny dla:

- dostępności,
- czytników ekranu,
- sytuacji, gdy obrazek się nie załaduje,
- częściowo SEO.

### Jak pisać dobre `alt`

#### Dobre przykłady

```html
<img src="pies.jpg" alt="Czarny pies biegnący po trawie" />
```

#### Złe przykłady

```html
<img src="pies.jpg" alt="image" />
<img src="pies.jpg" alt="foto" />
<img src="pies.jpg" alt="pies pies pies" />
```

### Zasady pisania `alt`

- Opisuj sens obrazka.
- Nie pisz bez potrzeby „obrazek przedstawia”.
- Jeśli obraz jest dekoracyjny, użyj pustego `alt`.

### Obraz dekoracyjny

```html
<img src="divider.png" alt="" />
```

### `picture`

Pozwala ładować różne obrazy zależnie od warunków, np. szerokości ekranu lub obsługiwanego formatu.

```html
<picture>
  <source srcset="image.webp" type="image/webp" />
  <source srcset="image.jpg" type="image/jpeg" />
  <img src="image.jpg" alt="Widok gór o zachodzie słońca" />
</picture>
```

### `figure` i `figcaption`

Do ilustracji z podpisem.

```html
<figure>
  <img src="chart.png" alt="Wykres wzrostu sprzedaży w 2025 roku" />
  <figcaption>Sprzedaż rosła przez cały 2025 rok.</figcaption>
</figure>
```

---

## 9. Video i audio

### `video`

```html
<video controls width="600">
  <source src="movie.mp4" type="video/mp4" />
  Twoja przeglądarka nie obsługuje elementu video.
</video>
```

### `audio`

```html
<audio controls>
  <source src="podcast.mp3" type="audio/mpeg" />
  Twoja przeglądarka nie obsługuje elementu audio.
</audio>
```

### Przydatne atrybuty

- `controls` — pokazuje kontrolki,
- `autoplay` — automatyczne odtwarzanie,
- `muted` — wyciszenie,
- `loop` — zapętlenie,
- `poster` — miniatura dla video.

### Dobra praktyka

Nie nadużywaj `autoplay`.  
Automatyczne odtwarzanie dźwięku to zły UX.

---

## 10. Tabele

Tabele służą do prezentowania **danych tabelarycznych**, a nie do budowania layoutu strony.

### Podstawowe elementy tabeli

- `table` — tabela,
- `thead` — nagłówek tabeli,
- `tbody` — ciało tabeli,
- `tr` — wiersz,
- `th` — komórka nagłówkowa,
- `td` — komórka danych.

### Przykład

```html
<table>
  <thead>
    <tr>
      <th>Nazwa</th>
      <th>Cena</th>
      <th>Dostępność</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Laptop</td>
      <td>4500 zł</td>
      <td>Tak</td>
    </tr>
    <tr>
      <td>Monitor</td>
      <td>1200 zł</td>
      <td>Nie</td>
    </tr>
  </tbody>
</table>
```

### Dobre praktyki

- Używaj tabel tylko do danych tabelarycznych.
- Nagłówki oznaczaj przez `th`.
- Przy bardziej zaawansowanych tabelach warto znać `scope`.

### Przykład z `scope`

```html
<table>
  <thead>
    <tr>
      <th scope="col">Produkt</th>
      <th scope="col">Cena</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Klawiatura</th>
      <td>300 zł</td>
    </tr>
  </tbody>
</table>
```

To poprawia dostępność tabeli.

---

## 11. Formularze

Formularze to jeden z najważniejszych tematów w HTML.

### `form`

Opakowuje pola formularza.

```html
<form action="/send" method="post">
  <label for="email">Email</label>
  <input id="email" name="email" type="email" />

  <button type="submit">Wyślij</button>
</form>
```

### Najważniejsze atrybuty formularza

#### `action`

Adres, na który formularz ma zostać wysłany.

#### `method`

Metoda wysyłki:

- `get` — dane trafiają do URL,
- `post` — dane trafiają w body zapytania.

### `label`

Etykieta pola.

```html
<label for="name">Imię</label> <input id="name" name="name" type="text" />
```

### Dlaczego `label` jest ważny

- poprawia dostępność,
- kliknięcie etykiety aktywuje pole,
- zwiększa czytelność formularza.

### Jak poprawnie połączyć `label` z polem

#### Sposób 1 — `for` + `id`

```html
<label for="email">Email</label> <input id="email" name="email" type="email" />
```

#### Sposób 2 — zagnieżdżenie

```html
<label>
  Email
  <input name="email" type="email" />
</label>
```

Oba podejścia są poprawne.

---

## 12. Pola formularza

### `input`

Najbardziej uniwersalne pole formularza.

#### Typ `text`

```html
<input type="text" name="firstName" />
```

#### Typ `email`

```html
<input type="email" name="email" />
```

#### Typ `password`

```html
<input type="password" name="password" />
```

#### Typ `number`

```html
<input type="number" name="age" min="1" max="120" />
```

#### Typ `tel`

```html
<input type="tel" name="phone" />
```

#### Typ `url`

```html
<input type="url" name="website" />
```

#### Typ `date`

```html
<input type="date" name="birthDate" />
```

#### Typ `checkbox`

```html
<label>
  <input type="checkbox" name="terms" />
  Akceptuję regulamin
</label>
```

#### Typ `radio`

```html
<p>Wybierz plan:</p>

<label>
  <input type="radio" name="plan" value="basic" />
  Basic
</label>

<label>
  <input type="radio" name="plan" value="pro" />
  Pro
</label>
```

Radio buttony z tym samym `name` tworzą jedną grupę.

#### Typ `file`

```html
<input type="file" name="avatar" />
```

#### Typ `submit`

```html
<input type="submit" value="Wyślij" />
```

W praktyce częściej używa się:

```html
<button type="submit">Wyślij</button>
```

---

## 13. `textarea`

Służy do wpisywania dłuższego tekstu.

```html
<label for="message">Wiadomość</label>
<textarea id="message" name="message" rows="5" cols="30"></textarea>
```

---

## 14. `select`

Lista rozwijana.

```html
<label for="country">Kraj</label>
<select id="country" name="country">
  <option value="">Wybierz kraj</option>
  <option value="pl">Polska</option>
  <option value="de">Niemcy</option>
  <option value="cz">Czechy</option>
</select>
```

---

## 15. `button`

Przycisk.

```html
<button type="button">Kliknij</button>
<button type="submit">Wyślij</button>
<button type="reset">Wyczyść</button>
```

### Typy przycisków

#### `type="button"`

Do zwykłych akcji JavaScript.

#### `type="submit"`

Wysyła formularz.

#### `type="reset"`

Resetuje formularz.

### Ważne

Jeśli przycisk znajduje się w formularzu i nie ma jawnie ustawionego `type`, może działać jak `submit`.  
Dlatego warto zawsze podawać typ.

---

## 16. `fieldset` i `legend`

Służą do grupowania powiązanych pól formularza.

```html
<form>
  <fieldset>
    <legend>Dane kontaktowe</legend>

    <label for="name">Imię</label>
    <input id="name" name="name" type="text" />

    <label for="email">Email</label>
    <input id="email" name="email" type="email" />
  </fieldset>
</form>
```

To poprawia strukturę i dostępność formularza.

---

## 17. Najważniejsze atrybuty HTML

### `id`

Unikalny identyfikator elementu.

```html
<input id="email" type="email" />
```

Zastosowania:

- połączenie z `label`,
- linkowanie do sekcji,
- selekcja w CSS i JavaScript.

### `class`

Klasa CSS lub znacznik pomocniczy.

```html
<p class="description">Opis produktu</p>
```

Element może mieć wiele klas.

### `name`

Bardzo ważny atrybut formularza.  
To pod tym kluczem pole zostanie wysłane.

```html
<input name="email" type="email" />
```

### `value`

Wartość pola.

```html
<input type="text" name="city" value="Warszawa" />
```

### `placeholder`

Podpowiedź w polu.

```html
<input type="text" name="search" placeholder="Wpisz nazwę produktu" />
```

### Uwaga

`placeholder` **nie zastępuje labela**.

### `disabled`

Wyłącza element.

```html
<input type="text" disabled /> <button disabled>Zapisz</button>
```

Wyłączone pola zwykle nie są wysyłane z formularzem.

### `required`

Oznacza pole obowiązkowe.

```html
<input type="email" name="email" required />
```

---

## 18. Podstawy ARIA

**ARIA** (_Accessible Rich Internet Applications_) pomaga technologiom wspierającym lepiej interpretować interfejs.

Najważniejsza zasada:

> Najpierw używaj poprawnego semantycznego HTML.  
> Dopiero później sięgaj po ARIA, jeśli naprawdę jest potrzebna.

### Podstawowe atrybuty ARIA

#### `aria-label`

Nadaje etykietę elementowi, który nie ma widocznego tekstu.

```html
<button aria-label="Zamknij okno">×</button>
```

#### `aria-hidden="true"`

Ukrywa element dla czytników ekranu.

```html
<span aria-hidden="true">★</span>
```

#### `aria-expanded`

Informuje, czy element rozwijany jest otwarty.

```html
<button aria-expanded="false">Pokaż menu</button>
```

#### `aria-describedby`

Łączy pole z dodatkowym opisem.

```html
<label for="password">Hasło</label>
<input
  id="password"
  name="password"
  type="password"
  aria-describedby="password-help"
/>
<p id="password-help">Hasło musi mieć minimum 8 znaków.</p>
```

### Ważne

Nie dodawaj ARIA bez potrzeby.  
Źle użyte ARIA może pogorszyć dostępność.

---

## 19. Walidacja HTML5

HTML oferuje wbudowaną walidację formularzy bez JavaScript.

### `required`

```html
<input type="text" name="firstName" required />
```

### `minlength`

```html
<input type="text" name="username" minlength="3" />
```

### `maxlength`

```html
<input type="text" name="username" maxlength="20" />
```

### `pattern`

```html
<input type="text" name="postalCode" pattern="[0-9]{2}-[0-9]{3}" />
```

Przykład dla polskiego kodu pocztowego: `00-000`.

### `min` i `max`

```html
<input type="number" name="age" min="18" max="99" />
```

### Typy inputów wspierające walidację

- `email`
- `url`
- `number`
- `date`
- `password` — sam typ nie waliduje siły hasła
- `tel` — walidacja jest ograniczona

### Przykład formularza z walidacją

```html
<form>
  <label for="email">Email</label>
  <input id="email" name="email" type="email" required />

  <label for="username">Nazwa użytkownika</label>
  <input
    id="username"
    name="username"
    type="text"
    minlength="3"
    maxlength="20"
    required
  />

  <label for="postalCode">Kod pocztowy</label>
  <input
    id="postalCode"
    name="postalCode"
    type="text"
    pattern="[0-9]{2}-[0-9]{3}"
    required
  />

  <button type="submit">Wyślij</button>
</form>
```

---

## 20. Constraint Validation — podstawy

Constraint Validation API to mechanizm przeglądarki do sprawdzania poprawności pól formularza.

W praktyce warto rozumieć, że:

- przeglądarka sprawdza warunki typu `required`, `pattern`, `minlength`,
- jeśli pole jest niepoprawne, formularz nie zostanie wysłany,
- użytkownik zobaczy komunikat walidacyjny przeglądarki.

### Co warto zapamiętać

- HTML potrafi zrobić podstawową walidację bez JavaScript,
- JavaScript często rozszerza walidację,
- backend i tak zawsze musi ponownie sprawdzić dane.

---

## 21. Dlaczego używać semantycznych tagów zamiast samych `div`

`div` sam w sobie nic nie znaczy.  
To tylko ogólny kontener.

### Problem z nadmiarem `div`

```html
<div class="header">
  <div class="menu">...</div>
</div>
<div class="content">...</div>
<div class="footer">...</div>
```

Taki kod nie komunikuje znaczenia elementów.

### Lepsza wersja

```html
<header>
  <nav>...</nav>
</header>
<main>...</main>
<footer>...</footer>
```

### Korzyści

- lepsza dostępność,
- lepsze SEO,
- bardziej czytelny kod,
- łatwiejsze utrzymanie projektu.

---

## 22. Jak poprawnie budować formularze

Dobry formularz powinien mieć:

- poprawny element `form`,
- logiczne grupowanie pól,
- etykiety `label`,
- odpowiednie typy `input`,
- walidację HTML5,
- jasny przycisk submit,
- dobrą dostępność.

### Dobry przykład

```html
<form action="/contact" method="post">
  <fieldset>
    <legend>Formularz kontaktowy</legend>

    <div>
      <label for="name">Imię i nazwisko</label>
      <input id="name" name="name" type="text" required />
    </div>

    <div>
      <label for="email">Adres email</label>
      <input id="email" name="email" type="email" required />
    </div>

    <div>
      <label for="topic">Temat</label>
      <select id="topic" name="topic" required>
        <option value="">Wybierz temat</option>
        <option value="offer">Oferta</option>
        <option value="support">Wsparcie</option>
        <option value="other">Inne</option>
      </select>
    </div>

    <div>
      <label for="message">Wiadomość</label>
      <textarea id="message" name="message" rows="6" required></textarea>
    </div>

    <div>
      <label>
        <input type="checkbox" name="terms" required />
        Akceptuję regulamin
      </label>
    </div>

    <button type="submit">Wyślij wiadomość</button>
  </fieldset>
</form>
```

---

## 23. Jak robić dostępne etykiety do inputów

To bardzo ważny temat.

### Dobra etykieta:

- mówi, czego dotyczy pole,
- jest powiązana z inputem,
- nie znika po wpisaniu treści,
- nie jest zastąpiona samym placeholderem.

### Poprawnie

```html
<label for="email">Adres email</label>
<input id="email" name="email" type="email" />
```

### Źle

```html
<input type="email" placeholder="Adres email" />
```

Tutaj brakuje prawdziwej etykiety.

### Dodatkowy opis pola

```html
<label for="password">Hasło</label>
<input
  id="password"
  name="password"
  type="password"
  aria-describedby="password-info"
/>
<p id="password-info">Hasło musi mieć minimum 8 znaków i jedną cyfrę.</p>
```

---

## 24. Poprawne alt texty

### Funkcja `alt`

Tekst alternatywny opisuje obraz wtedy, gdy użytkownik go nie widzi.

### Jak pisać `alt`

Pytanie pomocnicze:

> Jaką informację niesie ten obraz?

Jeśli obraz jest ważny, `alt` powinien przekazać jego sens.

### Przykłady

#### Obraz informacyjny

```html
<img src="team.jpg" alt="Zespół pięciu programistów stojących w biurze" />
```

#### Ikona w przycisku

Jeśli przycisk ma już tekst, ikona może być dekoracyjna:

```html
<button>
  <img src="search.svg" alt="" />
  Szukaj
</button>
```

#### Obraz dekoracyjny

```html
<img src="background-shape.svg" alt="" />
```

### Czego unikać

- `alt="image"`
- `alt="foto"`
- upychania słów kluczowych
- powtarzania informacji, która już jest obok obrazka

---

## 25. Globalne atrybuty, które warto znać

### `title`

Dodatkowa podpowiedź tekstowa.

```html
<button title="Usuń element">Usuń</button>
```

Nie traktuj `title` jako podstawowego sposobu komunikacji z użytkownikiem.

### `hidden`

Ukrywa element.

```html
<p hidden>Ukryta informacja</p>
```

### `tabindex`

Steruje kolejnością fokusu klawiatury.

Na start warto wiedzieć:

- natywne elementy interaktywne zwykle nie potrzebują `tabindex`,
- nie należy go nadużywać.

### `data-*`

Atrybuty do przechowywania własnych danych.

```html
<button data-product-id="123">Dodaj do koszyka</button>
```

---

## 26. Komentarze w HTML

```html
<!-- To jest komentarz -->
```

Komentarze pomagają organizować kod, ale nie należy przesadzać z ich liczbą.

---

## 27. Encje HTML

Niektóre znaki mają specjalne znaczenie i trzeba je zapisywać encjami.

Przykłady:

- `&lt;` = `<`
- `&gt;` = `>`
- `&amp;` = `&`
- `&copy;` = ©
- `&nbsp;` = twarda spacja

Przykład:

```html
<p>&copy; 2026 Moja strona</p>
```

---

## 28. SEO basics w HTML

HTML ma duży wpływ na SEO.

### Najważniejsze podstawy

- poprawny `<title>`,
- logiczna struktura nagłówków,
- semantyczne tagi,
- opisywne linki,
- poprawne `alt`,
- unikalna i sensowna treść,
- poprawny język dokumentu (`lang`).

### Zły link

```html
<a href="/oferta">Kliknij tutaj</a>
```

### Lepszy link

```html
<a href="/oferta">Zobacz ofertę tworzenia stron internetowych</a>
```

Link powinien jasno mówić, dokąd prowadzi.

---

## 29. Dostępność — podstawy, które musisz znać

Dostępność (_accessibility, a11y_) oznacza tworzenie stron tak, aby mogły z nich korzystać także osoby:

- niewidome,
- słabowidzące,
- korzystające z klawiatury,
- z ograniczeniami ruchowymi,
- korzystające z czytników ekranu.

### Podstawowe zasady

- używaj semantycznego HTML,
- dodawaj `label` do pól,
- pisz sensowne `alt`,
- nie używaj `div` jako przycisków,
- dbaj o logiczną strukturę nagłówków,
- nie opieraj znaczenia wyłącznie na kolorze,
- sprawdzaj obsługę klawiaturą.

### Zły przykład

```html
<div onclick="submitForm()">Wyślij</div>
```

### Dobry przykład

```html
<button type="submit">Wyślij</button>
```

---

## 30. Najczęstsze błędy juniorów w HTML

### 1. Używanie samych `div`

Brak semantyki.

### 2. Brak `label` przy inputach

Słaba dostępność.

### 3. Używanie `placeholder` zamiast etykiety

To nie jest to samo.

### 4. Złe użycie `a` i `button`

Link do akcji albo button do nawigacji.

### 5. Brak `alt` w obrazkach

Problem z dostępnością.

### 6. Tabele używane do layoutu

To zła praktyka.

### 7. Zła hierarchia nagłówków

Na przykład `h1`, a potem od razu `h4`.

### 8. Brak `lang` w `<html>`

Błąd dla SEO i czytników ekranu.

### 9. Brak `type` przy `button`

Może prowadzić do niechcianego wysłania formularza.

### 10. Nieczytelne linki typu „czytaj więcej”

Bez kontekstu są słabe dla użytkowników i czytników ekranu.

---

## 31. Przykład małej poprawnej strony HTML

```html
<!DOCTYPE html>
<html lang="pl">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Kurs HTML dla początkujących</title>
  </head>
  <body>
    <header>
      <h1>Kurs HTML</h1>
      <nav aria-label="Główna nawigacja">
        <ul>
          <li><a href="#o-kursie">O kursie</a></li>
          <li><a href="#program">Program</a></li>
          <li><a href="#kontakt">Kontakt</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section id="o-kursie">
        <h2>O kursie</h2>
        <p>
          Ten kurs uczy podstaw HTML: semantyki, formularzy, tabel, obrazów i
          dostępności.
        </p>
      </section>

      <section id="program">
        <h2>Program kursu</h2>
        <article>
          <h3>Moduł 1 — Struktura dokumentu</h3>
          <p>Poznasz podstawowy szkielet strony HTML.</p>
        </article>
        <article>
          <h3>Moduł 2 — Semantyka</h3>
          <p>
            Dowiesz się, kiedy używać `header`, `main`, `section`, `article` i
            innych tagów.
          </p>
        </article>
      </section>

      <section>
        <h2>Przykładowa tabela</h2>
        <table>
          <thead>
            <tr>
              <th>Nazwa modułu</th>
              <th>Poziom</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Podstawy HTML</td>
              <td>Beginner</td>
            </tr>
            <tr>
              <td>Formularze</td>
              <td>Junior</td>
            </tr>
          </tbody>
        </table>
      </section>

      <section>
        <h2>Zapisz się</h2>
        <form id="kontakt" action="/signup" method="post">
          <fieldset>
            <legend>Formularz zapisu</legend>

            <div>
              <label for="name">Imię</label>
              <input id="name" name="name" type="text" required />
            </div>

            <div>
              <label for="email">Email</label>
              <input id="email" name="email" type="email" required />
            </div>

            <div>
              <label for="message">Wiadomość</label>
              <textarea id="message" name="message" rows="5"></textarea>
            </div>

            <div>
              <label>
                <input type="checkbox" name="terms" required />
                Akceptuję regulamin
              </label>
            </div>

            <button type="submit">Wyślij</button>
          </fieldset>
        </form>
      </section>
    </main>

    <aside>
      <h2>Materiały dodatkowe</h2>
      <ul>
        <li><a href="https://developer.mozilla.org/">MDN</a></li>
        <li><a href="https://www.w3.org/">W3C</a></li>
      </ul>
    </aside>

    <footer>
      <p>&copy; 2026 Kurs HTML</p>
    </footer>
  </body>
</html>
```

---

## 32. Checklista — co muszę umieć z HTML

### Struktura dokumentu

- rozumiem `<!DOCTYPE html>`,
- wiem, do czego służą `html`, `head`, `body`,
- umiem ustawić `lang`, `meta charset`, `viewport`, `title`.

### Semantyka

- umiem używać `header`, `main`, `section`, `article`, `nav`, `aside`, `footer`,
- rozumiem, dlaczego semantyczny HTML jest ważny,
- nie buduję wszystkiego na `div`.

### Tekst i treść

- umiem używać `h1-h6`,
- rozumiem hierarchię nagłówków,
- umiem używać `p`, `span`, `strong`, `em`,
- umiem tworzyć listy `ul`, `ol`, `li`.

### Linki i media

- umiem tworzyć linki `a`,
- rozumiem różnicę między `a` i `button`,
- umiem dodać obraz przez `img`,
- umiem napisać poprawny `alt`,
- znam podstawy `picture`, `video`, `audio`.

### Tabele

- umiem zbudować tabelę z użyciem `table`, `thead`, `tbody`, `tr`, `th`, `td`,
- wiem, że tabele służą do danych, nie do layoutu.

### Formularze

- umiem zbudować formularz z `form`,
- umiem używać `input`, `textarea`, `select`, `button`,
- umiem połączyć `label` z inputem,
- znam `fieldset` i `legend`,
- rozumiem atrybuty `name`, `value`, `required`, `disabled`, `placeholder`.

### Walidacja

- znam typy inputów HTML5,
- umiem użyć `required`,
- umiem użyć `minlength`, `maxlength`, `pattern`, `min`, `max`,
- rozumiem podstawy constraint validation.

### Dostępność

- wiem, czym jest semantyczny HTML,
- potrafię robić dostępne etykiety,
- wiem, jak pisać dobre `alt`,
- znam podstawy `aria-*`,
- wiem, że natywny HTML jest pierwszym wyborem.

---

## 33. Najważniejsze zasady do zapamiętania

1. **HTML to struktura i znaczenie treści.**
2. **Semantyczne tagi są lepsze niż same `div`.**
3. **`a` służy do nawigacji, `button` do akcji.**
4. **Każdy input powinien mieć etykietę.**
5. **`placeholder` nie zastępuje `label`.**
6. **Obraz informacyjny powinien mieć sensowny `alt`.**
7. **Formularze trzeba budować logicznie i dostępnie.**
8. **Tabele służą do danych tabelarycznych.**
9. **Nagłówki powinny tworzyć sensowną hierarchię.**
10. **Dobry HTML pomaga w SEO, dostępności i utrzymaniu projektu.**
