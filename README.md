<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RRX | YOUR AURA, YOUR RULES</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-pure: #000000;
            --rrx-red: #ff0000;
            --rrx-glow: rgba(255, 0, 0, 0.6);
            --glass: rgba(255, 255, 255, 0.03);
        }

        /* Basic Setup */
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background-color: var(--bg-pure); color: #ffffff; overflow-x: hidden; }

        /* --- Fix: Header Layer Issue --- */
        header {
            padding: 20px 5%; 
            display: flex; 
            justify-content: center; 
            align-items: center;
            background: #000000; /* Solid Black Background */
            border-bottom: 2px solid var(--rrx-red);
            box-shadow: 0 5px 25px var(--rrx-glow);
            position: sticky; 
            top: 0; 
            z-index: 999; /* Higher than everything else */
        }

        .brand-name {
            font-family: 'Orbitron', sans-serif; 
            font-size: clamp(28px, 5vw, 40px);
            font-weight: 800; 
            color: var(--rrx-red); 
            text-shadow: 0 0 20px var(--rrx-red); 
            letter-spacing: 8px;
        }

        /* --- Welcome Overlay --- */
        #welcome-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(20px);
            z-index: 10000; /* Must be highest */
            display: flex; justify-content: center; align-items: center;
            transition: 1s ease;
        }

        .welcome-card {
            max-width: 550px; width: 90%;
            background: #080808; border: 1px solid var(--rrx-red);
            border-radius: 20px; padding: 40px; text-align: center;
            box-shadow: 0 0 40px rgba(255, 0, 0, 0.2);
        }

        .continue-btn {
            background: transparent; border: 2px solid var(--rrx-red); color: white;
            padding: 15px 45px; font-family: 'Orbitron', sans-serif; font-weight: bold;
            text-transform: uppercase; cursor: pointer; transition: 0.3s;
        }
        .continue-btn:hover { background: var(--rrx-red); box-shadow: 0 0 20px var(--rrx-red); }

        /* --- Hero Section --- */
        .hero {
            height: 50vh; display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center;
            background: radial-gradient(circle, rgba(255, 0, 0, 0.1) 0%, rgba(0,0,0,1) 80%);
            padding: 20px;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif; 
            font-size: clamp(40px, 10vw, 80px);
            background: linear-gradient(to bottom, #fff 40%, var(--rrx-red));
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }

        .aura-text {
            font-family: 'Orbitron', sans-serif; letter-spacing: 5px;
            color: #fff; margin-top: 10px; animation: glow 3s infinite;
        }
        @keyframes glow { 0%, 100% { opacity: 0.7; } 50% { opacity: 1; text-shadow: 0 0 15px var(--rrx-red); } }

        /* --- Product Grid & Cards --- */
        .grid { 
            display: grid; 
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); 
            gap: 30px; padding: 50px 5%; 
            max-width: 1400px; margin: 0 auto;
            position: relative; 
            z-index: 1; /* Lower than header */
        }
        
        .product-card { 
            position: relative;
            background: var(--glass); 
            border: 1px solid #1a1a1a; 
            border-radius: 15px; 
            padding: 25px; 
            text-align: center; 
            transition: 0.4s;
            z-index: 2; /* Lower than header */
        }

        .product-card:hover { border-color: var(--rrx-red); transform: translateY(-10px); }

        .badge {
            position: absolute; top: 15px; right: 15px;
            padding: 5px 12px; font-size: 11px; font-weight: bold; border-radius: 4px;
            z-index: 10;
        }
        .stock-out { background: #222; color: #777; }
        .offer-tag { background: var(--rrx-red); color: white; box-shadow: 0 0 10px var(--rrx-red); }

        .img-box { 
            background: #050505; height: 250px; border-radius: 10px; 
            overflow: hidden; margin-bottom: 20px; border: 1px solid #111;
            display: flex; align-items: center; justify-content: center;
        }

        .img-box img {
            width: 100%; height: 100%; object-fit: contain; padding: 10px;
        }

        .price { font-size: 28px; color: var(--rrx-red); font-weight: bold; margin: 15px 0; display: block; }

        .rrx-btn {
            padding: 12px 25px; background: transparent;
            border: 1px solid #333; color: #444; font-family: 'Orbitron', sans-serif;
            cursor: not-allowed; border-radius: 4px;
        }

        footer { text-align: center; padding: 40px; border-top: 1px solid #1a1a1a; color: #444; font-size: 12px; }
    </style>
</head>
<body>

    <div id="welcome-overlay">
        <div class="welcome-card">
            <h2 style="font-family: 'Orbitron'; color: var(--rrx-red); margin-bottom: 20px;">RRX STUDIOS</h2>
            <p style="color: #bbb; line-height: 1.6; margin-bottom: 20px;">আপনার বিশ্বস্ত গেমিং মার্কেটপ্লেস। দ্রুত ডেলিভারি ও সিকিউর লেনদেনের নিশ্চয়তা।</p>
            <button class="continue-btn" onclick="enterSite()">Enter RRX CORE</button>
        </div>
    </div>

    <header>
        <div class="brand-name">RRX</div>
    </header>

    <main>
        <section class="hero">
            <h1>RRX CORE</h1>
            <p class="aura-text">YOUR AURA, YOUR RULES</p>
        </section>

        <div class="grid">
            <div class="product-card">
                <div class="badge offer-tag">OFFER (STOCK OUT)</div>
                <div class="img-box"><img src="mccombo.png"></div>
                <h3 style="font-size: 18px; min-height: 50px;">Minecraft Java + Bedrock Edition (Combo)</h3>
                <span class="price">৳ 2,000</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
            </div>

            <div class="product-card">
                <div class="badge stock-out">OUT OF STOCK</div>
                <div class="img-box"><img src="gtav.png"></div>
                <h3 style="font-size: 18px; min-height: 50px;">Grand Theft Auto 5 | Online Premium Edition</h3>
                <span class="price">৳ 2,100</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
            </div>

            <div class="product-card">
                <div class="badge offer-tag">OFFER (STOCK OUT)</div>
                <div class="img-box"><img src="forza.png"></div>
                <h3 style="font-size: 18px; min-height: 50px;">Forza Horizon 5 – Premium Edition</h3>
                <span class="price">৳ 3,999</span>
                <button class="rrx-btn" disabled>OUT OF STOCK</button>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 RRX BRAND | POWERED BY RRX STUDIOS</p>
    </footer>

    <script>
        function enterSite() {
            const overlay = document.getElementById('welcome-overlay');
            overlay.style.opacity = '0';
            setTimeout(() => {
                overlay.style.display = 'none';
                document.body.style.overflow = 'auto';
            }, 800);
        }
    </script>
</body>
</html>
