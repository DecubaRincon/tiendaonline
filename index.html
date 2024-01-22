function generarCupon() {
  var longitud = 8; 
  var caracteres = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
  var cupon = 'r';
  for ( var i = 0; i < longitud; i++ ) {
     cupon += caracteres.charAt(Math.floor(Math.random() * caracteres.length));
  }
  cupon += '10';
  return cupon;
}

const cuponElement = document.getElementById('cupon');
const discountCode = document.getElementById('discountCode');

var modal = document.getElementById('anuncio-modal');

modal.addEventListener('shown.bs.modal', function () {
  var nuevoCupon = generarCupon();

  if (cuponElement) {
    cuponElement.value = nuevoCupon;
  }
});

document.querySelector('#anuncio-modal .btn-primary').addEventListener('click', function() {
  cuponElement.select();
  document.execCommand('copy');

  discountCode.value = cuponElement.value;
});

const headerMenu = document.querySelector('.hm-header');

window.addEventListener('scroll', () => {
  if (window.pageYOffset > 80) {
    headerMenu.classList.add('header-fixed');
  } else {
    headerMenu.classList.remove('header-fixed');
  }
});

if (document.querySelector('.hm-tabs')) {
  const tabLinks = document.querySelectorAll('.hm-tab-link');
  const tabsContent = document.querySelectorAll('.tabs-content');

  tabLinks[0].classList.add('active');

  if (document.querySelector('.tabs-content')) {
    tabsContent[0].classList.add('tab-active');
  }

  for (let i = 0; i < tabLinks.length; i++) {
    tabLinks[i].addEventListener('click', () => {
      tabLinks.forEach((tab) => tab.classList.remove('active'));
      tabLinks[i].classList.add('active');
      tabsContent.forEach((tabCont) => tabCont.classList.remove('tab-active'));
      tabsContent[i].classList.add('tab-active');
    });
  }
}

const menu = document.querySelector('.icon-menu');
const menuClose = document.querySelector('.cerrar-menu');

menu.addEventListener('click', () => {
  document.querySelector('.header-menu-movil').classList.add('active');
});

menuClose.addEventListener('click', () => {
  document.querySelector('.header-menu-movil').classList.remove('active');
});

var icono = document.querySelector(".hm-icon-cart a");

icono.addEventListener("click", function (e) {
  e.preventDefault();
  var modal = document.getElementById("cartModal");
  modal.modal("show");
});

