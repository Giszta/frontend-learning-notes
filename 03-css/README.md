## 1. Czym jest CSS

**CSS (Cascading Style Sheets)** to język służący do opisywania wyglądu elementów HTML.  
HTML odpowiada za strukturę treści, a CSS za prezentację: układ, kolory, odstępy, rozmiary, animacje i responsywność.

### Prosty przykład

```html
<h1 class="title">Witaj świecie</h1>
```

```css
.title {
  color: steelblue;
  font-size: 2rem;
  text-align: center;
}
```

W tym przykładzie:

- HTML tworzy nagłówek
- CSS nadaje mu kolor, rozmiar i wyrównanie

---

## 2. Jak podłączyć CSS do projektu

### 2.1. Zewnętrzny plik CSS — najczęściej używane rozwiązanie

```html
<head>
  <link rel="stylesheet" href="styles.css" />
</head>
```

To najlepszy i najbardziej praktyczny sposób.

### 2.2. Styl wewnątrz dokumentu

```html
<head>
  <style>
    h1 {
      color: red;
    }
  </style>
</head>
```

Przydaje się rzadko, głównie do prostych testów.

### 2.3. Styl inline

```html
<h1 style="color: red;">Witaj</h1>
```

To rozwiązanie jest mało skalowalne. W praktyce używaj go jak najrzadziej.

---

## 3. Składnia CSS

Każda reguła CSS składa się z:

- **selektora** — wskazuje, co stylujemy
- **deklaracji** — określa, jak to stylujemy

```css
p {
  color: blue;
  font-size: 16px;
}
```

Tutaj:

- `p` to selektor
- `color: blue;` to deklaracja
- `font-size: 16px;` to kolejna deklaracja

### Budowa deklaracji

```css
property: value;
```

Przykład:

```css
margin: 20px;
```

- `margin` — właściwość
- `20px` — wartość

---

## 4. Selektory CSS

Selektory pozwalają wskazać elementy, które chcesz ostylować.

## 4.1. Selektor po tagu

```css
p {
  color: gray;
}
```

Styluje wszystkie paragrafy.

## 4.2. Selektor klasy

```css
.card {
  background: white;
}
```

Styluje wszystkie elementy z klasą `card`.

```html
<div class="card">Treść</div>
```

## 4.3. Selektor ID

```css
#main-title {
  font-size: 3rem;
}
```

```html
<h1 id="main-title">Nagłówek</h1>
```

ID powinno być unikalne na stronie.

## 4.4. Selektor uniwersalny

```css
* {
  box-sizing: border-box;
}
```

Styluje wszystkie elementy.

## 4.5. Selektor potomka

```css
nav a {
  text-decoration: none;
}
```

Styluje wszystkie linki znajdujące się wewnątrz `nav`.

## 4.6. Selektor bezpośredniego dziecka

```css
.card > h2 {
  margin-bottom: 1rem;
}
```

Styluje tylko `h2`, które są bezpośrednimi dziećmi `.card`.

## 4.7. Selektor wielu elementów

```css
h1,
h2,
h3 {
  font-family: sans-serif;
}
```

## 4.8. Łączenie klas

```css
.button.primary {
  background: royalblue;
}
```

Styluje element, który ma **jednocześnie** klasy `button` i `primary`.

## 4.9. Atrybuty

```css
input[type="text"] {
  border: 1px solid #ccc;
}
```

## 4.10. Sąsiadujące elementy

```css
h2 + p {
  margin-top: 0;
}
```

Styluje pierwszy paragraf występujący bezpośrednio po `h2`.

---

## 5. Kaskadowość i specyficzność

To jeden z najważniejszych tematów w CSS.

### 5.1. Kaskadowość

Jeżeli kilka reguł styluje ten sam element i tę samą właściwość, CSS musi zdecydować, która wygra.

Przykład:

```css
p {
  color: blue;
}

p {
  color: red;
}
```

Wygra druga reguła, bo jest niżej.

### 5.2. Specyficzność

Nie zawsze wygrywa reguła niżej. CSS bierze pod uwagę też **specyficzność**.

Ogólna zasada:

- selektor tagu ma niską specyficzność
- klasa ma wyższą
- ID ma jeszcze wyższą
- `!important` nadpisuje prawie wszystko, ale nie należy go nadużywać

Przykład:

```css
p {
  color: blue;
}

.text {
  color: green;
}

#intro {
  color: red;
}
```

```html
<p id="intro" class="text">Hello</p>
```

Wygra kolor czerwony, bo ID ma najwyższą specyficzność.

### 5.3. Kolejność ważności uproszczona

Od słabszego do silniejszego:

1. selektor tagu
2. klasa / pseudo-klasa / atrybut
3. ID
4. inline style
5. `!important`

### 5.4. Dlaczego to ważne w praktyce

Jeśli coś „nie chce się stylować”, zwykle problemem jest:

- zły selektor
- zbyt niska specyficzność
- inna reguła nadpisuje styl
- styl pochodzi z biblioteki i ma mocniejszy selektor

### 5.5. Dobra praktyka

- opieraj stylowanie głównie na klasach
- unikaj nadmiernego zagnieżdżania selektorów
- unikaj `!important`, chyba że naprawdę wiesz, po co go używasz

---

## 6. Dziedziczenie

Niektóre właściwości przechodzą z rodzica na dzieci, a inne nie.

### Dziedziczą się często:

- `color`
- `font-family`
- `font-size`
- `line-height`

