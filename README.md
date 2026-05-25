<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Loading...</title>
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
            position: relative;
        }

        /* 1. ANIMASI KELOPAK MAWAR GUGUR */
        .petal {
            position: absolute;
            background-color: #ff1a40;
            border-radius: 150% 0 150% 150%;
            opacity: 0.7;
            user-select: none;
            pointer-events: none;
            z-index: 1;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% {
                transform: translateY(-10vh) rotate(0deg);
                opacity: 0;
            }
            10% { opacity: 0.7; }
            90% { opacity: 0.7; }
            100% {
                transform: translateY(105vh) rotate(360deg);
                opacity: 0;
            }
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

        /* Kotak Hati & Animasi Berdegup */
        .heart-text-container {
            font-family: 'Times New Roman', Times, serif; 
            color: #ff0000; /* Warna merah terang */
            font-size: 16px;
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            display: inline-block;
            animation: heartbeat 1.2s infinite ease-in-out;
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

        /* 2. EFEK MESIN TAIP UNTUK LUAHAN */
        .pesan {
            color: #ffffff;
            font-size: 18px;
            font-weight: bold;
            margin-top: 30px;
            font-family: 'Times New Roman', Times, serif;
            letter-spacing: 1px;
            min-height: 24px; /* Elak teks melompat masa menaip */
        }

        /* 3. KAUNTER HARI AUTOMATIK */
        .counter-box {
            margin-top: 15px;
            color: #ff4d6d;
            font-family: Arial, sans-serif;
            font-size: 13px;
            font-weight: bold;
            letter-spacing: 1px;
            text-transform: uppercase;
            opacity: 0;
            animation: fadeIn 1s ease-in-out 3s forwards; /* Keluar selepas typewriter selesai */
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
        // Fungsi untuk hidupkan hujan kelopak mawar
        function buatHujanMawar() {
            const jumlahKelopak = 20;
            for (let i = 0; i < jumlahKelopak; i++) {
                let petal = document.createElement('div');
                petal.className = 'petal';
                
                // Set saiz rawak untuk rupa natural
                let saiz = Math.random() * 10 + 8;
                petal.style.width = saiz + 'px';
                petal.style.height = (saiz * 1.2) + 'px';
                
                petal.style.left = Math.random() * 100 + 'vw';
                petal.style.animationDuration = (Math.random() * 4 + 4) + 's'; 
                petal.style.animationDelay = (Math.random() * 5) + 's';
                document.body.appendChild(petal);
            }
        }

        // Fungsi efek mesin taip (Typewriter)
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

        // Fungsi kira hari automatik dari tarikh 3/3/2024
        function kiraHari() {
            const tarikhMula = new Date("2024-03-03");
            const tarikhSekarang = new Date();
            
            // Pengiraan beza hari
            const bezaMasa = tarikhSekarang.getTime() - tarikhMula.getTime();
            const jumlahHari = Math.floor(bezaMasa / (1000 * 3600 * 24));
            
            document.getElementById("love-counter").innerText = `Day ${jumlahHari} with you and counting... 🖤`;
        }

        // Fungsi utama bila skrin di-klik
        function bukaKejutan() {
            // Sorok skrin intro
            document.getElementById('intro-screen').style.display = 'none';
            
            // Paparkan skrin utama
            document.getElementById('main-screen').style.display = 'block';
            
            // Jalankan ketiga-tiga fungsi serentak!
            buatHujanMawar();
            kesanMesinTaip("I Love You Sayang <3", "typewriter-text", 100);
            kiraHari();
        }
    </script>

</body>
</html>
          
           
