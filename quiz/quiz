const questions = [
    {
        question: "What does a large language model actually predict?",
        answers: [
            "The next token",
            "The next webpage",
            "The next computer",
            "The next image"
        ],
        correct: 0
    },

    {
        question: "What comes before the colon in a commit message format?",
        answers: [
            "A paragraph",
            "A type such as feat/fix",
            "A password",
            "A URL"
        ],
        correct: 1
    },

    {
        question: "What must a unit test do before a bug is fixed?",
        answers: [
            "Pass",
            "Disappear",
            "Fail",
            "Restart the computer"
        ],
        correct: 2
    },

    {
        question: "Where should styling live?",
        answers: [
            "Inside the JavaScript file",
            "Inside the CSS file",
            "Inside the browser console",
            "Inside the URL"
        ],
        correct: 1
    },

    {
        question: "A nested loop usually means what?",
        answers: [
            "Constant time",
            "Quadratic time",
            "No computation",
            "HTML styling"
        ],
        correct: 1
    }
];

let currentQuestion = 0;
let score = 0;
let answered = false;

const questionNumber = document.getElementById("question-number");
const questionElement = document.getElementById("question");
const answersElement = document.getElementById("answers");
const scoreElement = document.getElementById("score");
const messageElement = document.getElementById("message");

function showQuestion() {

    answered = false;

    const current = questions[currentQuestion];

    questionNumber.textContent =
        `Question ${currentQuestion + 1} of ${questions.length}`;

    questionElement.textContent = current.question;

    answersElement.innerHTML = "";

    current.answers.forEach(function(answer, index) {

        const button = document.createElement("button");

        button.textContent = answer;

        button.className = "answer-button";

        button.addEventListener("click", function() {
            checkAnswer(index);
        });

        answersElement.appendChild(button);
    });
}

function checkAnswer(selectedAnswer) {

    if (answered) return;

    answered = true;

    const current = questions[currentQuestion];

    if (selectedAnswer === current.correct) {

        score++;

        messageElement.textContent = "Correct!";

    } else {

        messageElement.textContent = "Incorrect!";
    }

    scoreElement.textContent = `Score: ${score}`;

    setTimeout(function() {

        currentQuestion++;

        if (currentQuestion < questions.length) {

            messageElement.textContent = "";

            showQuestion();

        } else {

            showFinalScore();
        }

    }, 800);
}

function showFinalScore() {

    questionNumber.textContent = "Quiz Complete!";

    questionElement.textContent =
        `Your final score is ${score} / ${questions.length}`;

    answersElement.innerHTML = "";

    messageElement.textContent =
        "Refresh the page to try the quiz again.";
}

showQuestion();
