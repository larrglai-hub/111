<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>精品咖啡豆 - Coffee Roasters</title>
    <style>
        body { 
            font-family: 'Noto Sans TC', sans-serif; 
            margin: 0; 
            padding: 0; 
            
            /* 淺咖啡色底與指定的浮水印底圖 */
            background-color: #F4E7D3;
            background-image: 
                linear-gradient(rgba(244, 231, 211, 0.88), rgba(244, 231, 211, 0.88)), 
                url('https://6ac085fa734225d0baef3e5c.imgix.net/sandbox/20240129-odaPN4kWszLCS2T913gJVXh22aNHHjtAhD6VQRYw.jpg'); 
            background-size: cover; 
            background-attachment: fixed; 
            background-position: center; 
            
            color: #333;
        }
        /* Header */
        header { 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            padding: 15px 40px; 
            background: white; 
            border-bottom: 1px solid #eee; 
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .logo { 
            font-size: 26px; 
            font-weight: 900; 
            color: #4A2E1B; 
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .nav-links { 
            display: flex; 
            gap: 30px; 
        }
        .nav-links a { 
            text-decoration: none; 
            color: #333; 
            font-weight: 500; 
            font-size: 15px;
        }
        .nav-links a:hover {
            color: #d9a05b;
        }
        .actions { 
            display: flex; 
            gap: 20px; 
            align-items: center; 
        }
        .search-bar { 
            padding: 8px 15px; 
            border-radius: 20px; 
            border: 1px solid #ccc; 
            background: #f1f1f1;
            outline: none;
        }
        .icon { font-size: 20px; cursor: pointer; }

        /* Main Hero Section */
        .hero { 
            display: flex; 
            gap: 20px; 
            padding: 20px 40px; 
            max-width: 1400px; 
            margin: 0 auto; 
        }
        .hero-main { 
            flex: 2.5; 
            background: #ddd; 
            height: 450px; 
            border-radius: 8px; 
            display: flex; 
            align-items: flex-end; 
            justify-content: flex-start; 
            background-image: url('https://images.unsplash.com/photo-1497935586351-b67a49e012bf?auto=format&fit=crop&w=1200&q=80'); 
            background-size: cover; 
            background-position: center; 
            position: relative;
            padding: 30px;
            box-sizing: border-box;
        }
        .hero-main::after {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.6) 0%, rgba(0,0,0,0) 50%);
            border-radius: 8px;
        }
        .hero-main-title {
            position: relative;
            z-index: 1;
            color: white; 
            font-size: 36px; 
            font-weight: bold; 
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
        .hero-side { 
            flex: 1; 
            display: flex; 
            flex-direction: column; 
            gap: 20px; 
        }
        .hero-side-top { 
            flex: 1; 
            background: #ccc; 
            border-radius: 8px; 
            background-image: url('https://images.unsplash.com/photo-1611162458324-aae1eb4129a4?auto=format&fit=crop&w=600&q=80'); 
            background-size: cover; 
            background-position: center;
        }
        .hero-side-text { 
            flex: 1;
            background: white; 
            padding: 25px; 
            border-radius: 8px; 
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .hero-side-text h3 { margin: 0 0 10px 0; font-size: 20px; color: #4A2E1B;}
        .hero-side-text p { color: #666; font-size: 14px; line-height: 1.6; margin-bottom: 15px;}
        .hero-side-text a { color: #0066cc; text-decoration: none; font-size: 14px; font-weight: bold;}

        /* Products Section */
        .products { 
            display: grid; 
            grid-template-columns: repeat(4, 1fr); 
            gap: 20px; 
            padding: 20px 40px 60px; 
            max-width: 1400px; 
            margin: 0 auto; 
        }
        .product-card { 
            background: white; 
            padding: 20px; 
            border-radius: 8px; 
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
            transition: transform 0.2s;
        }
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        .product-img { 
            width: 100%; 
            height: 250px; 
            object-fit: cover; 
            border-radius: 6px; 
            margin-bottom: 15px;
        }
        .badges { 
            display: flex; 
            gap: 8px; 
            margin-bottom: 10px; 
        }
        .badge { 
            background: #d9a05b; 
            color: white; 
            padding: 4px 8px; 
            font-size: 12px; 
            border-radius: 4px; 
            font-weight: bold;
        }
        .badge.dark { background: #4A2E1B; }
        .product-title { 
            font-size: 16px; 
            margin: 0 0 10px 0; 
            font-weight: bold; 
            line-height: 1.4;
            height: 44px;
            overflow: hidden;
        }
        .price-section {
            display: flex;
            flex-direction: column;
            gap: 2px;
        }
        .price { 
            color: #999; 
            text-decoration: line-through; 
            font-size: 13px; 
        }
        .discount-price { 
            color: #d32f2f; 
            font-size: 22px; 
            font-weight: bold; 
        }
        .actions-bottom {
            display: flex;
            justify-content: flex-end;
            gap: 15px;
            margin-top: -25px;
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .hero { flex-direction: column; }
            .hero-main { height: 350px; }
            .hero-side { flex-direction: row; height: 200px; }
            .products { grid-template-columns: repeat(2, 1fr); }
        }
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero-side { flex-direction: column; height: auto; }
            .hero-side-top { height: 200px; }
            .products { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <!-- Header Area -->
    <header>
        <div class="logo">☕ Coffee Roasters</div>
        <div class="nav-links">
            <a href="#">產區分類 ∨</a>
            <a href="#">烘焙程度 ∨</a>
            <a href="#">手沖器具 ∨</a>
            <a href="#">莊園豆專區 ∨</a>
            <a href="#">門市資訊</a>
        </div>
        <div class="actions">
            <input type="text" class="search-bar" placeholder="搜尋咖啡豆...">
            <span class="icon">📱</span>
            <span class="icon">👤</span>
            <span class="icon">🛒 <span style="font-size:14px; background:#d9a05b; color:white; border-radius:50%; padding:2px 6px;">0</span></span>
        </div>
    </header>

    <!-- Hero Section (Banners) -->
    <section class="hero">
        <div class="hero-main">
            <div class="hero-main-title">精品莊園咖啡，新鮮烘焙直送</div>
        </div>
        <div class="hero-side">
            <div class="hero-side-top"></div>
            <div class="hero-side-text">
                <h3>淺焙水洗技術</h3>
                <p>專業的淺焙技術，保留咖啡豆最豐富的果香與花香。採用世界頂級莊園豆，每一口都充滿健康與美味層次，為您的早晨帶來全新體驗。</p>
                <a href="#">去看看</a>
            </div>
        </div>
    </section>

    <!-- Product Grid -->
    <section class="products">
        <!-- Product 1 -->
        <div class="product-card">
            <img src="https://images.unsplash.com/photo-1559525839-b184a4d698c7?auto=format&fit=crop&w=400&q=80" class="product-img" alt="衣索比亞 耶加雪菲">
            <div class="badges">
                <span class="badge dark">淺焙</span>
                <span class="badge">水洗</span>
                <span class="badge" style="background:#e63946;">2026 新產季</span>
            </div>
            <h4 class="product-title">【衣索比亞】耶加雪菲 果丁丁合作社 G1 咖啡豆 225g</h4>
            <div class="price-section">
                <span class="price">NT$650</span>
                <span class="discount-price">NT$450</span>
            </div>
            <div class="actions-bottom">
                <span class="icon">♡</span>
                <span class="icon">🛒</span>
            </div>
        </div>

        <!-- Product 2 -->
        <div class="product-card">
            <img src="https://images.unsplash.com/photo-1587734195503-904fca47e0e9?auto=format&fit=crop&w=400&q=80" class="product-img" alt="肯亞 AA">
            <div class="badges">
                <span class="badge dark">中焙</span>
                <span class="badge">水洗</span>
            </div>
            <h4 class="product-title">【肯亞】AA 祈安布 頂級莊園 咖啡豆 225g (濃郁黑莓調)</h4>
            <div class="price-section">
                <span class="price">NT$750</span>
                <span class="discount-price">NT$550</span>
            </div>
            <div class="actions-bottom">
                <span class="icon">♡</span>
                <span class="icon">🛒</span>
            </div>
        </div>
    </section>
</body>
</html>