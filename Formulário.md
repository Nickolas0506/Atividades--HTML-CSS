<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Login</title>
  <style>
    * {
      box-sizing: border-box;
    }
 
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #3f51b5, #5c6bc0);
      margin: 0;
      padding: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
 
    .login-container {
      background-color: white;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
      width: 100%;
      max-width: 400px;
    }
 
    .login-container h2 {
      text-align: center;
      margin-bottom: 24px;
      color: #333;
    }
 
    .form-group {
      margin-bottom: 18px;
    }
 
    label {
      display: block;
      margin-bottom: 6px;
      color: #555;
    }
 
    input[type="text"],
    input[type="password"] {
      width: 100%;
      padding: 12px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }
 
    button {
      width: 100%;
      padding: 12px;
      background-color: #3f51b5;
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      transition: background 0.3s;
    }
 
    button:hover {
      background-color: #303f9f;
    }
 
    .register-link {
      text-align: center;
      margin-top: 15px;
      font-size: 14px;
    }
 
    .register-link a {
      color: #3f51b5;
      text-decoration: none;
    }
 
    .register-link a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <div class="login-container">
    <h2>Login</h2>
    <form>
      <div class="form-group">
        <label for="username">Usuário</label>
        <input type="text" id="username" name="username" placeholder="Digite seu usuário" required>
      </div>
      <div class="form-group">
        <label for="password">Senha</label>
        <input type="password" id="password" name="password" placeholder="Digite sua senha" required>
      </div>
      <button type="submit">Entrar</button>
      <div class="register-link">
        Não tem uma conta? <a href="#">Cadastre-se</a>
      </div>
    </form>
  </div>
</body>
</html>
 
