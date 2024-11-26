let cart = [];

function addToCart(productId) {
    const productElement = document.querySelector(`.product[data-id='${productId}']`);
    const productName = productElement.dataset.name;
    const productPrice = parseFloat(productElement.dataset.price);

    // Verifica se o produto já está no carrinho
    const existingProductIndex = cart.findIndex(item => item.name === productName);
    
    if (existingProductIndex > -1) {
        // Se o produto já estiver no carrinho, aumenta a quantidade
        cart[existingProductIndex].quantity += 1;
    } else {
        // Se o produto não estiver no carrinho, adiciona ele com quantidade 1
        cart.push({ name: productName, price: productPrice, quantity: 1 });
    }

    updateCart();
}

function updateCart() {
    const cartItemsContainer = document.getElementById('cart-items');
    const cartTotal = document.getElementById('cart-total');
    cartItemsContainer.innerHTML = '';
    
    let totalPrice = 0;
    
    cart.forEach(item => {
        const itemElement = document.createElement('p');
        itemElement.textContent = `${item.name} x${item.quantity} - R$ ${(item.price * item.quantity).toFixed(2)}`;
        cartItemsContainer.appendChild(itemElement);
        totalPrice += item.price * item.quantity;
    });

    cartTotal.textContent = `Total: R$ ${totalPrice.toFixed(2)}`;
}

function checkout() {
    alert('Compra finalizada! Em breve você receberá as instruções de pagamento.');
    cart = [];  // Limpa o carrinho após a compra
    updateCart();  // Atualiza a visualização do carrinho
}
