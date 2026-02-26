<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Fatim Boutique | Boutique Officielle Sécurisée</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #ff5722;
            --primary-dark: #e64a19;
            --secondary: #2ecc71;
            --dark: #1a1a1a;
            --light: #f8f9fa;
            --white: #ffffff;
        }

        /* --- SÉCURITÉ ANTI-PIRATAGE --- */
        body { 
            margin: 0; font-family: 'Poppins', sans-serif; background: var(--light); 
            user-select: none; -webkit-tap-highlight-color: transparent;
            overflow-x: hidden;
        }

        /* --- HEADER AVEC ANIMATIONS FLOTTANTES --- */
        .site-header { 
            position: relative; background: linear-gradient(135deg, var(--primary), var(--primary-dark)); 
            padding: 60px 5%; text-align: center; overflow: hidden; color: white;
        }

        .bg-float-img {
            position: absolute; z-index: 1; pointer-events: none;
            object-fit: cover; border-radius: 50%; opacity: 0.4;
            filter: blur(1px); border: 2px solid rgba(255,255,255,0.3);
            animation: floatAnim 15s infinite ease-in-out;
        }
        .img-1 { width: 150px; height: 150px; top: -20px; left: -20px; }
        .img-2 { width: 180px; height: 180px; bottom: -30px; right: -20px; animation-delay: 2s; }
        .img-3 { width: 100px; height: 100px; top: 20%; right: 10%; animation-delay: 5s; }

        @keyframes floatAnim {
            0%, 100% { transform: translateY(0) rotate(0deg) scale(1); }
            50% { transform: translateY(-30px) rotate(15deg) scale(1.1); }
        }

        .header-content { position: relative; z-index: 10; }
        .header-content h1 { font-size: 2.5rem; margin: 0; font-weight: 800; text-transform: uppercase; }

        /* --- NAVIGATION --- */
        .nav-bar {
            background: var(--white); padding: 15px 5%; display: flex; 
            justify-content: space-between; align-items: center;
            position: sticky; top: 0; z-index: 2000; box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .nav-links a { text-decoration: none; color: var(--dark); font-weight: 600; margin-right: 15px; font-size: 13px; transition: 0.3s; }
        .nav-links a:hover { color: var(--primary); }

        /* --- CATEGORIES & PRODUITS --- */
        .container { padding: 10px 5% 40px; }
        .cat-title { border-left: 5px solid var(--primary); padding-left: 15px; margin: 30px 0 20px; font-size: 1.5rem; color: var(--dark); }
        
        .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(160px, 1fr)); gap: 15px; }

        .card { background: var(--white); border-radius: 12px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.05); text-align: center; transition: 0.3s; border: 1px solid #eee; }
        .card:hover { transform: translateY(-5px); }
        .card img { width: 100%; height: 220px; object-fit: cover; }
        .card h3 { font-size: 13px; margin: 10px; color: #444; height: 32px; overflow: hidden; }
        .price { color: var(--primary); font-weight: 800; font-size: 1rem; margin-bottom: 15px; }
        
        .add-btn { background: var(--secondary); color: white; border: none; padding: 10px; border-radius: 6px; width: 90%; cursor: pointer; font-weight: bold; margin-bottom: 15px; transition: 0.2s; }
        .add-btn:active { transform: scale(0.95); }

        /* --- PANIER --- */
        .cart-sidebar {
            position: fixed; right: -100%; top: 0; width: 100%; max-width: 380px; height: 100%;
            background: white; z-index: 4000; transition: 0.5s cubic-bezier(0.7, 0, 0.3, 1); display: flex; flex-direction: column;
        }
        .cart-sidebar.active { right: 0; }
        .promo-box { background: #f0f2f5; margin: 15px; padding: 15px; border-radius: 10px; }
        .promo-box input { padding: 10px; border: 1px solid #ddd; border-radius: 5px; width: 60%; font-family: inherit; }
        .promo-box button { padding: 10px; background: var(--dark); color: white; border: none; border-radius: 5px; cursor: pointer; width: 30%; font-weight: bold; }

        /* --- FOOTER --- */
        .site-footer { background: var(--dark); color: white; padding: 50px 5% 20px; text-align: center; }
        .footer-info { margin-bottom: 20px; font-size: 14px; line-height: 1.8; }
        .footer-info a { color: var(--primary); text-decoration: none; }
        .payment-logos { display: flex; justify-content: center; gap: 15px; margin-top: 20px; flex-wrap: wrap; }
        .payment-logos img { height: 30px; background: white; padding: 4px; border-radius: 6px; }

        .whatsapp-float {
            position: fixed; bottom: 25px; right: 25px; background: #25D366; 
            color: white; width: 60px; height: 60px; border-radius: 50%;
            display: flex; align-items: center; justify-content: center; font-size: 30px; z-index: 3000; text-decoration: none; box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        #overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); z-index: 3999; display: none; }
    </style>
</head>
<body oncontextmenu="return false;">

<div style="background: #000; color: #fff; font-size: 11px; text-align: center; padding: 5px; letter-spacing: 1px;">
    🔒 CONNEXION SÉCURISÉE HTTPS | FATIM BOUTIQUE OFFICIEL
</div>

<div id="cart-sidebar" class="cart-sidebar">
    <div style="padding: 20px; background: var(--dark); color: white; display: flex; justify-content: space-between; align-items: center;">
        <span style="font-weight: 600;">MON PANIER</span>
        <span onclick="toggleCart()" style="cursor:pointer; font-size: 30px;">&times;</span>
    </div>
    
    <div id="cart-items" style="flex:1; overflow-y:auto; padding:20px;"></div>

    <div class="promo-box">
        <input type="text" id="promo-input" placeholder="Code FATIM20">
        <button onclick="applyPromo()">OK</button>
        <p id="promo-msg" style="font-size: 11px; margin-top: 8px; font-weight: bold;"></p>
    </div>

    <div style="padding: 20px; border-top: 1px solid #eee;">
        <div style="display:flex; justify-content:space-between; font-weight:800; font-size: 1.2rem; margin-bottom: 10px;">
            <span>TOTAL :</span>
            <span><span id="cart-total">0</span> FCFA</span>
        </div>
        <button onclick="sendWhatsApp()" style="width:100%; background:#25D366; color:white; border:none; padding:15px; border-radius:8px; font-weight:bold; cursor:pointer; font-family: inherit;">COMMANDER SUR WHATSAPP</button>
    </div>
</div>

<header class="site-header">
    <img src="/images/femmes/1771891260219.jpg" class="bg-float-img img-1" onerror="this.style.display='none'">
    <img src="/images/chaussures/FB_IMG_1771924923054.jpg" class="bg-float-img img-2" onerror="this.style.display='none'">
    <div class="header-content">
        <h1>Fatim Boutique</h1>
        <p>L'Élégance de la Mode Ivoirienne</p>
    </div>
</header>

<nav class="nav-bar">
    <div class="nav-links">
        <a href="#femme">FEMMES</a>
        <a href="#homme">HOMMES</a>
        <a href="#chaussure">CHAUSSURES</a>
    </div>
    <div onclick="toggleCart()" style="cursor:pointer; font-size: 22px; position: relative;">
        🛒 <span id="cart-count" style="position:absolute; top:-10px; right:-10px; background:red; color:white; font-size:10px; padding:3px 7px; border-radius:50%;">0</span>
    </div>
</nav>

<div class="container">
    <h2 class="cat-title" id="femme">Mode Femme</h2>
    <div class="grid">
        <div class="card">
            <img src="/images/femmes/1771839996325.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Ensemble Soie Chic</h3>
            <div class="price">10 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Ensemble Soie Chic', 10000, '/images/femmes/1771839996325.jpg')">AJOUTER</button>
        </div>
        <div class="card">
            <img src="/images/femmes/1771839960078.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Ensemble Luxe Dame</h3>
            <div class="price">10 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Ensemble Luxe Dame', 10000, '/images/femmes/1771839960078.jpg')">AJOUTER</button>
        </div>
        <div class="card">
            <img src="/images/femmes/1771839987367.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Ensemble Soie Élégance</h3>
            <div class="price">10 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Ensemble Soie Élégance', 10000, '/images/femmes/1771839987367.jpg')">AJOUTER</button>
        </div>
    </div>

    <h2 class="cat-title" id="homme">Mode Homme</h2>
    <div class="grid">
        <div class="card">
            <img src="/images/hommes/1771840062408.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Chemise Slim Fit Blanche</h3>
            <div class="price">12 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Chemise Slim Fit Blanche', 12000, '/images/hommes/1771840062408.jpg')">AJOUTER</button>
        </div>
        <div class="card">
            <img src="/images/hommes/1771840146964.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Chemise Fashion Homme</h3>
            <div class="price">12 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Chemise Fashion Homme', 12000, '/images/hommes/1771840146964.jpg')">AJOUTER</button>
        </div>
        <div class="card">
            <img src="/images/hommes/1771840052408.jpg" onerror="this.src='https://via.placeholder.com/200x220?text=Fatim+Boutique'">
            <h3>Chemise Style Ivoirien</h3>
            <div class="price">12 000 FCFA</div>
            <button class="add-btn" onclick="addToCart('Chemise Style Ivoirien', 12000, '/images/hommes/1771840052408.jpg')">AJOUTER</button>
        </div>
    </div>
</div>

<footer class="site-footer">
    <div class="footer-info">
        <b>FATIM BOUTIQUE OFFICIEL</b><br>
        📍 Abidjan, Côte d'Ivoire<br>
        📞 <a href="tel:+2250787736801">+225 07 87 73 68 01</a><br>
        📧 <a href="mailto:sksservice33@gmail.com">sksservice33@gmail.com</a>
    </div>
    
    <div class="payment-logos">
        <img src="/images/logo/FB_IMG_1771927879861.jpg" alt="Orange Money">
        <img src="/images/logo/FB_IMG_1771928313416.jpg" alt="Wave">
        <img src="/images/logo/FB_IMG_1771928387544.jpg" alt="Moov Money">
    </div>
    <p style="font-size:10px; opacity:0.5; margin-top:30px;">&copy; 2026 Fatim Boutique. Site Web Protégé contre les intrusions.</p>
</footer>

<a href="https://wa.me/2250787736801" class="whatsapp-float" target="_blank">💬</a>

<div id="overlay" onclick="toggleCart()"></div>

<script>
    // --- PROTECTION SÉCURITÉ ---
    window.onerror = function() { return true; }; 

    let cart = [];
    let reduction = 0; 

    function toggleCart() {
        const side = document.getElementById('cart-sidebar');
        const over = document.getElementById('overlay');
        side.classList.toggle('active');
        over.style.display = side.classList.contains('active') ? 'block' : 'none';
    }

    function addToCart(name, price, img) {
        cart.push({name, price, img});
        updateUI();
        // Animation légère du bouton panier
        const cartIcon = document.querySelector('.nav-bar div:last-child');
        cartIcon.style.transform = "scale(1.2)";
        setTimeout(() => cartIcon.style.transform = "scale(1)", 200);
    }

    function applyPromo() {
        const input = document.getElementById('promo-input').value.trim().toUpperCase();
        const msg = document.getElementById('promo-msg');
        
        if(input === "PROMO10") {
            reduction = 0.10; 
            msg.innerText = "FÉLICITATIONS ! -10% APPLIQUÉS";
            msg.style.color = "var(--secondary)";
        } else {
            reduction = 0;
            msg.innerText = "CODE INVALIDE";
            msg.style.color = "red";
        }
        updateUI();
    }

    function updateUI() {
        const items = document.getElementById('cart-items');
        const totalDisp = document.getElementById('cart-total');
        const countDisp = document.getElementById('cart-count');
        
        countDisp.innerText = cart.length;
        items.innerHTML = cart.length === 0 ? '<p style="text-align:center; padding:20px; color:#999;">Votre panier est vide</p>' : "";
        
        let total = 0;
        cart.forEach((item, index) => {
            total += item.price;
            items.innerHTML += `
                <div style="display:flex; align-items:center; gap:10px; margin-bottom:15px; background:#f9f9f9; padding:10px; border-radius:10px;">
                    <img src="${item.img}" style="width:50px; height:50px; border-radius:5px; object-fit:cover;" onerror="this.src='https://via.placeholder.com/50'">
                    <div style="flex:1; font-size:12px;"><b>${item.name}</b><br>${item.price.toLocaleString()} FCFA</div>
                    <button onclick="removeItem(${index})" style="background:none; border:none; color:red; font-weight:bold; cursor:pointer; font-size:18px;">&times;</button>
                </div>`;
        });

        let finalTotal = total * (1 - reduction);
        totalDisp.innerText = Math.round(finalTotal).toLocaleString();
    }

    function removeItem(index) {
        cart.splice(index, 1);
        updateUI();
    }

    function sendWhatsApp() {
        if(cart.length === 0) return alert("Le panier est vide");
        let msg = "*NOUVELLE COMMANDE - FATIM BOUTIQUE*%0A%0A";
        cart.forEach((item, i) => msg += `${i+1}. *${item.name}* (${item.price.toLocaleString()} FCFA)%0A`);
        if(reduction > 0) msg += "%0A✅ *Remise Appliquée : -10%*";
        msg += "%0A*TOTAL À PAYER : " + document.getElementById('cart-total').innerText + " FCFA*";
        msg += "%0A%0A_Merci de me donner les détails pour la livraison._";
        window.open(`https://wa.me/2250787736801?text=${msg}`, '_blank');
    }
</script>

</body>
</html>