### Zwykle się nie dziedziczą:

- `margin`
- `padding`
- `border`
- `width`
- `height`
- `background`

Przykład:

```css
body {
  color: #222;
  font-family: Arial, sans-serif;
}
```

Tekst wewnątrz większości elementów odziedziczy te wartości.

---

## 7. Box model

Każdy element HTML można traktować jak prostokątne pudełko.

Box model składa się z:

- **content** — zawartość
- **padding** — przestrzeń wewnątrz, wokół treści
- **border** — obramowanie
- **margin** — przestrzeń na zewnątrz elementu

### 7.1. Schemat

```text
margin
  border
    padding
      content
```

### 7.2. Przykład

```css
.box {
  width: 300px;
  padding: 20px;
  border: 2px solid black;
  margin: 16px;
}
```

### 7.3. width i height

Domyślnie `width` i `height` dotyczą **content box**, a nie całego pudełka.

Czyli:

- szerokość treści = 300px
- do tego dochodzi padding
- do tego dochodzi border

Efektywnie element może zajmować więcej miejsca niż myślisz.

### 7.4. box-sizing

To bardzo ważna właściwość.

```css
* {
  box-sizing: border-box;
}
```

Przy `border-box`:

- `width` i `height` obejmują content + padding + border

To jest najwygodniejsze i najczęściej stosowane ustawienie w nowoczesnych projektach.

### 7.5. Margin collapse

W pionie marginesy sąsiadujących bloków mogą się „zlewać”.

Przykład:

```css
h2 {
  margin-bottom: 20px;
}

p {
  margin-top: 30px;
}
```

Odstęp nie zawsze wyniesie 50px. Może wynieść 30px, bo marginesy pionowe potrafią się sklejać.

W praktyce dlatego często lepiej kontrolować odstępy przez:

- `padding` w kontenerze
- `gap` w flex/grid
- spójny system spacingu

---

## 8. Jednostki w CSS

## 8.1. px

Piksele — najprostsza i najbardziej przewidywalna jednostka.

```css
width: 320px;
```

Dobra dla:

- borderów
- precyzyjnych wymiarów ikon
- drobnych elementów UI

## 8.2. %

Wartość procentowa względem rodzica.

```css
width: 100%;
```

Przydatne do:

- responsywnych szerokości
- elementów dopasowujących się do kontenera

## 8.3. rem

Jednostka względem rozmiaru fonta elementu `html`.

Najczęściej:

```css
html {
  font-size: 16px;
}
```

Wtedy:

- `1rem = 16px`
- `2rem = 32px`
- `0.5rem = 8px`

To bardzo dobra jednostka do typografii, spacingu i layoutu.

## 8.4. em

Jednostka względem rozmiaru fonta **bieżącego elementu**.

```css
.card {
  font-size: 20px;
}

.card p {
  font-size: 1em; /* 20px */
}
```

`em` bywa przydatne, ale łatwo robi się trudne do przewidzenia przy zagnieżdżeniach.

## 8.5. vh i vw

- `1vh` = 1% wysokości okna
- `1vw` = 1% szerokości okna

Przykład:

```css
.hero {
  min-height: 100vh;
}
```

Często używane w hero section i layoutach pełnoekranowych.

### Uwaga praktyczna

Na mobile `100vh` może czasem zachowywać się inaczej przez pasek przeglądarki. W nowoczesnym CSS pojawiają się też jednostki typu `svh`, `lvh`, `dvh`, ale na poziomie juniora wystarczy rozumieć `vh` i wiedzieć, że na mobile bywają pułapki.

---

## 9. Najczęściej używane właściwości rozmiaru

```css
width
min-width
max-width
height
min-height
max-height
```

### Bardzo praktyczny przykład

```css
.container {
  width: min(100% - 2rem, 1200px);
  margin-inline: auto;
}
```

Jeśli nie znasz jeszcze `min()`, możesz zacząć od prostszej wersji:

```css
.container {
  max-width: 1200px;
  width: 100%;
  margin: 0 auto;
  padding: 0 1rem;
}
```

To klasyczny kontener centrowany na stronie.

---

## 10. display

Właściwość `display` określa, jak element zachowuje się w układzie.

## 10.1. block

Element blokowy:

- zajmuje całą dostępną szerokość
- przechodzi do nowej linii

Przykłady elementów blokowych:

- `div`
- `section`
- `article`
- `p`
- `h1`

```css
display: block;
```

## 10.2. inline

Element liniowy:

- nie zaczyna nowej linii
- zajmuje tylko tyle miejsca, ile potrzebuje treść
- `width` i `height` zwykle nie działają tak, jak w blokach

Przykłady:

- `span`
- `a`
- `strong`

```css
display: inline;
```

## 10.3. inline-block

Łączy cechy `inline` i `block`:

- element stoi w linii
- można ustawiać `width`, `height`, `padding`, `margin`

```css
display: inline-block;
```

## 10.4. none

Ukrywa element i usuwa go z layoutu.

```css
display: none;
```

To co innego niż:

```css
visibility: hidden;
```

`visibility: hidden` ukrywa element, ale miejsce nadal zostaje zajęte.

## 10.5. flex

Aktywuje Flexbox.

```css
display: flex;
```

## 10.6. grid

Aktywuje CSS Grid.

```css
display: grid;
```

---

## 11. Pozycjonowanie

Właściwość `position` kontroluje sposób ustawiania elementu.

