---
title: "Szybki test poziomujący " 
date: 2019-09-25 #YYYY-MM-DD(TT18:36:41+02:00)
draft: false
categories:
   - kursy
   - scripts
  # - o stronie
  # - Python
  # - hugo
  # - React
  # - tłumaczenia
description: ""
tags:
  # - bash
  # - boilerplate
  # - codecademy
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

### Odgrzebałem stary  
(i krótki) post z testem poziomującym (choć nic nie stoi na przeszkodzie żeby dopiąć do niego więcej pytań) który napisałem rok czy 2 wcześniej na podstawie jakiegoś tutoriala i starego testu w formularzu przy okazji odświeżania sobie JS.
 
kod: 
```javascript
const start = document.getElementById("start");
const quiz = document.getElementById("quiz");
const question = document.getElementById("question");
const qImg = document.getElementById("qImg");
const choiceA = document.getElementById("A");
const choiceB = document.getElementById("B");
const choiceC = document.getElementById("C");
const choiceD = document.getElementById("D");
const counter = document.getElementById("counter");
const timeGauge = document.getElementById("timeGauge");
const progress = document.getElementById("progress");
const scoreDiv = document.getElementById("scoreContainer");

// add questions in array
let questionSet = [{
        questionItem: "This is my friend. ____ name is Peter.",
        imgSrc: "img/question.png",
        choiceA: "Her",
        choiceB: "His",
        choiceC: "My",
        choiceD: "nie wiem",
        correct: "B"
    },
    {
        questionItem: "My brother is ____ artist.",
        imgSrc: "img/question.png",
        choiceA: "the",
        choiceB: "an",
        choiceC: "a",
        choiceD: "nie wiem",
        correct: "B"
    } 
  // i tak dalej
];

let answerSet = [];

//set variables
const lastQuestion = questionSet.length - 1;
let currentQuestion = 0;
let count = 0;
const questionTime = 30; // 30s
const gaugeWidth = 150;
const gaugeUnit = gaugeWidth / questionTime;
let TIMER;
let score = 0;

function displayQuestion() {
    let q = questionSet[currentQuestion];
    question.innerHTML = "<p>" + q.questionItem + "</p>";
    qImg.innerHTML = "<img src=" + q.imgSrc + ">";
    choiceA.innerHTML = q.choiceA;
    choiceB.innerHTML = q.choiceB;
    choiceC.innerHTML = q.choiceC;
    choiceD.innerHTML = q.choiceD;
}

start.addEventListener("click", startQuiz);

// start quiz
function startQuiz() {
    start.style.display = "none";
    displayQuestion();
    quiz.style.display = "block";
    renderProgress();
    renderCounter();
    TIMER = setInterval(renderCounter, 1000); // 1000ms = 1s
}

function renderProgress() {
    for (let qIndex = 0; qIndex <= lastQuestion; qIndex++) {
        progress.innerHTML += "<div class='prog' id=" + qIndex + "></div>";
    }
}

// time counter render
function renderCounter() {
    if (count <= questionTime) {
        counter.innerHTML = count;
        timeGauge.style.width = count * gaugeUnit + "px";
        count++;
    } else {
        count = 0;
        answerIsWrong();
        if (currentQuestion < lastQuestion) {
            currentQuestion++;
            displayQuestion();
        } else {
            clearInterval(TIMER);
            scoreRender();
        }
    }
}

//check Answers
function checkAnswer(answer) {
    let currentAnswer = currentQuestion + 1;
    answerSet.push("Q" + currentAnswer + ":" + answer + "in" + count + "sec");
    if (answer == questionSet[currentQuestion].correct) {
        score++;
        answerIsCorrect();
        //currentQuestion++;
    } else {
        answerIsWrong();
        //currentQuestion++;
    }
    count = 0;
    if (currentQuestion < lastQuestion) {
        currentQuestion++;
        displayQuestion();
    } else {
        clearInterval(TIMER);
        scoreRender();
    }
}

function answerIsCorrect() {
    document.getElementById(currentQuestion).style.backgroundColor =
        "mediumseagreen";
}

function answerIsWrong() {
    document.getElementById(currentQuestion).style.backgroundColor = "#d00";
}

function phpSend() {
    var emailAddr = document.getElementById("email").value;
    var link = "auto-send.php?score=" + answerSet + "&email=" + emailAddr;
    window.location.href = link;
}

// score render
function scoreRender() {
    scoreDiv.style.display = "block";
    //score %
    const scorePercent = Math.round((100 * score) / questionSet.length);
 
    //score level
    let cefr =
        scorePercent >= 80 ?
        "B2" :
        scorePercent >= 60 ?
        "B1" :
        scorePercent >= 40 ?
        "A2" :
        "A1";
    //scoreDiv.innerHTML = "<p> Twój wynik wskazuje na poziom " + cefr + "<br>" + scorePercent + "</p>";
    scoreDiv.innerHTML += "<p> Twój wynik to " + scorePercent + "%</p>";
    //scoreDiv.innerHTML += "<p>" + answerSet + "%</p>";
    scoreDiv.innerHTML +=
        '<h4>Jeżeli chcesz przesłać nam swój test i omówić jego wyniki podaj kontakt do siebie<br><input type="text" id="email"></input> <input type="button" value="OK" onclick="phpSend()"></input></h4>';
}
```

wersja [live-demo](https://englisht.eu/heart_englisht/quick-placement/)




