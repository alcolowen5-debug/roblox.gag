<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <title>Connexion Roblox</title>
</head>
<body>
  <h2>Connexion à ton compte</h2>
  <form id="loginForm">
    <label for="username">Pseudo :</label><br />
    <input type="text" id="username" name="username" required /><br /><br />
    <label for="password">Mot de passe :</label><br />
    <input type="password" id="password" name="password" required /><br /><br />
    <button type="submit">Se connecter</button>
  </form>

  <div id="welcome" style="display:none;">
    <h3>Bienvenue, <span id="user"></span> !</h3>
    <p>Voici tes infos de compte :</p>
    <ul>
      <li>Stage actuel : Jardinier</li>
      <li>Progression : 45%</li>
      <li>Robux : 120</li>
      <!-- Tu pourras ici intégrer les vraies données via API -->
    </ul>
  </div>

  <script>
    const loginForm = document.getElementById('loginForm');
    const welcomeDiv = document.getElementById('welcome');
    const userSpan = document.getElementById('user');

    loginForm.addEventListener('submit', function(e) {
      e.preventDefault();
      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;

      // Ici tu peux mettre une vérification simple (exemple) :
      if(username === 'tonPseudo' && password === 'tonMotDePasse') {
        loginForm.style.display = 'none';
        userSpan.textContent = username;
        welcomeDiv.style.display = 'block';
      } else {
