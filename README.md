# MATRIX-WORLD
Easy to purchase
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple E-Commerce Website</title>
    <style>
        /* CSS Styles for E-commerce website */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: white;
            padding: 10px 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .product-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        .product {
            background: white;
            border: 1px solid #ddd;
            margin: 10px;
            padding: 10px;
            width: 23%;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .product img {
            max-width: 100%;
            height: auto;
        }

        .product h3 {
            margin: 10px 0;
        }

        .product p {
            margin: 5px 0;
        }

        .product button {
            background-color: #28a745;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
        }

        .product button:hover {
            background-color: #218838;
        }

        /* Cart Section */
        .cart {
            background: white;
            padding: 20px;
            margin-top: 20px;
        }

        .cart h2 {
            margin-bottom: 20px;
        }

        .cart ul {
            list-style-type: none;
            padding: 0;
        }

        .cart li {
            margin-bottom: 10px;
            border-bottom: 1px solid #ddd;
            padding-bottom: 10px;
        }

        .cart-total {
            margin-top: 20px;
            font-size: 1.2em;
            font-weight: bold;
        }

        .checkout-btn {
            background-color: #007bff;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
        }

        .checkout-btn:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

<header>
    <h1>MATRIX WORLD</h1>
</header>

<div class="container">

    <!-- Product Listing Section -->
    <section class="product-list" id="product-list">
        <!-- Product 1 -->
        <div class="product">
            <img src="one.png">
          <h3>ONEPLUS</h3>
          <p>Price: ₹50000.00</p>
            <button onclick="addToCart(1, 'Product 1', 50000.00)">Add to Cart</button>
        </div>

        <!-- Product 2 -->
        <div class="product">
            <img src="mi.png" alt="Product 2">
            <h3>XIAOMI</h3>
          <p>Price: ₹40000.00</p>
            <button onclick="addToCart(2, 'Product 2', 40000.00)" >Add to Cart</button>
        </div>

        <!-- Product 3 -->
        <div class="product">
            <img src="real.webp" alt="Product 3">
            <h3>REALME</h3>
          <p>Price: ₹20000.00</p>
            <button onclick="addToCart(3, 'Product 3', 20000.00)">Add to Cart</button>
        </div>

        <!-- Product 4 -->
        <div class="product">
            <img src="vivo.jpg" alt="Product 4">
            <h3>VIVO</h3>
          <p>Price: ₹49999.00</p>
            <button onclick="addToCart(4, 'Product 4', 49999.00)">Add to Cart</button>
        </div>
        <div class="product">
            <img src="sam.webp" alt="WATCH">
            <h3>SAMSUNG</h3>
          <p>Price: ₹89999.00</p>
            <button onclick="addToCart(1, 'Product 1', 89999.00)">Add to Cart</button>
        </div>
  <div class="product">
            <img src="images.jpg" alt="WATCH">
            <h3>IPHONE</h3>
    <p>Price: ₹149000</p>
            <button onclick="addToCart(1, 'Product 1', 149000.00)">Add to Cart</button>
        </div>

    </section>

    <!-- Shopping Cart Section -->
    <section class="cart" id="cart">
        <h2>Your Cart</h2>
        <ul id="cart-items">
            <!-- Cart items will appear here -->
        </ul>
        <div class="cart-total" id="cart-total">Total: ₹0.00</div>
        <button class="checkout-btn" onclick="checkout()">Checkout</button>
    </section>

</div>

<script>
    // JavaScript Code for E-commerce functionality

    // Cart array to store items
    let cart = [];

    // Function to add products to the cart
    function addToCart(id, name, price) {
        // Check if the product is already in the cart
        let productInCart = cart.find(product => product.id === id);

        if (productInCart) {
            productInCart.quantity += 1;
        } else {
            cart.push({ id: id, name: name, price: price, quantity: 1 });
        }

        updateCart();
    }

    // Function to update the cart display
    function updateCart() {
        const cartItemsContainer = document.getElementById('cart-items');
        const cartTotalContainer = document.getElementById('cart-total');

        // Clear the cart items container
        cartItemsContainer.innerHTML = '';

        // Calculate total price
        let total = 0;

        // Add each product in the cart to the display
        cart.forEach(product => {
            let item = document.createElement('li');
            item.textContent = `${product.name} - $${product.price} x ${product.quantity}`;
            cartItemsContainer.appendChild(item);

            total += product.price * product.quantity;
        });

        // Update the total price
        cartTotalContainer.textContent = `Total: $${total.toFixed(2)}`;
    }

    // Function to handle the checkout
    function checkout() {
        if (cart.length === 0) {
            alert("Your cart is empty!");
        } else {
            alert("Thank you for your purchase!");
            cart = []; // Clear the cart
            updateCart();
        }
    }
</script>

</body>
</html>
