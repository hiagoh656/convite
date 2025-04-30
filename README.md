<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Convite Romântico para Jantar</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        .container {
            text-align: center;
            background: linear-gradient(145deg, rgba(255, 204, 204, 0.9), rgba(255, 182, 193, 0.9));
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            width: 90%;
            max-width: 600px;
            margin: 20px;
        }

        h1 {
            color: #ff4d4d;
            font-size: 28px;
            margin-bottom: 15px;
        }

        p {
            font-size: 16px;
            color: #333;
            margin-bottom: 15px;
        }

        .form-section {
            margin-top: 20px;
        }

        input[type="text"] {
            padding: 12px;
            width: 80%;
            font-size: 16px;
            border-radius: 5px;
            border: 1px solid #ddd;
            margin-bottom: 15px;
        }

        .acceptance {
            margin-top: 15px;
        }

        .acceptance input[type="checkbox"] {
            margin-right: 10px;
        }

        .submit-btn {
            background-color: #ff4d4d;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }

        .submit-btn:hover {
            background-color: #ff1a1a;
        }

        @media (max-width: 600px) {
            h1 {
                font-size: 24px;
            }

            p {
                font-size: 14px;
            }

            .submit-btn {
                padding: 10px 18px;
                font-size: 14px;
            }
        }

        .celebration {
            background: linear-gradient(135deg, #ffccd5, #ffe6eb);
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 50px;
            font-family: 'Arial', sans-serif;
        }

        .hearts-and-confetti {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 999;
        }

        .confetti, .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            opacity: 0.8;
            animation: floatUp 4s linear infinite;
        }

        .confetti {
            background-color: #f39c12;
            transform: rotate(45deg);
        }

        .heart::before, .heart::after {
            content: "";
            position: absolute;
            width: 10px;
            height: 16px;
            background: red;
            border-radius: 50% 50% 0 0;
        }

        .heart::before {
            left: 0;
            transform: rotate(-45deg);
            transform-origin: right bottom;
        }

        .heart::after {
            left: 10px;
            transform: rotate(45deg);
            transform-origin: left bottom;
        }

        @keyframes floatUp {
            from {
                transform: translateY(100vh);
                opacity: 1;
            }
            to {
                transform: translateY(-10vh);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>💌 Convite Especial para um Jantar Romântico 💕🍔🍟🥤</h1>
        <p>Querido(a) noivo(a), estou preparando algo especial para nós dois... ❤️🍽️✨</p>
        <p style="font-style: italic; color: #b30059; margin-top: 10px;">
            “Tu te tornas eternamente responsável por aquilo que cativas.”<br>
            E você, meu amor, me cativou como as estrelas cativam o céu. Cada momento ao seu lado é poesia pura, 
            como se o mundo tivesse parado só para nos ver sorrir juntos. 🌹✨
        </p>

        <div class="form-section">
            <p>Por favor, digite o seu nome:</p>
            <input type="text" id="name" placeholder="Seu nome aqui">
            
            <div class="acceptance">
                <p>Você aceita o meu convite para o jantar romântico?</p>
                <label>
                    <input type="checkbox" id="accept"> Sim, aceito com prazer!
                </label>
            </div>
            
            <button class="submit-btn" onclick="submitForm()">Enviar</button>
        </div>
    </div>

    <script>
        function submitForm() {
            var name = document.getElementById("name").value;
            var accept = document.getElementById("accept").checked;

            if (!name) {
                alert("Por favor, digite seu nome.");
                return;
            }

            if (accept) {
                document.body.innerHTML = `
                    <div class="celebration">
                        <div class="hearts-and-confetti"></div>
                        <h1>Obrigado, ${name}!</h1>
                        <p>Você aceitou o convite. Vai ser uma noite incrível! ❤️🍕🍷💑</p>
                    </div>
                `;
                startAnimation();
            } else {
                alert("Por favor, marque a opção 'Sim'.");
            }
        }

        function startAnimation() {
            const container = document.querySelector(".hearts-and-confetti");
            for (let i = 0; i < 50; i++) {
                const el = document.createElement("div");
                el.className = Math.random() > 0.5 ? "confetti" : "heart";
                el.style.left = Math.random() * 100 + "vw";
                el.style.animationDelay = Math.random() * 2 + "s";
                container.appendChild(el);
            }
        }
    </script>

</body>
</html>
