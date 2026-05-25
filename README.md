<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>&lrm;</title> <style>
        *, *::before, *::after {
            box-sizing: border-box;
        }

        body {
            background-color: #000000; /* Skrin permulaan kekal hitam pekat bersih */
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

        /* SKRIN KEDUA: Gambar pixel korang akan berulang-ulang macam wallpaper */
        body.skrin-dua {
            background: url('pixel-couple.jpeg');
            background-repeat: repeat; /* Paksa gambar berulang ke seluruh lantai skrin */
            background-position: center;
            background-size: 180px; /* Awak boleh ejas nombor ni (contoh: 150px atau 200px) untuk besarkan/kecilkan saiz corak wallpaper tu */
        }

        /* Overlay hitam 70% di atas wallpaper berulang supaya tulisan tak tenggelam */
        body.skrin-dua::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7); 
            z-index: 1;
        }

        /* Skrin 1: Intro Klik Heart */
        #intro-screen {
            text-align: center;
            cursor: pointer;
            z-index: 10;
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
        }

        /* Kotak Hati Nama Azri & Animasi Berdegup */
        .heart-text-container {
            font-family: 'Times New Roman', Times, serif; 
            color: #ff0000; /* Warna merah terang menyala */
            font-size: 16px;
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            display: inline-block;
            animation: heartbeat 1.2s infinite ease-in-out;
            filter: drop-shadow(0 0 10px rgba(255, 0, 0, 0.7)); /* Efek glow merah bagi terang */
        }

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

        /* EFEK MESIN TAIP UNTUK LUAHAN */
        .pesan {
            color: #ffffff;
            font-size: 18px;
            font-weight: bold;
            margin-top: 30px;
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
            
            document.getElementById("love-counter").innerText = `Day ${jumlahHari} with you and counting... 🖤`;
        }

        function bukaKejutan() {
            // Sorok skrin pertama
            document.getElementById('intro-screen').style.display = 'none';
            
            // Aktifkan corak wallpaper gambar pixel pada body
            document.body.classList.add('skrin-dua');
            
            // Paparkan skrin kedua
            document.getElementById('main-screen').style.display = 'block';
            
            // Jalankan teks mesin taip & kaunter hari
            kesanMesinTaip("I Love You Sayang <3", "typewriter-text", 100);
            kiraHari();
        }
    </script>

</body>
</html>