document.addEventListener('DOMContentLoaded', function () {
  let cartItems = JSON.parse(localStorage.getItem('cartItems')) || {};

  const addToCartButtons = document.querySelectorAll('.add-to-cart');

  addToCartButtons.forEach(button => {
    button.addEventListener('click', function (event) {
      event.preventDefault();

      const productCard = this.closest('.product-item');
      const productName = productCard.querySelector('h3').textContent;
      const productImage = productCard.querySelector('.card-img-top').src;
      const productPriceText = productCard.querySelector('.precio span').textContent.trim();

      const productPrice = extractPrice(productPriceText);

      addToCart(productName, productImage, productPrice);
    });
  });

  function extractPrice(priceText) {
    const currencySymbols = ['S/', '$', '€'];
    const priceArray = priceText.split(' ');

    let price = 0;

    for (const item of priceArray) {
      if (!isNaN(parseFloat(item))) {
        price = parseFloat(item);
        break;
      } else {
        for (const symbol of currencySymbols) {
          if (item.includes(symbol)) {
            const number = item.replace(symbol, '');
            price = parseFloat(number);
            break;
          }
        }
      }
    }

    return price;
  }

  function addToCart(productName, productImage, productPrice) {
    if (cartItems[productName]) {
      cartItems[productName].quantity++;
      cartItems[productName].totalPrice = cartItems[productName].quantity * productPrice;
    } else {
      cartItems[productName] = {
        image: productImage,
        quantity: 1,
        price: productPrice,
        totalPrice: productPrice
      };
    }

    localStorage.setItem('cartItems', JSON.stringify(cartItems));
    updateCart();
  }

  function updateCart() {
    const cartList = document.querySelector('.cart-list');
    const cartTotal = document.querySelector('.cart-total');
    cartList.innerHTML = '';

    let grandTotal = 0;

    for (const productName in cartItems) {
      const {
        image,
        quantity,
        price,
        totalPrice
      } = cartItems[productName];

      const li = document.createElement('li');
      li.classList.add('cart-item');
      li.innerHTML = `
                <img src="${image}" alt="${productName}" class="cart-item-image">
                <span class="cart-item-name">${productName}</span>
                <span class="cart-item-quantity">
                    <button class="cart-item-decrease">-</button>
                    ${quantity}
                    <button class="cart-item-increase">+</button>
                </span>
                <span class="cart-item-total-price">$ ${totalPrice.toFixed(2)} us</span>
                <button class="cart-item-remove">X</button>
            `;

      cartList.appendChild(li);

      grandTotal += totalPrice;
    }

    cartTotal.textContent = `Total: $ ${grandTotal.toFixed(2)} us`;

    const cartCounter = document.querySelector('.hm-icon-cart .badge');
    const totalCount = Object.values(cartItems).reduce((acc, item) => acc + item.quantity, 0);
    cartCounter.textContent = totalCount;
  }

  const clearCart = () => {
    cartItems = {};
    localStorage.removeItem('cartItems');
    updateCart();
  };

  const removeProduct = (productName) => {
    delete cartItems[productName];
    localStorage.setItem('cartItems', JSON.stringify(cartItems));
    updateCart();
  };

  const clearCartButton = document.getElementById("clearCart");
  clearCartButton.addEventListener("click", clearCart);

  const cartList = document.querySelector(".cart-list");
  cartList.addEventListener("click", function (event) {
    if (event.target.classList.contains("cart-item-remove")) {
      const productCard = event.target.closest(".cart-item");
      const productName = productCard.querySelector(".cart-item-name").textContent;
      removeProduct(productName);
    } else if (event.target.classList.contains("cart-item-increase")) {
      const productCard = event.target.closest(".cart-item");
      const productName = productCard.querySelector(".cart-item-name").textContent;
      increaseQuantity(productName);
    } else if (event.target.classList.contains("cart-item-decrease")) {
      const productCard = event.target.closest(".cart-item");
      const productName = productCard.querySelector(".cart-item-name").textContent;
      decreaseQuantity(productName);
    }
  });



  const sendToWhatsApp = () => {
    const cartItems = document.querySelectorAll('.cart-item');
    let cartProducts = '';
  
    cartItems.forEach(item => {
      const quantity = item.querySelector('.cart-item-quantity').textContent.trim().split('\n')[1].trim();
      const name = item.querySelector('.cart-item-name').textContent.trim();
      cartProducts += `${quantity} ${name}\n`;
    });
  
    const cartTotal = document.querySelector('.cart-total').textContent.trim().split(':')[1].trim();
  
    const discountCode = document.querySelector('#discountCode').value.trim();
  
    const name = document.querySelector('#name').value.trim();
    const recipient = document.querySelector('#recipient').value.trim();
    const recipientPhone = document.querySelector('#recipient-phone').value.trim();
    const street = document.querySelector('#street').value.trim();
    const between = document.querySelector('#between').value.trim();
    const number = document.querySelector('#number').value.trim();
  
    let message = `Hola desde la Tienda Online Rincon de Cuba,\n`;
    message += `Mi nombre es ${name} y he realizado un pedido de:\n`;
    message += `${cartProducts}`;    
    message += `He usado el cupón de descuento: ${discountCode}.\n`;
    message += `Con un total de: ${cartTotal}.\n`;
    message += `Deseo enviarlo a ${recipient}.\n`;
    message += `Su número de Teléfono es: +${recipientPhone}.\n`;
    message += `Y su dirección es: Calle ${street}, entre ${between}, #${number}.\n`;
    message += `Espero su respuesta... saludos.\n`;
  
    const whatsappLink = `https://api.whatsapp.com/send?phone=5350545976&text=${encodeURIComponent(message)}`;
  
    window.open(whatsappLink, '_blank');
  };
  
  const sendButton = document.querySelector('.btn-primary[type="submit"]');
  sendButton.addEventListener('click', sendToWhatsApp);



  const increaseQuantity = (productName) => {
    cartItems[productName].quantity++;
    cartItems[productName].totalPrice = cartItems[productName].quantity * cartItems[productName].price;
    localStorage.setItem('cartItems', JSON.stringify(cartItems));
    updateCart();
  };

  const decreaseQuantity = (productName) => {
    cartItems[productName].quantity--;
    cartItems[productName].totalPrice = cartItems[productName].quantity * cartItems[productName].price;
    if (cartItems[productName].quantity === 0) {
      delete cartItems[productName];
    }
    localStorage.setItem('cartItems', JSON.stringify(cartItems));
    updateCart();
  };

  updateCart();
});

