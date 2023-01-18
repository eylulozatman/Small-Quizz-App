# Small-Quizz-App
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quiz App</title>

    <style>
          #background1
        {   margin-left: 300px;
            width: 700px;
            height: 600px;
            background-color: rgb(113, 124, 223);
            border: 20px;
            border-style:dashed;
        }
        #questions{
            font-size: larger;
            margin-top: 20px;
            margin-left: 150px;
            height: 200px;
            width: 420px;
            align-items: center;
            background-color: rgb(184, 219, 127);
        }
        #buttons{
            background-color: rgb(197, 226, 28);
            margin-top: 1px;
            margin-left: 280px;
            width: 100px;
            
        }
        #q1
        {
            margin-top: 10px;
        }
        #score
        {
            font-size: larger;
            background-color: antiquewhite;
        }
      
    

    </style>

</head>
<body>
    <div id="background1">

        <div id="questions">
            <div id="q1">
                <label id="question1"></label>
                <input type="text" id="ans1">
            </div>
    
            <div id="q2">
              <label id="question2"></label>
              <input type="text" id="ans2">
            </div>
    
            <div id="q3">
              <label id="question3"></label>
              <input type="text" id="ans3">
            </div>
            <div id="q4">
            
            <label id="question4"></label>
            <input type="text" id="ans4">
            </div>
           
          
        </div>
        <div id ="buttons">
                <input type="submit" id="confirm" value="show score">
                <input type="submit" id="restart" value="restart">
                <p id="score"></p>
        </div>


    </div>
    
        

    <script>
            const valueArr=[
                {
                "id":0,"question":"What is the name of the tallest mountain on earth?","ans":"everest"
            },
            {
                "id":1,"question":"How many zeros are in ten thousand?","ans":"four","ans2":"4"
            },
            {
                "id":2,"question":"How many colors of the rainbow are there?","ans":"seven","ans2":"7"
            },
            {
                "id":3,"question":"In the Wizard of Oz, what was the lion searching for?","ans":"courage"
            },
        ]

        document.getElementById('question1').innerHTML=valueArr[0].question
        document.getElementById('question2').innerHTML=valueArr[1].question
        document.getElementById('question3').innerHTML=valueArr[2].question
        document.getElementById('question4').innerHTML=valueArr[3].question

        let result = 0;
        let clicknum = 0;

        document.getElementById('confirm').addEventListener("click",function(){
            while(clicknum<1)
            {
                clicknum++;
            if(document.getElementById('ans1').value==valueArr[0].ans)
            {
                result+=1;
            }
            if(document.getElementById('ans2').value==valueArr[1].ans || document.getElementById('ans2').value==valueArr[1].ans2)
            {
                result+=1;
            }
            if(document.getElementById('ans3').value==valueArr[2].ans || document.getElementById('ans3').value==valueArr[2].ans2)
            {
                result+=1;
            }
            if(document.getElementById('ans4').value==valueArr[3].ans)
            {
                result+=1;
            }
            document.getElementById('score').style.visibility = "visible";
            document.getElementById('score').innerHTML="Score:" + result
            }

        })

        document.getElementById('restart').addEventListener("click",function(){

            result = 0;
            clicknum = 0;
           // document.getElementById('score').innerHTML="Score:" + result
            document.getElementById('ans1').value =null
            document.getElementById('ans2').value =null
            document.getElementById('ans3').value =null
            document.getElementById('ans4').value =null
            document.getElementById('score').style.visibility = "hidden";
           

        })
      
    </script>

    
</body>
</html>
