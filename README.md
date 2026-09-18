<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>AURA — Premium Clothing</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #f7f5f0;
      color: #111;
    }

    /* ================= NAVBAR ================= */

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;

      display: flex;
      justify-content: space-between;
      align-items: center;

      padding: 22px 7%;
      background: rgba(247,245,240,0.92);
      backdrop-filter: blur(15px);

      border-bottom: 1px solid rgba(0,0,0,0.08);
    }

    .logo {
      font-size: 28px;
      font-weight: 800;
      letter-spacing: 8px;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 35px;
    }

    nav ul li a {
      text-decoration: none;
      color: #111;
      font-size: 13px;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .nav-icons {
      display: flex;
      gap: 20px;
      font-size: 20px;
      cursor: pointer;
    }

    .menu {
      display: none;
      font-size: 25px;
      cursor: pointer;
    }

    /* ================= HERO ================= */

    .hero {
      height: 100vh;
      min-height: 650px;

      display: flex;
      align-items: center;

      padding: 0 7%;

      background:
        linear-gradient(
          90deg,
          rgba(0,0,0,0.65),
          rgba(0,0,0,0.15)
        ),
        url("https://images.unsplash.com/photo-1496747611176-843222e1e57c?auto=format&fit=crop&w=2000&q=90");

      background-size: cover;
      background-position: center;
      color: white;
    }

    .hero-content {
      max-width: 650px;
    }

    .hero-content p {
      font-size: 13px;
      letter-spacing: 5px;
      margin-bottom: 20px;
    }

    .hero-content h1 {
      font-size: clamp(60px, 9vw, 130px);
      line-height: 0.9;
      letter-spacing: -5px;
      margin-bottom: 30px;
    }

    .hero-content span {
      font-family: Georgia, serif;
      font-style: italic;
    }

    .hero-content button {
      padding: 17px 35px;
      border: none;
      background: white;
      color: #111;
      cursor: pointer;
      font-weight: bold;
      letter-spacing: 2px;
      transition: 0.3s;
    }

    .hero-content button:hover {
      background: #111;
      color: white;
    }

    /* ================= SECTION ================= */

    section {
      padding: 100px 7%;
    }

    .section-title {
      display: flex;
      justify-content: space-between;
      align-items: end;
      margin-bottom: 45px;
    }

    .section-title h2 {
      font-size: 45px;
      letter-spacing: -2px;
    }

    .section-title p {
      color: #777;
      font-size: 14px;
    }

    /* ================= CATEGORIES ================= */

    .categories {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .category {
      height: 500px;
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }

    .category img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.6s;
    }

    .category:hover img {
      transform: scale(1.08);
    }

    .category-overlay {
      position: absolute;
      inset: 0;

      display: flex;
      align-items: end;

      padding: 30px;

      background: linear-gradient(
        transparent,
        rgba(0,0,0,0.65)
      );

      color: white;
    }

    .category-overlay h3 {
      font-size: 32px;
      font-family: Georgia, serif;
      font-style: italic;
    }

    /* ================= PRODUCTS ================= */

    .products {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 22px;
    }

    .product {
      cursor: pointer;
    }

    .product-image {
      height: 420px;
      overflow: hidden;
      background: #eee;
      position: relative;
    }

    .product-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.5s;
    }

    .product:hover img {
      transform: scale(1.05);
    }

    .badge {
      position: absolute;
      top: 15px;
      left: 15px;

      background: #111;
      color: white;

      padding: 7px 12px;

      font-size: 10px;
      letter-spacing: 1px;
    }

    .product-info {
      padding: 17px 0;
    }

    .product-info h3 {
      font-size: 14px;
      margin-bottom: 8px;
    }

    .product-info p {
      color: #666;
      font-size: 13px;
    }

    /* ================= EDITORIAL ================= */

    .editorial {
      min-height: 650px;

      display: grid;
      grid-template-columns: 1fr 1fr;

      background: #171717;
      color: white;
    }

    .editorial-image {
      min-height: 650px;
      background:
        url("https://images.unsplash.com/photo-1483985988355-763728e1935b?auto=format&fit=crop&w=1200&q=90")
        center/cover;
    }

    .editorial-content {
      display: flex;
      flex-direction: column;
      justify-content: center;

      padding: 10%;
    }

    .editorial-content small {
      letter-spacing: 4px;
      color: #aaa;
      margin-bottom: 25px;
    }

    .editorial-content h2 {
      font-size: 65px;
      font-family: Georgia, serif;
      font-style: italic;
      line-height: 1;
      margin-bottom: 25px;
    }

    .editorial-content p {
      color: #aaa;
      line-height: 1.8;
      max-width: 450px;
      margin-bottom: 30px;
    }

    .outline-btn {
      width: fit-content;
      padding: 15px 30px;

      background: transparent;
      color: white;
      border: 1px solid white;

      cursor: pointer;
      letter-spacing: 2px;
    }

    /* ================= ABOUT ================= */

    .about {
      text-align: center;
      max-width: 950px;
      margin: auto;
    }

    .about small {
      letter-spacing: 4px;
      color: #777;
    }

    .about h2 {
      font-size: clamp(40px, 6vw, 80px);
      font-family: Georgia, serif;
      font-weight: normal;
      margin: 25px 0;
    }

    .about p {
      color: #666;
      line-height: 2;
      font-size: 15px;
    }

    /* ================= NEWSLETTER ================= */

    .newsletter {
      background: #e7e2d8;
      text-align: center;
    }

    .newsletter h2 {
      font-size: 45px;
      margin-bottom: 15px;
    }

    .newsletter p {
      color: #666;
      margin-bottom: 30px;
    }

    .newsletter-form {
      max-width: 500px;
      margin: auto;
      display: flex;
    }

    .newsletter-form input {
      flex: 1;
      padding: 17px;
      border: 1px solid #aaa;
      background: transparent;
      outline: none;
    }

    .newsletter-form button {
      padding: 17px 25px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= FOOTER ================= */

    footer {
      background: #111;
      color: white;
      padding: 70px 7% 30px;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 40px;
      padding-bottom: 60px;
    }

    .footer-brand h2 {
      font-size: 35px;
      letter-spacing: 8px;
      margin-bottom: 20px;
    }

    footer p {
      color: #999;
      font-size: 13px;
      line-height: 1.8;
    }

    footer h4 {
      margin-bottom: 20px;
      font-size: 13px;
      letter-spacing: 2px;
    }

    footer ul {
      list-style: none;
    }

    footer li {
      margin-bottom: 12px;
      color: #999;
      font-size: 13px;
      cursor: pointer;
    }

    .copyright {
      border-top: 1px solid #333;
      padding-top: 25px;
      color: #666;
      font-size: 12px;
    }

    /* ================= CART ================= */

    .cart {
      position: fixed;
      top: 0;
      right: -420px;

      width: 400px;
      height: 100vh;

      background: white;
      z-index: 2000;

      padding: 30px;

      transition: 0.4s;
      box-shadow: -10px 0 30px rgba(0,0,0,0.15);
    }

    .cart.active {
      right: 0;
    }

    .cart-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 40px;
    }

    .cart-header h2 {
      font-size: 25px;
    }

    .close-cart {
      font-size: 25px;
      cursor: pointer;
    }

    .cart-item {
      border-bottom: 1px solid #ddd;
      padding: 20px 0;
      display: flex;
      justify-content: space-between;
    }

    .cart-total {
      position: absolute;
      bottom: 30px;
      left: 30px;
      right: 30px;
    }

    .cart-total h3 {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20px;
    }

    .checkout {
      width: 100%;
      padding: 16px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= RESPONSIVE ================= */

    @media(max-width: 900px) {

      nav ul {
        position: absolute;
        top: 75px;
        left: 0;
        width: 100%;

        background: #f7f5f0;

        flex-direction: column;
        align-items: center;

        padding: 30px;

        display: none;
      }

      nav ul.active {
        display: flex;
      }

      .menu {
        display: block;
      }

      .nav-icons {
        display: none;
      }

      .categories {
        grid-template-columns: 1fr;
      }

      .category {
        height: 450px;
      }

      .products {
        grid-template-columns: repeat(2, 1fr);
      }

      .editorial {
        grid-template-columns: 1fr;
      }

      .editorial-image {
        min-height: 500px;
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media(max-width: 600px) {

      section {
        padding: 70px 5%;
      }

      nav {
        padding: 20px 5%;
      }

      .hero {
        padding: 0 5%;
      }

      .hero-content h1 {
        font-size: 70px;
      }

      .section-title {
        display: block;
      }

      .section-title h2 {
        margin-bottom: 10px;
      }

      .products {
        grid-template-columns: 1fr 1fr;
        gap: 12px;
      }

      .product-image {
        height: 280px;
      }

      .editorial-content h2 {
        font-size: 50px;
      }

      .newsletter-form {
        flex-direction: column;
        gap: 10px;
      }

      .footer-grid {
        grid-template-columns: 1fr;
      }

      .cart {
        width: 100%;
        right: -100%;
      }
    }
  </style>
</head>

<body>

  <!-- ================= NAVBAR ================= -->

  <nav>

    <div class="logo">AURA</div>

    <ul id="navLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#shop">Shop</a></li>
      <li><a href="#collections">Collections</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="nav-icons">
      <span onclick="openCart()">🛒</span>
    </div>

    <div class="menu" onclick="toggleMenu()">☰</div>

  </nav>


  <!-- ================= HERO ================= -->

  <section class="hero" id="home">

    <div class="hero-content">

      <p>THE NEW ERA OF STYLE</p>

      <h1>
        Wear Your
        <span>Aura.</span>
      </h1>

      <button onclick="document.getElementById('shop').scrollIntoView()">
        SHOP COLLECTION
      </button>

    </div>

  </section>


  <!-- ================= CATEGORIES ================= -->

  <section id="collections">

    <div class="section-title">

      <div>
        <h2>Collections</h2>
      </div>

      <p>Explore the world of AURA.</p>

    </div>


    <div class="categories">

      <div class="category">

        <img src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Women</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Essentials</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1506629905607-d9b1a9e7f0ad?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Men</h3>
        </div>

      </div>

    </div>

  </section>


  <!-- ================= SHOP ================= -->

  <section id="shop">

    <div class="section-title">

      <div>
        <h2>New Arrivals</h2>
      </div>

      <p>Fresh pieces. Timeless attitude.</p>

    </div>


    <div class="products">


      <div class="product" onclick="addToCart('AURA Essential Tee', 45)">

        <div class="product-image">

          <span class="badge">NEW</span>

          <img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Essential Tee</h3>

          <p>$45.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Oversized Street Hoodie', 89)">

        <div class="product-image">

          <span class="badge">BESTSELLER</span>

          <img src="https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Oversized Street Hoodie</h3>

          <p>$89.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('AURA Linen Shirt', 75)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1602810318383-e386cc2a3ccf?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Linen Shirt</h3>

          <p>$75.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Minimal Cargo Pants', 95)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Minimal Cargo Pants</h3>

          <p>$95.00</p>

        </div>

      </div>


    </div>

  </section>


  <!-- ================= EDITORIAL ================= -->

  <section style="padding-top:0;">

    <div class="editorial">

      <div class="editorial-image"></div>

      <div class="editorial-content">

        <small>AURA EDITORIAL 2026</small>

        <h2>Less noise.<br>More Aura.</h2>

        <p>
          Designed for those who don't follow the crowd.
          AURA blends timeless silhouettes with modern
          streetwear to create pieces made for everyday
          expression.
        </p>

        <button class="outline-btn">
          DISCOVER AURA
        </button>

      </div>

    </div>

  </section>


  <!-- ================= ABOUT ================= -->

  <section id="about">

    <div class="about">

      <small>OUR PHILOSOPHY</small>

      <h2>Style is an energy.</h2>

      <p>
        AURA is more than clothing. It's a feeling, an attitude,
        and a way of expressing who you are without saying a word.
        We create premium everyday pieces with clean silhouettes,
        refined details and a timeless point of view.
      </p>

    </div>

  </section>


  <!-- ================= NEWSLETTER ================= -->

  <section class="newsletter" id="contact">

    <h2>Join the AURA.</h2>

    <p>
      Get early access to new drops and exclusive collections.
    </p>

    <form class="newsletter-form" onsubmit="subscribe(event)">

      <input
        type="email"
        placeholder="Your email address"
        required
      >

      <button type="submit">
        JOIN
      </button>

    </form>

  </section>


  <!-- ================= FOOTER ================= -->

  <footer>

    <div class="footer-grid">

      <div class="footer-brand">

        <h2>AURA</h2>

        <p>
          Premium clothing for modern expression.
          Designed with intention. Worn with confidence.
        </p>

      </div>


      <div>

        <h4>SHOP</h4>

        <ul>
          <li>New Arrivals</li>
          <li>Women</li>
          <li>Men</li>
          <li>Essentials</li>
        </ul>

      </div>


      <div>

        <h4>HELP</h4>

        <ul>
          <li>Shipping</li>
          <li>Returns</li>
          <li>Size Guide</li>
          <li>FAQ</li>
        </ul>

      </div>


      <div>

        <h4>FOLLOW</h4>

        <ul>
          <li>Instagram</li>
          <li>TikTok</li>
          <li>Facebook</li>
          <li>Pinterest</li>
        </ul>

      </div>

    </div>


    <div class="copyright">
      © 2026 AURA. All Rights Reserved.
    </div>

  </footer>


  <!-- ================= CART ================= -->

  <div class="cart" id="cart">

    <div class="cart-header">

      <h2>Your Cart</h2>

      <span
        class="close-cart"
        onclick="closeCart()"
      >
        ×
      </span>

    </div>


    <div id="cartItems">
      <p style="color:#777;">
        Your cart is empty.
      </p>
    </div>


    <div class="cart-total">

      <h3>
        <span>Total</span>
        <span>$<span id="cartTotal">0</span></span>
      </h3>

      <button
        class="checkout"
        onclick="checkout()"
      >
        CHECKOUT
      </button>

    </div>

  </div>


  <!-- ================= JAVASCRIPT ================= -->

  <script>

    let cart = [];

    function toggleMenu() {

      document
        .getElementById("navLinks")
        .classList.toggle("active");

    }


    function openCart() {

      document
        .getElementById("cart")
        .classList.add("active");

    }


    function closeCart() {

      document
        .getElementById("cart")
        .classList.remove("active");

    }


    function addToCart(name, price) {

      cart.push({
        name: name,
        price: price
      });

      updateCart();

      openCart();

    }


    function updateCart() {

      const cartItems =
        document.getElementById("cartItems");

      const cartTotal =
        document.getElementById("cartTotal");


      if (cart.length === 0) {

        cartItems.innerHTML =
          '<p style="color:#777;">Your cart is empty.</p>';

        cartTotal.innerText = "0";

        return;

      }


      let total = 0;

      cartItems.innerHTML = "";


      cart.forEach((item, index) => {

        total += item.price;

        cartItems.innerHTML += `

          <div class="cart-item">

            <div>
              <strong>${item.name}</strong>
              <br>
              <small>$${item.price}</small>
            </div>

            <span
              style="cursor:pointer;"
              onclick="removeItem(${index})"
            >
              ×
            </span>

          </div>

        `;

      });


      cartTotal.innerText =
        total.toFixed(2);

    }


    function removeItem(index) {

      cart.splice(index, 1);

      updateCart();

    }


    function checkout() {

      if (cart.length === 0) {

        alert("Your cart is empty.");

        return;

      }

      alert(
        "Thank you for shopping with AURA! Checkout system can be connected to your payment gateway."
      );

    }


    function subscribe(event) {

      event.preventDefault();

      alert(
        "Welcome to AURA. You're now subscribed!"
      );

      event.target.reset();

    }

  </script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>AURA — Premium Clothing</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #f7f5f0;
      color: #111;
    }

    /* ================= NAVBAR ================= */

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;

      display: flex;
      justify-content: space-between;
      align-items: center;

      padding: 22px 7%;
      background: rgba(247,245,240,0.92);
      backdrop-filter: blur(15px);

      border-bottom: 1px solid rgba(0,0,0,0.08);
    }

    .logo {
      font-size: 28px;
      font-weight: 800;
      letter-spacing: 8px;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 35px;
    }

    nav ul li a {
      text-decoration: none;
      color: #111;
      font-size: 13px;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .nav-icons {
      display: flex;
      gap: 20px;
      font-size: 20px;
      cursor: pointer;
    }

    .menu {
      display: none;
      font-size: 25px;
      cursor: pointer;
    }

    /* ================= HERO ================= */

    .hero {
      height: 100vh;
      min-height: 650px;

      display: flex;
      align-items: center;

      padding: 0 7%;

      background:
        linear-gradient(
          90deg,
          rgba(0,0,0,0.65),
          rgba(0,0,0,0.15)
        ),
        url("https://images.unsplash.com/photo-1496747611176-843222e1e57c?auto=format&fit=crop&w=2000&q=90");

      background-size: cover;
      background-position: center;
      color: white;
    }

    .hero-content {
      max-width: 650px;
    }

    .hero-content p {
      font-size: 13px;
      letter-spacing: 5px;
      margin-bottom: 20px;
    }

    .hero-content h1 {
      font-size: clamp(60px, 9vw, 130px);
      line-height: 0.9;
      letter-spacing: -5px;
      margin-bottom: 30px;
    }

    .hero-content span {
      font-family: Georgia, serif;
      font-style: italic;
    }

    .hero-content button {
      padding: 17px 35px;
      border: none;
      background: white;
      color: #111;
      cursor: pointer;
      font-weight: bold;
      letter-spacing: 2px;
      transition: 0.3s;
    }

    .hero-content button:hover {
      background: #111;
      color: white;
    }

    /* ================= SECTION ================= */

    section {
      padding: 100px 7%;
    }

    .section-title {
      display: flex;
      justify-content: space-between;
      align-items: end;
      margin-bottom: 45px;
    }

    .section-title h2 {
      font-size: 45px;
      letter-spacing: -2px;
    }

    .section-title p {
      color: #777;
      font-size: 14px;
    }

    /* ================= CATEGORIES ================= */

    .categories {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .category {
      height: 500px;
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }

    .category img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.6s;
    }

    .category:hover img {
      transform: scale(1.08);
    }

    .category-overlay {
      position: absolute;
      inset: 0;

      display: flex;
      align-items: end;

      padding: 30px;

      background: linear-gradient(
        transparent,
        rgba(0,0,0,0.65)
      );

      color: white;
    }

    .category-overlay h3 {
      font-size: 32px;
      font-family: Georgia, serif;
      font-style: italic;
    }

    /* ================= PRODUCTS ================= */

    .products {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 22px;
    }

    .product {
      cursor: pointer;
    }

    .product-image {
      height: 420px;
      overflow: hidden;
      background: #eee;
      position: relative;
    }

    .product-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.5s;
    }

    .product:hover img {
      transform: scale(1.05);
    }

    .badge {
      position: absolute;
      top: 15px;
      left: 15px;

      background: #111;
      color: white;

      padding: 7px 12px;

      font-size: 10px;
      letter-spacing: 1px;
    }

    .product-info {
      padding: 17px 0;
    }

    .product-info h3 {
      font-size: 14px;
      margin-bottom: 8px;
    }

    .product-info p {
      color: #666;
      font-size: 13px;
    }

    /* ================= EDITORIAL ================= */

    .editorial {
      min-height: 650px;

      display: grid;
      grid-template-columns: 1fr 1fr;

      background: #171717;
      color: white;
    }

    .editorial-image {
      min-height: 650px;
      background:
        url("https://images.unsplash.com/photo-1483985988355-763728e1935b?auto=format&fit=crop&w=1200&q=90")
        center/cover;
    }

    .editorial-content {
      display: flex;
      flex-direction: column;
      justify-content: center;

      padding: 10%;
    }

    .editorial-content small {
      letter-spacing: 4px;
      color: #aaa;
      margin-bottom: 25px;
    }

    .editorial-content h2 {
      font-size: 65px;
      font-family: Georgia, serif;
      font-style: italic;
      line-height: 1;
      margin-bottom: 25px;
    }

    .editorial-content p {
      color: #aaa;
      line-height: 1.8;
      max-width: 450px;
      margin-bottom: 30px;
    }

    .outline-btn {
      width: fit-content;
      padding: 15px 30px;

      background: transparent;
      color: white;
      border: 1px solid white;

      cursor: pointer;
      letter-spacing: 2px;
    }

    /* ================= ABOUT ================= */

    .about {
      text-align: center;
      max-width: 950px;
      margin: auto;
    }

    .about small {
      letter-spacing: 4px;
      color: #777;
    }

    .about h2 {
      font-size: clamp(40px, 6vw, 80px);
      font-family: Georgia, serif;
      font-weight: normal;
      margin: 25px 0;
    }

    .about p {
      color: #666;
      line-height: 2;
      font-size: 15px;
    }

    /* ================= NEWSLETTER ================= */

    .newsletter {
      background: #e7e2d8;
      text-align: center;
    }

    .newsletter h2 {
      font-size: 45px;
      margin-bottom: 15px;
    }

    .newsletter p {
      color: #666;
      margin-bottom: 30px;
    }

    .newsletter-form {
      max-width: 500px;
      margin: auto;
      display: flex;
    }

    .newsletter-form input {
      flex: 1;
      padding: 17px;
      border: 1px solid #aaa;
      background: transparent;
      outline: none;
    }

    .newsletter-form button {
      padding: 17px 25px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= FOOTER ================= */

    footer {
      background: #111;
      color: white;
      padding: 70px 7% 30px;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 40px;
      padding-bottom: 60px;
    }

    .footer-brand h2 {
      font-size: 35px;
      letter-spacing: 8px;
      margin-bottom: 20px;
    }

    footer p {
      color: #999;
      font-size: 13px;
      line-height: 1.8;
    }

    footer h4 {
      margin-bottom: 20px;
      font-size: 13px;
      letter-spacing: 2px;
    }

    footer ul {
      list-style: none;
    }

    footer li {
      margin-bottom: 12px;
      color: #999;
      font-size: 13px;
      cursor: pointer;
    }

    .copyright {
      border-top: 1px solid #333;
      padding-top: 25px;
      color: #666;
      font-size: 12px;
    }

    /* ================= CART ================= */

    .cart {
      position: fixed;
      top: 0;
      right: -420px;

      width: 400px;
      height: 100vh;

      background: white;
      z-index: 2000;

      padding: 30px;

      transition: 0.4s;
      box-shadow: -10px 0 30px rgba(0,0,0,0.15);
    }

    .cart.active {
      right: 0;
    }

    .cart-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 40px;
    }

    .cart-header h2 {
      font-size: 25px;
    }

    .close-cart {
      font-size: 25px;
      cursor: pointer;
    }

    .cart-item {
      border-bottom: 1px solid #ddd;
      padding: 20px 0;
      display: flex;
      justify-content: space-between;
    }

    .cart-total {
      position: absolute;
      bottom: 30px;
      left: 30px;
      right: 30px;
    }

    .cart-total h3 {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20px;
    }

    .checkout {
      width: 100%;
      padding: 16px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= RESPONSIVE ================= */

    @media(max-width: 900px) {

      nav ul {
        position: absolute;
        top: 75px;
        left: 0;
        width: 100%;

        background: #f7f5f0;

        flex-direction: column;
        align-items: center;

        padding: 30px;

        display: none;
      }

      nav ul.active {
        display: flex;
      }

      .menu {
        display: block;
      }

      .nav-icons {
        display: none;
      }

      .categories {
        grid-template-columns: 1fr;
      }

      .category {
        height: 450px;
      }

      .products {
        grid-template-columns: repeat(2, 1fr);
      }

      .editorial {
        grid-template-columns: 1fr;
      }

      .editorial-image {
        min-height: 500px;
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media(max-width: 600px) {

      section {
        padding: 70px 5%;
      }

      nav {
        padding: 20px 5%;
      }

      .hero {
        padding: 0 5%;
      }

      .hero-content h1 {
        font-size: 70px;
      }

      .section-title {
        display: block;
      }

      .section-title h2 {
        margin-bottom: 10px;
      }

      .products {
        grid-template-columns: 1fr 1fr;
        gap: 12px;
      }

      .product-image {
        height: 280px;
      }

      .editorial-content h2 {
        font-size: 50px;
      }

      .newsletter-form {
        flex-direction: column;
        gap: 10px;
      }

      .footer-grid {
        grid-template-columns: 1fr;
      }

      .cart {
        width: 100%;
        right: -100%;
      }
    }
  </style>
</head>

<body>

  <!-- ================= NAVBAR ================= -->

  <nav>

    <div class="logo">AURA</div>

    <ul id="navLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#shop">Shop</a></li>
      <li><a href="#collections">Collections</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="nav-icons">
      <span onclick="openCart()">🛒</span>
    </div>

    <div class="menu" onclick="toggleMenu()">☰</div>

  </nav>


  <!-- ================= HERO ================= -->

  <section class="hero" id="home">

    <div class="hero-content">

      <p>THE NEW ERA OF STYLE</p>

      <h1>
        Wear Your
        <span>Aura.</span>
      </h1>

      <button onclick="document.getElementById('shop').scrollIntoView()">
        SHOP COLLECTION
      </button>

    </div>

  </section>


  <!-- ================= CATEGORIES ================= -->

  <section id="collections">

    <div class="section-title">

      <div>
        <h2>Collections</h2>
      </div>

      <p>Explore the world of AURA.</p>

    </div>


    <div class="categories">

      <div class="category">

        <img src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Women</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Essentials</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1506629905607-d9b1a9e7f0ad?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Men</h3>
        </div>

      </div>

    </div>

  </section>


  <!-- ================= SHOP ================= -->

  <section id="shop">

    <div class="section-title">

      <div>
        <h2>New Arrivals</h2>
      </div>

      <p>Fresh pieces. Timeless attitude.</p>

    </div>


    <div class="products">


      <div class="product" onclick="addToCart('AURA Essential Tee', 45)">

        <div class="product-image">

          <span class="badge">NEW</span>

          <img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Essential Tee</h3>

          <p>$45.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Oversized Street Hoodie', 89)">

        <div class="product-image">

          <span class="badge">BESTSELLER</span>

          <img src="https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Oversized Street Hoodie</h3>

          <p>$89.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('AURA Linen Shirt', 75)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1602810318383-e386cc2a3ccf?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Linen Shirt</h3>

          <p>$75.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Minimal Cargo Pants', 95)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Minimal Cargo Pants</h3>

          <p>$95.00</p>

        </div>

      </div>


    </div>

  </section>


  <!-- ================= EDITORIAL ================= -->

  <section style="padding-top:0;">

    <div class="editorial">

      <div class="editorial-image"></div>

      <div class="editorial-content">

        <small>AURA EDITORIAL 2026</small>

        <h2>Less noise.<br>More Aura.</h2>

        <p>
          Designed for those who don't follow the crowd.
          AURA blends timeless silhouettes with modern
          streetwear to create pieces made for everyday
          expression.
        </p>

        <button class="outline-btn">
          DISCOVER AURA
        </button>

      </div>

    </div>

  </section>


  <!-- ================= ABOUT ================= -->

  <section id="about">

    <div class="about">

      <small>OUR PHILOSOPHY</small>

      <h2>Style is an energy.</h2>

      <p>
        AURA is more than clothing. It's a feeling, an attitude,
        and a way of expressing who you are without saying a word.
        We create premium everyday pieces with clean silhouettes,
        refined details and a timeless point of view.
      </p>

    </div>

  </section>


  <!-- ================= NEWSLETTER ================= -->

  <section class="newsletter" id="contact">

    <h2>Join the AURA.</h2>

    <p>
      Get early access to new drops and exclusive collections.
    </p>

    <form class="newsletter-form" onsubmit="subscribe(event)">

      <input
        type="email"
        placeholder="Your email address"
        required
      >

      <button type="submit">
        JOIN
      </button>

    </form>

  </section>


  <!-- ================= FOOTER ================= -->

  <footer>

    <div class="footer-grid">

      <div class="footer-brand">

        <h2>AURA</h2>

        <p>
          Premium clothing for modern expression.
          Designed with intention. Worn with confidence.
        </p>

      </div>


      <div>

        <h4>SHOP</h4>

        <ul>
          <li>New Arrivals</li>
          <li>Women</li>
          <li>Men</li>
          <li>Essentials</li>
        </ul>

      </div>


      <div>

        <h4>HELP</h4>

        <ul>
          <li>Shipping</li>
          <li>Returns</li>
          <li>Size Guide</li>
          <li>FAQ</li>
        </ul>

      </div>


      <div>

        <h4>FOLLOW</h4>

        <ul>
          <li>Instagram</li>
          <li>TikTok</li>
          <li>Facebook</li>
          <li>Pinterest</li>
        </ul>

      </div>

    </div>


    <div class="copyright">
      © 2026 AURA. All Rights Reserved.
    </div>

  </footer>


  <!-- ================= CART ================= -->

  <div class="cart" id="cart">

    <div class="cart-header">

      <h2>Your Cart</h2>

      <span
        class="close-cart"
        onclick="closeCart()"
      >
        ×
      </span>

    </div>


    <div id="cartItems">
      <p style="color:#777;">
        Your cart is empty.
      </p>
    </div>


    <div class="cart-total">

      <h3>
        <span>Total</span>
        <span>$<span id="cartTotal">0</span></span>
      </h3>

      <button
        class="checkout"
        onclick="checkout()"
      >
        CHECKOUT
      </button>

    </div>

  </div>


  <!-- ================= JAVASCRIPT ================= -->

  <script>

    let cart = [];

    function toggleMenu() {

      document
        .getElementById("navLinks")
        .classList.toggle("active");

    }


    function openCart() {

      document
        .getElementById("cart")
        .classList.add("active");

    }


    function closeCart() {

      document
        .getElementById("cart")
        .classList.remove("active");

    }


    function addToCart(name, price) {

      cart.push({
        name: name,
        price: price
      });

      updateCart();

      openCart();

    }


    function updateCart() {

      const cartItems =
        document.getElementById("cartItems");

      const cartTotal =
        document.getElementById("cartTotal");


      if (cart.length === 0) {

        cartItems.innerHTML =
          '<p style="color:#777;">Your cart is empty.</p>';

        cartTotal.innerText = "0";

        return;

      }


      let total = 0;

      cartItems.innerHTML = "";


      cart.forEach((item, index) => {

        total += item.price;

        cartItems.innerHTML += `

          <div class="cart-item">

            <div>
              <strong>${item.name}</strong>
              <br>
              <small>$${item.price}</small>
            </div>

            <span
              style="cursor:pointer;"
              onclick="removeItem(${index})"
            >
              ×
            </span>

          </div>

        `;

      });


      cartTotal.innerText =
        total.toFixed(2);

    }


    function removeItem(index) {

      cart.splice(index, 1);

      updateCart();

    }


    function checkout() {

      if (cart.length === 0) {

        alert("Your cart is empty.");

        return;

      }

      alert(
        "Thank you for shopping with AURA! Checkout system can be connected to your payment gateway."
      );

    }


    function subscribe(event) {

      event.preventDefault();

      alert(
        "Welcome to AURA. You're now subscribed!"
      );

      event.target.reset();

    }

  </script>

</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>AURA — Premium Clothing</title>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, Helvetica, sans-serif;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: #f7f5f0;
      color: #111;
    }

    /* ================= NAVBAR ================= */

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;

      display: flex;
      justify-content: space-between;
      align-items: center;

      padding: 22px 7%;
      background: rgba(247,245,240,0.92);
      backdrop-filter: blur(15px);

      border-bottom: 1px solid rgba(0,0,0,0.08);
    }

    .logo {
      font-size: 28px;
      font-weight: 800;
      letter-spacing: 8px;
    }

    nav ul {
      display: flex;
      list-style: none;
      gap: 35px;
    }

    nav ul li a {
      text-decoration: none;
      color: #111;
      font-size: 13px;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .nav-icons {
      display: flex;
      gap: 20px;
      font-size: 20px;
      cursor: pointer;
    }

    .menu {
      display: none;
      font-size: 25px;
      cursor: pointer;
    }

    /* ================= HERO ================= */

    .hero {
      height: 100vh;
      min-height: 650px;

      display: flex;
      align-items: center;

      padding: 0 7%;

      background:
        linear-gradient(
          90deg,
          rgba(0,0,0,0.65),
          rgba(0,0,0,0.15)
        ),
        url("https://images.unsplash.com/photo-1496747611176-843222e1e57c?auto=format&fit=crop&w=2000&q=90");

      background-size: cover;
      background-position: center;
      color: white;
    }

    .hero-content {
      max-width: 650px;
    }

    .hero-content p {
      font-size: 13px;
      letter-spacing: 5px;
      margin-bottom: 20px;
    }

    .hero-content h1 {
      font-size: clamp(60px, 9vw, 130px);
      line-height: 0.9;
      letter-spacing: -5px;
      margin-bottom: 30px;
    }

    .hero-content span {
      font-family: Georgia, serif;
      font-style: italic;
    }

    .hero-content button {
      padding: 17px 35px;
      border: none;
      background: white;
      color: #111;
      cursor: pointer;
      font-weight: bold;
      letter-spacing: 2px;
      transition: 0.3s;
    }

    .hero-content button:hover {
      background: #111;
      color: white;
    }

    /* ================= SECTION ================= */

    section {
      padding: 100px 7%;
    }

    .section-title {
      display: flex;
      justify-content: space-between;
      align-items: end;
      margin-bottom: 45px;
    }

    .section-title h2 {
      font-size: 45px;
      letter-spacing: -2px;
    }

    .section-title p {
      color: #777;
      font-size: 14px;
    }

    /* ================= CATEGORIES ================= */

    .categories {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 20px;
    }

    .category {
      height: 500px;
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }

    .category img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.6s;
    }

    .category:hover img {
      transform: scale(1.08);
    }

    .category-overlay {
      position: absolute;
      inset: 0;

      display: flex;
      align-items: end;

      padding: 30px;

      background: linear-gradient(
        transparent,
        rgba(0,0,0,0.65)
      );

      color: white;
    }

    .category-overlay h3 {
      font-size: 32px;
      font-family: Georgia, serif;
      font-style: italic;
    }

    /* ================= PRODUCTS ================= */

    .products {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 22px;
    }

    .product {
      cursor: pointer;
    }

    .product-image {
      height: 420px;
      overflow: hidden;
      background: #eee;
      position: relative;
    }

    .product-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: 0.5s;
    }

    .product:hover img {
      transform: scale(1.05);
    }

    .badge {
      position: absolute;
      top: 15px;
      left: 15px;

      background: #111;
      color: white;

      padding: 7px 12px;

      font-size: 10px;
      letter-spacing: 1px;
    }

    .product-info {
      padding: 17px 0;
    }

    .product-info h3 {
      font-size: 14px;
      margin-bottom: 8px;
    }

    .product-info p {
      color: #666;
      font-size: 13px;
    }

    /* ================= EDITORIAL ================= */

    .editorial {
      min-height: 650px;

      display: grid;
      grid-template-columns: 1fr 1fr;

      background: #171717;
      color: white;
    }

    .editorial-image {
      min-height: 650px;
      background:
        url("https://images.unsplash.com/photo-1483985988355-763728e1935b?auto=format&fit=crop&w=1200&q=90")
        center/cover;
    }

    .editorial-content {
      display: flex;
      flex-direction: column;
      justify-content: center;

      padding: 10%;
    }

    .editorial-content small {
      letter-spacing: 4px;
      color: #aaa;
      margin-bottom: 25px;
    }

    .editorial-content h2 {
      font-size: 65px;
      font-family: Georgia, serif;
      font-style: italic;
      line-height: 1;
      margin-bottom: 25px;
    }

    .editorial-content p {
      color: #aaa;
      line-height: 1.8;
      max-width: 450px;
      margin-bottom: 30px;
    }

    .outline-btn {
      width: fit-content;
      padding: 15px 30px;

      background: transparent;
      color: white;
      border: 1px solid white;

      cursor: pointer;
      letter-spacing: 2px;
    }

    /* ================= ABOUT ================= */

    .about {
      text-align: center;
      max-width: 950px;
      margin: auto;
    }

    .about small {
      letter-spacing: 4px;
      color: #777;
    }

    .about h2 {
      font-size: clamp(40px, 6vw, 80px);
      font-family: Georgia, serif;
      font-weight: normal;
      margin: 25px 0;
    }

    .about p {
      color: #666;
      line-height: 2;
      font-size: 15px;
    }

    /* ================= NEWSLETTER ================= */

    .newsletter {
      background: #e7e2d8;
      text-align: center;
    }

    .newsletter h2 {
      font-size: 45px;
      margin-bottom: 15px;
    }

    .newsletter p {
      color: #666;
      margin-bottom: 30px;
    }

    .newsletter-form {
      max-width: 500px;
      margin: auto;
      display: flex;
    }

    .newsletter-form input {
      flex: 1;
      padding: 17px;
      border: 1px solid #aaa;
      background: transparent;
      outline: none;
    }

    .newsletter-form button {
      padding: 17px 25px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= FOOTER ================= */

    footer {
      background: #111;
      color: white;
      padding: 70px 7% 30px;
    }

    .footer-grid {
      display: grid;
      grid-template-columns: 2fr 1fr 1fr 1fr;
      gap: 40px;
      padding-bottom: 60px;
    }

    .footer-brand h2 {
      font-size: 35px;
      letter-spacing: 8px;
      margin-bottom: 20px;
    }

    footer p {
      color: #999;
      font-size: 13px;
      line-height: 1.8;
    }

    footer h4 {
      margin-bottom: 20px;
      font-size: 13px;
      letter-spacing: 2px;
    }

    footer ul {
      list-style: none;
    }

    footer li {
      margin-bottom: 12px;
      color: #999;
      font-size: 13px;
      cursor: pointer;
    }

    .copyright {
      border-top: 1px solid #333;
      padding-top: 25px;
      color: #666;
      font-size: 12px;
    }

    /* ================= CART ================= */

    .cart {
      position: fixed;
      top: 0;
      right: -420px;

      width: 400px;
      height: 100vh;

      background: white;
      z-index: 2000;

      padding: 30px;

      transition: 0.4s;
      box-shadow: -10px 0 30px rgba(0,0,0,0.15);
    }

    .cart.active {
      right: 0;
    }

    .cart-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 40px;
    }

    .cart-header h2 {
      font-size: 25px;
    }

    .close-cart {
      font-size: 25px;
      cursor: pointer;
    }

    .cart-item {
      border-bottom: 1px solid #ddd;
      padding: 20px 0;
      display: flex;
      justify-content: space-between;
    }

    .cart-total {
      position: absolute;
      bottom: 30px;
      left: 30px;
      right: 30px;
    }

    .cart-total h3 {
      display: flex;
      justify-content: space-between;
      margin-bottom: 20px;
    }

    .checkout {
      width: 100%;
      padding: 16px;
      border: none;
      background: #111;
      color: white;
      cursor: pointer;
    }

    /* ================= RESPONSIVE ================= */

    @media(max-width: 900px) {

      nav ul {
        position: absolute;
        top: 75px;
        left: 0;
        width: 100%;

        background: #f7f5f0;

        flex-direction: column;
        align-items: center;

        padding: 30px;

        display: none;
      }

      nav ul.active {
        display: flex;
      }

      .menu {
        display: block;
      }

      .nav-icons {
        display: none;
      }

      .categories {
        grid-template-columns: 1fr;
      }

      .category {
        height: 450px;
      }

      .products {
        grid-template-columns: repeat(2, 1fr);
      }

      .editorial {
        grid-template-columns: 1fr;
      }

      .editorial-image {
        min-height: 500px;
      }

      .footer-grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media(max-width: 600px) {

      section {
        padding: 70px 5%;
      }

      nav {
        padding: 20px 5%;
      }

      .hero {
        padding: 0 5%;
      }

      .hero-content h1 {
        font-size: 70px;
      }

      .section-title {
        display: block;
      }

      .section-title h2 {
        margin-bottom: 10px;
      }

      .products {
        grid-template-columns: 1fr 1fr;
        gap: 12px;
      }

      .product-image {
        height: 280px;
      }

      .editorial-content h2 {
        font-size: 50px;
      }

      .newsletter-form {
        flex-direction: column;
        gap: 10px;
      }

      .footer-grid {
        grid-template-columns: 1fr;
      }

      .cart {
        width: 100%;
        right: -100%;
      }
    }
  </style>
</head>

<body>

  <!-- ================= NAVBAR ================= -->

  <nav>

    <div class="logo">AURA</div>

    <ul id="navLinks">
      <li><a href="#home">Home</a></li>
      <li><a href="#shop">Shop</a></li>
      <li><a href="#collections">Collections</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>

    <div class="nav-icons">
      <span onclick="openCart()">🛒</span>
    </div>

    <div class="menu" onclick="toggleMenu()">☰</div>

  </nav>


  <!-- ================= HERO ================= -->

  <section class="hero" id="home">

    <div class="hero-content">

      <p>THE NEW ERA OF STYLE</p>

      <h1>
        Wear Your
        <span>Aura.</span>
      </h1>

      <button onclick="document.getElementById('shop').scrollIntoView()">
        SHOP COLLECTION
      </button>

    </div>

  </section>


  <!-- ================= CATEGORIES ================= -->

  <section id="collections">

    <div class="section-title">

      <div>
        <h2>Collections</h2>
      </div>

      <p>Explore the world of AURA.</p>

    </div>


    <div class="categories">

      <div class="category">

        <img src="https://images.unsplash.com/photo-1529139574466-a303027c1d8b?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Women</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Essentials</h3>
        </div>

      </div>


      <div class="category">

        <img src="https://images.unsplash.com/photo-1506629905607-d9b1a9e7f0ad?auto=format&fit=crop&w=900&q=90">

        <div class="category-overlay">
          <h3>Men</h3>
        </div>

      </div>

    </div>

  </section>


  <!-- ================= SHOP ================= -->

  <section id="shop">

    <div class="section-title">

      <div>
        <h2>New Arrivals</h2>
      </div>

      <p>Fresh pieces. Timeless attitude.</p>

    </div>


    <div class="products">


      <div class="product" onclick="addToCart('AURA Essential Tee', 45)">

        <div class="product-image">

          <span class="badge">NEW</span>

          <img src="https://images.unsplash.com/photo-1521572163474-6864f9cf17ab?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Essential Tee</h3>

          <p>$45.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Oversized Street Hoodie', 89)">

        <div class="product-image">

          <span class="badge">BESTSELLER</span>

          <img src="https://images.unsplash.com/photo-1556821840-3a63f95609a7?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Oversized Street Hoodie</h3>

          <p>$89.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('AURA Linen Shirt', 75)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1602810318383-e386cc2a3ccf?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>AURA Linen Shirt</h3>

          <p>$75.00</p>

        </div>

      </div>


      <div class="product" onclick="addToCart('Minimal Cargo Pants', 95)">

        <div class="product-image">

          <img src="https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?auto=format&fit=crop&w=800&q=90">

        </div>

        <div class="product-info">

          <h3>Minimal Cargo Pants</h3>

          <p>$95.00</p>

        </div>

      </div>


    </div>

  </section>


  <!-- ================= EDITORIAL ================= -->

  <section style="padding-top:0;">

    <div class="editorial">

      <div class="editorial-image"></div>

      <div class="editorial-content">

        <small>AURA EDITORIAL 2026</small>

        <h2>Less noise.<br>More Aura.</h2>

        <p>
          Designed for those who don't follow the crowd.
          AURA blends timeless silhouettes with modern
          streetwear to create pieces made for everyday
          expression.
        </p>

        <button class="outline-btn">
          DISCOVER AURA
        </button>

      </div>

    </div>

  </section>


  <!-- ================= ABOUT ================= -->

  <section id="about">

    <div class="about">

      <small>OUR PHILOSOPHY</small>

      <h2>Style is an energy.</h2>

      <p>
        AURA is more than clothing. It's a feeling, an attitude,
        and a way of expressing who you are without saying a word.
        We create premium everyday pieces with clean silhouettes,
        refined details and a timeless point of view.
      </p>

    </div>

  </section>


  <!-- ================= NEWSLETTER ================= -->

  <section class="newsletter" id="contact">

    <h2>Join the AURA.</h2>

    <p>
      Get early access to new drops and exclusive collections.
    </p>

    <form class="newsletter-form" onsubmit="subscribe(event)">

      <input
        type="email"
        placeholder="Your email address"
        required
      >

      <button type="submit">
        JOIN
      </button>

    </form>

  </section>


  <!-- ================= FOOTER ================= -->

  <footer>

    <div class="footer-grid">

      <div class="footer-brand">

        <h2>AURA</h2>

        <p>
          Premium clothing for modern expression.
          Designed with intention. Worn with confidence.
        </p>

      </div>


      <div>

        <h4>SHOP</h4>

        <ul>
          <li>New Arrivals</li>
          <li>Women</li>
          <li>Men</li>
          <li>Essentials</li>
        </ul>

      </div>


      <div>

        <h4>HELP</h4>

        <ul>
          <li>Shipping</li>
          <li>Returns</li>
          <li>Size Guide</li>
          <li>FAQ</li>
        </ul>

      </div>


      <div>

        <h4>FOLLOW</h4>

        <ul>
          <li>Instagram</li>
          <li>TikTok</li>
          <li>Facebook</li>
          <li>Pinterest</li>
        </ul>

      </div>

    </div>


    <div class="copyright">
      © 2026 AURA. All Rights Reserved.
    </div>

  </footer>


  <!-- ================= CART ================= -->

  <div class="cart" id="cart">

    <div class="cart-header">

      <h2>Your Cart</h2>

      <span
        class="close-cart"
        onclick="closeCart()"
      >
        ×
      </span>

    </div>


    <div id="cartItems">
      <p style="color:#777;">
        Your cart is empty.
      </p>
    </div>


    <div class="cart-total">

      <h3>
        <span>Total</span>
        <span>$<span id="cartTotal">0</span></span>
      </h3>

      <button
        class="checkout"
        onclick="checkout()"
      >
        CHECKOUT
      </button>

    </div>

  </div>


  <!-- ================= JAVASCRIPT ================= -->

  <script>

    let cart = [];

    function toggleMenu() {

      document
        .getElementById("navLinks")
        .classList.toggle("active");

    }


    function openCart() {

      document
        .getElementById("cart")
        .classList.add("active");

    }


    function closeCart() {

      document
        .getElementById("cart")
        .classList.remove("active");

    }


    function addToCart(name, price) {

      cart.push({
        name: name,
        price: price
      });

      updateCart();

      openCart();

    }


    function updateCart() {

      const cartItems =
        document.getElementById("cartItems");

      const cartTotal =
        document.getElementById("cartTotal");


      if (cart.length === 0) {

        cartItems.innerHTML =
          '<p style="color:#777;">Your cart is empty.</p>';

        cartTotal.innerText = "0";

        return;

      }


      let total = 0;

      cartItems.innerHTML = "";


      cart.forEach((item, index) => {

        total += item.price;

        cartItems.innerHTML += `

          <div class="cart-item">

            <div>
              <strong>${item.name}</strong>
              <br>
              <small>$${item.price}</small>
            </div>

            <span
              style="cursor:pointer;"
              onclick="removeItem(${index})"
            >
              ×
            </span>

          </div>

        `;

      });


      cartTotal.innerText =
        total.toFixed(2);

    }


    function removeItem(index) {

      cart.splice(index, 1);

      updateCart();

    }


    function checkout() {

      if (cart.length === 0) {

        alert("Your cart is empty.");

        return;

      }

      alert(
        "Thank you for shopping with AURA! Checkout system can be connected to your payment gateway."
      );

    }


    function subscribe(event) {

      event.preventDefault();

      alert(
        "Welcome to AURA. You're now subscribed!"
      );

      event.target.reset();

    }

  </script>

</body>
</html>
