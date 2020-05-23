---
title: "Matlab - IDE vs notepad"
date: 2020-05-22
draft: false
categories:
  - kursy
  # - scripts
  # - o stronie
  # - Python
  # - hugo
  # - React
description:
tags:
  # - bash
  # - coursera
  - codecademy
  - course
  # - python
  # - script
  - snippets
  - boilerplate
  # - git
  # - hugo
  # - marketing
  # - organizacja
  # - react
  # - ruby
  # - vcs
  # - web-scraping
---

# Matlab

na forum Coursery w kursie mnóstwo ludzi ma problem z napisaniem pierwszej funkcji w testach - nie otwierają się w edytorze na https://matlab.mathworks.com/ tylko w zwykłym textboksie. Tymczasem...

## edytor funkcji

otwiera się z gotowym szablonem

```matlab
function [outputArg1,outputArg2] = untitled2(inputArg1,inputArg2)
    %UNTITLED2 Summary of this function goes here
    %   Detailed explanation goes here
    outputArg1 = inputArg1;
    outputArg2 = inputArg2;
end
```

## min i max

w ćwiczeniu w środku tygodnia
główny cel to chyba zmuszenie ludzi do zajrzenia do dokumentacji, bo ma bardzo niewiele wspólnego z filmami z tego tygodnia

```matlab
function [mmr,mmm] = minimax(M)
    %UNTITLED Summary of this function goes here
    %   Detailed explanation goes here
    mmr = transpose(abs(max(M,[],2)-min(M,[],2)));
    mmm = abs(max(M,[],'all')-min(M,[],'all'));
end
```

## tworzenie matrycy

ćwiczenie na koniec tygodnia - dziwne bo wydaje się o wiele prostsze od poprzedniego. Tym razem bez dokumentacji, za to na podstawie filmów. Zadanie polega na stworzeniu matrycy o wysokości 3\*n i szerokości m w której 1/3 wysokości będzie wypełniona jedynkami, potem dwójkami i na końcu trójkami.
Główny cel to chyba rozbicie na mniejsze problemy i powtórka z poprzedniego tygodnia (łączenie matryc)

```matlab
function [mat] = trio(n,m)
    %UNTITLED2 Summary of this function goes here
    %   Detailed explanation goes here
    mat = [ones(n,m);2*ones(n,m);3*ones(n,m)];
end
```
