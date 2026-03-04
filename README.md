<!DOCTYPE html>
<html>
<head>
<title>Arun Maths Classes</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>

body{
  margin:0;
  font-family: Arial, sans-serif;
  background: linear-gradient(to right, #667eea, #764ba2);
  color:white;
}

header{
  padding:20px;
  text-align:center;
  font-size:28px;
  font-weight:bold;
  background:rgba(0,0,0,0.4);
}

nav{
  display:flex;
  justify-content:center;
  background:black;
}

nav a{
  color:white;
  padding:14px 20px;
  text-decoration:none;
}

nav a:hover{
  background:#ff416c;
}

section{
  display:none;
  padding:30px;
  text-align:center;
}

.active{
  display:block;
}

.card{
  background:white;
  color:black;
  padding:20px;
  border-radius:15px;
  width:80%;
  margin:auto;
  box-shadow:0 8px 20px rgba(0,0,0,0.3);
}

button{
  background:#ff4b2b;
  color:white;
  border:none;
  padding:10px 20px;
  border-radius:25px;
  cursor:pointer;
}

footer{
  text-align:center;
  padding:15px;
  background:black;
  margin-top:20px;
}

</style>

<script>
function showPage(pageId){
  var sections = document.querySelectorAll("section");
  sections.forEach(function(sec){
    sec.classList.remove("active");
  });
  document.getElementById(pageId).classList.add("active");
}
</script>

</head>
<body>

<header>
Arun Maths Classes
</header>

<nav>
  <a href="#" onclick="showPage('home')">Home</a>
  <a href="#" onclick="showPage('about')">About</a>
  <a href="#" onclick="showPage('courses')">Courses</a>
  <a href="#" onclick="showPage('contact')">Contact</a>
</nav>

<section id="home" class="active">
  <div class="card">
    <h2>Welcome Students 👋</h2>
    <p>Yaha par aapko Maths ke easy solutions milenge.</p>
    <button onclick="alert('Start Learning Now!')">Start</button>
  </div>
</section>

<section id="about">
  <div class="card">
    <h2>About Me</h2>
    <p>My name is Arun Bordoloi. Main Maths teacher hoon aur students ko easy tareeke se padhata hoon.</p>
  </div>
</section>

<section id="courses">
  <div class="card">
    <h2>Our Courses</h2>
    <p>Class 8 Maths</p>
    <p>Class 9 Maths</p>
    <p>Class 10 Board Preparation</p>
  </div>
</section>

<section id="contact">
  <div class="card">
    <h2>Contact Us</h2>
    <p>Email: arunphangsung@gmail.com</p>
    <p>Phone: 7708270633</p>
  </div>
</section>

<footer>
© 2026 Arun Maths Classes | All Rights Reserved
</footer>
<!-- Chatbot Button -->
<div id="chatIcon" onclick="openChat()">💬</div>

<!-- Chat Window -->
<div id="chatBox">
  <div id="chatHeader">
    Arun AI Chatbot
    <span onclick="closeChat()" style="float:right;cursor:pointer;">✖</span>
  </div>
  <div id="chatMessages"></div>
  <input type="text" id="userInput" placeholder="Type message..." onkeypress="handleKey(event)">
</div>

<style>
#chatIcon{
  position:fixed;
  bottom:20px;
  right:20px;
  background:#ff4b2b;
  color:white;
  padding:15px;
  border-radius:50%;
  cursor:pointer;
  font-size:20px;
}

#chatBox{
  display:none;
  position:fixed;
  bottom:80px;
  right:20px;
  width:300px;
  background:white;
  border-radius:10px;
  box-shadow:0 5px 15px rgba(0,0,0,0.3);
  overflow:hidden;
}

#chatHeader{
  background:#667eea;
  color:white;
  padding:10px;
  font-weight:bold;
}

#chatMessages{
  height:200px;
  overflow-y:auto;
  padding:10px;
  font-size:14px;
}

#userInput{
  width:100%;
  padding:10px;
  border:none;
  border-top:1px solid #ccc;
}
</style>

<script>
function openChat(){
  document.getElementById("chatBox").style.display="block";
}

function closeChat(){
  document.getElementById("chatBox").style.display="none";
}

function handleKey(e){
  if(e.key === "Enter"){
    sendMessage();
  }
}

function sendMessage(){
  var input = document.getElementById("userInput");
  var message = input.value;
  if(message === "") return;

  var chat = document.getElementById("chatMessages");
  chat.innerHTML += "<p><b>You:</b> " + message + "</p>";

  var reply = getReply(message);
  chat.innerHTML += "<p><b>Bot:</b> " + reply + "</p>";

  input.value="";
  chat.scrollTop = chat.scrollHeight;
}

function getReply(msg){
  msg = msg.toLowerCase();

  if(msg.includes("hello")) return "Hello Arun 👋";
  if(msg.includes("math")) return "Maths question puchiye 😊";
  if(msg.includes("course")) return "Hamare paas Class 8, 9, 10 Maths hai.";
  return "Sorry, main abhi simple AI hoon 😅";
}
</script>
</body>
</html>
