<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aya 💖</title>
<style>
body {
  margin: 0;
  font-family: 'Courier New', monospace;
  background: linear-gradient(to bottom right, #2c2c2c, #1a1a1a);
  color: #f5f5f5;
  overflow: hidden;
  text-align: center;
  position: relative;
  transition: background 0.5s, color 0.5s;
}

body.light-mode {
  background: linear-gradient(to bottom right, #fde2e4, #fad2e1);
  color: #333;
}

section {
  display: none;
  height: 100vh;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
section.active { display: flex; }

input {
  padding: 10px;
  font-size: 16px;
  border-radius: 10px;
  border: 1px solid #888;
  background: #444;
  color: #f5f5f5;
}

body.light-mode input {
  background: white;
  color: #333;
  border: 1px solid #ccc;
}

button {
  margin-top: 10px;
  padding: 10px 20px;
  border: none;
  border-radius: 10px;
  background: #ff6b81;
  color: white;
  cursor: pointer;
  transition: background 0.5s, color 0.5s;
}

#errorMessage { color: red; margin-top: 10px; opacity: 0; transition: 0.3s; }

#catchable-image {
  position: absolute;
  width: 150px;
  height: 120px;
  cursor: pointer;
  border-radius: 0; /* مستطيل */
  transition: left 0.5s, top 0.5s;
  z-index: 10;
}

#message {
  font-size: 20px;
  white-space: pre-line;
  max-width: 80%;
  max-height: 60vh;
  margin: 20px auto;
  position: relative;
  z-index: 20;
  overflow-y: auto;
  padding: 10px;
  background: rgba(0,0,0,0.1);
  border-radius: 10px;
}

.heart {
  position: absolute;
  width: 50px;
  height: 50px;
  opacity: 0.3;
  z-index: 5;
  pointer-events: none;
  transition: top 0.1s;
  clip-path: polygon(
    50% 0%, 61% 5%, 68% 10%, 75% 20%, 85% 35%, 90% 50%,
    85% 65%, 75% 75%, 60% 90%, 50% 100%, 40% 90%, 25% 75%,
    15% 65%, 10% 50%, 15% 35%, 25% 20%, 32% 10%, 39% 5%
  );
}

#timer {
  margin-top: 20px;
  font-size: 18px;
  font-weight: bold;
}

#themeToggle {
  position: fixed;
  top: 10px;
  right: 10px;
  z-index: 30;
}
</style>
</head>
<body>

<section id="passwordGateSection" class="active">
<h2>Enter Password 💌</h2>
<input type="password" id="passwordInput" placeholder="Password"/>
<button onclick="checkPassword()">Enter</button>
<div id="errorMessage">Wrong password!</div>
</section>

<section id="gameSection">
<h2>Catch me if you can 😘</h2>
<img id="catchable-image" src="https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/catch_aya.png?raw=true" alt="Catch me"/>
</section>

<section id="mainMessageSection">
<h2 id="changingName">Aya 💖</h2>
<div id="message"></div>
<div id="timer"></div>
<audio id="background-music" src="https://github.com/Mk0123811819/aya/blob/main/aya_ds/audio/me_gustas_tu.mp3?raw=true" loop></audio>
<button id="themeToggle">Switch Theme</button>
</section>

<script>
const passwordGateSection = document.getElementById('passwordGateSection');
const gameSection = document.getElementById('gameSection');
const mainMessageSection = document.getElementById('mainMessageSection');
const image = document.getElementById('catchable-image');
const music = document.getElementById('background-music');
const messageEl = document.getElementById('message');
const changingName = document.getElementById('changingName');
const timerEl = document.getElementById('timer');
const themeToggle = document.getElementById('themeToggle');

// Theme switch
themeToggle.addEventListener('click', () => {
  document.body.classList.toggle('light-mode');
});

// Password
function checkPassword() {
  const password = document.getElementById('passwordInput').value.trim();
  const correctPassword = "me gusta tu";
  const errorMessage = document.getElementById('errorMessage');
  if (password === correctPassword) {
    errorMessage.style.opacity = "0";
    passwordGateSection.classList.remove('active');
    gameSection.classList.add('active');
  } else {
    errorMessage.style.opacity = "1";
  }
}

