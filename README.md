# pizzeriaWeb
progetto di gruppo A-B-C
ogni sviluppatore deve aggiungere due portate nel proprio menù:
-sviluppatore a: assegnato al menù pizze
-sviluppatore b: assegnato al menù dolci
-sviluppatore c: assegnato al menù bevande
pizzeriaWeb/
│
├── index.html
├── style.css
├── script.js
│
└── README.md

<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Scopri il menù della nostra pizzeria: pizze artigianali, dolci e bevande.">
    <title>La Bella Pizza | Pizzeria Artigianale</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js" defer></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@600;700;800&display=swap" rel="stylesheet">
</head>
<body>

    <header class="header">
        <a href="#home" class="logo">
            <span class="logo-icon">🍕</span>
            La Bella <span>Pizza</span>
        </a>

        <nav class="navbar">
            <a href="#home">Home</a>
            <a href="#pizze">Pizze</a>
            <a href="#dolci">Dolci</a>
            <a href="#bevande">Bevande</a>
        </nav>

        <a href="#carrello" class="cart-button">
            🛒 Carrello <span id="cart-count">0</span>
        </a>
    </header>

    <main>
        <section class="hero" id="home">
            <div class="hero-content">
                <span class="eyebrow">🍅 TRADIZIONE E PASSIONE</span>
                <h1>La vera pizza,<br>fatta con <span>amore.</span></h1>
                <p>
                    Ingredienti freschi, impasto a lunga lievitazione
                    e tutto il gusto della tradizione italiana.
                </p>
                <a href="#pizze" class="primary-button">Scopri il menù ↓</a>

                <div class="hero-details">
                    <div>
                        <strong>48h</strong>
                        <span>di lievitazione</span>
                    </div>
                    <div>
                        <strong>100%</strong>
                        <span>ingredienti selezionati</span>
                    </div>
                </div>
            </div>

            <div class="hero-image">
                <img
                    src="https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=1000&q=85"
                    alt="Pizza artigianale appena sfornata">
                <div class="image-label">
                    <span>★ ★ ★ ★ ★</span>
                    <p>Il gusto della tradizione</p>
                </div>
            </div>
        </section>

        <section class="menu-section" id="pizze">
            <div class="section-heading">
                <span class="eyebrow">IL NOSTRO MENÙ</span>
                <h2>Le nostre <span>pizze</span></h2>
                <p>Realizzate al momento, con ingredienti di qualità.</p>
            </div>
            <div class="menu-grid" id="pizza-list"></div>
        </section>

        <section class="menu-section alternate" id="dolci">
            <div class="section-heading">
                <span class="eyebrow">UNA DOLCE CONCLUSIONE</span>
                <h2>Dolci <span>tentazioni</span></h2>
                <p>Il piacere di concludere in bellezza.</p>
            </div>
            <div class="menu-grid" id="dessert-list"></div>
        </section>

        <section class="menu-section" id="bevande">
            <div class="section-heading">
                <span class="eyebrow">PER ACCOMPAGNARE</span>
                <h2>Le nostre <span>bevande</span></h2>
                <p>La bevanda perfetta per ogni occasione.</p>
            </div>
            <div class="menu-grid" id="drink-list"></div>
        </section>

        <section class="cart-section" id="carrello">
            <div class="cart-panel">
                <div>
                    <span class="eyebrow">IL TUO ORDINE</span>
                    <h2>Il tuo <span>carrello</span></h2>
                    <p>Aggiungi le tue specialità preferite dal menù.</p>
                </div>

                <div id="cart-items">
                    <p class="empty-cart">Il carrello è vuoto. È ora di scegliere! 🍕</p>
                </div>

                <div class="cart-total">
                    <span>Totale ordine</span>
                    <strong id="cart-total">€ 0,00</strong>
                </div>

                <button class="primary-button checkout-button" id="checkout-button">
                    Procedi con l'ordine →
                </button>
                <p class="cart-note">
                    Demo scolastica: il pagamento e l'invio dell'ordine
                    non sono collegati a un servizio reale.
                </p>
            </div>
        </section>
    </main>

    <footer class="footer">
        <a href="#home" class="logo">🍕 La Bella <span>Pizza</span></a>
        <p>Fatto con passione, servito con amore.</p>
        <p class="copyright">
            © <span id="current-year"></span> La Bella Pizza · Progetto pizzeriaWeb A-B-C
        </p>
    </footer>

</body>
</html>

