<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Градієнтний фон з анімацією</title>
    <style>
        body {
            height: 100vh;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(to bottom, #001f3f, #b03060); /* Темно-синій до темно-червоного */
            color: white;
            font-size: 2em;
            text-align: center;
            transition: background 0.5s;
            overflow: hidden; /* Забезпечує, що анімації не виходять за межі */
        }

        .emoji {
            position: absolute;
            font-size: 48px;
        }

        #cat {
            top: 10%;
            left: 10%;
            animation: moveCat 3s infinite alternate ease-in-out;
        }

        #hearts {
            bottom: 10%;
            right: 10%;
            animation: moveHearts 3s infinite alternate ease-in-out;
        }

        #heart {
            display: none; /* Ховаємо серце спочатку */
            font-size: 48px;
            position: absolute;
            bottom: 20%; /* Розміщуємо серце в нижній частині */
            left: 50%;
            transform: translateX(-50%); /* Центруємо серце */
        }

        @keyframes moveCat {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(50px, 50px);
            }
        }

        @keyframes moveHearts {
            from {
                transform: translate(0, 0);
            }
            to {
                transform: translate(-50px, -50px);
            }
        }
    </style>
</head>
<body>
    <div id="text">Просто натискай на екран 🤍</div>

    <!-- Кіт та серця -->
    <div id="cat" class="emoji">🐈‍⬛🤍🐈‍⬛🤍🐈‍⬛🤍</div>
    <div id="hearts" class="emoji">🤍🐈‍⬛🤍🐈‍⬛🤍🐈‍⬛</div>
    <div id="heart" class="emoji">❤️</div> <!-- Додаємо червоне серце -->

    <script>
        const texts = [
            "Хелоу котусик🐈‍⬛ ...",
            "Ну що, здогадався, що це і як працює? 😎",
            "Або я все ж таки підстрахуюсь і поясню? 🤔 Короче просто натискай на екран, коли прочитаєш повідомлення) ",
            "Подумки обійняла! 🤗",
            "Отже, все почалося з дня народження Тьоми. 🍰 🎉",
            "Пам'ятаєш, як ти сказав, що такого ще не отримував? ",
            "Я тоді серйозно задумалася, і тепер ось тобі… проєкт від мене, без поспіху!",
            "І без зайвих багів, хоча… може один-два проскочать 😂",
            "Я, звичайно, програмістка та ще та… колись хотіла писати код і бути крутою айтішницею.",
            "Але не склалось! 😆 Якщо щось не працює — вибачай! ",
        ];

        let index = 0;
        const textElement = document.getElementById('text');
        const heartElement = document.getElementById('heart'); // Отримуємо серце

        document.addEventListener('click', () => {
            if (index < texts.length) {
                textElement.innerText = texts[index];
                index++;
            } else {
                textElement.innerText = ""; // Сховати текст
                heartElement.style.display = 'block'; // Показати серце
            }
        });
    </script>
</body>
</html>
