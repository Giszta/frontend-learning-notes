# Frontend Learning Roadmap

To moje uporządkowane notatki i plan nauki w kierunku **Junior Frontend Developera**.  
Traktuję ten dokument jako:

- plan kolejności nauki,
- checklistę postępów,
- bazę do budowy projektów,
- punkt odniesienia dla przyszłych rekruterów, żeby mogli zobaczyć, jak świadomie podchodzę do rozwoju.

Nie chcę uczyć się chaotycznie.  
Moim celem jest zbudowanie mocnych podstaw, a potem rozwijanie umiejętności praktycznych w oparciu o projekty, testy i realne problemy frontendowe.

---

## Główny cel

Chcę osiągnąć poziom, na którym potrafię samodzielnie:

- zbudować nowoczesny, responsywny frontend,
- pracować z API,
- pisać czytelny kod w `JavaScript` i `TypeScript`,
- tworzyć aplikacje w `React` i `Next.js`,
- korzystać z `Git` i pracować jak w prawdziwym projekcie,
- pisać podstawowe testy,
- budować portfolio, które pokaże moje umiejętności praktyczne.

---

# Etapy nauki

## Etap 1 — Fundamenty web developmentu

Najpierw chcę bardzo dobrze zrozumieć podstawy, bo bez nich frameworki będą tylko „nakładką”.

### 1. Jak działa web

Muszę zrozumieć:

- czym różni się frontend od backendu,
- jak działa przeglądarka,
- czym są `request` i `response`,
- czym jest `HTTP / HTTPS`,
- czym jest `DOM`,
- czym jest `JSON`,
- czym jest `REST API`,
- czym są `cookies`, `localStorage`, `sessionStorage`,
- jak działa renderowanie strony.

### Cel:

Nie chcę tylko pisać kodu „który działa”, ale rozumieć, co faktycznie dzieje się w aplikacji.

---

## Etap 2 — HTML

HTML chcę opanować porządnie, a nie tylko na poziomie podstawowych tagów.

### Muszę umieć:

- poprawna struktura dokumentu HTML,
- semantyczne tagi:
  - `header`
  - `main`
  - `section`
  - `article`
  - `nav`
  - `footer`
- nagłówki i struktura treści,
- listy,
- linki,
- obrazy,
- tabele,
- formularze,
- przyciski i inputy,
- atrybuty HTML,
- podstawowa walidacja formularzy,
- dostępne formularze i poprawne użycie `label`.

### Chcę rozumieć:

- kiedy używać `button`, a kiedy `a`,
- dlaczego semantyka jest ważna,
- jak pisać HTML przyjazny dla użytkownika.

### Checklista:

- [ ] umiem stworzyć semantyczny layout strony
- [ ] umiem zbudować formularz kontaktowy
- [ ] umiem używać poprawnych tagów HTML
- [ ] rozumiem podstawy dostępności w HTML

---

## Etap 3 — CSS

CSS chcę traktować jako jedną z kluczowych umiejętności.  
Dobry frontend bez dobrego CSS praktycznie nie istnieje.

### Muszę umieć:

- selektory,
- kaskadowość,
- specyficzność,
- box model,
- `margin`, `padding`, `border`,
- jednostki (`px`, `%`, `rem`, `em`, `vh`, `vw`),
- `display`,
- pozycjonowanie,
- `z-index`,
- `overflow`,
- `Flexbox`,
- `Grid`,
- media queries,
- responsive design,
- pseudo-klasy i pseudo-elementy,
- stany `hover`, `focus`, `disabled`,
- przejścia i podstawowe animacje,
- zmienne CSS.

### Dodatkowo chcę umieć:

- odtwarzać layout z projektu,
- robić responsywny navbar,
- budować karty, modale, dropdowny, accordiony,
- tworzyć spójne UI.

### Checklista:

- [ ] umiem zrobić layout w Flexboxie
- [ ] umiem zrobić layout w Gridzie
- [ ] umiem stworzyć responsywną stronę
- [ ] umiem odtworzyć prosty projekt z Figmy
- [ ] umiem stylować komponenty i ich stany

---

## Etap 4 — JavaScript

To najważniejszy fundament logiki na frontendzie.

### Muszę umieć:

- zmienne: `let`, `const`,
- typy danych,
- warunki,
- pętle,
- funkcje,
- scope,
- hoisting,
- closures,
- tablice i obiekty,
- destructuring,
- spread / rest,
- template literals,
- metody tablic:
  - `map`
  - `filter`
  - `find`
  - `some`
  - `every`
  - `reduce`
  - `sort`
- moduły `import / export`,
- eventy,
- manipulacja DOM,
- formularze,
- `fetch`,
- `Promise`,
- `async / await`,
- `try / catch`,
- obsługa błędów.

### Chcę rozumieć:

- różnicę między mutacją i niemutowalnością,
- asynchroniczność,
- jak przekształcać dane z API,
- jak pisać czytelne i praktyczne funkcje.

### Checklista:

