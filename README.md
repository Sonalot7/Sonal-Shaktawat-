<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>BTS Quiz Game</title>

    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">

    <!-- Link to CSS file -->
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <h1>BTS Quiz Game</h1>

    <div id="quiz-container">
        <h2 id="question">Question will appear here</h2>

        <div class="options">
            <button id="btn1" onclick="checkAnswer(this.innerText)">Option 1</button>
            <button id="btn2" onclick="checkAnswer(this.innerText)">Option 2</button>
            <button id="btn3" onclick="checkAnswer(this.innerText)">Option 3</button>
            <button id="btn4" onclick="checkAnswer(this.innerText)">Option 4</button>
        </div>

        <p id="result"></p>

        <button id="next-btn" onclick="nextQuestion()">Next Question</button>
    </div>

    <!-- Link to JavaScript file -->
    <script src="script.js"></script>

</body>
</html>
// Simple BTS Quiz for Beginners

// Questions and Answers
var questions = [
    {
        question: "In which year did BTS win their first Daesang (Grand Prize) at the Melon Music Awards?",
        option1: "2015",
        option2: "2016",
        option3: "2017",
        option4: "2018",
        answer: "2016"
    },
    {
        question: "Which BTS song was inspired by Hermann Hesse’s novel ‘Demian’?",
        option1: "Spring Day",
        option2: "Blood Sweat & Tears",
        option3: "Fake Love",
        option4: "Black Swan",
        answer: "Blood Sweat & Tears"
    },
    {
        question: "What’s the meaning of 'Bangtan Sonyeondan' in English?",
        option1: "Beyond The Scene",
        option2: "Bulletproof Boy Scouts",
        option3: "Bangtan Boys",
        option4: "Young Forever",
        answer: "Bulletproof Boy Scouts"
    },
    {
        question: "What is the name of BTS’s official webtoon?",
        option1: "We Are Bulletproof",
        option2: "Save Me",
        option3: "Run BTS",
        option4: "HYYH Notes",
        answer: "Save Me"
    }
];

var currentQuestion = 0;

// Show the question and options
function showQuestion() {
    var q = questions[currentQuestion];
    document.getElementById("question").innerText = q.question;
    document.getElementById("btn1").innerText = q.option1;
    document.getElementById("btn2").innerText = q.option2;
    document.getElementById("btn3").innerText = q.option3;
    document.getElementById("btn4").innerText = q.option4;
    document.getElementById("result").innerText = "";
}

// Check Answer
function checkAnswer(selectedOption) {
    var q = questions[currentQuestion];
    if (selectedOption === q.answer) {
        document.getElementById("result").innerText = "Correct! 💜";
    } else {
        document.getElementById("result").innerText = "Wrong! Answer: " + q.answer;
    }
}

// Next Question
function nextQuestion() {
    currentQuestion++;
    if (currentQuestion < questions.length) {
        showQuestion();
    } else {
        document.getElementById("question").innerText = "Quiz Finished!";
        document.getElementById("btn1").style.display = "none";
        document.getElementById("btn2").style.display = "none";
        document.getElementById("btn3").style.display = "none";
        document.getElementById("btn4").style.display = "none";
        document.getElementById("next-btn").style.display = "none";
        document.getElementById("result").innerText = "";
    }
}

// Load first question
showQuestion();
body {
    background-color: #E6E6FA; /* Light lavender */
    font-family: 'Poppins', sans-serif;
    color: #333;
    margin: 0;
    padding: 20px;
}

h1 {
    text-align: center;
    font-weight: 600;
    font-size: 2em;
}

#quiz-container {
    max-width: 600px;
    margin: 30px auto;
    background-color: white;
    padding: 20px;
    border-radius: 12px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

button.option {
    display: block;
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    font-size: 1em;
    border: 1px solid #ccc;
    background-color: #F8F8FF; /* Light background for buttons */
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s;
}

button.option:hover {
    background-color: #D8BFD8; /* Slight lavender shade on hover */
}

#next-btn {
    display: block;
    margin: 20px auto 0;
    padding: 10px 20px;
    font-size: 1em;
    background-color: #DDA0DD;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

#next-btn:hover {
    background-color: #BA55D3;
}