## 11.1. static

Domyślna wartość.

```css
position: static;
```

Element zachowuje się normalnie zgodnie z flow dokumentu.

## 11.2. relative

```css
position: relative;
top: 10px;
left: 20px;
```

Element przesuwa się względem swojego normalnego położenia.

Dodatkowo tworzy punkt odniesienia dla elementów `absolute` wewnątrz.

## 11.3. absolute

```css
position: absolute;
top: 0;
right: 0;
```

Element jest wyjmowany z normalnego flow i pozycjonowany względem:

- najbliższego przodka z `position` innym niż `static`
- albo całego viewportu, jeśli takiego przodka nie ma

Przykład badge na karcie:

```css
.card {
  position: relative;
}

.badge {
  position: absolute;
  top: 8px;
  right: 8px;
}
```

## 11.4. fixed

```css
position: fixed;
bottom: 20px;
right: 20px;
```

Element jest przypięty do okna przeglądarki.

Przykłady:

- przycisk „wróć na górę”
- sticky help button
- fixed navbar

## 11.5. sticky

```css
position: sticky;
top: 0;
```

Element zachowuje się normalnie, dopóki nie dojedzie do określonej pozycji, a potem „przykleja się”.

Przykłady:

- sticky navbar
- sticky sidebar
- nagłówki tabel

### Kiedy sticky nie działa?

Najczęstsze powody:

- rodzic ma `overflow: hidden/auto/scroll`
- nie ustawiono `top`
- element nie ma miejsca, by się przykleić

---

## 12. Overflow i scroll

Właściwość `overflow` kontroluje, co się dzieje, gdy treść nie mieści się w elemencie.

```css
overflow: visible;
overflow: hidden;
overflow: auto;
overflow: scroll;
```

### Znaczenie

- `visible` — treść wychodzi poza element
- `hidden` — nadmiar ukryty
- `auto` — scrollbar pojawia się, gdy potrzeba
- `scroll` — scrollbar zawsze widoczny

### Przykład

```css
.modal-body {
  max-height: 70vh;
  overflow: auto;
}
```

### Przydatne warianty

```css
overflow-x: auto;
overflow-y: hidden;
```

To często przydaje się np. dla tabel lub poziomych list.

---

## 13. z-index

`z-index` kontroluje kolejność nakładania się elementów.

```css
.modal {
  position: fixed;
  z-index: 1000;
}
```

### Ważne

`z-index` działa na elementach pozycjonowanych, czyli zwykle takich, które mają:

- `position: relative`
- `position: absolute`
- `position: fixed`
- `position: sticky`

### Typowy przykład

- tło strony
- navbar
- dropdown
- modal
- tooltip

Każdy z tych elementów może wymagać innego poziomu `z-index`.

### Dobra praktyka

Zamiast losowych liczb typu `999999`, warto ustalić prostą skalę:

```css
--z-dropdown: 100;
--z-sticky: 200;
--z-modal: 1000;
--z-tooltip: 1100;
```

---

## 14. Flexbox

Flexbox służy do układania elementów w jednym wymiarze:

- w wierszu
- albo w kolumnie

Świetnie nadaje się do:

- navbarów
- przycisków
- grup elementów
- centrowania
- prostych layoutów

## 14.1. Podstawy

```css
.container {
  display: flex;
}
```

### Oś główna i poprzeczna

Domyślnie:

- **main axis** — pozioma
- **cross axis** — pionowa

Jeśli ustawisz:

```css
flex-direction: column;
```

to:

- oś główna staje się pionowa
- oś poprzeczna pozioma

## 14.2. flex-direction

```css
flex-direction: row;
flex-direction: column;
```

## 14.3. justify-content

Ustawia elementy wzdłuż osi głównej.

```css
justify-content: flex-start;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

Przykład:

```css
.nav {
  display: flex;
  justify-content: space-between;
}
```

## 14.4. align-items

Ustawia elementy wzdłuż osi poprzecznej.

```css
align-items: stretch;
align-items: center;
align-items: flex-start;
align-items: flex-end;
```

Przykład:

```css
.actions {
  display: flex;
  align-items: center;
}
```

## 14.5. gap

Odstęp między elementami.

```css
.list {
  display: flex;
  gap: 1rem;
}
```

To lepsze i czystsze niż sztuczne marginesy na dzieciach.

## 14.6. flex-wrap

Pozwala elementom zawijać się do kolejnego wiersza.

```css
display: flex;
flex-wrap: wrap;
gap: 1rem;
```

Bardzo przydatne przy kartach lub tagach.

## 14.7. flex-grow, flex-shrink, flex-basis

### flex-grow

Mówi, czy element może rosnąć.

```css
.sidebar {
  flex-grow: 0;
}

.content {
  flex-grow: 1;
}
```

### flex-shrink

Mówi, czy element może się kurczyć.

```css
.logo {
  flex-shrink: 0;
}
```

### flex-basis

Początkowy rozmiar elementu przed rozdzielaniem miejsca.

```css
.card {
  flex-basis: 300px;
}
```

### Skrót `flex`

```css
flex: 1;
```

To bardzo częsty zapis.

Przykład:

```css
.item {
  flex: 1;
}
```

Oznacza w uproszczeniu, że elementy dzielą miejsce po równo.

## 14.8. Typowe użycia Flexboxa

### Wyśrodkowanie

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### Navbar

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

### Karty w rzędzie z zawijaniem

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
```

