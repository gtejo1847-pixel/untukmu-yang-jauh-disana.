# untukmu-yang-jauh-disana.
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Untukmu</title>

<style>
body{
  margin:0;
  height:100vh;
  font-family: Georgia, serif;
  background: linear-gradient(135deg,#f9f6f2,#ffe6f0);
  display:flex;
  justify-content:center;
  align-items:center;
  overflow:hidden;
}

.container{
  background:white;
  padding:30px;
  max-width:520px;
  border-radius:20px;
  box-shadow:0 10px 30px rgba(0,0,0,.15);
  text-align:center;
  position:relative;
  z-index:2;
}

h1{
  color:#c94f7c;
  margin-bottom:20px;
}

.poem{
  text-align:left;
  white-space:pre-line;
  font-size:18px;
  line-height:1.7;
  color:#333;
}

.tap{
  margin-top:20px;
  font-size:14px;
  color:#888;
  cursor:pointer;
  animation:pulse 1.5s infinite;
}

.signature{
  margin-top:18px;
  font-style:italic;
  color:#666;
}

@keyframes pulse{
  0%{opacity:.4}
  50%{opacity:1}
  100%{opacity:.4}
}

/* HATI */
.heart{
  position:fixed;
  top:-10px;
  font-size:20px;
  color:#e63963;
  animation:fall linear infinite;
  z-index:1;
}

@keyframes fall{
  to{
    transform:translateY(110vh) rotate(360deg);
    opacity:0;
  }
}
</style>
</head>

<body>

<div class="container" onclick="start()">
  <h1>Untukmu</h1>

  <div class="poem">
Aku sudah sampai di titik
tidak berharap apa-apa dari siapa pun.
Bukan karena kuat,
tapi karena capek jatuh di lubang yang sama.

Aku sudah yakin
tidak ada lagi yang bisa menggeser perhatianku,
lalu kamu datang
dan merusak keyakinan itu dengan cara yang tenang.

Aku tidak minta janji,
tidak juga kepastian.
Kalau pun ini salah,
biarlah salah yang aku pilih dengan sadar.

Kalau kamu mau tinggal sebentar,
ajari aku pelan-pelan
bahwa percaya tidak selalu berakhir
dengan kehilangan.
  </div>

  <div class="tap">Tap di sini</div>
  <div class="signature">— Djati</div>
</div>

<audio id="music" loop>
  <source src="musik.mpeg" type="audio/mpeg">
</audio>

<script>
let started=false;

function start(){
  if(started) return;
  started=true;

  const music=document.getElementById("music");
  music.play().catch(()=>alert("Pastikan file musik.mpeg ada"));

  setInterval(()=>{
    const h=document.createElement("div");
    h.className="heart";
    h.innerHTML="❤";
    h.style.left=Math.random()*100+"vw";
    h.style.animationDuration=(Math.random()*3+3)+"s";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),6000);
  },500);
}
</script>

</body>
</html>