:root {
    --red: #c63d2f;
    --red-dark: #a92f24;
    --cream: #fffaf2;
    --paper: #ffffff;
    --dark: #29251f;
    --muted: #777168;
    --green: #355c42;
    --border: #eee5d9;
    --shadow: 0 12px 35px rgba(54, 39, 25, 0.08);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
    scroll-padding-top: 90px;
}

body {
    font-family: "DM Sans", sans-serif;
    background: var(--cream);
    color: var(--dark);
    line-height: 1.6;
}

a {
    color: inherit;
    text-decoration: none;
}

button {
    font: inherit;
}

.header {
    position: sticky;
    top: 0;
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
    padding: 17px 7%;
    background: rgba(255, 250, 242, 0.96);
    border-bottom: 1px solid var(--border);
    backdrop-filter: blur(12px);
}

.logo {
    display: flex;
    align-items: center;
    gap: 7px;
    font-family: "Playfair Display", serif;
    font-size: 23px;
    font-weight: 800;
    white-space: nowrap;
}

.logo > span:last-child,
.logo span:not(.logo-icon) {
    color: var(--red);
}

.logo-icon {
    font-size: 26px;
}

.navbar {
    display: flex;
    gap: 28px;
}

.navbar a {
    font-size: 14px;
    font-weight: 600;
    transition: color 0.2s;
}

.navbar a:hover {
    color: var(--red);
}

.cart-button {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 15px;
    border: 1px solid var(--border);
    border-radius: 30px;
    background: white;
    font-size: 13px;
    font-weight: 700;
    white-space: nowrap;
}

#cart-count {
    display: grid;
    place-items: center;
    width: 23px;
    height: 23px;
    border-radius: 50%;
    background: var(--red);
    color: white;
}

.hero {
    display: grid;
    grid-template-columns: 1fr 0.9fr;
    align-items: center;
    gap: 65px;
    padding: 75px 9% 90px;
    overflow: hidden;
}

.hero-content {
    max-width: 570px;
}

.eyebrow {
    display: inline-block;
    margin-bottom: 17px;
    color: var(--red);
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 2px;
}

.hero h1,
.section-heading h2,
.cart-panel h2 {
    font-family: "Playfair Display", serif;
    font-weight: 800;
    line-height: 1.12;
}

.hero h1 {
    margin-bottom: 22px;
    font-size: clamp(42px, 5.2vw, 70px);
    letter-spacing: -2px;
}

.hero h1 span,
.section-heading h2 span,
.cart-panel h2 span {
    color: var(--red);
}

.hero-content > p {
    max-width: 440px;
    margin-bottom: 28px;
    color: var(--muted);
    font-size: 16px;
}

.primary-button {
    display: inline-block;
    padding: 14px 23px;
    border: none;
    border-radius: 7px;
    background: var(--red);
    color: white;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    transition: background 0.2s, transform 0.2s;
}

.primary-button:hover {
    background: var(--red-dark);
    transform: translateY(-2px);
}

.hero-details {
    display: flex;
    gap: 35px;
    margin-top: 43px;
}

.hero-details div {
    display: flex;
    flex-direction: column;
}

.hero-details strong {
    font-family: "Playfair Display", serif;
    font-size: 25px;
}

.hero-details span {
    color: var(--muted);
    font-size: 12px;
}

.hero-image {
    position: relative;
}

.hero-image img {
    display: block;
    width: 100%;
    height: 420px;
    object-fit: cover;
    border-radius: 48% 48% 12px 12px;
    box-shadow: var(--shadow);
}

.image-label {
    position: absolute;
    right: -20px;
    bottom: 22px;
    padding: 16px 22px;
    border-radius: 10px;
    background: white;
    box-shadow: var(--shadow);
}

.image-label span {
    color: #dba632;
    font-size: 13px;
}

.image-label p {
    font-family: "Playfair Display", serif;
    font-size: 14px;
    font-weight: 700;
}

.menu-section {
    padding: 85px 8%;
}

.alternate {
    background: #f5eee3;
}

.section-heading {
    margin-bottom: 38px;
    text-align: center;
}

.section-heading .eyebrow {
    margin-bottom: 10px;
}

.section-heading h2,
.cart-panel h2 {
    margin-bottom: 12px;
    font-size: clamp(32px, 4vw, 45px);
}

.section-heading > p,
.cart-panel > div:first-child > p {
    color: var(--muted);
    font-size: 14px;
}

.menu-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 25px;
    max-width: 1150px;
    margin: 0 auto;
}

