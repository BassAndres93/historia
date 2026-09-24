<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Carta Romántica</title>
 
<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
}
 
body{
font-family: 'Segoe UI', sans-serif;
background: linear-gradient(180deg,#ffd6ec,#fff8dc);
min-height:100vh;
text-align:center;
overflow-x:hidden;
}
 
header{
padding:20px;
}
 
.imagen-pareja{
width:80%;
max-width:500px;
border-radius:20px;
box-shadow:0 0 20px rgba(0,0,0,.3);
}
 
.contenedor{
margin-top:20px;
padding:20px;
}
 
button{
padding:12px 25px;
border:none;
border-radius:30px;
background:#ff5e8a;
color:white;
font-size:18px;
cursor:pointer;
transition:.3s;
margin:10px;
}
 
button:hover{
transform:scale(1.08);
background:#ff2f68;
}
 
.carta{
width:80%;
max-width:600px;
margin:20px auto;
padding:25px;
background:white;
border-radius:20px;
box-shadow:0 0 15px rgba(0,0,0,.2);
display:none;
animation:aparecer 1s ease;
}
 
.carta h2{
color:#e91e63;
margin-bottom:15px;
}
 
.carta p{
font-size:18px;
line-height:1.7;
}
 
@keyframes aparecer{
from{
opacity:0;
transform:translateY(30px);
}
to{
opacity:1;
transform:translateY(0);
}
}
 
.flor{
position:fixed;
font-size:40px;
animation:caer 6s linear forwards;
}
 
@keyframes caer{
0%{
transform:translateY(-100px) rotate(0deg);
opacity:1;
}
100%{
transform:translateY(100vh) rotate(360deg);
opacity:0;
}
}
</style>
</head>
 
<body>
 
<header>
<img class="imagen-pareja"
src="https://images.unsplash.com/photo-1516589091380-5d8e87df6999?auto=format&fit=crop&w=900&q=80"
alt="Pareja romántica">
</header>
 
 
💌 Abrir Carta
</button>
 
<div class="carta" id="carta">
 
<h2>Para Ti ❤️</h2>
 
<p>
Aquí puedes escribir el mensaje que desees.
<br><br>
 
Mi amor:
<br><br>
 
Gracias por iluminar mis días con tu sonrisa.
Cada instante contigo se convierte en un recuerdo
especial que guardo en mi corazón.
Eres mi alegría, mi inspiración y la persona
con quien quiero compartir los momentos más hermosos.
<br><br>
 
Con todo mi cariño 🌹❤️
</p>
 
<button onclick="mostrarFlores()">
🌻 Presiona para ver flores y girasoles
</button>
 
</div>
 
</div>
 
<script>
function abrirCarta(){
document.getElementById("carta").style.display="block";
}
 
function mostrarFlores(){
 
const emojis = ["🌻","🌼","🌷","🌹","💐","🌺"];
 
for(let i=0;i<40;i++){
 
let flor=document.createElement("div");
flor.classList.add("flor");
 
flor.innerHTML=
emojis[Math.floor(Math.random()*emojis.length)];
 
flor.style.left=Math.random()*100+"vw";
flor.style.animationDuration=
(Math.random()*3+4)+"s";
 
document.body.appendChild(flor);
 
setTimeout(()=>{
flor.remove();
},7000);
}
}
</script>
 
</body>
</html>
