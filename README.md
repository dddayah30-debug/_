<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Loading...</title>
    <style>
        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            /* SKRIN 1: Hanya keluar gradient maroon + hitam + emas sahaja */
            background: linear-gradient(135deg, #000000 0%, #1a0005 45%, #2a000d 75%, #261a00 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            font-family: Arial, sans-serif;
            position: relative;
        }

        /* SKRIN 2: Gabungan gambar pattern pixel kecik + gradient di belakangnya */
        body.skrin-dua {
            /* Kita panggil gambar pattern (pastikan nama fail gambar awak betul, contoh: pixel-couple.jpeg) */
            background: url('pixel-couple.jpeg'), linear-gradient(135deg, #000000 0%, #1a0005 45%, #2a000d 75%, #261a00 100%);
            background-repeat: repeat; /* Biar dia berulang */
            background-position: center;
            
            /* Taktik nak kasi gambar pixel tu jadi bersaiz KECIL: kita set 120px sahaja! */
            background-size: 120px, auto; 
        }

        /* Skrin 1: Intro Klik Heart */
        #intro-screen {
            text-align: center;
            cursor: pointer;
            z-index: 20;
            position: relative;
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
            position: relative;
            
            /* KOTAK HITAM: Supaya nama azri bertindih di atas warna hitam pekat, bukan direct atas gambar */
            background-color: rgba(0, 0, 0, 0.9); 
            padding: 35px 25px;
            border-radius: 20px; 
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8); 
            max-width: 90%;
            width: 400px;
        }

        /* Kotak Hati & Animasi Berdegup */
        .heart-text-container {
            font-family: 'Times New Roman', Times, serif; 
            color: #ff0000; /* Warna merah terang menyala */
            font-size: 15px;
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            display: inline-block;
            animation: heartbeat 1.2s infinite ease-in-out;
            filter: drop-shadow(0 0 10px rgba(255, 0, 0, 0.7));
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
        
        <div class="pesan" id="typewriter-text"></div>
        <div class="counter-box" id="love-counter"></div>
    </div>

    <script>
        function kesanMesinTaip(teks, elemenId, kelajuan) {
            let i = 0;
            let elemen = document.getElementById(elemenId);
            elemen.innerHTML = "";
            function taip() {
                if (i < teks.length) {
                    elemen.innerHTML += teks.charAt(i);
                    i++;
                    setTimeout(taip, kelajuan);
                }
            }
            taip();
        }

        function kiraHari() {
            const tarikhMula = new Date("2024-03-03");
            const tarikhSekarang = new Date();
            
            const bezaMasa = tarikhSekarang.getTime() - tarikhMula.getTime();
            const jumlahHari = Math.floor(bezaMasa / (1000 * 3600 * 24));
            
            document.getElementById("love-counter").innerText = `Day ${jumlahHari} with you and counting...`;
        }

        function bukaKejutan() {
            document.getElementById('intro-screen').style.display = 'none';
            
            // Tambah kelas skrin-dua untuk panggil wallpaper pixel kecik + gradient serentak
            document.body.classList.add('skrin-dua');
            
            document.getElementById('main-screen').style.display = 'block';
            
            kesanMesinTaip("I Love You Sayang <3", "typewriter-text", 100);
            kiraHari();
        }
    </script>

</body>
</html>