.menu-card {
    overflow: hidden;
    border: 1px solid var(--border);
    border-radius: 12px;
    background: white;
    transition: transform 0.25s, box-shadow 0.25s;
}

.menu-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow);
}

.product-image {
    display: grid;
    place-items: center;
    height: 190px;
    overflow: hidden;
    background: #f4eadb;
}

.product-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.4s;
}

.menu-card:hover .product-image img {
    transform: scale(1.05);
}

.product-emoji {
    font-size: 76px;
}

.product-info {
    padding: 20px;
}

.product-info h3 {
    margin-bottom: 7px;
    font-family: "Playfair Display", serif;
    font-size: 21px;
}

.product-info p {
    min-height: 45px;
    color: var(--muted);
    font-size: 13px;
}

.product-bottom {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 12px;
    margin-top: 19px;
}

.product-price {
    color: var(--red);
    font-size: 19px;
    font-weight: 800;
}

.add-button {
    padding: 9px 12px;
    border: 0;
    border-radius: 6px;
    background: var(--green);
    color: white;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
}

.add-button:hover {
    background: #244630;
}

.cart-section {
    padding: 85px 8%;
}

.cart-panel {
    max-width: 800px;
    margin: 0 auto;
    padding: 38px;
    border: 1px solid var(--border);
    border-radius: 14px;
    background: white;
    box-shadow: var(--shadow);
}

.cart-panel h2 {
    font-size: 37px;
}

#cart-items {
    margin-top: 28px;
}

.empty-cart {
    padding: 25px 10px;
    color: var(--muted);
    text-align: center;
}

.cart-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 15px;
    padding: 15px 0;
    border-bottom: 1px solid var(--border);
}

.cart-item-info strong {
    display: block;
    font-size: 14px;
}

.cart-item-info span {
    color: var(--muted);
    font-size: 12px;
}

.cart-controls {
    display: flex;
    align-items: center;
    gap: 10px;
}

.quantity-button,
.remove-button {
    display: grid;
    place-items: center;
    width: 30px;
    height: 30px;
    border: 1px solid var(--border);
    border-radius: 6px;
    background: white;
    cursor: pointer;
}

.remove-button {
    color: var(--red);
}

.cart-total {
    display: flex;
    justify-content: space-between;
    margin-top: 25px;
    padding-top: 20px;
    border-top: 2px solid var(--border);
}

.cart-total strong {
    color: var(--red);
    font-size: 23px;
}

.checkout-button {
    width: 100%;
    margin-top: 25px;
}

.cart-note {
    margin-top: 13px;
    color: var(--muted);
    font-size: 11px;
    text-align: center;
}

.footer {
    padding: 40px 7%;
    background: #29251f;
    color: white;
    text-align: center;
}

.footer .logo {
    justify-content: center;
    margin-bottom: 12px;
}

.footer p {
    color: #c5bdb2;
    font-size: 13px;
}

.footer .copyright {
    margin-top: 22px;
    padding-top: 18px;
    border-top: 1px solid #484138;
    font-size: 11px;
}

@media (max-width: 900px) {
    .header {
        flex-wrap: wrap;
        justify-content: space-between;
        padding: 15px 5%;
    }

    .navbar {
        order: 3;
        justify-content: center;
        width: 100%;
        gap: 24px;
    }

    .hero {
        gap: 35px;
        padding: 55px 6%;
    }

    .hero-image img {
        height: 340px;
    }

    .menu-section,
    .cart-section {
        padding: 65px 5%;
    }

    .menu-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }
}

@media (max-width: 600px) {
    .logo {
        font-size: 20px;
    }

    .cart-button {
        padding: 8px 10px;
        font-size: 12px;
    }

    .navbar {
        gap: 19px;
    }

    .navbar a {
        font-size: 12px;
    }

    .hero {
        grid-template-columns: 1fr;
        padding: 45px 6%;
    }

    .hero h1 {
        font-size: 47px;
    }

    .hero-image {
        margin: 0 12px 10px 0;
    }

    .hero-image img {
        height: 300px;
    }

    .image-label {
        right: -10px;
    }

    .hero-details {
        gap: 25px;
    }

    .menu-grid {
        grid-template-columns: 1fr;
        max-width: 390px;
    }

    .product-image {
        height: 220px;
    }

    .cart-panel {
        padding: 24px 17px;
    }

    .cart-panel h2 {
        font-size: 32px;
    }

    .cart-controls {
        gap: 6px;
    }
}

"use strict";