- [ ] dobrze rozumiem tablice i obiekty
- [ ] umiem pisać czyste funkcje
- [ ] umiem pobierać dane z API
- [ ] umiem obsłużyć loading i błędy
- [ ] rozumiem async / await w praktyce

---

## Etap 5 — Git i GitHub

Chcę od początku pracować jak developer, a nie tylko „robić projekt lokalnie”.

### Muszę umieć:

- `git init`
- `git clone`
- `git add`
- `git commit`
- `git push`
- `git pull`
- `git status`
- branchowanie
- mergowanie
- podstawy rebase
- rozwiązywanie prostych konfliktów
- pull requesty
- `.gitignore`

### Na GitHubie chcę pilnować:

- porządku w repo,
- czytelnego README,
- sensownych commitów,
- spójnej struktury projektu.

### Checklista:

- [ ] umiem pracować na branchach
- [ ] robię czytelne commity
- [ ] umiem wypchnąć projekt na GitHub
- [ ] dbam o porządek w repo

---

# Etap 6 — TypeScript

Po JavaScript chcę wejść w TypeScript, żeby pisać bezpieczniejszy i bardziej profesjonalny kod.

### Muszę umieć:

- podstawowe typy,
- typowanie funkcji,
- typowanie obiektów,
- typowanie tablic,
- `type` i `interface`,
- union types,
- optional properties,
- typowanie propsów,
- typowanie eventów,
- typowanie danych z API,
- podstawy generics,
- `unknown` vs `any`.

### Cel:

Nie chcę używać `any` wszędzie.  
Chcę rozumieć typy i umieć z nich korzystać praktycznie.

### Checklista:

- [ ] umiem wytypować funkcję
- [ ] umiem wytypować komponent
- [ ] umiem wytypować dane z API
- [ ] rozumiem różnicę między `type` i `interface`

---

# Etap 7 — React

To główny framework, na którym chcę budować swoje projekty frontendowe.

### Muszę umieć:

- czym jest komponent,
- props,
- state,
- event handling,
- conditional rendering,
- renderowanie list,
- controlled inputs,
- lifting state up,
- `useState`,
- `useEffect`,
- podstawy `useMemo`,
- podstawy `useCallback`,
- custom hooks,
- formularze w React,
- fetchowanie danych,
- loading / error / empty state,
- podstawy routingu,
- podział UI na komponenty.

### Chcę rozumieć:

- czym jest re-render,
- po co są `key` w listach,
- kiedy podnosić stan wyżej,
- jak nie tworzyć zbyt dużych komponentów,
- jak organizować strukturę projektu.

### Checklista:

- [ ] umiem tworzyć komponenty wielokrotnego użytku
- [ ] umiem używać `useState` i `useEffect`
- [ ] umiem zbudować formularz w React
- [ ] umiem pobierać dane i wyświetlać stany aplikacji
- [ ] umiem napisać prosty custom hook

---

# Etap 8 — Next.js

Chcę rozwijać się w kierunku nowoczesnego frontendu, dlatego planuję pracować też z Next.js.

### Muszę umieć:

- routing,
- struktura projektu,
- layouty,
- fetchowanie danych,
- podstawy SSR / SSG / ISR,
- różnica między komponentem serwerowym a klienckim,
- strony błędów,
- loading states,
- metadata i podstawy SEO,
- deployment na Vercel.

### Checklista:

- [ ] umiem stworzyć aplikację w Next.js
- [ ] umiem dodać routing
- [ ] umiem pobrać dane i wyświetlić je w UI
- [ ] rozumiem podstawy renderowania po stronie serwera

---

# Etap 9 — API i praca z danymi

Frontend bez pracy z danymi to za mało.  
Chcę dobrze umieć podłączać aplikacje do API.

### Muszę umieć:

- wykonywać requesty HTTP,
- obsługiwać:
  - loading,
  - error,
  - success,
  - empty state,
- wysyłać dane formularzem,
- rozumieć metody:
  - `GET`
  - `POST`
  - `PUT`
  - `PATCH`
  - `DELETE`
- czytać dokumentację API,
- mapować dane do komponentów,
- filtrować, sortować i paginować dane.

### Checklista:

- [ ] umiem pobierać dane z zewnętrznego API
- [ ] umiem wysłać formularz
- [ ] umiem obsłużyć błędy
- [ ] umiem przekształcić dane pod UI
- [ ] umiem zrobić filtrowanie i sortowanie

---

# Etap 10 — Accessibility

Chcę budować aplikacje nie tylko działające, ale też poprawne i dostępne.

### Muszę umieć:

- semantyczny HTML,
- poprawne etykiety formularzy,
- fokus klawiatury,
- logiczną strukturę nagłówków,
- alt text dla obrazów,
- podstawy ARIA,
- dostępne komponenty UI,
- kontrast i czytelność.

### Checklista:

- [ ] dbam o semantykę HTML
- [ ] umiem stworzyć dostępny formularz
- [ ] pilnuję focus state
- [ ] pamiętam o obsłudze klawiatury

---

