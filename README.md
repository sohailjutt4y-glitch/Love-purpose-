<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Secret Love ❤️</title>

<style>
body{
    margin:0;
    height:100vh;
    font-family:'Segoe UI',sans-serif;
    background:linear-gradient(135deg,#ff758c,#ff7eb3);
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;
}

/* LOGIN */
.login{
    background:white;
    padding:35px;
    border-radius:20px;
    text-align:center;
    box-shadow:0 20px 50px rgba(0,0,0,0.3);
    width:90%;
    max-width:350px;
}

.login input{
    width:90%;
    padding:12px;
    font-size:16px;
    margin:15px 0;
    border-radius:10px;
    border:1px solid #ccc;
}

.login button{
    padding:12px 30px;
    font-size:18px;
    background:#e60073;
    color:white;
    border:none;
    border-radius:30px;
    cursor:pointer;
}

/* MAIN CARD */
.card{
    display:none;
    background:white;
    padding:30px;
    border-radius:20px;
    box-shadow:0 20px 50px rgba(0,0,0,0.3);
    text-align:center;
    width:90%;
    max-width:420px;
    z-index:5;
}

.card img{
    width:120px;
    height:120px;
    border-radius:50%;
    object-fit:cover;
    margin-bottom:10px;
    border:4px solid #ff7eb3;
}

h1{
    color:#e60073;
}

#message{
    font-size:20px;
    margin:15px 0;
    min-height:50px;
}

.buttons{
    display:flex;
    justify-content:center;
    gap:20px;
    position:relative;
    height:70px;
}

button{
    padding:12px 30px;
    font-size:18px;
    border:none;
    border-radius:30px;
    cursor:pointer;
}

#yes{background:#28a745;color:white;}
#no{background:#dc3545;color:white;position:relative;}

/* Hearts */
.heart{
    position:fixed;
    top:-10px;
    font-size:20px;
    animation:fall linear forwards;
}
@keyframes fall{
    to{transform:translateY(110vh);opacity:0;}
}
</style>
</head>

<body>

<!-- 🔐 PASSWORD SCREEN -->
<div class="login" id="login">
    <h1>🔒 Private Page</h1>
    <p>Password likho warna entry nahi 😏</p>
    <input type="password" id="pass" placeholder="Enter password">
    <br>
    <button onclick="checkPass()">Enter ❤️</button>
</div>

<!-- ❤️ MAIN CONTENT -->
<div class="card" id="card">
    <img src="https://images.unsplash.com/photo-1529626455594-4ff0802cfb7e">
    <h1>I Love You ❤️</h1>
    <div id="message">Kya tum bhi mujhe pasand karti ho? 🥺</div>

    <div class="buttons">
        <button id="yes" onclick="yesClick()">Yes 😍</button>
        <button id="no" onclick="noClick()">No 🙄</button>
    </div>
</div>

<script>
let noCount=0;

function checkPass(){
    const p=document.getElementById("pass").value;
    if(p==="love123"){
        login.style.display="none";
        card.style.display="block";
    }else{
        alert("Galat password 😈 Dobara try karo");
    }
}

function yesClick(){
    document.body.innerHTML=`
    <div style="color:white;text-align:center;">
        <h1 style="font-size:45px;">🎉 Surprise 🎉</h1>
        <p style="font-size:26px;">Tum meri zindagi ho ❤️</p>
        <p>Ab to haan keh di 😎</p>
    </div>`;
}

function noClick(){
    noCount++;
    if(noCount===1) message.innerText="Ek baar phir soch lo 😢";
    else if(noCount===2) message.innerText="Maan jao na please 😭";
    else{
        no.style.transform=`translate(${Math.random()*120-60}px,${Math.random()*40-20}px)`;
    }
}

/* Hearts */
setInterval(()=>{
    const h=document.createElement("div");
    h.className="heart";
    h.innerHTML="❤️";
    h.style.left=Math.random()*100+"vw";
    h.style.animationDuration=(2+Math.random()*3)+"s";
    document.body.appendChild(h);
    setTimeout(()=>h.remove(),5000);
},350);
</script>

</body>
</html>
