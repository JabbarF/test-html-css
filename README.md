<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toko Sepatu Impian - Exercise 2</title>
    <!-- Memuat Tailwind CSS untuk utilitas styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Mengatur font Inter sebagai font utama untuk konsistensi desain */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f7fafc; /* Warna background abu-abu muda */
            margin: 0; /* Menghilangkan margin default body */
            padding: 0; /* Menghilangkan padding default body */
        }

        /* Class Container sesuai petunjuk: max-width, margin auto */
        .Container {
            max-width: 1024px;
            margin-left: auto;
            margin-right: auto;
            padding: 1.5rem; /* Menambah padding untuk kenyamanan visual */
        }

        /* Gaya untuk navigation bar */
        .navbar {
            background-color: #3498db; /* Warna biru untuk navbar */
            padding: 1rem 0; /* Padding atas dan bawah */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Bayangan lembut */
        }

        .navbar ul {
            display: flex; /* Menggunakan Flexbox untuk item navigasi */
            justify-content: center; /* Memposisikan item di tengah */
            list-style: none; /* Menghilangkan bullet point default */
            margin: 0;
            padding: 0;
        }

        .navbar ul li a {
            color: #ffffff; /* Warna teks putih */
            text-decoration: none; /* Menghilangkan garis bawah link */
            font-weight: bold; /* Teks tebal */
            font-size: 1.1rem; /* Ukuran font lebih besar */
            padding: 0.5rem 1rem; /* Padding untuk setiap link */
            transition: color 0.3s ease; /* Transisi halus saat hover */
        }

        .navbar ul li a:hover {
            color: #ecf0f1; /* Warna teks lebih terang saat hover */
        }

        /* Gaya untuk heading utama */
        .main-heading {
            text-align: center;
            font-size: 2.5rem; /* Ukuran font besar untuk judul utama */
            font-weight: 700; /* Tebal */
            color: #2c3e50; /* Warna teks gelap */
            margin-bottom: 2rem; /* Margin bawah */
        }

        /* Gaya untuk grid produk */
        .product-grid {
            display: grid; /* Menggunakan Grid untuk layout produk */
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* 3 kolom responsif */
            gap: 2rem; /* Jarak antar item grid */
            margin-bottom: 3rem; /* Margin bawah */
        }

        /* Gaya untuk setiap kartu produk */
        .product-card {
            background-color: #ffffff; /* Latar belakang putih */
            border-radius: 1rem; /* Sudut membulat */
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05); /* Bayangan lebih kuat */
            overflow: hidden; /* Memastikan sudut membulat gambar terlihat */
            transition: transform 0.3s ease; /* Transisi untuk efek hover */
        }

        .product-card:hover {
            transform: translateY(-5px); /* Sedikit naik saat dihover */
        }

        .product-image {
            width: 100%;
            height: 200px; /* Tinggi tetap untuk gambar produk */
            object-fit: cover; /* Memastikan gambar mengisi area tanpa distorsi */
            border-top-left-radius: 1rem; /* Sudut membulat hanya di bagian atas */
            border-top-right-radius: 1rem;
        }

        .product-info {
            padding: 1.5rem; /* Padding di dalam kartu produk */
            text-align: center; /* Teks di tengah */
        }

        .product-title {
            font-size: 1.5rem; /* Ukuran font judul produk */
            font-weight: 600; /* Tebal */
            color: #34495e; /* Warna teks gelap */
            margin-bottom: 0.5rem;
        }

        .product-price {
            font-size: 1.3rem; /* Ukuran font harga */
            font-weight: 700; /* Sangat tebal */
            color: #e74c3c; /* Warna merah untuk harga */
            margin-bottom: 1rem;
        }

        .buy-button {
            background-color: #27ae60; /* Warna hijau untuk tombol */
            color: white; /* Warna teks putih */
            padding: 0.75rem 1.5rem; /* Padding tombol */
            border-radius: 0.75rem; /* Sudut membulat */
            text-align: center;
            text-decoration: none;
            display: inline-block; /* Agar bisa diatur padding dan margin */
            font-size: 1rem;
            font-weight: bold;
            transition: background-color 0.3s ease; /* Transisi warna saat hover */
        }

        .buy-button:hover {
            background-color: #2ecc71; /* Warna hijau lebih terang saat hover */
        }

        /* Gaya untuk tabel */
        .data-table {
            width: 100%;
            border-collapse: collapse; /* Menggabungkan border sel */
            margin-top: 2rem;
            margin-bottom: 3rem;
            background-color: #ffffff; /* Latar belakang putih */
            border-radius: 1rem; /* Sudut membulat */
            overflow: hidden; /* Memastikan sudut membulat terlihat */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* Bayangan */
        }

        .data-table th, .data-table td {
            padding: 1rem;
            text-align: left;
            border-bottom: 1px solid #ecf0f1; /* Garis bawah tipis */
        }

        .data-table th {
            background-color: #5d9cec; /* Biru muda */
            color: white;
            font-weight: 600;
            text-transform: uppercase; /* Huruf kapital */
            font-size: 0.9rem;
        }

        .data-table tr:last-child td {
            border-bottom: none; /* Menghilangkan border bawah pada baris terakhir */
        }

        .data-table tbody tr:nth-child(even) {
            background-color: #f9f9f9; /* Warna latar belakang selang-seling */
        }

        /* Gaya untuk footer */
        .footer {
            background-color: #2c3e50; /* Warna abu-abu gelap */
            color: white;
            text-align: center;
            padding: 1.5rem 0;
            border-top-left-radius: 1rem;
            border-top-right-radius: 1rem;
            box-shadow: 0 -4px 6px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar">
        <div class="Container">
            <ul>
                <li><a href="#produk">Produk Terbaru</a></li>
                <li><a href="#panduan">Panduan Ukuran</a></li>
                <li><a href="#promo">Promo</a></li>
                <li><a href="#keranjang">Keranjang</a></li>
            </ul>
        </div>
    </nav>

    <!-- Main Content Container -->
    <div class="Container">
        <h2 class="main-heading" id="produk">Produk Terbaru</h2>

        <!-- Product List (Grid 3 kolom) -->
        <div class="product-grid">
            <!-- Product Card 1 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/3498db/ffffff?text=Sepatu+Sneakers" alt="Sepatu Sneakers Urban" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sepatu Sneakers Urban</h3>
                    <p class="product-price">Rp 500.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>

            <!-- Product Card 2 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/2ecc71/ffffff?text=Sepatu+Lari" alt="Sepatu Lari ProRunner" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sepatu Lari ProRunner</h3>
                    <p class="product-price">Rp 650.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>

            <!-- Product Card 3 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/e67e22/ffffff?text=Sepatu+Formal" alt="Sepatu Formal Elegance" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sepatu Formal Elegance</h3>
                    <p class="product-price">Rp 780.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>

            <!-- Product Card 4 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/9b59b6/ffffff?text=Sepatu+Casual" alt="Sepatu Casual Lifestyle" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sepatu Casual Lifestyle</h3>
                    <p class="product-price">Rp 420.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>

            <!-- Product Card 5 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/f1c40f/ffffff?text=Sepatu+Boots" alt="Sepatu Boots Adventure" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sepatu Boots Adventure</h3>
                    <p class="product-price">Rp 900.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>

            <!-- Product Card 6 -->
            <div class="product-card">
                <img src="https://placehold.co/400x200/c0392b/ffffff?text=Sepatu+Sandal" alt="Sandal Santai Summer" class="product-image">
                <div class="product-info">
                    <h3 class="product-title">Sandal Santai Summer</h3>
                    <p class="product-price">Rp 250.000</p>
                    <a href="#" class="buy-button">Beli Sekarang</a>
                </div>
            </div>
        </div>

        <h2 class="main-heading" id="panduan">Panduan Ukuran Sepatu</h2>

        <!-- Size Guide Table -->
        <table class="data-table">
            <thead>
                <tr>
                    <th>Ukuran EU</th>
                    <th>Ukuran US (Pria)</th>
                    <th>Ukuran US (Wanita)</th>
                    <th>Panjang Kaki (cm)</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>38</td>
                    <td>6</td>
                    <td>7</td>
                    <td>24</td>
                </tr>
                <tr>
                    <td>39</td>
                    <td>6.5</td>
                    <td>7.5</td>
                    <td>24.5</td>
                </tr>
                <tr>
                    <td>40</td>
                    <td>7</td>
                    <td>8</td>
                    <td>25</td>
                </tr>
                <tr>
                    <td>41</td>
                    <td>8</td>
                    <td>9</td>
                    <td>26</td>
                </tr>
                <tr>
                    <td>42</td>
                    <td>8.5</td>
                    <td>9.5</td>
                    <td>26.5</td>
                </tr>
                <tr>
                    <td>43</td>
                    <td>9.5</td>
                    <td>10.5</td>
                    <td>27.5</td>
                </tr>
                <tr>
                    <td>44</td>
                    <td>10</td>
                    <td>11</td>
                    <td>28</td>
                </tr>
            </tbody>
        </table>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <p>&copy; 2025 Toko Sepatu Impian. Semua Hak Dilindungi.</p>
    </footer>
</body>
</html>
