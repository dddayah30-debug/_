<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>&lrm;</title> <style>
        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            background-color: #000000; /* Skrin 1 mula dengan hitam pekat kosong */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            padding: 0;
            overflow: hidden;
            font-family: Arial, sans-serif;
            position: relative;
        }

        /* SKRIN KEDUA: Wallpaper pixel terang 100% tanpa malap */
        body.skrin-dua {
            background: url('WhatsApp Image 2026-05-25 at 10.55.21 PM.jpeg');
            background-repeat: repeat;
            background-position: center;
            background-size: 250px; /* Boleh ejas saiz corak di sini (contoh: 200px) */
        }

        /* OVERLAY MALAP DAH DIBUANG SEPENUHNYA DI SINI */

        /* Skrin 1: Intro Klik Heart */
        #intro-screen {
            text-align: center;
            cursor: pointer;
            z-index: 20;
            position:relative;
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

        /* Skrin 2: Kandungan Utama */
        #main-screen {
            display: none;
            text-align: center;
            z-index: 10;
            
            /* KOTAK PELINDUNG HITAM: Supaya kandungan tengah tak bertindih dengan wallpaper */
            background-color: rgba(0, 0, 0, 0.9); /* Hitam pekat 85% untuk perlindungan maksima */
            padding: 35px 25px;
            border-radius: 20px; /* Buat bucu kotak jadi bulat comel */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8); /* Efek bayang mampat di luar kotak */
            max-width: 90%;
            width: 400px;
        }

        /* Kotak Hati Nama Azri & Animasi Berdegup */
        .heart-text-container {
            font-family: 'Times New Roman', Times, serif; 
            color: #ff0000; /* Warna merah terang menyala */
            font-size: 15px; /* Dikecilkan sikit tona font biar ngam masuk kotak */
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            display: inline-block;
            animation: heartbeat 1.2s infinite ease-in-out;
            filter: drop-shadow(0 0 8px rgba(255, 0, 0, 0.7)); /* Efek glow merah */
        }

        .line {
            display: block;
            text-align: center;
            white-space: pre;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.04); }
            100% { transform: scale(1); }
        }

        /* EFEK MESIN TAIP UNTUK LUAHAN */
        .pesan {
            color: #ffffff;
            font-size: 18px;
            font-weight: bold;
            margin-top: 25px;
            font-family: 'Times New Roman', Times, serif;
            letter-spacing: 1px;
            min-height: 24px;
        }

        /* KAUNTER HARI AUTOMATIK */
        .counter-box {
            margin-top: 15px;
            color: #ff4d6d;
            font-family: Arial, sans-serif;
            font-size: 13px;
            font-weight: bold;
            letter-spacing: 1px;
            text-transform: uppercase;
            opacity: 0;
            animation: fadeIn 1s ease-in-out 3s forwards;
        }

        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(10px); }
            100% { opacity: 1; transform: translateY(0); }
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
            <span class="line">azriazriazriazriazriazri
 