---

## 15. CSS Grid

Grid służy do układania elementów w dwóch wymiarach:

- kolumny
- wiersze

Świetnie nadaje się do:

- layoutów całych sekcji
- galerii
- dashboardów
- siatek kart
- bardziej złożonych układów

## 15.1. Podstawy

```css
.grid {
  display: grid;
}
```

## 15.2. grid-template-columns

Określa liczbę i szerokość kolumn.

```css
grid-template-columns: 1fr 1fr 1fr;
```

To trzy równe kolumny.

### Co to jest `fr`?

`fr` oznacza część dostępnego miejsca.

```css
grid-template-columns: 1fr 2fr;
```

Druga kolumna będzie dwa razy szersza od pierwszej.

## 15.3. grid-template-rows

Ustala wiersze.

```css
grid-template-rows: auto 1fr auto;
```

Przydatne np. w layoutach strony.

## 15.4. gap

Odstępy między elementami.

```css
display: grid;
gap: 1rem;
```

## 15.5. repeat()

Bardzo wygodna funkcja.

```css
grid-template-columns: repeat(3, 1fr);
```

To to samo co:

```css
grid-template-columns: 1fr 1fr 1fr;
```

## 15.6. minmax()

Pozwala ustawić minimalny i maksymalny rozmiar.

```css
grid-template-columns: repeat(3, minmax(200px, 1fr));
```

Bardzo przydatne przy responsywnych kartach.

## 15.7. Auto-fit / auto-fill

Częsty wzorzec do responsywnych siatek:

```css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}
```

To jeden z najpraktyczniejszych zapisów w CSS.

Działa tak:

- jeśli jest miejsce, pojawi się więcej kolumn
- jeśli miejsca jest mniej, elementy przejdą niżej

## 15.8. grid-column i grid-row

Pozwalają rozciągać elementy przez kilka kolumn lub wierszy.

```css
.item-large {
  grid-column: span 2;
}
```

## 15.9. grid-area

Można przypisać element do obszaru.

```css
.layout {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}
```

```css
.header {
  grid-area: header;
}

.sidebar {
  grid-area: sidebar;
}

.main {
  grid-area: main;
}

.footer {
  grid-area: footer;
}
```

To bardzo czytelne przy większych layoutach.

---

## 16. Flexbox vs Grid

### Kiedy Flexbox?

Gdy układasz elementy głównie w **jednym kierunku**:

- navbar
- lista przycisków
- grupa inputów
- prosty układ sekcji

### Kiedy Grid?

Gdy układ jest bardziej **dwuwymiarowy**:

- sekcja kart
- dashboard
- galeria
- cała struktura strony

### Dobra praktyka

W realnych projektach używa się **obu**:

- Grid do większego układu
- Flexbox do wyrównywania wewnątrz poszczególnych bloków

---

## 17. Responsywność

Responsywność oznacza, że strona działa dobrze na różnych rozmiarach ekranu:

- mobile
- tablet
- desktop

## 17.1. Mobile first

To bardzo ważne podejście.

Najpierw piszesz style dla najmniejszych ekranów, a potem rozbudowujesz je dla większych.

Przykład:

```css
.card-list {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 768px) {
  .card-list {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1024px) {
  .card-list {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
```

## 17.2. Media queries

Pozwalają zastosować style tylko przy określonych warunkach.

```css
@media (min-width: 768px) {
  .container {
    padding: 2rem;
  }
}
```

Najczęstsze breakpointy przykładowe:

- `640px`
- `768px`
- `1024px`
- `1280px`

Nie ucz się breakpointów na pamięć jako jedynego rozwiązania. Ważniejsze jest rozumienie, **kiedy layout się psuje**.

## 17.3. Praktyczne zasady responsywności

- używaj `max-width`, a nie sztywnej szerokości wszędzie
- pozwalaj elementom zawijać się
- korzystaj z `flex-wrap` i Grid
- testuj na wąskich ekranach
- unikaj ogromnych stałych wartości
- pilnuj długości tekstów
- używaj `width: 100%` dla obrazów i inputów, gdy trzeba

## 17.4. Responsywny obraz

```css
img {
  max-width: 100%;
  height: auto;
}
```

To absolutna podstawa.

---

## 18. Kolory i tła

## 18.1. color

Kolor tekstu:

```css
color: #222;
```

## 18.2. background

Tło elementu:

```css
background: #f5f5f5;
```

Można też użyć:

```css
background-color
background-image
background-position
background-size
background-repeat
```

### Przykład tła z obrazem

