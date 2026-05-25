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
            transition: transform 0.2s;
        }
        #intro-screen:hover {
            transform: scale(1.1);
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

        /* Skrin 2: Main Screen (Hati Besar) */
        #main-screen {
            display: none;
            text-align: center;
        }

        /* Animasi Berdegup untuk Hati Besar */
        .heart-container {
            animation: heartbeat 1.2s infinite ease-in-out;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.08); }
            100% { transform: scale(1); }
        }

        /* Teks Pesanan Paling Bawah */
        .pesan {
            color: #ffffff;
            font-size: 16px;
            font-weight: bold;
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <div id="intro-screen" onclick="bukaKejutan()">
        <div class="heart-emoji">❤️</div>
        <div class="click-text">klik heart</div>
    </div>

    <div id="main-screen">
        <div class="heart-container">
            <svg width="350" height="350" viewBox="0 0 24 24" fill="#ff0000" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
                
                <text x="12" y="10" 
                      fill="#ffffff" 
                      font-family="'Times New Roman', Times, serif" 
                      font-size="3px" 
                      font-weight="bold" 
                      text-anchor="middle">AZRI</text>
            </svg>
        </div>
        <div class="pesan">I love you Sayang</div>
    </div>

    <script>
        function bukaKejutan() {
            // Sorok skrin intro
            document.getElementById('intro-screen').style.display = 'none';
            
            // Paparkan skrin hati besar
            document.getElementById('main-screen').style.display = 'block';
        }
    </script>

</body>
</html>
