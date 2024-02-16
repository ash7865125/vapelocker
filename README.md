# VapeLocker
Welcome to VapeLocker, your premier destination for an unparalleled vaping experience in India! At VapeLocker, we curate a diverse selection of top-notch vapes, ensuring that every puff is a journey into satisfaction. Our commitment to quality, innovation, and safety sets us apart, providing our customers with the confidence to indulge in the latest and finest vaping products. Explore our virtual aisles, where each vape is a testament to craftsmanship and cutting-edge technology. Elevate your vaping lifestyle with VapeLocker – where passion meets performance, and satisfaction is just a click away. Experience the difference and join the VapeLocker community, where excellence is not just a choice but a standard.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VapeLocker - Online Vape Shop</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

<header>
    <h1>VapeLocker</h1>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#products">Products</a></li>
            <li><a href="#cart">Cart</a></li>
        </ul>
    </nav>
</header>

<section id="home">
    <h2>Welcome to VapeLocker - Your Online Vape Shop</h2>
    <p>Explore our wide range of vape products and accessories.</p>
</section>

<section id="products">
    <h2>Our Products</h2>
    <div class="product">
        <img src="vape1.jpg" alt="Vape Product 1">
        <h3>Vape Product 1</h3>
        <p>Description of the product.</p>
        <button onclick="addToCart('Product 1', 29.99)">Add to Cart</button>
    </div>
    <!-- Add more product entries as needed -->
</section>

<section id="cart">
    <h2>Shopping Cart</h2>
    <ul id="cart-items"></ul>
    <p>Total: $<span id="total">0.00</span></p>
    <button onclick="checkout()">Checkout</button>
</section>

<script src="script.js"></script>

</body>
</html>
/* styles.css */
body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: #fff;
    padding: 1rem;
    text-align: center;
}

nav ul {
    list-style-type: none;
}

nav ul li {
    display: inline;
    margin: 0 10px;
}

section {
    padding: 20px;
}

.product {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 20px;
}

button {
    background-color: #333;
    color: #fff;
    padding: 8px 12px;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #555;
}
// script.js
let cartItems = [];
let total = 0;

function addToCart(productName, price) {
    cartItems.push({ productName, price });
    total += price;
    updateCart();
}

function updateCart() {
    const cartList = document.getElementById('cart-items');
    const totalElement = document.getElementById('total');
    cartList.innerHTML = '';
    
    cartItems.forEach(item => {
        const listItem = document.createElement('li');
        listItem.textContent = `${item.productName} - $${item.price.toFixed(2)}`;
        cartList.appendChild(listItem);
    });

    totalElement.textContent = total.toFixed(2);
}

function checkout() {
    // Implement payment processing and order handling here
    alert('Thank you for your purchase!');
    cartItems = [];
    total = 0;
    updateCart();
}

