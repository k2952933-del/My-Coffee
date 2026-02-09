# My-Coffee
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coffee Quick — Заказ и Доставка</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://api-maps.yandex.ru/2.1/?apikey=bcb019e3-0015-44f2-abf1-e8bcfce3cc49&lang=ru_RU" type="text/javascript"></script>
</head>
<body>
    <button class="theme-toggle" id="themeBtn">🌙</button>

    <nav class="navbar">
        <div class="container nav-content">
            <div class="logo">☕ Coffee<span>Quick</span></div>
            <div class="cart-btn" id="openCart">
                🛒 Корзина (<span id="cartCount">0</span>)
            </div>
        </div>
    </nav>

    <div class="container">
        <section class="hero">
            <div class="info">
                <h1>Быстрый кофе <br> в твоем районе</h1>
                <p>Укажите адрес на карте или воспользуйтесь кнопкой автоопределения.</p>
                
                <div class="address-box" style="margin-top: 20px; display: flex; flex-direction: column; gap: 10px;">
                    <button id="findMe" class="location-btn" type="button">📍 Найти меня</button>
                    <input type="text" id="addressInput" placeholder="Ваш адрес появится здесь" readonly>
                </div>
            </div>
            
            <div id="map"></div>
        </section>

        <div id="coffeeList" class="coffee-list-container">
    <p style="text-align: center; color: #888;">Выберите место на карте, чтобы увидеть кофейни рядом</p>
</div>

        <main class="grid">
    <div class="item-card" data-base="180">
    <img src="https://images.unsplash.com/photo-1570968915860-54d5c301fa9f?q=80&w=500&auto=format&fit=crop" alt="Латте">
    <h3>Латте Классик</h3>
        <div class="options">
            <select class="size">
                <option value="0">250 мл</option>
                <option value="60">350 мл (+60₽)</option>
                <option value="110">450 мл (+110₽)</option>
            </select>
        </div>
        <div class="price-display">180 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

    <div class="item-card" data-base="160">
        <img src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?w=400" alt="Капучино">
        <h3>Капучино</h3>
        <div class="options">
            <select class="size">
                <option value="0">200 мл</option>
                <option value="50">300 мл (+50₽)</option>
                <option value="90">400 мл (+90₽)</option>
            </select>
        </div>
        <div class="price-display">160 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

    <div class="item-card" data-base="220">
        <img src="https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?w=400" alt="Раф">
        <h3>Раф Кофе</h3>
        <div class="options">
            <select class="size">
                <option value="0">Ванильный (стандарт)</option>
                <option value="30">Цитрусовый (+30₽)</option>
                <option value="30">Лавандовый (+30₽)</option>
            </select>
        </div>
        <div class="price-display">220 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

    <div class="item-card" data-base="120">
    <img src="https://images.pexels.com/photos/302899/pexels-photo-302899.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Американо">
    <h3>Американо</h3>
    <div class="options">
        <select class="size">
            <option value="0">180 мл</option>
            <option value="40">300 мл (+40₽)</option>
        </select>
    </div>
    <div class="price-display">120 ₽</div>
    <button class="add-to-cart-btn">В корзину</button>
</div>

    <div class="item-card" data-base="200">
        <img src="https://images.unsplash.com/photo-1542990253-0d0f5be5f0ed?w=500" alt="Горячий шоколад">
        <h3>Горячий шоколад</h3>
        <div class="options">
            <select class="size">
                <option value="0">Классический</option>
                <option value="40">С маршмэллоу (+40₽)</option>
            </select>
        </div>
        <div class="price-display">200 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

    <div class="item-card" data-base="150">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/45/A_small_cup_of_coffee.JPG/500px-A_small_cup_of_coffee.JPG" alt="Фильтр-кофе">
    <h3>Фильтр-кофе</h3>
    <div class="options">
        <select class="size">
            <option value="0">250 мл</option>
            <option value="50">350 мл (+50₽)</option>
        </select>
    </div>
    <div class="price-display">150 ₽</div>
    <button class="add-to-cart-btn">В корзину</button>
    </div>
    <div class="item-card" data-base="100">
        <img src="https://images.unsplash.com/photo-1510707577719-ae7c14805e3a?w=500" alt="Эспрессо">
        <h3>Эспрессо</h3>
        <div class="options">
            <select class="size">
                <option value="0">Одинарный</option>
                <option value="50">Двойной (+50₽)</option>
            </select>
        </div>
        <div class="price-display">100 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

<div class="item-card" data-base="190">
        <img src="https://images.unsplash.com/photo-1599398054066-846f28917f38?w=500" alt="Флэт Уайт">
        <h3>Флэт Уайт</h3>
        <div class="options">
            <select class="size">
                <option value="0">Стандарт (190 мл)</option>
                <option value="60">На альтернативном молоке (+60₽)</option>
            </select>
        </div>
        <div class="price-display">190 ₽</div>
        <button class="add-to-cart-btn">В корзину</button>
    </div>

</div>
</main>

    <div class="modal" id="cartModal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Ваш заказ</h2>
            <div class="cart-list" id="cartItems">
                </div>
            <div class="total-line">Итого: <span id="finalPrice">0</span> ₽</div>
            
            <form id="checkoutForm">
                <input type="tel" id="userPhone" placeholder="Ваш телефон" required>
                <select id="payment">
                    <option value="Картой">Картой в приложении</option>
                    <option value="Наличными">Наличными курьеру</option>
                </select>
                <button type="submit" class="confirm-btn">Оформить заказ</button>
            </form>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
