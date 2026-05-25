
  <!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Khas Untuk Azri</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@700&display=swap" rel="stylesheet">
    
    <style>
        * {
            box-sizing: border-box;
        }
        
        body {
            background-color: #000000; /* Latar belakang hitam pekat */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            position: relative;
        }

        /* Tulisan Maroon "I LOVE YOU" (Roboto) bergerak di background */
        .moving-text {
            position: absolute;
            color: #500014; /* Warna Maroon gelap */
            font-family: 'Roboto', sans-serif;
            font-weight: 700;
            font-size: 26px;
            white-space: nowrap;
            opacity: 0.25;
            user-select: none;
            pointer-events: none;
        }

        /* Animasi pergerakan rawak tulisan background */
        @keyframes floatLeftRight {
            0% { transform: translate(-60vw, -20vh); }
            50% { transform: translate(60vw, 30vh); }
            100% { transform: translate(-60vw, -20vh); }
        }
        @keyframes floatRightLeft {
            0% { transform: translate(50vw, -40vh); }
            50% { transform: translate(-50vw, 20vh); }
            100% { transform: translate(50vw, -40vh); }
        }

        /* Skrin 1: Butang Surat Misteri */
        #envelope-screen {
            text-align: center;
            cursor: pointer;
            z-index: 10;
        }
        .letter-container {
            background: #111111;
            padding: 25px 40px;
            border-radius: 30px;
            border: 2px solid #ff0000;
            box-shadow: 0 15px 35px rgba(255, 0, 0, 0.3);
            animation: floatButton 2s infinite ease-in-out;
        }
        .letter-icon {
            font-size: 60px;
            margin-bottom: 10px;
        }
        .click-text {
            font-weight: bold;
            color: #ff0000;
            font-size: 16px;
            font-family: Arial, sans-serif;
        }
        @keyframes floatButton {
            0% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0); }
        }

        /* Skrin 2: Kandungan Hati Teks (Sorok dulu) */
        #heart-screen {
            display: none;
            text-align: center;
            z-index: 10;
            max-width: 95%;
        }

        /* Animasi Masuk Awal (Pop-In) */
        .animate-pop {
            animation: popIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        /* SUSUNAN TEKS BENTUK HATI (Times New Roman & Warna Merah) */
        pre {
            color: #ff0000; /* Tulisan merah terang */
            font-family: 'Times New Roman', Times, serif; /* Font New Times Roman */
            font-size: 15px;
            font-weight: bold;
            line-height: 1.2;
            letter-spacing: 2px;
            margin: 0;
            display: inline-block;
            text-shadow: 0 0 15px rgba(255, 0, 0, 0.5);
            /* Animasi berdegup */
            animation: beat 1.5s infinite ease-in-out;
        }

        /* Kotak Pesanan Bawah */
        .pesan-box {
            margin-top: 30px;
            background: rgba(17, 17, 17, 0.9);
            border: 1px solid #ff0000;
            padding: 18px 25px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(255,0,0,0.2);
            color: #ffffff;
            font-family: Arial, sans-serif;
            font-size: 15px;
            font-weight: bold;
            opacity: 0;
            animation: fadeIn 1s ease-in-out 0.8s forwards;
        }

        /* Keyframes */
        @keyframes popIn {
            0% { transform: scale(0); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        @keyframes beat {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(10px); }
            100% { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <div class="moving-text" style="animation: floatLeftRight 14s infinite linear;">I LOVE YOU</div>
    <div class="moving-text" style="animation: floatRightLeft 18s infinite linear;">I LOVE YOU</div>
    <div class="moving-text" style="animation: floatLeftRight 16s infinite linear; animation-delay: 4s;">I LOVE YOU</div>

    <div id="envelope-screen" onclick="bukaSurat()">
        <div class="letter-container">
            <div class="letter-icon">✉️</div>
            <div class="click-text">SISTEM MENGESAN KOD KHAS. KLIK SINI.</div>
        </div>
    </div>

    <div id="heart-screen">
        <pre>
     azriazri           azriazri
   azriazriazri       azriazriazri
 azriazriazriazri   azriazriazriazri
 azriazriazriazriazriazriazriazri
   azriazriazriazriazriazriazri
     azriazriazriazriazriazri
       azriazriazriazriazri
         azriazriazriazri
           azriazriazri
             azriazri
               azri
</pre>
        
        <div class="pesan-box">
            Sistem mengesan kod ini untuk kau. 😉 <br>
            Genggam ego tu kuat-kuat tau!
        </div>
    </div>

    <script>
        function bukaSurat() {
            document.getElementById('envelope-screen').style.display = 'none';
            
            var mainScreen = document.getElementById('heart-screen');
            mainScreen.style.display = 'block';
            mainScreen.classList.add('animate-pop');
        }
    </script>

</body>
</html>
