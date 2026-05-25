<!DOCTYPE html>
<html lang="ms">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Khas</title>
    <style>
        body {
            /* Latar belakang bertema pastel comel (Warna merah jambu lembut ke ungu cair) */
            background: linear-gradient(135deg, #ffe5ec, #ffc2d1, #e8dbfc);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Courier New', Courier, monospace;
            overflow: hidden;
        }

        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.75);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            backdrop-filter: blur(5px);
            
            /* Animasi Awal: Kotak akan muncul dengan efek melompat (Pop-In) */
            animation: popIn 1.2s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        pre {
            color: #ff4d6d; /* Warna merah hati yang terang */
            font-size: 16px;
            font-weight: bold;
            line-height: 1.3;
            letter-spacing: 2px;
            margin: 0;
            
            /* Animasi Berterusan: Efek berdegup lembut */
            animation: pulse 1.8s infinite ease-in-out;
            animation-delay: 1.2s; /* Bermula selepas animasi popIn selesai */
        }

        .pesan {
            margin-top: 25px;
            color: #4a4a4a;
            font-size: 14px;
            font-weight: bold;
            opacity: 0;
            /* Teks pesanan muncul perlahan-lahan selepas animasi hati */
            animation: fadeIn 1s ease-in-out 1.5s forwards;
        }

        /* Deklarasi Animasi CSS */
        @keyframes popIn {
            0% { transform: scale(0); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); text-shadow: 0 0 10px rgba(255,77,109,0.3); }
            100% { transform: scale(1); }
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }
    </style>
</head>
<body>

<div class="container">
<pre>
  azriazria       azriazria
azriazriazria   azriazriazria
azriazriazriazriazriazriazria
  azriazriazriazriazriazria
    azriazriazriazriazria
      azriazriazriazria
        azriazriazri
          azriazri
            azri
</pre>
    <div class="pesan">Sistem mengesan kod ini untuk kau. 😉</div>
</div>

</body>
</html>