```css
.hero {
  background-image: url("./hero.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

## 18.3. Formaty kolorów

### Hex

```css
color: #ff0000;
color: #222222;
```

### rgb

```css
color: rgb(255, 0, 0);
```

### rgba

```css
background: rgba(0, 0, 0, 0.5);
```

Świetne do overlayów.

### hsl

```css
color: hsl(220, 60%, 50%);
```

Warto znać, bo bywa wygodne przy projektowaniu systemu kolorów.

---

## 19. Typografia w CSS

Najważniejsze właściwości:

```css
font-family
font-size
font-weight
line-height
letter-spacing
text-align
text-transform
text-decoration
```

### Przykład

```css
body {
  font-family: Inter, Arial, sans-serif;
  font-size: 16px;
  line-height: 1.5;
  color: #1f2937;
}
```

### Dobre praktyki

- dla tekstu bazowego często `16px` lub `1rem`
- `line-height` zwykle od `1.4` do `1.7`
- nie przesadzaj z liczbą fontów
- pilnuj kontrastu tekstu do tła

---

## 20. Border, border-radius, shadows

## 20.1. border

```css
border: 1px solid #ddd;
```

Składa się z:

- szerokości
- stylu
- koloru

## 20.2. border-radius

Zaokrąglenie rogów:

```css
border-radius: 12px;
```

Często używane przy:

- kartach
- przyciskach
- modalach
- inputach

## 20.3. box-shadow

Cień elementu:

```css
box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
```

Dobrze używać z umiarem.

### Typowa karta

```css
.card {
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
  padding: 1.5rem;
}
```

---

## 21. Pseudo-klasy i pseudo-elementy

## 21.1. Pseudo-klasy

Opisują **stan** elementu.

### `:hover`

```css
.button:hover {
  background: #1d4ed8;
}
```

Działa, gdy użytkownik najedzie kursorem.

### `:focus`

```css
input:focus {
  outline: 2px solid royalblue;
}
```

Działa po skupieniu elementu, np. tabulatorem lub kliknięciem.

### `:focus-visible`

Lepsze dla dostępności niż ślepe usuwanie outline.

```css
button:focus-visible {
  outline: 3px solid #2563eb;
  outline-offset: 2px;
}
```

Bardzo przydatne dla użytkowników klawiatury.

### `:disabled`

```css
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

### Inne przydatne

- `:first-child`
- `:last-child`
- `:nth-child()`
- `:not()`

## 21.2. Pseudo-elementy

Pozwalają tworzyć „wirtualne” elementy.

### `::before`

```css
.link::before {
  content: "→ ";
}
```

### `::after`

```css
.badge::after {
  content: "";
  display: block;
  width: 100%;
  height: 2px;
  background: currentColor;
}
```

### Bardzo ważne

Pseudo-elementy wymagają zwykle `content`, inaczej się nie pojawią.

---

## 22. Transition i podstawy animacji

## 22.1. transition

Umożliwia płynne przejścia między stanami.

```css
.button {
  transition:
    background-color 0.2s ease,
    transform 0.2s ease;
}

.button:hover {
  transform: translateY(-2px);
}
```

### Co warto animować

Najbezpieczniej i najwydajniej:

- `opacity`
- `transform`

### Czego nie nadużywać

- dużych animacji layoutu
- zbyt wielu cieni i filtrów
- animowania wszystkiego naraz

## 22.2. Animacje `@keyframes`

```css
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.alert {
  animation: fade-in 0.3s ease;
}
```

### Inny przykład

```css
@keyframes slide-up {
  from {
    transform: translateY(12px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}
```

---

## 23. Zmienne CSS

Zmienne CSS są bardzo przydatne do budowy spójnego design systemu.

```css
:root {
  --color-primary: #2563eb;
  --color-text: #111827;
  --color-bg: #ffffff;
  --radius-md: 12px;
  --shadow-sm: 0 4px 10px rgba(0, 0, 0, 0.08);
  --space-md: 1rem;
}
```

Użycie:

```css
.button {
  background: var(--color-primary);
  border-radius: var(--radius-md);
  padding: var(--space-md);
}
```

### Zalety

- łatwe zarządzanie kolorami i spacingiem
- spójność projektu
- wygodne dark mode
- mniej powtórzeń

---

## 24. Stany UI, które musisz umieć stylować

W prawdziwej aplikacji nie stylujesz tylko „ładnych” komponentów. Musisz ogarniać stany.

## 24.1. Hover

```css
.card:hover {
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.1);
}
```

## 24.2. Focus

```css
input:focus-visible {
  outline: 2px solid #2563eb;
  outline-offset: 2px;
}
```

## 24.3. Error

```css
.input-error {
  border-color: #dc2626;
}

.error-text {
  color: #dc2626;
  font-size: 0.875rem;
}
```

## 24.4. Success

```css
.input-success {
  border-color: #16a34a;
}
```

## 24.5. Loading

```css
.button-loading {
  opacity: 0.7;
  pointer-events: none;
}
```

## 24.6. Disabled

```css
button:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}
```

---

## 25. Najważniejsze komponenty UI, które musisz umieć zbudować

To jest bardzo praktyczna część CSS.

---

## 25.1. Hero section

Hero to główna sekcja na górze strony.

### Czego zwykle potrzebujesz

- kontenera
- układu tekst + obraz
- nagłówka
- opisu
- CTA buttonów
- responsywności

### Przykład

```html
<section class="hero">
  <div class="hero__content">
    <p class="hero__eyebrow">Nowość</p>
    <h1>Buduj nowoczesne interfejsy</h1>
    <p class="hero__text">Naucz się HTML, CSS i JavaScript krok po kroku.</p>
    <div class="hero__actions">
      <a href="#" class="button button--primary">Zacznij</a>
      <a href="#" class="button button--secondary">Dowiedz się więcej</a>
    </div>
  </div>

  <div class="hero__image">
    <img src="./hero.png" alt="Podgląd aplikacji" />
  </div>
</section>
```

```css
.hero {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  align-items: center;
  padding: 4rem 1rem;
}

.hero__content h1 {
  font-size: 2.5rem;
  line-height: 1.1;
  margin-bottom: 1rem;
}

.hero__text {
  color: #4b5563;
  margin-bottom: 1.5rem;
}

.hero__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.hero__image img {
  width: 100%;
  height: auto;
  display: block;
}

@media (min-width: 900px) {
  .hero {
    grid-template-columns: 1.1fr 0.9fr;
  }
}
```

