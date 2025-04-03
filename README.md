<!DOCTYPE html>
<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Magazin Produse Forestiere</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background: #2c5f2d;
            color: white;
            padding: 15px;
            text-align: center;
        }
        .container {
            width: 80%;
            margin: auto;
            overflow: hidden;
        }
        .category {
            margin-top: 20px;
            padding: 10px;
            background: #d9ead3;
            border-radius: 5px;
        }
        .category h2 {
            text-align: center;
        }
        .product {
            background: white;
            padding: 20px;
            margin: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .product img {
            max-width: 100%;
            height: auto;
        }
        .product button {
            background: #2c5f2d;
            color: white;
            padding: 10px;
            border: none;
            cursor: pointer;
            margin-top: 10px;
        }
        .product button:hover {
            background: #3e7a3a;
        }
        .cart {
            margin-top: 30px;
            padding: 20px;
            background: #fff;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .cart h2 {
            text-align: center;
        }
        .cart-items {
            list-style: none;
            padding: 0;
        }
        .cart-items li {
            padding: 10px;
            border-bottom: 1px solid #ddd;
        }
        .cart-total {
            text-align: center;
            margin-top: 10px;
            font-weight: bold;
        }
    </style>
    <script>
        let cart = [];
        function addToCart(productName, price) {
            cart.push({ name: productName, price: price });
            updateCart();
        }
        function updateCart() {
            const cartList = document.getElementById("cart-items");
            cartList.innerHTML = "";
            let total = 0;
            cart.forEach(item => {
                let li = document.createElement("li");
                li.textContent = `${item.name} - ${item.price} RON`;
                cartList.appendChild(li);
                total += item.price;
            });
            document.getElementById("cart-total").textContent = `Total: ${total} RON`;
        }
    </script>
</head>
<body>
    <header>
        <h1>Magazin Produse Forestiere</h1>
    </header>
    <div class="container">
        <div class="category">
            <h2>Produse din Lemn</h2>
            <div class="product">
                <img src="lemn_de_foc.jpg" alt="Lemn de Foc">
                <h2>Lemn de Foc</h2>
                <p>Pret: 250 RON/mc</p>
                <button onclick="addToCart('Lemn de Foc', 250)">Adaugă în coș</button>
            </div>
            <div class="product">
                <img src="brichete_din_lemn.jpg" alt="Brichete din Lemn">
                <h2>Brichete din Lemn</h2>
                <p>Pret: 500 RON/palet</p>
                <button onclick="addToCart('Brichete din Lemn', 500)">Adaugă în coș</button>
            </div>
            <div class="product">
                <img src="peleti.jpg" alt="Peleti">
                <h2>Peleti</h2>
                <p>Pret: 600 RON/palet</p>
                <button onclick="addToCart('Peleti', 600)">Adaugă în coș</button>
            </div>
        </div>
        <div class="category">
            <h2>Produse din Fructe de Pădure</h2>
            <div class="product">
                <img src="dulceata_afine.jpg" alt="Dulceață de Afine">
                <h2>Dulceață de Afine</h2>
                <p>Pret: 25 RON/borcan</p>
                <button onclick="addToCart('Dulceață de Afine', 25)">Adaugă în coș</button>
            </div>
            <div class="product">
                <img src="sirop_muguri_brad.jpg" alt="Sirop din Muguri de Brad">
                <h2>Sirop din Muguri de Brad</h2>
                <p>Pret: 30 RON/sticlă</p>
                <button onclick="addToCart('Sirop din Muguri de Brad', 30)">Adaugă în coș</button>
            </div>
        </div>
        <div class="category">
            <h2>Ciuperci</h2>
            <div class="product">
                <img src="ciuperci_uscate.jpg" alt="Ciuperci Uscate">
                <h2>Ciuperci Uscate</h2>
                <p>Pret: 80 RON/kg</p>
                <button onclick="addToCart('Ciuperci Uscate', 80)">Adaugă în coș</button>
            </div>
        </div>
        <div class="cart">
            <h2>Coș de Cumpărături</h2>
            <ul id="cart-items" class="cart-items"></ul>
            <p id="cart-total" class="cart-total">Total: 0 RON</p>
        </div>
        <div class="payment-methods">
            <h2>Metode de Plată</h2>
            <p>- Plata cu cardul (Visa, MasterCard)</p>
            <p>- Transfer bancar</p>
            <p>- Ramburs la livrare</p>
            <p>- PayPal</p>
        </div>
    </div>
</body>
</html>
