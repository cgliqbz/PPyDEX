# PPyDEX
PPyDex
/subscription_website
  /index.html
  /style.css
  /script.js

<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Перепдекс</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="container">
            <h1>Підпишись на наші новини!</h1>
            <p>Отримуй свіжі новини про наші продукти, акції та оновлення прямо на пошту.</p>
        </div>
    </header>

    <main>
        <div class="subscription-form">
            <h2>Підпишись на наші новини</h2>
            <form id="subscribeForm">
                <input type="email" id="email" placeholder="Введіть ваш email" required>
                <button type="submit">Підписатися</button>
            </form>
            <p id="message"></p>
        </div>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2025 Перпдекс - Всі права захищені</p>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    color: #333;
}

.container {
    width: 80%;
    margin: 0 auto;
    text-align: center;
}

header {
    background-color: #1e90ff;
    color: white;
    padding: 50px 0;
}

h1 {
    font-size: 2.5rem;
    margin-bottom: 10px;
}

p {
    font-size: 1.1rem;
}

main {
    padding: 40px 0;
}

.subscription-form {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    display: inline-block;
}

h2 {
    font-size: 1.8rem;
    margin-bottom: 20px;
}

input[type="email"] {
    padding: 10px;
    font-size: 1rem;
    width: 100%;
    max-width: 300px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

button {
    padding: 10px 20px;
    font-size: 1.1rem;
    background-color: #1e90ff;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
}

button:hover {
    background-color: #4682b4;
}

footer {
    background-color: #1e90ff;
    color: white;
    padding: 20px 0;
}
// Слухач події для форми
document.getElementById('subscribeForm').addEventListener('submit', function(event) {
    event.preventDefault();

    // Отримуємо введену електронну адресу
    const email = document.getElementById('email').value;

    // Перевірка, чи правильно введена адреса
    if (validateEmail(email)) {
        document.getElementById('message').textContent = 'Дякуємо за підписку! Перевірте свою пошту.';
        document.getElementById('message').style.color = 'green';

        // Очистити форму
        document.getElementById('email').value = '';
    } else {
        document.getElementById('message').textContent = 'Будь ласка, введіть правильну електронну адресу.';
        document.getElementById('message').style.color = 'red';
    }
});

// Функція для перевірки правильності електронної адреси
function validateEmail(email) {
    const re = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
    return re.test(email);
}
