<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>FrostHaven — Winter Collection</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Lato:wght@300;400;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
    :root {
      --navy: #1a2540;
      --navy-light: #243059;
      --ice: #e8f0f7;
      --ice-dark: #cddcea;
      --frost: #f4f8fb;
      --gold: #c8a96e;
      --gold-light: #e0c98a;
      --white: #ffffff;
      --text-dark: #1a2540;
      --text-mid: #4a5568;
      --text-light: #7a8a9e;
      --card-shadow: 0 4px 24px rgba(26,37,64,0.10);
      --transition: 0.25s ease;
    }
 
    body {
      font-family: 'Lato', sans-serif;
      background: var(--frost);
      color: var(--text-dark);
      min-height: 100vh;
    }
 
    /* ── NAV ── */
    nav {
      background: var(--navy);
      padding: 0 2rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 70px;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.6rem;
      color: var(--gold);
      letter-spacing: 0.04em;
      text-decoration: none;
    }
    .nav-logo span { color: var(--white); }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      color: var(--ice);
      text-decoration: none;
      font-size: 0.9rem;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      font-weight: 700;
      transition: color var(--transition);
    }
    .nav-links a:hover { color: var(--gold); }
    .cart-icon {
      color: var(--white);
      font-size: 1.5rem;
      cursor: pointer;
      position: relative;
    }
    .cart-count {
      position: absolute;
      top: -8px;
      right: -8px;
      background: var(--gold);
      color: var(--navy);
      border-radius: 50%;
      width: 18px;
      height: 18px;
      font-size: 0.65rem;
      font-weight: 700;
      display: flex;
      align-items: center;
      justify-content: center;
    }
 
    /* ── HERO ── */
    .hero {
      background: linear-gradient(135deg, var(--navy) 0%, var(--navy-light) 60%, #2d4a7a 100%);
      color: var(--white);
      text-align: center;
      padding: 90px 2rem 80px;
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='60' height='60'%3E%3Ccircle cx='4' cy='4' r='1.5' fill='%23ffffff' opacity='0.07'/%3E%3Ccircle cx='30' cy='15' r='1' fill='%23ffffff' opacity='0.05'/%3E%3Ccircle cx='52' cy='8' r='1.2' fill='%23ffffff' opacity='0.06'/%3E%3Ccircle cx='14' cy='40' r='0.8' fill='%23ffffff' opacity='0.04'/%3E%3Ccircle cx='45' cy='48' r='1.5' fill='%23ffffff' opacity='0.05'/%3E%3C/svg%3E") repeat;
      pointer-events: none;
    }
    .hero-eyebrow {
      font-size: 0.8rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold-light);
      font-weight: 700;
      margin-bottom: 1rem;
    }
    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 6vw, 4.2rem);
      font-weight: 700;
      line-height: 1.12;
      margin-bottom: 1.2rem;
    }
    .hero h1 em {
      font-style: italic;
      color: var(--gold-light);
    }
    .hero p {
      font-size: 1.1rem;
      font-weight: 300;
      color: var(--ice);
      max-width: 500px;
      margin: 0 auto 2.4rem;
      line-height: 1.7;
    }
    .hero-cta {
      display: inline-block;
      background: var(--gold);
      color: var(--navy);
      text-decoration: none;
      padding: 0.9rem 2.4rem;
      border-radius: 3px;
      font-weight: 700;
      font-size: 0.9rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: background var(--transition), transform var(--transition);
    }
    .hero-cta:hover { background: var(--gold-light); transform: translateY(-2px); }
 
    /* ── SECTION ── */
    .section { max-width: 1160px; margin: 0 auto; padding: 70px 2rem; }
    .section-header { text-align: center; margin-bottom: 3rem; }
    .section-eyebrow {
      font-size: 0.75rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 700;
      margin-bottom: 0.6rem;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.8rem, 3.5vw, 2.6rem);
      color: var(--navy);
      font-weight: 600;
    }
 
    /* ── FILTERS ── */
    .filters {
      display: flex;
      gap: 0.6rem;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 2.8rem;
    }
    .filter-btn {
      background: var(--white);
      border: 1.5px solid var(--ice-dark);
      color: var(--text-mid);
      padding: 0.45rem 1.2rem;
      border-radius: 30px;
      font-size: 0.85rem;
      font-weight: 700;
      cursor: pointer;
      transition: all var(--transition);
      font-family: 'Lato', sans-serif;
      letter-spacing: 0.04em;
    }
    .filter-btn:hover, .filter-btn.active {
      background: var(--navy);
      border-color: var(--navy);
      color: var(--white);
    }
 
    /* ── GRID ── */
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(270px, 1fr));
      gap: 2rem;
    }
 
    /* ── CARD ── */
    .product-card {
      background: var(--white);
      border-radius: 8px;
      overflow: hidden;
      box-shadow: var(--card-shadow);
      transition: transform var(--transition), box-shadow var(--transition);
      display: flex;
      flex-direction: column;
    }
    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 12px 36px rgba(26,37,64,0.15);
    }
    .card-image {
      width: 100%;
      aspect-ratio: 4/3;
      object-fit: cover;
      background: var(--ice);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 5rem;
      position: relative;
    }
    .card-badge {
      position: absolute;
      top: 14px;
      left: 14px;
      background: var(--navy);
      color: var(--gold);
      font-size: 0.7rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      padding: 4px 10px;
      border-radius: 3px;
    }
    .card-body {
      padding: 1.2rem 1.4rem 1.4rem;
      display: flex;
      flex-direction: column;
      flex: 1;
    }
    .card-category {
      font-size: 0.72rem;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: var(--text-light);
      font-weight: 700;
      margin-bottom: 0.4rem;
    }
    .card-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.15rem;
      color: var(--navy);
      margin-bottom: 0.5rem;
      font-weight: 600;
      line-height: 1.3;
    }
    .card-desc {
      font-size: 0.88rem;
      color: var(--text-mid);
      line-height: 1.6;
      flex: 1;
      margin-bottom: 1.1rem;
    }
    .card-footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.8rem;
    }
    .card-price {
      font-size: 1.4rem;
      font-weight: 700;
      color: var(--navy);
    }
    .card-price-old {
      font-size: 0.9rem;
      color: var(--text-light);
      text-decoration: line-through;
      font-weight: 400;
    }
    .add-btn {
      background: var(--navy);
      color: var(--white);
      border: none;
      padding: 0.6rem 1.2rem;
      border-radius: 4px;
      font-size: 0.82rem;
      font-weight: 700;
      letter-spacing: 0.06em;
      text-transform: uppercase;
      cursor: pointer;
      transition: background var(--transition), transform var(--transition);
      font-family: 'Lato', sans-serif;
      white-space: nowrap;
    }
    .add-btn:hover { background: var(--gold); color: var(--navy); }
    .add-btn:active { transform: scale(0.97); }
    .add-btn.added { background: #2d7a4f; }
 
    /* ── FEATURES STRIP ── */
    .features {
      background: var(--navy);
      color: var(--white);
      padding: 3rem 2rem;
    }
    .features-inner {
      max-width: 1160px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 2rem;
      text-align: center;
    }
    .feature-icon { font-size: 2rem; margin-bottom: 0.7rem; }
    .feature-title {
      font-family: 'Playfair Display', serif;
      font-size: 1rem;
      color: var(--gold);
      margin-bottom: 0.35rem;
    }
    .feature-desc { font-size: 0.85rem; color: var(--ice); line-height: 1.6; }
 
    /* ── CART TOAST ── */
    .toast {
      position: fixed;
      bottom: 2rem;
      right: 2rem;
      background: var(--navy);
      color: var(--white);
      padding: 0.9rem 1.5rem;
      border-radius: 6px;
      font-size: 0.9rem;
      font-weight: 700;
      border-left: 4px solid var(--gold);
      transform: translateY(120%);
      transition: transform 0.3s ease;
      z-index: 200;
    }
    .toast.show { transform: translateY(0); }
 
    /* ── FOOTER ── */
    footer {
      background: var(--navy);
      color: var(--ice);
      text-align: center;
      padding: 2.4rem 1rem;
      font-size: 0.85rem;
    }
    footer strong { color: var(--gold); font-family: 'Playfair Display', serif; font-size: 1rem; }
 
    @media (max-width: 600px) {
      .nav-links { display: none; }
      .hero { padding: 60px 1.2rem 60px; }
    }
  </style>
</head>
<body>
 
<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Frost<span>Haven</span></a>
  <ul class="nav-links">
    <li><a href="#shop">Shop</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <div class="cart-icon" onclick="openCart()">
    🛒 <span class="cart-count" id="cartCount">0</span>
  </div>
</nav>
 
<!-- HERO -->
<section class="hero">
  <p class="hero-eyebrow">New Winter Collection 2025</p>
  <h1>Stay Warm.<br /><em>Stay Stylish.</em></h1>
  <p>Premium winter essentials crafted for cold days. From cozy knitwear to weatherproof outerwear — everything you need for the season.</p>
  <a href="#shop" class="hero-cta">Shop the Collection</a>
</section>
 
<!-- SHOP -->
<section class="section" id="shop">
  <div class="section-header">
    <p class="section-eyebrow">Winter Essentials</p>
    <h2 class="section-title">Our Collection</h2>
  </div>
 
  <div class="filters">
    <button class="filter-btn active" onclick="filterProducts('all', this)">All Items</button>
    <button class="filter-btn" onclick="filterProducts('outerwear', this)">Outerwear</button>
    <button class="filter-btn" onclick="filterProducts('knitwear', this)">Knitwear</button>
    <button class="filter-btn" onclick="filterProducts('accessories', this)">Accessories</button>
    <button class="filter-btn" onclick="filterProducts('footwear', this)">Footwear</button>
  </div>
 
  <div class="products-grid" id="productsGrid"></div>
</section>
 
<!-- FEATURES -->
<section class="features">
  <div class="features-inner">
    <div>
      <div class="feature-icon">🚚</div>
      <p class="feature-title">Free Delivery</p>
      <p class="feature-desc">Free shipping on all orders over R800. Fast delivery nationwide.</p>
    </div>
    <div>
      <div class="feature-icon">🔄</div>
      <p class="feature-title">Easy Returns</p>
      <p class="feature-desc">30-day hassle-free returns on all unworn items.</p>
    </div>
    <div>
      <div class="feature-icon">🛡️</div>
      <p class="feature-title">Quality Guarantee</p>
      <p class="feature-desc">Every item tested for warmth, durability, and comfort.</p>
    </div>
    <div>
      <div class="feature-icon">💳</div>
      <p class="feature-title">Secure Checkout</p>
      <p class="feature-desc">Encrypted payments. Your data is always safe.</p>
    </div>
  </div>
</section>
 
<!-- FOOTER -->
<footer id="contact">
  <p><strong>FrostHaven</strong></p>
  <p style="margin-top:0.5rem;">contact@frosthaven.co.za &nbsp;|&nbsp; +27 (0)12 555 0199</p>
  <p style="margin-top:0.5rem; opacity:0.5;">© 2025 FrostHaven. All rights reserved.</p>
</footer>
 
<!-- TOAST -->
<div class="toast" id="toast">✓ Added to cart!</div>
 
<script>
  const products = [
    {
      id: 1, name: "Alpine Down Parka", category: "outerwear",
      price: 2499, oldPrice: 3199,
      emoji: "🧥", badge: "Best Seller",
      desc: "Water-resistant shell with 650-fill duck down. Adjustable hood, zip storm flap, and deep hand pockets. Warmth rated to -20°C."
    },
    {
      id: 2, name: "Merino Cable-Knit Sweater", category: "knitwear",
      price: 899, oldPrice: null,
      emoji: "🧶", badge: null,
      desc: "100% extra-fine merino wool. Classic cable-knit pattern, ribbed cuffs and hem. Naturally odour-resistant and temperature regulating."
    },
    {
      id: 3, name: "Sherpa-Lined Beanie", category: "accessories",
      price: 249, oldPrice: null,
      emoji: "🎩", badge: "New",
      desc: "Double-layer knit exterior with plush sherpa lining. Slouchy fit, one size fits all. Available in 8 seasonal colours."
    },
    {
      id: 4, name: "Thermal Snow Boots", category: "footwear",
      price: 1649, oldPrice: 1999,
      emoji: "👢", badge: "Sale",
      desc: "Waterproof suede upper with 200g Thinsulate insulation. Non-slip Vibram outsole rated to -40°C. Perfect for ice and snow."
    },
    {
      id: 5, name: "Wool Tartan Scarf", category: "accessories",
      price: 349, oldPrice: null,
      emoji: "🧣", badge: null,
      desc: "Generous 210cm x 35cm pure lambswool scarf in a classic tartan weave. Fringed ends. Wrap twice for extra warmth."
    },
    {
      id: 6, name: "Fleece-Lined Joggers", category: "knitwear",
      price: 699, oldPrice: 849,
      emoji: "👖", badge: "Sale",
      desc: "Brushed fleece interior on a water-repellent shell. Elasticated waist with drawstring, deep side pockets. Tapered leg."
    },
    {
      id: 7, name: "Insulated Ski Gloves", category: "accessories",
      price: 449, oldPrice: null,
      emoji: "🧤", badge: null,
      desc: "Touchscreen-compatible fingertips. PrimaLoft Gold insulation, reinforced palm, adjustable cuff. Waterproof GORE-TEX insert."
    },
    {
      id: 8, name: "Trench Coat — Wool Blend", category: "outerwear",
      price: 3299, oldPrice: null,
      emoji: "🪡", badge: "New",
      desc: "60% wool 40% cashmere blend outer with a satin lining. Double-breasted with storm flap, belt and oversized lapels."
    },
  ];
 
  let cartCount = 0;
  let currentFilter = 'all';
 
  function renderProducts(filter) {
    const grid = document.getElementById('productsGrid');
    const filtered = filter === 'all' ? products : products.filter(p => p.category === filter);
    grid.innerHTML = filtered.map(p => `
      <div class="product-card" data-category="${p.category}">
        <div class="card-image">
          ${p.emoji}
          ${p.badge ? `<span class="card-badge">${p.badge}</span>` : ''}
        </div>
        <div class="card-body">
          <p class="card-category">${p.category}</p>
          <h3 class="card-name">${p.name}</h3>
          <p class="card-desc">${p.desc}</p>
          <div class="card-footer">
            <div>
              <div class="card-price">R${p.price.toLocaleString()}</div>
              ${p.oldPrice ? `<div class="card-price-old">R${p.oldPrice.toLocaleString()}</div>` : ''}
            </div>
            <button class="add-btn" onclick="addToCart(this, '${p.name}')">Add to Cart</button>
          </div>
        </div>
      </div>
    `).join('');
  }
 
  function filterProducts(cat, btn) {
    currentFilter = cat;
    document.querySelectorAll('.filter-btn').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    renderProducts(cat);
  }
 
  function addToCart(btn, name) {
    cartCount++;
    document.getElementById('cartCount').textContent = cartCount;
    btn.textContent = '✓ Added!';
    btn.classList.add('added');
    setTimeout(() => {
      btn.textContent = 'Add to Cart';
      btn.classList.remove('added');
    }, 1800);
    showToast(`"${name}" added to cart`);
  }
 
  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = '✓ ' + msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 2500);
  }
 
  function openCart() {
    if (cartCount === 0) {
      showToast('Your cart is empty');
    } else {
      showToast(`${cartCount} item${cartCount > 1 ? 's' : ''} in your cart`);
    }
  }
 
  renderProducts('all');
</script>
</body>
</html>
 

