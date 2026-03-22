# Mon-Restau-En-Ligne
Application pour passer ma commande 

<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Restaurant Chez KONDRO</title>

<style>
body{
font-family:Arial;
background:#f4f4f4;
}

.chat{
width:320px;
margin:auto;
background:white;
padding:10px;
border-radius:10px;
box-shadow:0 0 10px rgba(0,0,0,0.2);
}

#messages{
height:250px;
overflow:auto;
border:1px solid #ccc;
padding:5px;
margin-bottom:10px;
}

input{
width:95%;
padding:8px;
margin-top:5px;
}

button{
padding:8px;
background:green;
color:white;
border:none;
margin-top:5px;
width:100%;
cursor:pointer;
}

</style>

</head>

<body>

<div class="chat">

<h3>🍽️ Restaurant: Ma commande</h3>

<div id="messages"></div>

<!-- CHAT -->
<input type="text" id="msg" placeholder="Écrire un message...">
<button onclick="envoyer()">Envoyer</button>

<hr>

<h4>🛒 Commander</h4>

<input type="text" id="nom" placeholder="Votre nom">
<input type="text" id="commande" placeholder="Ex: Riz + poulet + boisson">

<button onclick="commander()">Envoyer la commande</button>

</div>

<script>

function envoyer(){

let input=document.getElementById("msg")
let message=input.value.toLowerCase()

let box=document.getElementById("messages")

box.innerHTML += "<p><b>Vous :</b> "+message+"</p>"

let reponse=""

if(message.includes("bonjour")){
reponse="Bonjour 👋 Bienvenue ! Tapez 'menu' pour voir nos plats ou descendez pour commander."
}

else if(message.includes("menu")){
reponse="🍽️ MENU :\n- Riz + poulet (2000f)\n- Attiéké + poisson (2500f)\n- Boisson (500f)"
}

else if(message.includes("commander")){
reponse="Veuillez remplir le formulaire ci-dessous pour passer votre commande 👇"
}

else{
reponse="Je n'ai pas compris 😅 Tapez 'menu' ou 'commander'"
}

box.innerHTML += "<p><b>Bot :</b> "+reponse+"</p>"

input.value=""

}

function commander(){

let nom = document.getElementById("nom").value
let commande = document.getElementById("commande").value

if(nom=="" || commande==""){
alert("Veuillez remplir tous les champs")
return
}

let numero = "2250506069353" // 🔴 METTRE NUMERO RESTAURATEUR

let message = "Nouvelle commande 🍽️%0A"
+ "Nom : " + nom + "%0A"
+ "Commande : " + commande

window.open("https://wa.me/"+numero+"?text="+message)

}

</script>

</body>
</html>
