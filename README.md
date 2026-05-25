<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Untuk Azri</title>
    <style>
        body {
            background-color: #000000; /* Latar belakang hitam pekat */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            font-family: Arial, sans-serif;
        }

        /* Skrin 1: Intro Klik Heart */
        #intro-screen {
            text-align: center;
            cursor: pointer;
        }
        .heart-emoji {
            font-size: 80px;
            margin-bottom: 10px;
            animation: slowPulse 2s infinite ease-in-out;
        }
        .click-text {
            color: #ffffff;
            font-size: 16px;
            font-weight: bold;
            letter-spacing: 1px;
        }
        @keyframes slowPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        /* Skrin 2: Hati Tulisan Nama Azri Besar */
        #main-screen {
            display: none;
            text-align: center;
        }

        /* Kotak Hati & Animasi Berdegup */
        .heart-text-container {
            /* Menggunakan Font New Times Roman */
            font-family: 'Times New Roman', Times, serif; 
            color: #ff0000; /* Warna merah terang */
            font-size: 16px;
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            display: inline-block;
            animation: heartbeat 1.2s infinite ease-in-out;
        }

        /* Setiap baris diletakkan dalam blok tengah supaya SIMETRI & TAK SENGET */
        .line {
            display: block;
            text-align: center;
            white-space: pre;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.06); }
            100% { transform: scale(1); }
        }

        /* Teks Pesanan Bawah */
        .pesan {
            color: #ffffff;
            font-size: 16px;
            font-weight: bold;
            margin-top: 30px;
            font-family: Arial, sans-serif;
        }
    </style>
</head>
<body>

    <div id="intro-screen" onclick="bukaKejutan()">
        <div class="heart-emoji">❤️</div>
        <div class="click-text">klik heart</div>
    </div>

    <div id="main-screen">
        <div class="heart-text-container">
            <span class="line">azriazri         azriazri</span>
            <span class="line">azriazriazri     azriazriazri</span>
            <span class="line">azriazriazriazriazriazriazriazri</span>
            <span class="line">azriazriazriazriazriazriazriazri</span>
            <span class="line">azriazriazriazriazriazriazri</span>
            <span class="line">azriazriazriazriazriazri</span>
            <span class="line">azriazriazriazriazri</span>
            <span class="line">azriazriazriazri</span>
            <span class="line">azriazriazri</span>
            <span class="line">azriazri</span>
            <span class="line">azri</span>
        </div>
        <div class="pesan">I Love You Sayang <3 </div>
    </div>

    <script>
        function bukaKejutan() {
            // Sorok intro
            document.getElementById('intro-screen').style.display = 'none';
            
            // Paparkan hati nama azri
            document.getElementById('main-screen').style.display = 'block';
        }
    </script>

</body>
</html>
