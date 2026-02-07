<!DOCTYPE html>
<html>
<head>
  <title>For You ❤️</title>
  <style>
    body {
      background: linear-gradient(to right, #ffdde1, #ee9ca7);
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 40px;
      overflow: hidden;
    }
    .box {
      background: white;
      padding: 30px;
      border-radius: 15px;
      max-width: 450px;
      margin: auto;
      box-shadow: 0 10px 25px rgba(0,0,0,0.25);
      position: relative;
      z-index: 2;
    }
    input {
      padding: 10px;
      width: 80%;
      border-radius: 8px;
      border: 1px solid #ccc;
      margin-top: 10px;
      text-align: center;
    }
    button {
      margin-top: 15px;
      padding: 10px 25px;
      border: none;
      background: #e60073;
      color: white;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
    }
    #message {
      display: none;
      margin-top: 20px;
      color: #4a0033;
      line-height: 1.6;
      white-space: pre-line;
    }

    /* ❤️ floating hearts */
    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 18px;
      animation: float 6s linear infinite;
      opacity: 0.6;
      z-index: 1;
    }
    @keyframes float {
      0% { transform: translateY(0); opacity: 0.6; }
      100% { transform: translateY(-110vh); opacity: 0; }
    }
  </style>
</head>
<body>

<div class="box">
  <h2>🔒 Locked Message</h2>
  <p>Password sirf tum jaanti ho ❤️</p>

  <input type="password" id="pass" placeholder="Anniversary date">
  <br>
  <button onclick="unlock()">Open</button>

  <div id="message"></div>
</div>

<script>
  const fullText = `I know tum mera se bohat zyada naraz ho, hurt ho, gussa ho…
Main tumhein bohat zehr lag raha hounga.

But tumhein achay se pata hai how much I love you jana.
Tumne kaha maine manaya nahi — theek hai, maan li aapki baat jana.
Main aapko is tareeqe se mana raha hoon ab.

Jana, I love you so much yaar.
Hamara inshallah rishta hone wala hai.
Aisay days chal rahe hain, laraiyan ho rahi hain, sab ho raha hai…
Lekin jana, maine aapko hurt kiya, gussa dilaya — I am so sorry yaar.

I am literally sorry.
Please maan jayein, maaf kar dein apni jana ko.
Main to aapka apna hoon na yaar…
Please maan jayein na meri jaan.

Maaf kar dein is larkay ko jo bohat pyaar karta hai tumse.
Ye larka tumhein is haal mein nahi dekh sakta.
Please maan jayein yaar.

I LOVE YOU SO MUCH ❤️❤️
SORRY YAAR

#AHFL ❤️`;

  let i = 0;

  function typeText() {
    if (i < fullText.length) {
      document.getElementById("message").innerHTML += fullText.charAt(i);
      i++;
      setTimeout(typeText, 35);
    }
  }

  function unlock() {
    var entered = document.getElementById("pass").value;
    var correct = "10082024";

    if (entered === correct) {
      document.getElementById("message").style.display = "block";
      typeText();
      startHearts();
    } else {
      alert("Galat password 😔 Apni yaadein yaad karo ❤️");
    }
  }

  function startHearts() {
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerText = "❤️";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDuration = (4 + Math.random() * 3) + "s";
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 7000);
    }, 500);
  }
</script>

</body>
</html>
