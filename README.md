<!DOCTYPE html>
<html lang="en">
<head>

    <title>Basic Store & Login</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: sans-serif;
        }
        body {
            background-color: #f4f4f6;
            color: #222;
            padding: 20px;
        }
        header {
            background: #fff;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-radius: 8px;
            margin-bottom: 30px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        .logo {
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
        }
        nav a {
            margin-left: 20px;
            text-decoration: none;
            color: #555;
            cursor: pointer;
        }
        nav a:hover {
            color: #222;
        }
        .page {
            display: none;
        }
        .page.active {
            display: block;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }
        .card {
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .item-placeholder {
            background: #e9ecef;
            height: 120px;
            border-radius: 4px;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #777;
            font-weight: bold;
            font-size: 14px;
            letter-spacing: 1px;
        }
        .title {
            font-size: 16px;
            margin-bottom: 8px;
            font-weight: 600;
        }
        .price {
            color: #007600;
            font-weight: bold;
            margin-bottom: 15px;
        }
        .form-container {
            background: #fff;
            max-width: 360px;
            margin: 60px auto;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.05);
        }
        .form-container h2 {
            margin-bottom: 20px;
            font-size: 22px;
            text-align: center;
        }
        .form-group {
            margin-bottom: 15px;
        }
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-size: 14px;
            font-weight: 600;
        }
        .form-group input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }
        .btn {
            background: #222;
            color: #fff;
            border: none;
            padding: 10px;
            width: 100%;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            font-size: 14px;
        }
        .btn:hover {
            background: #444;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo" onclick="showPage('store')">TextStore</div>
        <nav>
            <a onclick="showPage('store')">Shop</a>
            <a onclick="showPage('login')">Login</a>
            <a href="#">Cart (0)</a>
        </nav>
    </header>

    <main id="store" class="page active">
        <div class="grid">
            <div class="card">
                <div>
                    <div class="item-placeholder">WATCH</div>
                    <div class="title">Minimalist Watch</div>
                    <div class="price">$120.00</div>
                </div>
                <button class="btn">Add to Cart</button>
            </div>

            <div class="card">
                <div>
                    <div class="item-placeholder">AUDIO</div>
                    <div class="title">Wireless Headphones</div>
                    <div class="price">$199.99</div>
                </div>
                <button class="btn">Add to Cart</button>
            </div>

            <div class="card">
                <div>
                    <div class="item-placeholder">SHOES</div>
                    <div class="title">Running Sneakers</div>
                    <div class="price">$89.50</div>
                </div>
                <button class="btn">Add to Cart</button>
            </div>
        </div>
    </main>

    <div id="login" class="page">
        <div class="form-container">
            <h2>Account Login</h2>
            <form onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" required placeholder="name@example.com">
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" id="password" required placeholder="••••••••">
                </div>
                <button type="submit" class="btn">Sign In</button>
            </form>
        </div>
    </div>

    <script>
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
        }

        function handleLogin(event) {
            event.preventDefault();
            alert("Login submitted! Redirecting back to shop.");
            showPage('store');
        }
    </script>

</body>
</html>