// ==================================================
// SVILUPPATORE A — MENU PIZZE
// Modificare questa sezione per aggiungere le pizze.
// ==================================================

const pizzas = [
    {
        id: "pizza-margherita",
        name: "Margherita",
        description: "Pomodoro San Marzano, mozzarella e basilico fresco.",
        price: 6.50,
        emoji: "🍕",
        image: "https://images.unsplash.com/photo-1579751626657-72bc17010498?auto=format&fit=crop&w=700&q=80"
    },
    {
        id: "pizza-diavola",
        name: "Diavola",
        description: "Pomodoro, mozzarella e salame piccante.",
        price: 8.50,
        emoji: "🍕",
        image: "https://images.unsplash.com/photo-1571407970349-bc81e7e96d47?auto=format&fit=crop&w=700&q=80"
    },
    {
        id: "pizza-quattro-formaggi",
        name: "Quattro Formaggi",
        description: "Un mix cremoso di quattro formaggi selezionati.",
        price: 9.00,
        emoji: "🧀",
        image: "https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=700&q=80"
    },
    {
        id: "pizza-capricciosa",
        name: "Capricciosa",
        description: "Pomodoro, mozzarella, funghi, carciofi e prosciutto.",
        price: 9.50,
        emoji: "🍕"
    },
    {
        id: "pizza-vegetariana",
        name: "Vegetariana",
        description: "Verdure di stagione, mozzarella e pomodoro.",
        price: 8.50,
        emoji: "🥦"
    }
];


// ==================================================
// SVILUPPATORE B — MENU DOLCI
// Modificare questa sezione per aggiungere i dolci.
// ==================================================

const desserts = [
    {
        id: "dolce-tiramisu",
        name: "Tiramisù",
        description: "Crema al mascarpone, caffè e cacao.",
        price: 5.00,
        emoji: "🍰"
    },
    {
        id: "dolce-cheesecake",
        name: "Cheesecake",
        description: "Cheesecake cremosa con salsa ai frutti di bosco.",
        price: 5.50,
        emoji: "🍓"
    },
    {
        id: "dolce-panna-cotta",
        name: "Panna Cotta",
        description: "Delicata panna cotta con caramello.",
        price: 4.50,
        emoji: "🍮"
    },
    {
        id: "dolce-brownie",
        name: "Brownie",
        description: "Tortino al cioccolato dal cuore morbido.",
        price: 5.00,
        emoji: "🍫"
    }
];


// ==================================================
// SVILUPPATORE C — MENU BEVANDE
// Modificare questa sezione per aggiungere bevande.
// ==================================================

const drinks = [
    {
        id: "bevanda-acqua",
        name: "Acqua Minerale",
        description: "Acqua naturale o frizzante, 0,5 L.",
        price: 1.50,
        emoji: "💧"
    },
    {
        id: "bevanda-cola",
        name: "Cola",
        description: "Bibita fresca in lattina da 330 ml.",
        price: 2.50,
        emoji: "🥤"
    },
    {
        id: "bevanda-aranciata",
        name: "Aranciata",
        description: "Bibita all'arancia, 330 ml.",
        price: 2.50,
        emoji: "🍊"
    },
    {
        id: "bevanda-birra",
        name: "Birra Analcolica",
        description: "Birra analcolica fresca, 330 ml.",
        price: 3.50,
        emoji: "🍺"
    }
];


// ==================================================
// LOGICA GENERALE — CARRELLO E VISUALIZZAZIONE
// ==================================================

const allProducts = [...pizzas, ...desserts, ...drinks];
const cart = new Map();

const euro = new Intl.NumberFormat("it-IT", {
    style: "currency",
    currency: "EUR"
});

function formatPrice(price) {
    return euro.format(price);
}

function renderMenu(products, containerId) {
    const container = document.getElementById(containerId);

    container.innerHTML = products.map(product => {
        const image = product.image
            ? `<img src="${product.image}" alt="${product.name}" loading="lazy">`
            : `<span class="product-emoji" role="img" aria-label="${product.name}">${product.emoji}</span>`;

        return `
            <article class="menu-card">
                <div class="product-image">
                    ${image}
                </div>

                <div class="product-info">
                    <h3>${product.name}</h3>
                    <p>${product.description}</p>

                    <div class="product-bottom">
                        <span class="product-price">
                            ${formatPrice(product.price)}
                        </span>

                        <button
                            class="add-button"
                            type="button"
                            data-add="${product.id}"
                            aria-label="Aggiungi ${product.name} al carrello">
                            + Aggiungi
                        </button>
                    </div>
                </div>
            </article>
        `;
    }).join("");
}

