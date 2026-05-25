<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Sayang </title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Courier+Prime:wght@700&family=Roboto:wght@700&display=swap" rel="stylesheet">
    
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

        /* Hujan/Spam Tulisan Maroon "I LOVE YOU" di Latar Belakang */
        .rain-text {
            position: absolute;
            color: #4a000e; /* Maroon gelap */
            font-family: 'Roboto', sans-serif;
            font-weight: 700;
            font-size: 16px;
            white-space: nowrap;
            user-select: none;
            pointer-events: none;
            animation: rain linear infinite;
        }

        @keyframes rain {
            0% { transform: translateY(-100px); opacity: 0; }
            10% { opacity: 0.4; }
            90% { opacity: 0.4; }
            100% { transform: translateY(105vh); opacity: 0; }
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
            box-shadow: 0 15px 35px rgba(255, 0, 0, 0.4);
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

        /* Skrin 2: Kandungan Hati Teks */
        #heart-screen {
            display: none;
            text-align: center;
            z-index: 10;
            max-width: 100%;
        }

        .animate-pop {
            animation: popIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        /* BENTUK HATI TEKS (Wajib guna font Monospace supaya TIADA senget) */
        pre {
            color: #ff0000; /* Tulisan merah terang */
            /* Courier Prime ada 'ekor' tajam macam Times New Roman tapi lebar hurufnya sekata! */
            font-family: 'Courier Prime', 'Courier New', monospace; 
            font-size: 13px;
            font-weight: bold;
            line-height: 1.1;
            letter-spacing: 0px;
            margin: 0;
            display: inline-block;
            text-shadow: 0 0 15px rgba(255, 0, 0, 0.6);
            animation: beat 1.5s infinite ease-in-out;
        }

        /* Kotak Pesanan Bawah */
        .pesan-box {
            margin-top: 30px;
            background: rgba(17, 17, 17, 0.95);
            border: 1px solid #ff0000;
            padding: 18px 25px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(255,0,0,0.3);
            color: #ffffff;
            font-family: Arial, sans-serif;
            font-size: 15px;
            font-weight: bold;
            opacity: 0;
            animation: fadeIn 1s ease-in-out 0.8s forwards;
        }

        @keyframes popIn {
            0% { transform: scale(0); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        @keyframes beat {
            0% { transform: scale(1); }
            50% { transform: scale(1.04); }
            100% { transform: scale(1); }
        }
        @keyframes fadeIn {
            0% { opacity: 0; transform: translateY(10px); }
            100% { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <script>
        const totalLines = 25; // Jumlah spam tulisan kat belakang
        for (let i = 0; i < totalLines; i++) {
            let rain = document.createElement('div');
            rain.className = 'rain-text';
            rain.innerText = 'I LOVE YOU';
            rain.style.left = Math.random() * 100 + 'vw';
            rain.style.animationDuration = (Math.random() * 5 + 4) + 's'; // Kelajuan turun rawak
            rain.style.animationDelay = (Math.random() * 5) + 's';
            document.body.appendChild(rain);
        }
    </script>

    <div id="envelope-screen" onclick="bukaSurat()">
        <div class="letter-container">
            <div class="letter-icon">✉️</div>
            <div class="click-text">This is for you.</div>
        </div>
    </div>

    <div id="heart-screen">
        <pre>
    azriazriazr         azriazriazr
  azriazriazriazr     azriazriazriazr
 azriazriazriazriazriazriazriazriazr
 azriazriazriazriazriazriazriazriazr
  azriazriazriazriazriazriazriazrir
    azriazriazriazriazriazriazrir
      azriazriazriazriazriazri
        azriazriazriazriazr
          azriazriazriazr
            azriazriazr
              azriazr
                azr
</pre>
        
        <div class="pesan-box">
           I love you,Azri.<br>
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
