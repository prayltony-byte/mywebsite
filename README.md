# mywebsite
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aplikasi Pembaca Pikiran 🔮</title>
    <style>
        body {
            background: #fff0f5;
            font-family: 'Comic Sans MS', cursive, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
        }
        #container {
            background: white;
            padding: 30px;
            border-radius: 25px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            max-width: 400px;
            width: 90%;
            border: 3px solid #ffb6c1;
        }
        h2 { color: #d63384; margin-bottom: 20px; }
        p { color: #555; line-height: 1.6; }
        .btn-group { display: flex; flex-direction: column; gap: 10px; margin-top: 20px; }
        button {
            padding: 12px;
            border: none;
            border-radius: 15px;
            background: #ff69b4;
            color: white;
            cursor: pointer;
            font-size: 16px;
            transition: 0.3s;
        }
        button:hover { background: #ff1493; transform: scale(1.05); }
        .hidden { display: none; }
        .emoji { font-size: 40px; margin-bottom: 10px; }
    </style>
</head>
<body>

<div id="container">
    <div id="step1">
        <div class="emoji">🔮</div>
        <h2>Halo Cantik...</h2>
        <p>Aku punya kekuatan buat baca pikiran kamu sekarang. Mau bukti?</p>
        <div class="btn-group">
            <button onclick="nextStep(2)">Boleh, coba buktiin!</button>
        </div>
    </div>

    <div id="step2" class="hidden">
        <h2>Tebakan Pertama...</h2>
        <p>Sekarang kamu lagi pegang HP, terus lagi liatin layar sambil senyum-senyum sendiri baca tulisan ini kan?</p>
        <div class="btn-group">
            <button onclick="nextStep(3)">Ih kok tau?!</button>
            <button onclick="nextStep(3)">Enggak, aku lagi merengut</button>
        </div>
    </div>

    <div id="step3" class="hidden">
        <h2>Lanjut!</h2>
        <p>Sebenernya kamu lagi kangen seseorang ya sekarang? Ngaku deh!</p>
        <div class="btn-group">
            <button onclick="nextStep(4)">Iya sih..</button>
            <button onclick="nextStep(4)">Dikit doang</button>
        </div>
    </div>

    <div id="step4" class="hidden">
        <div class="emoji">🕵️‍♂️</div>
        <h2>Sama Siapa?</h2>
        <p>Aku tebak, kamu lagi sama orang paling beruntung di dunia ya? <br><b>(Coba sebutin nama orangnya di hati)</b></p>
        <div class="btn-group">
            <button onclick="checkMind()">Udah, lanjut!</button>
        </div>
    </div>

    <div id="step5" class="hidden">
        <h2>HASIL DETEKSI:</h2>
        <p>Pikiran kamu bilang: <br><br> <b id="resultText"></b></p>
        <div class="emoji">✨💖✨</div>
        <div class="btn-group">
            <button onclick="location.reload()">Main Lagi?</button>
        </div>
    </div>
</div>

<script>
    function nextStep(step) {
        // Sembunyikan semua div
        document.querySelectorAll('#container > div').forEach(div => {
            div.classList.add('hidden');
        });
        // Tampilkan step tujuan
        document.getElementById('step' + step).classList.remove('hidden');
    }

    function checkMind() {
        const text = "Kamu lagi kangen sama orang yang buat web ini kan? Dan orang paling beruntung itu aku, karena bisa dapet perhatian kamu sekarang. Hehe.";
        document.getElementById('resultText').innerText = text;
        nextStep(5);
    }
</script>

</body>
</html>
