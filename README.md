<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AV-GO Store</title>
    <style>
        body { margin: 0; font-family: sans-serif; background: #fff; color: #333; overflow-x: hidden; }
        .hidden { display: none !important; }
        
        /* Header & Search */
        .header { padding: 15px; border-bottom: 1px solid #eee; position: sticky; top: 0; background: white; z-index: 100; }
        .search-container { position: relative; margin-top: 10px; }
        .search-bar { width: 92%; background: #f3f4f6; padding: 12px 4%; border-radius: 10px; color: #333; border: 1px solid #eee; outline: none; font-size: 14px; }

        /* Category Home Grid - UPDATED ICON SIZES */
        .grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 15px; padding: 20px; }
        .cat-card { text-align: center; cursor: pointer; text-decoration: none; color: inherit; }
        .icon-box { 
            height: 110px; /* Increased from 90px */
            border-radius: 25px; 
            display: flex; 
            align-items: center; 
            justify-content: center; 
            margin-bottom: 8px; 
            border: 1px solid #eee; 
            transition: 0.2s;
            font-size: 45px; /* Increased emoji size */
        }

        /* Category Page Styles */
        .page-header { padding: 15px; display: flex; align-items: center; gap: 15px; color: white; position: sticky; top: 0; z-index: 100; }
        .tabs { display: flex; overflow-x: auto; gap: 10px; padding: 12px; background: #f8f9fa; border-bottom: 1px solid #eee; scrollbar-width: none; }
        .tab { background: #eee; padding: 8px 18px; border-radius: 20px; white-space: nowrap; font-size: 12px; font-weight: bold; color: #555; cursor: pointer; }
        .active-tab { background: #ffc107; color: black; }

        /* Product Grid */
        .product-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; padding: 12px; }
        .product-card { background: white; border: 1px solid #eee; border-radius: 12px; padding: 10px; text-align: center; box-shadow: 0 2px 5px rgba(0,0,0,0.05); display: flex; flex-direction: column; justify-content: space-between; }
        .img-container { height: 120px; display: flex; align-items: center; justify-content: center; margin-bottom: 8px; background: #fff; border-radius: 8px; }
        .product-img { max-width: 100%; max-height: 100%; object-fit: contain; }
        .product-title { font-size: 11px; font-weight: 600; color: #333; height: 40px; overflow: hidden; text-align: left; line-height: 1.2; margin-bottom: 4px; }
        .price { font-size: 16px; font-weight: 800; color: #000; margin: 4px 0; text-align: left; }
        .buy-btn { display: block; background: #FFD814; color: black; text-align: center; padding: 8px; text-decoration: none; border-radius: 8px; font-size: 11px; font-weight: bold; border: 1px solid #FCD200; }
        
        .footer-msg { text-align: center; padding: 30px 20px; color: #666; font-size: 13px; font-weight: 600; border-top: 1px solid #eee; margin-top: 20px; line-height: 1.5; }
    </style>
</head>
<body>

    <div id="home-page">
        <div class="header">
            <div style="font-weight: 800; font-size: 18px;">AV-GO Store</div>
            <div style="color: #666; font-size: 12px;">Shop by Department</div>
            <div class="search-container">
                <input type="text" id="searchInput" placeholder="🔍 Search categories..." class="search-bar">
            </div>
        </div>

        <h3 style="padding: 0 20px; margin-top: 20px; font-size: 16px;">What are you looking for?</h3>
        
        <div class="grid" id="categoryGrid">
            <div class="cat-card" onclick="switchPage('electronics-page')">
                <div class="icon-box" style="background: #f0f5ff;">📱</div>
                <p style="font-size: 11px; font-weight: 600;">Electronics</p>
            </div>
            <div class="cat-card" onclick="switchPage('clothes-page')">
                <div class="icon-box" style="background: #f5f0ff;">👕</div>
                <p style="font-size: 11px; font-weight: 600;">Clothes</p>
            </div>
            <div class="cat-card" onclick="switchPage('games-page')">
                <div class="icon-box" style="background: #fff0f0;">🎮</div>
                <p style="font-size: 11px; font-weight: 600;">Games</p>
            </div>
        </div>
        <div class="footer-msg">Press view deal and brouse all of our products</div>
    </div>

    <div id="electronics-page" class="hidden">
        <div class="page-header" style="background: #232f3e;">
            <div onclick="switchPage('home-page')" style="color: #ffc107; font-size: 24px; cursor: pointer;">←</div>
            <div style="font-weight: bold;">Electronics</div>
        </div>
        
        <div class="tabs">
            <div id="tab-cables" class="tab active-tab" onclick="showSubCat('cables')">Cables</div>
            <div id="tab-chargers" class="tab" onclick="showSubCat('chargers')">Chargers</div>
        </div>
        
        <div id="sec-cables" class="product-grid">
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/ZRTRx38G/61-TAAu1-Lrq-L-AC-AIweblab1006854-T4-FMavif-SF1050-1050-PQ64.avif" class="product-img"></div>
                <div class="product-title">Portronics Konnect L 1.2M Fast Charging Cable</div>
                <div class="price">₹119</div>
                <a href="https://amzn.to/4c989w7" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/LXL4nBwK/81u-Olhjs-OQL-AC-AIweblab1006854-T4-FMavif-SF1050-1050-PQ64.avif" class="product-img"></div>
                <div class="product-title">Duracell Braided Type C Charging Cable</div>
                <div class="price">₹239</div>
                <a href="https://amzn.to/4cuPa0n" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/jvWpDHtj/61-W8xe-ZTwx-L-AC-AIweblab1006854-T4-FMavif-SF1050-1050-PQ64.avif" class="product-img"></div>
                <div class="product-title">Ambrane Unbreakable 60W Type-C Cable</div>
                <div class="price">₹199</div>
                <a href="https://amzn.to/41lR5y5" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/7NNjbx1R/51m-QCeln-SFL-AC-AIweblab1006854-T4-FMavif-SF1050-1050-PQ64.avif" class="product-img"></div>
                <div class="product-title">Zebronics High Speed Data Cable</div>
                <div class="price">₹99</div>
                <a href="https://amzn.to/4vfiCyP" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/gZxfGZFh/81-Fx-WPmph-CL-AC-AIweblab1006854-T4-FMavif-SF1050-1050-PQ64-1.avif" class="product-img"></div>
                <div class="product-title">Xiaomi 2-in-1 Premium Cable</div>
                <div class="price">₹699</div>
                <a href="https://amzn.to/4mcWcdo" target="_blank" class="buy-btn">View Deal</a>
            </div>
        </div>

        <div id="sec-chargers" class="product-grid hidden">
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/JRhc5c77/4109y-UIu2s-L-MCnd-AC.jpg" class="product-img"></div>
                <div class="product-title">Portronics Adapto 20 Type C Fast Charger</div>
                <div class="price">₹449</div>
                <a href="https://www.amazon.in/dp/B09NJKMYVC/?tag=avgo08-21" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/1YqJf0hH/216-RQn6-Mvr-L-MCnd-AC.jpg" class="product-img"></div>
                <div class="product-title">Ambrane 20W Fast Charging Wall Adaptor</div>
                <div class="price">₹349</div>
                <a href="https://www.amazon.in/dp/B0BBRJVLWD/?tag=avgo08-21" target="_blank" class="buy-btn">View Deal</a>
            </div>
            <div class="product-card">
                <div class="img-container"><img src="https://i.ibb.co/xqBqQ9RF/31thq-OHab-EL-MCnd-AC.jpg" class="product-img"></div>
                <div class="product-title">Mi 33W SonicCharge 2.0 Fast Charger</div>
                <div class="price">₹699</div>
                <a href="https://www.amazon.in/dp/B0FQ5NFDML/?tag=avgo08-21" target="_blank" class="buy-btn">View Deal</a>
            </div>
        </div>
        
        <div class="footer-msg">Press view deal and brouse all of our products</div>
    </div>

    <div id="clothes-page" class="hidden">
        <div class="page-header" style="background: #2d3436;"><div onclick="switchPage('home-page')" style="color: #ffc107; font-size: 24px; cursor: pointer;">←</div><div style="font-weight: bold;">Clothes</div></div>
        <div style="text-align: center; padding: 50px 20px; color: #888;">🛍️ Coming Soon</div>
        <div class="footer-msg">Press view deal and brouse all of our products</div>
    </div>

    <div id="games-page" class="hidden">
        <div class="page-header" style="background: #5d4037;"><div onclick="switchPage('home-page')" style="color: #ffc107; font-size: 24px; cursor: pointer;">←</div><div style="font-weight: bold;">Games</div></div>
        <div style="text-align: center; padding: 50px 20px; color: #888;">🎲 Coming Soon</div>
        <div class="footer-msg">Press view deal and brouse all of our products</div>
    </div>

    <script>
        function switchPage(pageId) {
            document.getElementById('home-page').classList.add('hidden');
            document.getElementById('electronics-page').classList.add('hidden');
            document.getElementById('clothes-page').classList.add('hidden');
            document.getElementById('games-page').classList.add('hidden');
            document.getElementById(pageId).classList.remove('hidden');
            window.scrollTo(0,0);
        }

        function showSubCat(cat) {
            document.getElementById('sec-cables').classList.add('hidden');
            document.getElementById('sec-chargers').classList.add('hidden');
            document.getElementById('tab-cables').classList.remove('active-tab');
            document.getElementById('tab-chargers').classList.remove('active-tab');
            
            document.getElementById('sec-' + cat).classList.remove('hidden');
            document.getElementById('tab-' + cat).classList.add('active-tab');
        }
    </script>
</body>
</html>
