---
title: "Tarot z Codecademy"
date: 2020-05-27 #YYYY-MM-DD(TT18:36:41+02:00)
draft: false
categories:
  - kursy
  # - scripts
  # - o stronie
  - Python
  # - hugo
  # - React
description: ""
tags:
  # - bash
  # - boilerplate
  - codecademy
  # - course
  # - coursera
  # - git
  # - hugo
  # - marketing
  # - organizacja
  # - python
  # - react
  # - ruby
  - script
  # - snippets
  # - vcs
  # - web-scraping
---

## Codecademy

przy wszystkich swoich zaletach ma czasem ćwiczenia, któe są nudne i strasznie powtarzalne, ale ma też takie, które inspirują żeby zostać z nimi chwilę dłużej i trochę rozbudować. W tym przypadku chodziło o wyciągnięcie ze słownika sztywno przypisanych kluczy razem z wartościami i pokazanie ich w trzech linijkach tekście.

### Zwykłe ćwicznie

niby nic, ale fakt że wartościami są karty tarota a teksty układają się w prostą "wróżbę", daje potencjał. Wystarczyło dodać losowanie kart w funkcji (oryginalnie to była lista wybranych wartości) i można się przez chwilę pobawić. Gdybym tylko wiedział co to znaczy, że w przeszłości wychodzi powściągliwość, teraz głupiec, a w przyszłości koło fortuny.

### postaw sobie tarota

```python
import random

tarot = {1:	"The Magician", 2:	"The High Priestess", 3:	"The Empress", 4:	"The Emperor",
5:	"The Hierophant", 6:	"The Lovers", 7:	"The Chariot", 8:	"Strength",
9:	"The Hermit", 10:	"Wheel of Fortune", 11:	"Justice", 12:	"The Hanged Man",
13:	"Death", 14:	"Temperance", 15:	"The Devil", 16:	"The Tower",
17:	"The Star", 18:	"The Moon", 19:	"The Sun", 20:	"Judgement",
21:	"The World", 22: "The Fool"}


def draw():
    hand = ["past", "present", "future"]
    tell = {}
    for time in hand:
        tell[time] = tarot.pop(random.choice(list(tarot.keys())))
    for when, card in tell.items():
        print("Your {0} is the {1} card.".format(when, card))


draw()

```
