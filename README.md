
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Happy 20th Josh 💖</title>

<style>
body{
  margin:0;
  font-family:'Segoe UI',sans-serif;
  overflow:hidden;
  background:linear-gradient(to bottom,#ff9ecf,#ffc9e6);
  color:white;
  text-align:center;
}

/* Slides */
.slide{
  position:absolute;
  width:100%;
  height:100vh;
  top:0;
  left:100%;
  padding:30px;
  box-sizing:border-box;
  transition:1s ease;
}
.active{ left:0; }

button{
  padding:12px 25px;
  border:none;
  border-radius:30px;
  background:#ff4da6;
  color:white;
  font-size:16px;
  margin-top:20px;
  box-shadow:0 0 15px #fff;
  transition:0.3s;
  position:relative;
}
button:hover{ transform:scale(1.1); }

input{
  padding:10px;
  border-radius:20px;
  border:none;
  text-align:center;
}

/* Glow name */
.glow{
  font-size:42px;
  font-weight:bold;
  animation:glow 2s infinite alternate;
}
@keyframes glow{
  from{ text-shadow:0 0 10px #fff;}
  to{ text-shadow:0 0 40px #ff1493;}
}

/* Hearts */
.heart{
  position:absolute;
  animation:floatUp 6s linear forwards;
}
@keyframes floatUp{
  from{transform:translateY(100vh);}
  to{transform:translateY(-10vh); opacity:0;}
}

/* Flowers */
.flower{
  position:absolute;
  animation:fall 8s linear forwards;
}
@keyframes fall{
  from{transform:translateY(-10vh) rotate(0deg);}
  to{transform:translateY(110vh) rotate(360deg); opacity:0;}
}

/* Confetti */
.confetti{
  position:absolute;
  width:8px;
  height:8px;
  animation:confettiFall 5s linear forwards;
}
@keyframes confettiFall{
  to{ transform:translateY(100vh); opacity:0;}
}

/* Envelope */
.envelope{
  width:200px;
  height:130px;
  background:#ff66b2;
  margin:60px auto;
  border-radius:10px;
  position:relative;
  cursor:pointer;
}
.envelope:before{
  content:"";
  position:absolute;
  top:-65px;
  left:0;
  border-left:100px solid transparent;
  border-right:100px solid transparent;
  border-bottom:65px solid #ff85c1;
  transition:1s;
}
.open:before{
  transform:rotateX(180deg);
  transform-origin:top;
}

/* Stars */
.stars::after{
  content:"✨ ✨ ✨ ✨ ✨ ✨ ✨ ✨ ✨ ✨";
  position:absolute;
  width:100%;
  top:0;
  left:0;
  animation:twinkle 2s infinite alternate;
}
@keyframes twinkle{
  from{opacity:0.3;}
  to{opacity:1;}
}

/* Fireworks */
.firework{
  position:absolute;
  width:10px;
  height:10px;
  background:white;
  border-radius:50%;
  animation:explode 1s ease-out forwards;
}
@keyframes explode{
  to{ transform:scale(20); opacity:0;}
}
</style>
</head>

<body>

<!-- PASSCODE -->
<div class="slide active" id="slide0">
  <h2>Enter Passcode 🔑🔒</h2>
  <p>Hint: Your new age 😉</p>
  <input type="password" id="pass">
  <br><br>
  <button onclick="unlock()">Unlock</button>
</div>

<!-- SLIDE 1 -->
<div class="slide" id="slide1">
  <div class="envelope" onclick="openEnvelope(this)"></div>
  <p>Tap the envelope 💌</p>
</div>

<!-- SLIDE 2 -->
<div class="slide" id="slide2">
  <div class="glow">Happy 20th Birthday My Love 
  
</div>
  
  
  </p>
  <button class="runaway" onclick="nextSlide(3)">Next ➡</button>
</div>

<!-- SLIDE 3 -->
<div class="slide stars" id="slide3">
  <h2>Under Your Starry Night 🌌</h2>
  <p>
    May your twenties be fearless.<br>
    May your goals grow bigger.<br>
    May your heart stay beautiful.
  </p>
  <button class="runaway" onclick="nextSlide(4)">I said next ➡</button>
</div>

<!-- SLIDE 4 -->
<div class="slide" id="slide4">
  <h2>💌</h2>
  <p style="font-size:17px;">
    <br><br>
    🤍 You deserve success, peace, and love.
    🤍 Never doubt the strength inside you.
  </p>
  <button class="runaway" onclick="nextSlide(5)">Next ➡</button>
</div>

<!-- SLIDE 5 -->
<div class="slide" id="slide5">
  <h2>Forever Proud of You 🌸</h2>
  <p>
    May this decade bring powerful growth, meaningful love,  
    and unforgettable memories.  
    You are deeply loved.
    
    From Your Wife and beautiful baby Elias
  </p>
  <button onclick="celebrate()">Celebrate 🎆</button>
</div>

<script>
let current=0;

/* Unlock */
function unlock(){
  if(document.getElementById("pass").value=="20"){
    nextSlide(1);
  }else{ alert("Wrong passcode 💔"); }
}

/* Slide transition */
function nextSlide(n){
  document.getElementById("slide"+current).classList.remove("active");
  current=n;
  document.getElementById("slide"+n).classList.add("active");
}

/* Envelope */
function openEnvelope(el){
  el.classList.add("open");
  setTimeout(()=>nextSlide(2),1000);
}

/* Hearts */
setInterval(()=>{
  let h=document.createElement("div");
  h.className="heart";
  h.innerHTML="💖";
  h.style.left=Math.random()*100+"vw";
  h.style.fontSize=(20+Math.random()*25)+"px";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},400);

/* Pink flowers */
setInterval(()=>{
  let f=document.createElement("div");
  f.className="flower";
  f.innerHTML="🌸";
  f.style.left=Math.random()*100+"vw";
  f.style.fontSize=(20+Math.random()*30)+"px";
  document.body.appendChild(f);
  setTimeout(()=>f.remove(),8000);
},300);

/* Confetti */
function confettiBurst(){
  for(let i=0;i<50;i++){
    let c=document.createElement("div");
    c.className="confetti";
    c.style.left=Math.random()*100+"vw";
    c.style.background="hsl("+Math.random()*360+",100%,70%)";
    document.body.appendChild(c);
    setTimeout(()=>c.remove(),5000);
  }
}

/* Fireworks + Name Explosion */
function celebrate(){
  confettiBurst();
  for(let i=0;i<30;i++){
    let fw=document.createElement("div");
    fw.className="firework";
    fw.style.left=Math.random()*100+"vw";
    fw.style.top=Math.random()*100+"vh";
    document.body.appendChild(fw);
    setTimeout(()=>fw.remove(),1000);
  }

  let name=document.createElement("div");
  name.innerHTML="I love you Happy Birthday"
  name.style.position="absolute";
  name.style.top="40%";
  name.style.width="100%";
  name.style.fontSize="55px";
  name.style.fontWeight="bold";
  name.style.animation="glow 1s infinite alternate";
  document.body.appendChild(name);
}

/* RUNAWAY BUTTONS */
document.querySelectorAll(".runaway").forEach(btn=>{
  btn.addEventListener("mouseover",()=>{
    btn.style.position="absolute";
    btn.style.left=Math.random()*80+"%";
    btn.style.top=Math.random()*80+"%";
  });
});
</script>

</body>