function addToCart(productId) {
    const product = allProducts.find(item => item.id === productId);

    if (!product) return;

    const current = cart.get(productId);

    if (current) {
        current.quantity += 1;
    } else {
        cart.set(productId, {
            product,
            quantity: 1
        });
    }

    renderCart();
}

function changeQuantity(productId, amount) {
    const item = cart.get(productId);

    if (!item) return;

    item.quantity += amount;

    if (item.quantity <= 0) {
        cart.delete(productId);
    }

    renderCart();
}

function removeFromCart(productId) {
    cart.delete(productId);
    renderCart();
}

function renderCart() {
    const container = document.getElementById("cart-items");
    const countElement = document.getElementById("cart-count");
    const totalElement = document.getElementById("cart-total");

    let totalQuantity = 0;
    let totalPrice = 0;

    cart.forEach(item => {
        totalQuantity += item.quantity;
        totalPrice += item.product.price * item.quantity;
    });

    countElement.textContent = totalQuantity;
    totalElement.textContent = formatPrice(totalPrice);

    if (cart.size === 0) {
        container.innerHTML = `
            <p class="empty-cart">
                Il carrello è vuoto. È ora di scegliere! 🍕
            </p>
        `;
        return;
    }

    container.innerHTML = [...cart.entries()].map(([id, item]) => `
        <div class="cart-item">
            <div class="cart-item-info">
                <strong>${item.product.name}</strong>
                <span>
                    ${formatPrice(item.product.price)} × ${item.quantity}
                    = ${formatPrice(item.product.price * item.quantity)}
                </span>
            </div>

            <div class="cart-controls">
                <button class="quantity-button"
                    type="button"
                    data-minus="${id}"
                    aria-label="Riduci quantità di ${item.product.name}">−</button>

                <span>${item.quantity}</span>

                <button class="quantity-button"
                    type="button"
                    data-plus="${id}"
                    aria-label="Aumenta quantità di ${item.product.name}">+</button>

                <button class="remove-button"
                    type="button"
                    data-remove="${id}"
                    aria-label="Rimuovi ${item.product.name}">✕</button>
            </div>
        </div>
    `).join("");
}


// Event delegation: gestisce tutti i pulsanti dei prodotti
// e del carrello senza creare un listener per ogni scheda.

document.addEventListener("click", event => {
    const button = event.target.closest("button");

    if (!button) return;

    if (button.dataset.add) {
        addToCart(button.dataset.add);
    } else if (button.dataset.plus) {
        changeQuantity(button.dataset.plus, 1);
    } else if (button.dataset.minus) {
        changeQuantity(button.dataset.minus, -1);
    } else if (button.dataset.remove) {
        removeFromCart(button.dataset.remove);
    }
});

document.getElementById("checkout-button").addEventListener("click", () => {
    if (cart.size === 0) {
        alert("Il carrello è vuoto! Aggiungi almeno un prodotto.");
        return;
    }

    alert(
        "Ordine dimostrativo pronto!\n" +
        "Totale: " + document.getElementById("cart-total").textContent +
        "\n\nQuesta versione non invia ordini reali."
    );
});

document.getElementById("current-year").textContent =
    new Date().getFullYear();

renderMenu(pizzas, "pizza-list");
renderMenu(desserts, "dessert-list");
renderMenu(drinks, "drink-list");
renderCart();

# 🍕 pizzeriaWeb — La Bella Pizza

Progetto di gruppo A-B-C: sito web per una pizzeria artigianale.

## Tecnologie
- HTML5
- CSS3
- JavaScript vanilla

## Funzionalità
- Homepage responsive
- Menù diviso in pizze, dolci e bevande
- Schede con descrizione e prezzo
- Carrello interattivo con quantità e totale
- Layout per smartphone, tablet e computer

## Divisione del lavoro

### Sviluppatore A — Menù pizze
Responsabile dell'array `pizzas` in `script.js`.

### Sviluppatore B — Menù dolci
Responsabile dell'array `desserts` in `script.js`.

### Sviluppatore C — Menù bevande
Responsabile dell'array `drinks` in `script.js`.

## Avvio
Aprire `index.html` nel browser oppure utilizzare
l'estensione Live Server di Visual Studio Code.

Le immagini remote richiedono una connessione Internet.

## Nota
Il carrello è dimostrativo. Non sono implementati pagamenti,
invio degli ordini, autenticazione o database.
