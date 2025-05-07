LOJA DE MAQUIAGEM 

HTML

<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Loja de Maquiagem</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <header>
        <div class="logo">
            <h1>Loja de Maquiagem</h1>
        </div>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Produtos</a></li>
                <li><a href="#">Contato</a></li>
                <li><a href="#" id="cart-icon">Carrinho (<span id="cart-count">0</span>)</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="product-list">
            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Produto 1">
                <h3>Base Líquida</h3>
                <p>R$ 89,99</p>
                <button class="add-to-cart" data-product="Base Líquida" data-price="89.99">Adicionar ao Carrinho</button>
            </div>

            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Produto 2">
                <h3>Máscara de Cílios</h3>
                <p>R$ 49,99</p>
                <button class="add-to-cart" data-product="Máscara de Cílios" data-price="49.99">Adicionar ao Carrinho</button>
            </div>

            <div class="product-card">
                <img src="https://via.placeholder.com/150" alt="Produto 3">
                <h3>Sombra Compacta</h3>
                <p>R$ 39,99</p>
                <button class="add-to-cart" data-product="Sombra Compacta" data-price="39.99">Adicionar ao Carrinho</button>
            </div>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Loja de Maquiagem. Todos os direitos reservados.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>

CSS

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f9f9f9;
}

header {
    background-color: #d6638e;
    padding: 20px;
    text-align: center;
    color: white;
}

header nav ul {
    list-style: none;
    padding: 0;
}

header nav ul li {
    display: inline;
    margin: 0 15px;
}

header nav ul li a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

.product-list {
    display: flex;
    justify-content: center;
    margin: 20px 0;
}

.product-card {
    background-color: white;
    padding: 20px;
    margin: 10px;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    text-align: center;
    width: 200px;
}

.product-card img {
    width: 100%;
    height: auto;
    border-radius: 5px;
}

.product-card h3 {
    margin: 10px 0;
}

.product-card p {
    color: #d6638e;
    font-weight: bold;
}

button {
    background-color: #d6638e;
    color: white;
    border: none;
    padding: 10px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #a53c6d;
}

footer {
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
}

JAVASCRIPT

let cart = [];
const cartIcon = document.getElementById("cart-icon");
const cartCount = document.getElementById("cart-count");

// Função para adicionar produtos ao carrinho
document.querySelectorAll(".add-to-cart").forEach(button => {
    button.addEventListener("click", function() {
        const product = this.getAttribute("data-product");
        const price = parseFloat(this.getAttribute("data-price"));
        
        // Adicionando o produto ao carrinho
        cart.push({ product, price });
        
        // Atualizando o ícone do carrinho
        cartCount.textContent = cart.length;
    });
});
