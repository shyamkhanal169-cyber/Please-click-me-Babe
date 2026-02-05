<html lang="en">
<head>
<meta charset="UTF-8">
<title>For My Babe #Owner 💖</title>

<style>
  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(135deg, #ffafbd, #ffc3a0);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Georgia', serif;
  }

  .card {
    background: white;
    padding: 35px;
    border-radius: 22px;
    text-align: center;
    max-width: 420px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.25);
  }

  h1 {
    color: #c9184a;
  }

  button {
    padding: 12px 26px;
    font-size: 16px;
    border: none;
    border-radius: 25px;
    cursor: pointer;
    margin: 10px;
  }

  .yes {
    background: #ff4d6d;
    color: white;
  }

  .no {
    background: #6c757d;
    color: white;
  }

  p {
    font-size: 18px;
    line-height: 1.6;
    color: #5a1a2b;
  }

  /* Heartbeat animation for the big heart */
  @keyframes heartbeat {
    0% { transform: scale(1); }
    25% { transform: scale(1.3); }
    50% { transform: scale(1); }
    75% { transform: scale(1.3); }
    100% { transform: scale(1); }
  }

  #wigglyHeart {
    animation: heartbeat 1s infinite;
    display: inline-block;
  }

  @keyframes float {
    from { transform: translateY(0); opacity: 1; }
    to { transform: translateY(-800px); opacity: 0; }
  }
</style>
</head>

<body>

<audio autoplay loop>
  <source src="https://www.bensound.com/bensound-music/bensound-love.mp3" type="audio/mpeg">
</audio>

<div class="card">
  <h1 id="title">My Babe #Owner 💕</h1>
  <p id="question">Will you be my Valentine? 🌹</p>

  <div id="buttons">
    <button class="yes" onclick="yesClicked()">YES ❤️</button>
    <button class="no" onclick="noClicked()">NO 🙃</button>
  </div>

  <p id="noText"></p>

  <div id="poem" style="display:none;">
    <p>
      तिमी मुस्कुराउँदा उज्यालो हुन्छ मन,<br>
      तिमी बोल्दा शान्ति भेट्छ जीवन।<br>
      हजार शब्दभन्दा प्यारो तिम्रो साथ,<br>
      तिमी बिना अधुरो लाग्छ हर पल, हर रात।<br><br>
      साधारण दिनलाई विशेष बनाउने तिमी,<br>
      मेरो हाँसो, मेरो भरोसा, मेरो खुशी तिमी।<br>
      आज एउटा सानो प्रश्न, मनको गहिराइबाट,<br>
      <strong>Will you be my Valentine? 🌹</strong>
    </p>
  </div>

  <!-- BIG HEART AFTER POEM -->
  <div id="bigHeartContainer" style="display:none; margin-top:20px;">
    <button id="wigglyHeart" style="font-size:80px; background:none; border:none; cursor:pointer;">
      ❤️
    </button>
  </div>

  <!-- LOVE CARD AFTER CLICKING BIG HEART -->
  <div id="loveCard" style="display:none; text-align:center; margin-top:30px;">
    <h1 style="font-size:50px; color:#c9184a;">I LOVE YOU 💖</h1>
    <div style="margin-top:20px;">
      <img src="https://raw.githubusercontent.com/samkhanal-dev/valentine-images/main/chocolate.png" alt="Chocolate" width="100">
      <img src="https://raw.githubusercontent.com/samkhanal-dev/valentine-images/main/teddy.png" alt="Teddy" width="100">
      <img src="https://raw.githubusercontent.com/samkhanal-dev/valentine-images/main/heart.png" alt="Heart" width="100">
    </div>
  </div>

</div>

<script>
  let noCount = 0;

  const messages = [
    "Hmm… are you sure? 😌 Try again 💕",
    "My heart says that was an accident 🥺",
    "Nope… that button doesn’t feel right 😏",
    "Still asking nicely 💖 Try once more",
    "Okay okay… last chance 😌 (just kidding)",
    "At this point, YES is inevitable 😍"
  ];

  function noClicked() {
    noCount++;
    document.getElementById("noText").innerText =
      messages[Math.min(noCount - 1, messages.length - 1)];
  }

  function yesClicked() {
    document.getElementById("buttons").style.display = "none";
    document.getElementById("noText").style.display = "none";
    document.getElementById("question").style.display = "none";
    document.getElementById("title").innerText = "I knew it 😍";
    document.getElementById("poem").style.display = "block";
    hearts();
  }

  // HEARTS + SHOW BIG HEART
  function hearts() {
    for (let i = 0; i < 20; i++) {
      let heart = document.createElement("div");
      heart.innerText = "💖";
      heart.style.position = "fixed";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.bottom = "-20px";
      heart.style.fontSize = "24px";
      heart.style.animation = "float 6s linear";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 6000);
    }
    // show big heart after poem
    document.getElementById("bigHeartContainer").style.display = "block";
  }

  // BIG HEART CLICK EVENT
  document.getElementById("wigglyHeart").addEventListener("click", function() {
    document.getElementById("loveCard").style.display = "block";
    document.getElementById("bigHeartContainer").style.display = "none"; // hide heart
    // extra floating hearts
    for(let i=0;i<30;i++){
      let heart = document.createElement("div");
      heart.innerText = "💖";
      heart.style.position = "fixed";
      heart.style.left = Math.random()*100+"vw";
      heart.style.top = Math.random()*50+"vh";
      heart.style.fontSize = (20+Math.random()*30)+"px";
      document.body.appendChild(heart);
      setTimeout(()=>heart.remove(),4000);
    }
  });
</script>

</body>
</html>


