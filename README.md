<!DOCTYPE html>
<html lang= "en">
<head>
    <meta charset= "UTF-8">
    <meta http-equiv= "X-UA-Compatible" 
          content= "IE=edge">
    <meta name= "viewport" 
          content= "width=device-width, initial-scale=1.0">
    <title> How to Create StopWatch using HTML CSS and JavaScript ? </title>
    <style>
        body {
            margin: 250px;
            font-family: Times New Roman;
        }
        p {
            color: purple;
            padding: 20px;
            font-size: 30px;
            font-weight: bold;
        }
        .digits {
            font-size: 70px;
        }
        .text {
            font-size: 20px;
            color: black;
            font-weight: bold;
        }
        #buttons {
            margin-top: 35px;
        }
        .btn1, .btn2, .btn3, .btn4{
            width: 90px;
            height: 50px;
            margin: 10px 25px 20px 10px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 20px;
            transition: 0.7s;
            color: white;
            font-weight: 550;
            border: 0;
            font-family: Times new Roman;
        }
        .btn1:hover, .btn2:hover, .btn3:hover, .bt4:hover{
            color: black;
        }
        #start {
            background-color: black;
        }
        #pause {
            background-color: black;
        }
        #resume {
            background-color: black;
        }
        #clear {
            background-color: black;
        }
        #start:hover, #pause:hover, #resume:hover, #clear:hover  {
            background-color: white;
        }
    </style>
</head>
<body>
    <div class= "container">
        <div id= "time">
            <span class= "digits" id= "minute">
              00</span>
            <span class= "text"> Min </span>
            <span class= "digits" id= "second">
              00</span>
            <span class= "text"> Sec </span>
            <span class= "digits" id= "count">
              00</span>
        </div>
        <div id= "buttons">
            <button class= "btn1" id= "start">
              Start </button>
            <button class= "btn2" id= "pause">
              Pause </button>
            <button class= "btn3" id= "resume">
              Resume </button>
            <button class= "btn4" id= "clear">
                Clear </button>
        </div>
    </div>
    <script>
        let startButton = document.getElementById('start');
        let pauseButton = document.getElementById('pause');
        let resumeButton = document.getElementById('resume');
        let clearButton = document.getElementById('clear');
          
        let minute = 00;
        let second = 00;
        let count = 00;
          
        startButton.addEventListener('click', function () {
            timer = true;
            stopWatch();
        });
        pauseButton.addEventListener('click', function () {
            timer = false;
        }); 
        resumeButton.addEventListener('click', function () {
            timer = true;
            stopWatch();
        });
        clearButton.addEventListener('click', function () {
            timer = false;       
            minute = 0;
            second = 0;
            count = 0;
            document.getElementById('minute').innerHTML = "00";
            document.getElementById('second').innerHTML = "00";
            document.getElementById('count').innerHTML = "00";
        });
        function stopWatch() {
            if (timer) {
                count++;
                if (count == 100) {
                    second++;
                    count = 0;
                }
                if (second == 60) {
                    minute++;
                    second = 0;
                }
                let minuteString = minute;
                let secondString = second;
                let countString = count;
                if (minute < 10) {
                    minuteString = "0" + minuteString;
                }
                if (second < 10) {
                    secondString = "0" + secondString;
                }
          
                if (count < 10) {
                    countString = "0" + countString;
                }
                document.getElementById('minute').innerHTML = minuteString;
                document.getElementById('second').innerHTML = secondString;
                document.getElementById('count').innerHTML = countString;
                setTimeout(stopWatch, 10);
            }
        }
    </script>
</body>
</html>