---

## 25.2. Navbar desktop i mobile

### Desktop

```css
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}

.navbar__links {
  display: flex;
  gap: 1rem;
}
```

### Mobile

Na mobile zwykle:

- linki chowasz
- pokazujesz hamburger
- otwierasz menu pionowe

```css
.navbar__links {
  display: none;
}

.navbar__toggle {
  display: inline-flex;
}

@media (min-width: 768px) {
  .navbar__links {
    display: flex;
  }

  .navbar__toggle {
    display: none;
  }
}
```

### Co trzeba ogarnąć praktycznie

- spacing
- aktywny link
- hover/focus
- stan otwarcia menu
- warstwę `z-index`
- pozycjonowanie dropdownu albo panelu mobile

---

## 25.3. Cards

Karty są wszędzie: produkty, artykuły, profile, dashboardy.

```html
<article class="card">
  <img src="./img.jpg" alt="Miniatura artykułu" class="card__image" />
  <div class="card__body">
    <h2 class="card__title">Tytuł karty</h2>
    <p class="card__text">Krótki opis zawartości.</p>
    <a href="#" class="card__link">Czytaj więcej</a>
  </div>
</article>
```

```css
.card {
  overflow: hidden;
  border-radius: 16px;
  background: white;
  border: 1px solid #e5e7eb;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.06);
}

.card__image {
  width: 100%;
  display: block;
  aspect-ratio: 16 / 9;
  object-fit: cover;
}

.card__body {
  padding: 1rem;
}

.card__title {
  margin-bottom: 0.5rem;
}

.card__text {
  color: #4b5563;
  margin-bottom: 1rem;
}
```

---

## 25.4. Modal

Modal wymaga kilku rzeczy naraz:

- overlay
- centrowania
- `position: fixed`
- `z-index`
- scrolla przy dużej treści
- focus state dla przycisków

```css
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  display: grid;
  place-items: center;
  padding: 1rem;
  z-index: 1000;
}

.modal {
  width: min(100%, 600px);
  max-height: 80vh;
  overflow: auto;
  background: white;
  border-radius: 16px;
  padding: 1.5rem;
}
```

---

## 25.5. Dropdown

Najczęściej używa:

- `position: relative` na wrapperze
- `position: absolute` na panelu

```css
.dropdown {
  position: relative;
}

.dropdown__menu {
  position: absolute;
  top: calc(100% + 0.5rem);
  right: 0;
  min-width: 200px;
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.08);
  padding: 0.5rem;
}
```

---

## 25.6. Tabs

Zakładki wymagają:

- aktywnego stanu
- hover/focus
- układu przycisków

```css
.tabs__list {
  display: flex;
  gap: 0.5rem;
  border-bottom: 1px solid #e5e7eb;
}

.tabs__button {
  padding: 0.75rem 1rem;
  border: none;
  background: transparent;
  border-bottom: 2px solid transparent;
}

.tabs__button--active {
  border-bottom-color: #2563eb;
  color: #2563eb;
}
```

---

## 25.7. Accordion

Potrzebujesz:

- nagłówka klikalanego
- treści rozwijanej
- stanów active/open
- często przejścia wysokości lub opacity

---

## 25.8. Responsywna siatka kart

To bardzo częste zadanie.

```css
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1rem;
}
```

To jeden z najważniejszych wzorców do zapamiętania.

---

## 26. Formularze i elementy interaktywne

Junior musi umieć estetycznie ostylować:

- `input`
- `textarea`
- `select`
- `checkbox`
- `radio`
- `button`
- walidację

### Przykład inputa

```css
.input {
  width: 100%;
  padding: 0.875rem 1rem;
  border: 1px solid #d1d5db;
  border-radius: 12px;
  background: white;
}

.input:focus-visible {
  outline: 2px solid #2563eb;
  outline-offset: 2px;
}

.input::placeholder {
  color: #9ca3af;
}
```

---

## 27. Dobre praktyki organizacji stylów

Z czasem problemem nie jest samo pisanie CSS, ale utrzymanie porządku.

## 27.1. Grupuj style logicznie

Przykładowy układ:

```text
base/
components/
layout/
pages/
utilities/
```

### Przykład

- `base` — reset, zmienne, typografia
- `layout` — kontenery, gridy, sekcje
- `components` — button, card, modal
- `utilities` — klasy pomocnicze typu `.sr-only`, `.hidden`

## 27.2. Zachowuj spójne nazewnictwo

Nie mieszaj:

- `mainCard`
- `card-main`
- `cardMain`
- `super-box-v2`

Lepiej trzymaj jedną konwencję.

## 27.3. Unikaj zbyt głębokich selektorów

Źle:

```css
.page .section .card .content .title span {
  color: red;
}
```

Lepiej:

```css
.card__title {
  color: red;
}
```

## 27.4. Twórz system spacingu

Przykład:

- 4px
- 8px
- 12px
- 16px
- 24px
- 32px
- 48px

Dzięki temu UI wygląda spójniej.

---

## 28. BEM — podstawy metodologii nazewnictwa

BEM pomaga pisać czytelne i przewidywalne klasy.

Skrót:

- **B**lock
- **E**lement
- **M**odifier

### Przykład