if(localStorage.getItem('visitCount')) {
  let count = parseInt(localStorage.getItem('visitCount'));
  count++;
  localStorage.setItem('visitCount', count);
  
  if (count > 1) {
    document.getElementById('visit-count').textContent = `¡Bienvenido de nuevo! Nos has visitado ${count} veces. Nos alegra poder ayudarte.`;
  } else {
    document.getElementById('visit-count').textContent = `¡Bienvenido! Esta es tu segunda visita.`;
  }

  if (count == 3) {
    
  } else if (count == 4) {
    var otroModal = new bootstrap.Modal(document.getElementById('anuncio-modalimagen'), {});
    otroModal.show();
  } else if (count == 6) {
    
    var otroModal = new bootstrap.Modal(document.getElementById('anuncio-modalx'), {});
    otroModal.show();
  }
} else {
  localStorage.setItem('visitCount', 1); 
}

function resetCounter() {
  var personalCode = document.getElementById('personalCode').value;
  if(personalCode === predefinedCode) {
    
    localStorage.setItem('visitCount', 0);
    alert("El contador de la página se ha reiniciado.");
    
    location.reload();
  } else {
    alert("El código personal ingresado no es correcto.");
  }
}

var elementos = document.querySelectorAll(".add-to-modal");

elementos.forEach(function(elemento) {
  elemento.addEventListener("click", function(evento) {
    
    evento.preventDefault();
    
    var imagen = elemento.querySelector("img");
    
    var src = imagen.getAttribute("src");
    
    var modal = document.getElementById("product-modal");
    
    var modalImagen = document.getElementById("product-modal-image");
    
    modalImagen.setAttribute("src", src);
    
    $(modal).modal("show");
  });
});

// Función para compartir producto
function shareProduct(event) {

  event.preventDefault();
  
  // Obtener datos del producto
  const name = document.querySelector('.p-info h3').innerText;
  const image = document.querySelector('.p-portada img').src;
  const price = document.querySelector('.precio span').innerText;

  // Construir mensaje
  const shareMessage = `${name}\nPrecio: ${price}\n¡Visita la tienda para comprarlo!`;
  
  // URLs para compartir
  const waURL = `https://wa.me/?text=${encodeURIComponent(shareMessage)}`;
  const fbURL = `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(image)}&quote=${encodeURIComponent(shareMessage)}`;  
  const twURL = `https://twitter.com/intent/tweet?text=${encodeURIComponent(shareMessage)}`;

  // Abrir ventana para elegir
  window.open(`
    <a href="${waURL}" target="_blank">Compartir por WhatsApp</a>
    <a href="${fbURL}" target="_blank">Compartir por Facebook</a>
    <a href="${twURL}" target="_blank">Compartir por Twitter</a>`
  );

}

// Añadir listener al botón de compartir
document.querySelector('.bi-share').addEventListener('click', shareProduct);

AOS.init({
  duration: 1200
})

document.getElementById('reset-button').addEventListener('click', function() {

  localStorage.setItem('visitCount', 0);
  
  alert("El contador de la página se ha reiniciado.");
  
  location.reload();

});
