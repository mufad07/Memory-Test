<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Memory Test - 20 Soal</title>
    <style>
        body {
            font-family:Arial, Helvetica, sans-serif;
            text-align: center;
            margin-top: 60px;
            size-adjust: 10px;
        }
        #slide-container, #question {
            display: none;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin-top: 20px;
            cursor: pointer;
 
            
        }
    </style>
</head>
<body>
    <h1>Memory Test - 20 Soal</h1>
    <div id="start-container">
        <p>Tekan tombol "Start" untuk memulai tes memori.</p>
        <button onclick="startTest()">Start</button>
    </div>
    <div id="slide-container">
        <h2 id="slide"></h2>
    </div>
    <div id="question">
        <h3 id="question-text"></h3>
        <button onclick="checkAnswer('a')">a. <span id="option-a"></span></button>
        <button onclick="checkAnswer('b')">b. <span id="option-b"></span></button>
        <button onclick="checkAnswer('c')">c. <span id="option-c"></span></button>
        <button onclick="checkAnswer('d')">d. <span id="option-d"></span></button>
        <button onclick="checkAnswer('e')">e. <span id="option-e"></span></button>
    </div>
</div id="bacground">
<img src="C:\Users\Fadly\Downloads\Memory Test\Denso.jpg" alt="">
    <script>
        const questions = [
            {
                slides: [
                    { text: "Soal 1: 45 Kuda", delay: 3000 },
                    { text: "Soal 1: 68 Kerbau", delay: 3000 },
                    { text: "Soal 1: 29 Bebek", delay: 3000 },
                    { text: "Soal 1: 56 Ayam", delay: 3000 },
                    { text: "Soal 1: 14 Burung", delay: 3000 },
                ],
                questionText: "Ada berapa Bebek?",
                options: { a: "45", b: "68", c: "29", d: "56", e: "14" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 2: 34 Sapi", delay: 3000 },
                    { text: "Soal 2: 87 Ikan", delay: 3000 },
                    { text: "Soal 2: 21 Angsa", delay: 3000 },
                    { text: "Soal 2: 62 Unta", delay: 3000 },
                    { text: "Soal 2: 49 Harimau", delay: 3000 },
                ],
                questionText: "Ada berapa Unta?",
                options: { a: "34", b: "87", c: "21", d: "62", e: "49" },
                correctAnswer: "d",
            },
            {
                slides: [
                    { text: "Soal 3: 57 Kambing", delay: 3000 },
                    { text: "Soal 3: 92 Burung", delay: 3000 },
                    { text: "Soal 3: 18 Babi", delay: 3000 },
                    { text: "Soal 3: 73 Bebek", delay: 3000 },
                    { text: "Soal 3: 31 Ayam", delay: 3000 },
                ],
                questionText: "Ada berapa Burung?",
                options: { a: "57", b: "92", c: "18", d: "73", e: "31" },
                correctAnswer: "b",
            },
            {
                slides: [
                    { text: "Soal 4: 41 Rusa", delay: 3000 },
                    { text: "Soal 4: 28 Kelinci", delay: 3000 },
                    { text: "Soal 4: 96 Gajah", delay: 3000 },
                    { text: "Soal 4: 15 Kucing", delay: 3000 },
                    { text: "Soal 4: 64 Anjing", delay: 3000 },
                ],
                questionText: "Ada berapa Gajah?",
                options: { a: "41", b: "28", c: "96", d: "15", e: "64" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 5: 38 Zebra", delay: 3000 },
                    { text: "Soal 5: 53 Monyet", delay: 3000 },
                    { text: "Soal 5: 22 Elang", delay: 3000 },
                    { text: "Soal 5: 80 Tikus", delay: 3000 },
                    { text: "Soal 5: 49 Serigala", delay: 3000 },
                ],
                questionText: "Ada berapa Elang?",
                options: { a: "38", b: "53", c: "22", d: "80", e: "49" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 6: 12 Gajah", delay: 3000 },
                    { text: "Soal 6: 25 Badak", delay: 3000 },
                    { text: "Soal 6: 40 Jerapah", delay: 3000 },
                    { text: "Soal 6: 33 Zebra", delay: 3000 },
                    { text: "Soal 6: 19 Panda", delay: 3000 },
                ],
                questionText: "Ada berapa Jerapah?",
                options: { a: "12", b: "25", c: "40", d: "33", e: "19" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 7: 44 Harimau", delay: 3000 },
                    { text: "Soal 7: 31 Singa", delay: 3000 },
                    { text: "Soal 7: 50 Macan", delay: 3000 },
                    { text: "Soal 7: 26 Serigala", delay: 3000 },
                    { text: "Soal 7: 38 Ular", delay: 3000 },
                ],
                questionText: "Ada berapa Macan?",
                options: { a: "44", b: "31", c: "50", d: "26", e: "38" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 8: 17 Burung", delay: 3000 },
                    { text: "Soal 8: 43 Ikan", delay: 3000 },
                    { text: "Soal 8: 28 Kuda Laut", delay: 3000 },
                    { text: "Soal 8: 22 Paus", delay: 3000 },
                    { text: "Soal 8: 34 Lumba-lumba", delay: 3000 },
                ],
                questionText: "Ada berapa Kuda Laut?",
                options: { a: "17", b: "43", c: "28", d: "22", e: "34" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 9: 36 Kucing", delay: 3000 },
                    { text: "Soal 9: 48 Anjing", delay: 3000 },
                    { text: "Soal 9: 21 Tupai", delay: 3000 },
                    { text: "Soal 9: 30 Kelinci", delay: 3000 },
                    { text: "Soal 9: 27 Musang", delay: 3000 },
                ],
                questionText: "Ada berapa Tupai?",
                options: { a: "36", b: "48", c: "21", d: "30", e: "27" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 10: 55 Kerbau", delay: 3000 },
                    { text: "Soal 10: 68 Kuda", delay: 3000 },
                    { text: "Soal 10: 33 Ayam", delay: 3000 },
                    { text: "Soal 10: 49 Bebek", delay: 3000 },
                    { text: "Soal 10: 22 Angsa", delay: 3000 },
                ],
                questionText: "Ada berapa Ayam?",
                options: { a: "55", b: "68", c: "33", d: "49", e: "22" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 11: 14 Kucing", delay: 3000 },
                    { text: "Soal 11: 39 Anjing", delay: 3000 },
                    { text: "Soal 11: 26 Harimau", delay: 3000 },
                    { text: "Soal 11: 53 Singa", delay: 3000 },
                    { text: "Soal 11: 12 Ular", delay: 3000 },
                ],
                questionText: "Ada berapa Harimau?",
                options: { a: "14", b: "39", c: "26", d: "53", e: "12" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 12: 19 Ayam", delay: 3000 },
                    { text: "Soal 12: 25 Bebek", delay: 3000 },
                    { text: "Soal 12: 41 Angsa", delay: 3000 },
                    { text: "Soal 12: 62 Kerbau", delay: 3000 },
                    { text: "Soal 12: 37 Unta", delay: 3000 },
                ],
                questionText: "Ada berapa Angsa?",
                options: { a: "19", b: "25", c: "41", d: "62", e: "37" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 13: 18 Ikan", delay: 3000 },
                    { text: "Soal 13: 23 Gurita", delay: 3000 },
                    { text: "Soal 13: 30 Paus", delay: 3000 },
                    { text: "Soal 13: 42 Lumba-lumba", delay: 3000 },
                    { text: "Soal 13: 35 Kuda Laut", delay: 3000 },
                ],
                questionText: "Ada berapa Paus?",
                options: { a: "18", b: "23", c: "30", d: "42", e: "35" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 14: 12 Serigala", delay: 3000 },
                    { text: "Soal 14: 27 Rusa", delay: 3000 },
                    { text: "Soal 14: 45 Kelinci", delay: 3000 },
                    { text: "Soal 14: 33 Macan", delay: 3000 },
                    { text: "Soal 14: 50 Harimau", delay: 3000 },
                ],
                questionText: "Ada berapa Kelinci?",
                options: { a: "12", b: "27", c: "45", d: "33", e: "50" },
                correctAnswer: "c",
            },
            {
                slides: [
                    { text: "Soal 15: 24 Burung", delay: 3000 },
                    { text: "Soal 15: 37 Bebek", delay: 3000 },
                    { text: "Soal 15: 18 Ayam", delay: 3000 },
                    { text: "Soal 15: 29 Angsa", delay: 3000 },
                    { text: "Soal 15: 31 Ikan", delay: 3000 },
                ],
                questionText: "Ada berapa Bebek?",
                options: { a: "24", b: "37", c: "18", d: "29", e: "31" },
                correctAnswer: "b",
            },
            {
                slides: [
                    { text: "Soal 16: 11 Angsa", delay: 3000 },
                    { text: "Soal 16: 34 Harimau", delay: 3000 },
                    { text: "Soal 16: 76 Macan", delay: 3000 },
                    { text: "Soal 16: 98 Monyet", delay: 3000 },
                    { text: "Soal 16: 34 Buaya", delay: 3000 },
                ],
                questionText: "Ada berapa Harimau?",
                options: { a: "11", b: "34", c: "76", d: "98", e: "34" },
                correctAnswer: "b",
            },
            {
                slides: [
                    { text: "Soal 17: 12 Musang", delay: 3000 },
                    { text: "Soal 17: 23 Koala", delay: 3000 },
                    { text: "Soal 17: 45 Beruang", delay: 3000 },
                    { text: "Soal 17: 21 Kucing", delay: 3000 },
                    { text: "Soal 17: 34 Badak", delay: 3000 },
                ],
                questionText: "Ada berapa Kucing?",
                options: { a: "12", b: "23", c: "45", d: "21", e: "34" },
                correctAnswer: "d",
            },
            {
                slides: [
                    { text: "Soal 18: 78 Ikan", delay: 3000 },
                    { text: "Soal 18: 67 Biawak", delay: 3000 },
                    { text: "Soal 18: 90 Kadal", delay: 3000 },
                    { text: "Soal 18: 45 Zebra", delay: 3000 },
                    { text: "Soal 18: 34 Kura-Kura", delay: 3000 },
                ],
                questionText: "Ada berapa Kura-Kura?",
                options: { a: "78", b: "67", c: "90", d: "45", e: "34" },
                correctAnswer: "e",
            },
            {
                slides: [
                    { text: "Soal 19: 97 Anjing", delay: 3000 },
                    { text: "Soal 19: 34 Linta", delay: 3000 },
                    { text: "Soal 19: 67 Kambing", delay: 3000 },
                    { text: "Soal 19: 78 Belut", delay: 3000 },
                    { text: "Soal 19: 12 Jerapah", delay: 3000 },
                ],
                questionText: "Ada berapa Jerapah?",
                options: { a: "97", b: "34", c: "67", d: "78", e: "12" },
                correctAnswer: "e",
            },
            {
                slides: [
                    { text: "Soal 20: 54 Macan", delay: 3000 },
                    { text: "Soal 20: 23 Kedelai", delay: 3000 },
                    { text: "Soal 20: 83 Ular", delay: 3000 },
                    { text: "Soal 20: 56 Ayam", delay: 3000 },
                    { text: "Soal 20: 87 Tikus", delay: 3000 },
                ],
                questionText: "Ada berapa Ayam?",
                options: { a: "54", b: "23", c: "83", d: "56", e: "87" },
                correctAnswer: "d",
                
            }
        ];

        let currentQuestion = 0;
        let currentSlide = 0;

        function startTest() {
            document.getElementById("start-container").style.display = "none";
            document.getElementById("slide-container").style.display = "block";
            showSlide();
        }

        function showSlide() {
            const question = questions[currentQuestion];
            if (currentSlide < question.slides.length) {
                document.getElementById("slide").textContent = question.slides[currentSlide].text;
                setTimeout(showSlide, question.slides[currentSlide].delay);
                currentSlide++;
            } else {
                document.getElementById("slide-container").style.display = "none";
                showQuestion();
            }
        }

        function showQuestion() {
            const question = questions[currentQuestion];
            document.getElementById("question").style.display = "block";
            document.getElementById("question-text").textContent = question.questionText;
            document.getElementById("option-a").textContent = question.options.a;
            document.getElementById("option-b").textContent = question.options.b;
            document.getElementById("option-c").textContent = question.options.c;
            document.getElementById("option-d").textContent = question.options.d;
            document.getElementById("option-e").textContent = question.options.e;
        }

        function checkAnswer(answer) {
            const question = questions[currentQuestion];
            if (answer === question.correctAnswer) {
                alert("Jawaban benar!");
            } else {
                alert(`Jawaban salah! Jawaban yang benar adalah ${question.correctAnswer}. ${question.options[question.correctAnswer]}`);
            }

            currentSlide = 0;
            currentQuestion++;
            document.getElementById("question").style.display = "none";

            if (currentQuestion < questions.length) {
                document.getElementById("slide-container").style.display = "block";
                showSlide();
            } else {
                alert("Tes selesai! Terima kasih telah berpartisipasi.");
            }
        }
    </script>
</body>
</html>
