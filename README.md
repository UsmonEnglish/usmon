<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Register User</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #333, #444);
            color: #fff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .register-container {
            background: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            max-width: 400px;
            width: 100%;
            text-align: center;
        }

        .register-container h2 {
            color: #00e5ff;
            margin-bottom: 20px;
        }

        .register-container label {
            display: block;
            margin-bottom: 10px;
            color: #ddd;
            font-size: 16px;
        }

        .register-container input {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #00e5ff;
            border-radius: 5px;
            background: #444;
            color: #fff;
            font-size: 14px;
        }

        .register-container button {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 5px;
            background: #00e5ff;
            color: white;
            font-size: 16px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .register-container button:hover {
            background: #0091cb;
        }
    </style>
</head>
<body>
    <div class="register-container">
        <h2>Register</h2>
        <form id="registerForm">
            <label for="firstName">Ном:</label>
            <input type="text" id="firstName" name="firstName" required>

            <label for="lastName">Насаб:</label>
            <input type="text" id="lastName" name="lastName" required>

            <label for="email">Почтаи электронӣ:</label>
            <input type="email" id="email" name="email" required>

            <label for="password">Парол:</label>
            <input type="password" id="password" name="password" required>

            <label for="registrationDate">Санаи бақайдгирӣ:</label>
            <input type="date" id="registrationDate" name="registrationDate" required>

            <button type="submit">Бақайдгирӣ</button>
        </form>
    </div>

    <script>
        document.getElementById("registerForm").addEventListener("submit", async (e) => {
            e.preventDefault();

            const firstName = document.getElementById("firstName").value;
            const lastName = document.getElementById("lastName").value;
            const email = document.getElementById("email").value;
            const password = document.getElementById("password").value;
            const registrationDate = document.getElementById("registrationDate").value;

            const response = await fetch("https://script.google.com/macros/s/AKfycbwWXiH0JBjh0jGInDN7_NJUdCsCjFXUDQRPAtVthbki3j3Z276DA50lyT7E4rqT_dpm/exec", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                },
                body: JSON.stringify({ firstName, lastName, email, password, registrationDate }),
            });

            const result = await response.text();
            alert(result);
            window.location.href = "game.html";  // Пас аз бақайдгирӣ ба саҳифаи бози равона мекунад
        });
    </script>
</body>
</html>