```html
<article class="card card--featured">
  <h2 class="card__title">Tytuł</h2>
  <p class="card__text">Opis</p>
</article>
```

### Znaczenie

- `card` — blok
- `card__title` — element bloku
- `card--featured` — modyfikator

### Zalety

- łatwiej utrzymać porządek
- mniej konfliktów nazw
- lepsza czytelność w większych projektach

Nie musisz być ortodoksyjny, ale warto rozumieć ten sposób myślenia.

---

## 29. Tailwind CSS — co warto wiedzieć

Tailwind to framework utility-first.

Zamiast pisać osobne klasy CSS, stylujesz elementy klasami narzędziowymi:

```html
<button class="px-4 py-2 rounded-lg bg-blue-600 text-white hover:bg-blue-700">
  Zapisz
</button>
```

### Zalety

- szybkie budowanie UI
- duża spójność
- łatwe responsywne klasy
- wygodny w React / Next.js

### Wady

- HTML może stać się bardzo długi
- bez zrozumienia CSS łatwo kopiować bez myślenia
- nadal trzeba znać Flexbox, Grid, spacing, states, layout

### Ważna prawda

**Tailwind nie zastępuje znajomości CSS.**  
Jeśli nie rozumiesz CSS, Tailwind tylko zamaskuje braki na chwilę.

---

## 30. Reset i normalizacja stylów

Przeglądarki mają własne domyślne style. Dlatego zwykle stosuje się reset lub uproszczony base style.

### Prosty nowoczesny start

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

* {
  margin: 0;
}

body {
  min-height: 100vh;
  line-height: 1.5;
}

img,
picture,
video,
canvas,
svg {
  display: block;
  max-width: 100%;
}

input,
button,
textarea,
select {
  font: inherit;
}
```

To bardzo dobry fundament.

---

## 31. Dostępność a CSS

Junior frontend powinien rozumieć podstawy dostępności także w CSS.

## 31.1. Nie usuwaj focusa bez zastąpienia

Źle:

```css
button:focus {
  outline: none;
}
```

Lepiej:

```css
button:focus-visible {
  outline: 3px solid #2563eb;
  outline-offset: 2px;
}
```

## 31.2. Kontrast

Tekst musi mieć czytelny kontrast względem tła.

Źle:

- jasnoszary tekst na białym tle
- słabe kolory błędów i komunikatów

## 31.3. Hover to za mało

Na mobile nie ma hovera, a użytkownicy klawiatury potrzebują focus state.

Dlatego interaktywny element powinien mieć przynajmniej:

- normal state
- hover
- focus-visible
- disabled, jeśli dotyczy

## 31.4. Rozmiar klikalnych elementów

Małe przyciski i linki są trudniejsze w użyciu. Dbaj o wygodne kliknięcie.

---

## 32. Najczęstsze błędy początkujących w CSS

## 32.1. Za dużo `position: absolute`

Jeśli wszystko ustawiasz absolutnie, layout staje się kruchy i trudny w utrzymaniu.

Najpierw próbuj:

- Flexbox
- Grid
- normal flow dokumentu

## 32.2. Brak `box-sizing: border-box`

Powoduje trudniejsze liczenie rozmiarów.

## 32.3. Sztywne szerokości wszędzie

```css
width: 1200px;
```

Na mobile to się rozjedzie.

## 32.4. Brak responsywności tekstu i obrazów

Obrazy bez `max-width: 100%` często psują layout.

## 32.5. Używanie marginesów zamiast `gap` tam, gdzie lepszy byłby Flex/Grid

`gap` daje czystszy i bardziej przewidywalny kod.

## 32.6. Za duża specyficzność

Potem trzeba walczyć z własnym CSS-em.

## 32.7. Nadużywanie `!important`

To zwykle maskuje problem, zamiast go rozwiązywać.

## 32.8. Stylowanie bez systemu spacingu i kolorów

Efekt: interfejs wygląda niespójnie.

---

## 33. „Dlaczego to się rozjechało?” — praktyczne debugowanie CSS

To jedna z najważniejszych umiejętności juniora.

Kiedy layout się psuje, sprawdzaj po kolei:

### 33.1. Czy element jest `block`, `inline`, `flex`, czy `grid`?

Może problemem jest sam `display`.

### 33.2. Czy szerokość nie jest za duża?

Szukaj:

- `width`
- `min-width`
- długiego tekstu bez łamania
- obrazów bez ograniczenia szerokości

### 33.3. Czy Flexbox nie ściska elementów?

Sprawdź:

- `flex-shrink`
- `flex-basis`
- `flex-wrap`

### 33.4. Czy Grid ma poprawne kolumny?

Sprawdź:

- `grid-template-columns`
- `minmax`
- `span`
- rozmiary elementów w środku

### 33.5. Czy rodzic ma odpowiedni kontekst pozycjonowania?

Dla `absolute` zwykle rodzic powinien mieć `position: relative`.

### 33.6. Czy `overflow: hidden` nie ucina elementu?

Często zabija dropdowny, sticky, cienie i pseudo-elementy.

### 33.7. Czy nie ma konfliktu specyficzności?

DevTools bardzo pomagają zobaczyć, która reguła wygrywa.

### 33.8. Czy problem nie wynika z contentu?

Często to nie CSS jest „zepsuty”, tylko treść:

- za długi tekst
- brak łamania słów
- za duży obraz
- dziwny spacing z CMS-a lub API

### 33.9. Umiejętność pracy z DevTools

Musisz umieć:

- zaznaczyć element
- zobaczyć aktywne style
- zobaczyć nadpisane style
- sprawdzić box model
- przełączać stany `:hover` i `:focus`
- testować layout na różnych viewportach

To jest realna umiejętność frontendowa, nie dodatek.

---

## 34. Praktyczne wzorce, które warto znać

## 34.1. Centrowany kontener

```css
.container {
  width: min(100% - 2rem, 1200px);
  margin-inline: auto;
}
```

## 34.2. Sekcja z odstępami

```css
.section {
  padding: 4rem 0;
}
```

## 34.3. Responsywna siatka kart

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1rem;
}
```