// Catch image random movement
function moveImageRandomly() {
  const newX = Math.random() * (window.innerWidth - image.offsetWidth);
  const newY = Math.random() * (window.innerHeight - image.offsetHeight);
  image.style.left = `${newX}px`;
  image.style.top = `${newY}px`;
}
setInterval(moveImageRandomly, 2000);

// Click catch image
image.addEventListener('click', () => {
  music.play(); // الموسيقى تبدأ هنا
  gameSection.classList.remove('active');
  mainMessageSection.classList.add('active');
  startMainPage();
});

// Full message
const fullMessage = `heeeeeeeeeeyyyyy 7bibaaaa

Cv lyoma nhar mohim bnsba lya o lik o hwa nhar li zin dyali twldt fih yooooooooo kbrti 3am lyoma happy birthday sweetheart 💓🥀

hmmm e3rfi bli ana knbghik mxi gha knbghik knmoooooooooooooot 3lik nti hya klxi bnsba lya llah y5alik lya o ytawl f3omrk 😭💕

3rfi bli ana dima hna lik o ghtl9ini 7dak o forever hdxi m3aaaaaaaaaaaak ana albgoosa nti hya a7la 7aja trat m3aya had l3am wa5a kndabzo bzf hhh wlakin 3mr hdxi atr f3la9tna wola f7obi o m3zti lik mn nhar t9ablna o li hwa 7/7/2025 ktzid m3mrhhhhhaaaaaaaaaaa n9st🤍

ayooooshti smo7aaaat 3sbtk bzf 😂 sm7i lya wola mo3tarf brassi  eni knt kn3sbk wlakin ki3jbni fx tghiri 3lya kijbni fx tt3sbi 3lya klxi fik ki3jbni mkntmnax l3la9a dyalna tsali bxi mdabza sooo its a promise ila dabza ndwiw o nsal7o mn wraha🤞

I love lyoma I love lghda and i will love u forever✨🤎`;

let index = 0;
function typeWriter() {
  if (index < fullMessage.length) {
    messageEl.innerHTML += fullMessage.charAt(index);
    index++;
    setTimeout(typeWriter, 30);
  }
}

// Names changing
const names = ["Aya 💖", "7biba 💕", "3mri 🌹", "7yati 😘", "Ayoshti 🥰"];
function changeName() {
  const randomName = names[Math.floor(Math.random() * names.length)];
  changingName.textContent = randomName;
  document.title = randomName;
}

// Timer
function startTimer() {
  const startDate = new Date("2025-07-07T00:00:00");
  setInterval(() => {
    const now = new Date();
    const diff = now - startDate;
    const days = Math.floor(diff / (1000 * 60 * 60 * 24));
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
    const minutes = Math.floor((diff / (1000 * 60)) % 60);
    const seconds = Math.floor((diff / 1000) % 60);
    timerEl.textContent = `We’ve been together: ${days}d ${hours}h ${minutes}m ${seconds}s 💞`;
  }, 1000);
}

// Floating hearts
const hearts = [
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_1.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_2.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_3.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_4.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_5.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_6.png?raw=true",
  "https://github.com/Mk0123811819/aya/blob/main/aya_ds/images/aya_7.png?raw=true"
];

function createFloating() {
  const idx = Math.floor(Math.random() * hearts.length);
  const src = hearts[idx];
  const el = document.createElement("img");
  el.src = src;
  el.className = "heart";
  el.style.left = Math.random() * (window.innerWidth - 50) + "px";
  el.style.top = "-60px";
  el.style.width = "50px";
  el.style.height = "50px";
  el.style.opacity = 0.3 + Math.random() * 0.2;
  document.body.appendChild(el);

  let speed = 1 + Math.random() * 2;
  const fall = setInterval(() => {
    let top = parseFloat(el.style.top);
    if (top > window.innerHeight) {
      clearInterval(fall);
      el.remove();
    } else {
      el.style.top = top + speed + "px";
    }
  }, 20);
}

function startMainPage() {
  typeWriter();
  setInterval(createFloating, 500);
  setInterval(changeName, 2000);
  startTimer();
}
</script>
</body>
</html>
