---
title: "JS - shorthand"
date: 2020-05-20
draft: false
categories:
  - scripts
  - JavaScirpt
description: Pierwszy raz z Ruby
tags:
  - codecademy
  - course
  - snippets
---

Takie ćwiczenie na CodeCademy (część ścieżki więc konieczne do zaliczenia całości)

utwórz funkcję, `lifePhase()`, która na podstawie liczby `age`, as zwróci opisowy wiek.

Schemat:
0-3 `'baby'`
4-12 `'child'`
13-19 `'teen'`
20-64 `'adult'`
65-140 `'senior citizen'`
jeśli liczba jest mniejsza od 0 lub większa od 140 - `'This is not a valid age'`

Czasami przy takich rzeczach korzystam z podpowiedzi i zamiast pisać coś prostego wolę to skopiować i wkleić

Tym razem hint to:

Musisz wielokrotnie wykorzystać `if` statements.

nie pamiętam czy na tym etapie kursu pojawiły się już shorthandy ale spróbuję sobie odświeżyć:

```javascript
function lifePhase(age) {
  return 0 > age || age > 140
    ? "This is not a valid age"
    : age < 4
    ? "baby"
    : age < 13
    ? "child"
    : age < 20
    ? "teen"
    : age < 65
    ? "adult"
    : "senior citizen";
}
```

https://www.sitepoint.com/shorthand-javascript-techniques/

chyba jednak shorthandy musiały się pojawić bo gdzieś dalej jest;

```javascript
const truthyOrFalsy = (value) => {
  if (value) {
    return true;
  }
  return false;
};

// As a function declaration:
function truthyOrFalsy(value) {
  if (value) {
    return true;
  } else {
    return false;
  }
}

// Using a ternary:
const truthyOrFalsy = (value) => (value ? true : false);
```

a nawet coś w rodzaju:

```javascript
const motivateMe = (adjective, verb, noun) =>
  `I am so ${adjective} because I ${verb} shorthands! Time to refactor some more long ${noun}!`;
```

a zaraz potem wyjaśnienie że deklaracja funkcji albo łączenie łańcuchów znaków (concatenation) też jest ok. (tylko że tak samo bolesne jak napisanie "łączenie łańcuchów znaków")

```javascript
const howOld = (age, year) => {
  // jaki mamy rok?
  let dateToday = new Date();
  let thisYear = dateToday.getFullYear();

  const yeardiff = year - thisYear;
  const newAge = age + yeardiff;
  if (newAge < 0) {
    return `The year ${year} was ${-newAge} years before you were born`;
  } else if (newAge > age) {
    return `You will be ${newAge} in the year ${year}`;
  } else {
    return `You were ${newAge} in the year ${year}`;
  }
};
```