## 34.4. Wyśrodkowanie w pionie i poziomie

```css
.center {
  display: grid;
  place-items: center;
}
```

lub

```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

## 34.5. Overlay na obrazku

```css
.card {
  position: relative;
}

.card::after {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0, 0, 0, 0.5), transparent);
}
```

## 34.6. Sticky header

```css
.header {
  position: sticky;
  top: 0;
  z-index: 200;
  background: white;
}
```

---

## 35. Przykładowy mini system design tokens w CSS

```css
:root {
  --color-bg: #ffffff;
  --color-surface: #f9fafb;
  --color-text: #111827;
  --color-text-muted: #6b7280;
  --color-primary: #2563eb;
  --color-primary-hover: #1d4ed8;
  --color-border: #e5e7eb;
  --color-danger: #dc2626;
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --space-xs: 0.25rem;
  --space-sm: 0.5rem;
  --space-md: 1rem;
  --space-lg: 1.5rem;
  --space-xl: 2rem;
  --shadow-sm: 0 4px 12px rgba(0, 0, 0, 0.06);
  --shadow-md: 0 10px 30px rgba(0, 0, 0, 0.08);
}
```

To pomaga utrzymać porządek.

---

## 36. Minimalny zestaw właściwości CSS, które naprawdę musisz znać

To nie jest wszystko, ale to fundament używany ciągle:

```css
display
position
top
right
bottom
left
z-index
width
min-width
max-width
height
min-height
max-height
margin
padding
border
border-radius
box-sizing
overflow
color
background
font-size
font-weight
line-height
text-align
text-decoration
box-shadow
opacity
cursor
transition
transform
flex-direction
justify-content
align-items
flex-wrap
gap
grid-template-columns
grid-template-rows
grid-column
grid-row
```

---

## 37. Podsumowanie

CSS to nie dodatek do HTML i JavaScript. To pełnoprawna, bardzo ważna część frontendu.

Junior frontend developer musi umieć:

- rozumieć selektory, kaskadę i specyficzność
- kontrolować box model i spacing
- budować layout Flexboxem i Gridem
- robić responsywne interfejsy
- stylować komponenty i ich stany
- debugować problemy z układem
- utrzymywać porządek w stylach

Najważniejsze nie jest zapamiętanie każdego pojedynczego property, tylko zrozumienie:

- jak działa układ
- jak działają zależności między elementami
- jak tworzyć przewidywalny i skalowalny CSS

---

## 38. Krótkie przykłady do zapamiętania

### Kontener

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
```

### Flex row

```css
.row {
  display: flex;
  align-items: center;
  gap: 1rem;
}
```

### Grid cards

```css
.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1rem;
}
```

### Button

```css
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 0.75rem 1rem;
  border: none;
  border-radius: 12px;
  background: #2563eb;
  color: white;
  transition:
    background-color 0.2s ease,
    transform 0.2s ease;
}

.button:hover {
  background: #1d4ed8;
}

.button:focus-visible {
  outline: 3px solid #93c5fd;
  outline-offset: 2px;
}
```

### Input

```css
.input {
  width: 100%;
  padding: 0.875rem 1rem;
  border: 1px solid #d1d5db;
  border-radius: 12px;
}

.input:focus-visible {
  outline: 2px solid #2563eb;
  outline-offset: 2px;
}
```

### Sticky header

```css
.header {
  position: sticky;
  top: 0;
  z-index: 100;
  background: white;
}
```

---

## 39. Ostateczna checklista CSS dla juniora

### Muszę rozumieć

- czym jest CSS
- jak działają selektory
- czym jest kaskadowość
- czym jest specyficzność
- czym jest box model
- jak działają jednostki
- jak działa `display`
- jak działa `position`
- jak działa `overflow`
- jak działa `z-index`
- jak działa Flexbox
- jak działa Grid
- jak działa responsywność
- jak działają pseudo-klasy i pseudo-elementy
- jak działają transitions i podstawowe animacje
- po co są zmienne CSS
- po co są metodologie typu BEM
- czym jest Tailwind CSS

### Muszę umieć praktycznie

- zrobić layout hero + sekcje + footer
- zbudować navbar desktop i mobile
- zbudować cards, modal, dropdown, tabs, accordion
- zrobić responsywną siatkę
- ostylować formularz
- ogarnąć hover, focus, disabled, loading, error
- użyć Flexboxa i Grida świadomie
- naprawić rozjechany layout
- używać DevTools do debugowania

### Muszę wyrobić nawyki

- pisać mobile first
- używać `box-sizing: border-box`
- nie nadużywać `!important`
- nie opierać wszystkiego na `absolute`
- dbać o focus states
- zachowywać spójny spacing
- zachowywać spójne nazewnictwo
- dbać o czytelność i utrzymywalność CSS