# Etap 11 — Testy

Nie chcę tylko pisać kodu, ale też weryfikować, że działa poprawnie.

### Muszę umieć:

- czym są testy jednostkowe,
- czym są testy integracyjne,
- czym są testy e2e,
- podstawy `Vitest` lub `Jest`,
- podstawy `React Testing Library`,
- testowanie funkcji,
- testowanie komponentów,
- testowanie formularzy,
- testowanie stanów loading/error.

### Dodatkowo chcę poznać:

- podstawy `Playwright`,
- mockowanie danych,
- testowanie prostych flow użytkownika.

### Checklista:

- [ ] umiem napisać test funkcji
- [ ] umiem przetestować komponent
- [ ] umiem przetestować formularz
- [ ] mam podstawy testów e2e

---

# Etap 12 — Narzędzia i jakość pracy

Chcę korzystać z podstawowych narzędzi tak, jak robi się to w realnych projektach.

### Muszę umieć:

- `npm` / `pnpm`,
- `package.json`,
- skrypty projektu,
- `ESLint`,
- `Prettier`,
- terminal,
- debugowanie w DevTools,
- czytanie błędów,
- podstawy konfiguracji środowiska.

### Checklista:

- [ ] umiem uruchomić i skonfigurować projekt
- [ ] korzystam z lintowania
- [ ] dbam o formatowanie kodu
- [ ] potrafię debugować problemy w przeglądarce

---

# Etap 13 — Performance i SEO basics

Na poziomie juniora chcę znać podstawy, które realnie poprawiają jakość projektu.

### Muszę rozumieć:

- dlaczego zbyt duży bundle szkodzi,
- czym jest lazy loading,
- jak optymalizować obrazy,
- jak ograniczać niepotrzebne renderowanie,
- podstawy SEO:
  - title,
  - meta description,
  - semantyczna struktura,
  - alt texty,
  - przyjazne URL-e.

### Checklista:

- [ ] rozumiem podstawy optymalizacji
- [ ] dbam o poprawną strukturę strony
- [ ] pamiętam o podstawowym SEO

---

# Etap 14 — Projekty do portfolio

Najważniejszym elementem nauki będzie praktyka.  
Chcę budować projekty, które pokażą nie tylko znajomość technologii, ale też sposób myślenia.

## Typy projektów, które chcę zbudować

### 1. Strona firmowa / landing page

Powinna pokazać:

- semantyczny HTML,
- dobry CSS,
- responsywność,
- estetykę,
- formularz kontaktowy.

### 2. Dashboard z API

Powinien pokazać:

- pracę z danymi,
- filtrowanie,
- sortowanie,
- paginację,
- loading / error state,
- komponentowe podejście.

### 3. Aplikacja w React / Next.js

Powinna pokazać:

- routing,
- TypeScript,
- pobieranie danych,
- organizację kodu,
- komponenty wielokrotnego użytku.

### 4. Projekt bardziej „produktowy”

Powinien pokazać:

- formularze,
- walidację,
- bardziej rozbudowany interfejs,
- lepszą strukturę aplikacji,
- testy.

---

# Kolejność nauki

## Poziom 1 — absolutne podstawy

1. Jak działa web
2. HTML
3. CSS
4. JavaScript
5. Git i GitHub

## Poziom 2 — nowoczesny frontend

6. TypeScript
7. React
8. API i async JavaScript
9. Responsywność
10. Accessibility

## Poziom 3 — poziom projektowy

11. Next.js
12. Testy
13. Narzędzia developerskie
14. Performance i SEO basics
15. Deployment

## Poziom 4 — wejście na wyższy poziom

16. większe projekty
17. lepsza architektura komponentów
18. lepsza organizacja kodu
19. bardziej świadome decyzje techniczne

---

# Mój cel końcowy

Chcę dojść do poziomu, na którym mogę uczciwie powiedzieć, że jestem gotowy na pierwszą pracę jako **Junior Frontend Developer**.

To dla mnie oznacza, że potrafię:

- zbudować nowoczesny frontend,
- pracować z API,
- pisać czytelny kod,
- używać TypeScriptu w praktyce,
- budować aplikacje w React i Next.js,
- dbać o responsywność, dostępność i jakość,
- używać GitHuba jak w realnym projekcie,
- pokazać sensowne portfolio.

---

# Status postępów

## Fundamenty

- [ ] Jak działa web
- [ ] HTML
- [ ] CSS
- [ ] JavaScript
- [ ] Git i GitHub

## Nowoczesny frontend

- [ ] TypeScript
- [ ] React
- [ ] API i async JS
- [ ] Responsywność
- [ ] Accessibility

## Poziom projektowy

- [ ] Next.js
- [ ] Testy
- [ ] Narzędzia developerskie
- [ ] Performance basics
- [ ] SEO basics
- [ ] Deployment

## Portfolio

- [ ] Landing page
- [ ] Dashboard z API
- [ ] Aplikacja React / Next.js
- [ ] Bardziej rozbudowany projekt produktowy
