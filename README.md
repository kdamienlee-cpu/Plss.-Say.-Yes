<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine's Day</title>
<style>
  body {
    background-color: #FFDDEE;
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: start;
    height: 100vh;
    margin: 0;
    padding-top: 50px;
  }
  h1 {
    text-align: center;
    color: #C71585;
    font-size: 2rem;
    margin-bottom: 50px;
  }
  button {
    width: 200px;
    height: 60px;
    font-size: 1.5rem;
    border: none;
    border-radius: 15px;
    margin: 15px;
    cursor: pointer;
    color: white;
  }
  #yesBtn {
    background-color: #FF99CC;
  }
  #yesBtn:hover {
    background-color: #FF66AA;
  }
  #noBtn {
    background-color: #FF3366;
  }
  #noBtn:hover {
    background-color: #FF0033;
  }
  .heart {
    position: absolute;
    font-size: 2rem;
    color: #FF1493;
    animation: floatUp 3s linear forwards;
  }
  @keyframes floatUp {
    0% { transform: translateY(0); opacity:1;}
    100% { transform: translateY(-400px); opacity:0;}
  }
</style>
</head>
<body>

<h1 id="question">Hey bubbiez &lt;3<br>Will you be my Valentine?</h1>

<button id="yesBtn">YES &lt;3</button>
<button id="noBtn">NO :(</button>

<script>
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const question = document.getElementById("question");

// YES button functionality
yesBtn.addEventListener("click", () => {
    alert("You just made my Valentine’s Day, my love! <3");
    createHeart();
});

// NO button functionality
noBtn.addEventListener("click", () => {
    const confirmNo = confirm("Are you really sure, bubbiez? :(");
    if(confirmNo) {
        question.innerHTML = "Okay… but are you REALLY REALLY sure, bubbiez? :O";
    } else {
        question.innerHTML = "So that’s a yes then, bubbiez? :)";
    }
});

// Floating heart function
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.style.left = Math.random() * (window.innerWidth - 50) + "px";
    document.body.appendChild(heart);
    setTimeout(() => {
        heart.remove();
    }, 3000);
}
</script>

</body>
</html>
