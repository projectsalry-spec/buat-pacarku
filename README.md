<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Serta Mulia Untukmu</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;600&family=Playfair+Display:italic,wght@600&display=swap" rel="stylesheet">
    <style>
        body { margin: 0; padding: 0; background-color: #0b1622; color: #e0e0e0; font-family: 'Plus Jakarta Sans', sans-serif; display: flex; justify-content: center; align-items: center; min-height: 100vh; overflow: hidden; position: relative; }
        #stars-container { position: absolute; width: 100%; height: 100%; top: 0; left: 0; pointer-events: none; overflow: hidden; z-index: 0; }
        .star { position: absolute; width: 2px; height: 2px; background: rgba(255, 255, 255, 0.7); border-radius: 50%; opacity: 0; animation: moveStar linear infinite; }
        @keyframes moveStar { 0% { transform: translateY(0); opacity: 0; } 10% { opacity: 1; } 90% { opacity: 1; } 100% { transform: translateY(-100px); opacity: 0; } }
        .container { width: 85%; max-width: 380px; text-align: center; background: rgba(21, 34, 50, 0.95); padding: 25px; border-radius: 20px; box-shadow: 0 15px 35px rgba(0,0,0,0.6); position: relative; z-index: 10; border: 1px solid rgba(255,255,255,0.05); }
        .slide { display: none; animation: fadeIn 1s ease; }
        .active { display: block; }
        img { width: 100%; height: auto; max-height: 380px; object-fit: contain; border-radius: 15px; margin-bottom: 20px; border: 1px solid rgba(255,255,255,0.1); }
        h1 { font-family: 'Playfair Display', serif; color: #fff; font-size: 1.5rem; margin-top: 10px; }
        p { font-size: 0.9rem; color: #bdc3c7; line-height: 1.5; }
        .message { font-size: 0.9rem; line-height: 1.8; color: #bdc3c7; text-align: justify; margin-bottom: 20px; }
        .btn { background: transparent; border: 1px solid #fff; color: #fff; padding: 12px 25px; border-radius: 10px; cursor: pointer; font-size: 0.8rem; letter-spacing: 1px; transition: 0.3s; margin-top: 10px; text-decoration: none; display: inline-block; }
        .btn:hover { background: #fff; color: #0b1622; }
        .btn-wa { background: #25d366; border: none; color: white; margin-top: 20px; }
        .btn-wa:hover { background: #128c7e; color: white; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
    </style>
</head>
<body>
    <div id="stars-container"></div>
    <audio id="myAudio" loop>
        <source src="https://www.dropbox.com/scl/fi/uqwefdc1g4pkbmxo6dfki/Serta-Mulia.mp3?rlkey=m93pa3srjpq99sohlbwrhbten&st=ogjj1eqn&raw=1" type="audio/mpeg">
    </audio>
    <div class="container">
        <div class="slide active" id="slide1">
            <h1 style="font-style: italic;">Serta Mulia...</h1>
            <p style="color: #7f8c8d;">Sehat selalu <br> Sama aku terus ya ≧⁠▽⁠≦⁠</p>
            <button class="btn" onclick="start()">BUKA KADO</button>
        </div>
        <div class="slide" id="slide2">
            <img src="https://www.dropbox.com/scl/fi/awatcdr2hfit0svzmjbql/MyImage-1772633324-00.jpg?rlkey=gcui94y3aorzk356j9gixasdz&st=yhuinnfa&raw=1" alt="Kenangan 1">
            <p>"awalnya canggung ya?"</p>
            <button class="btn" onclick="nextSlide(3)">Lanjut →</button>
        </div>
        <div class="slide" id="slide3">
            <img src="https://www.dropbox.com/scl/fi/mq9rbjxip5qrlpgnl1jhz/IMG_20260304_211057.jpg?rlkey=gw8zabnxwiuhzglx6v912lqpt&st=hm2xxsrx&raw=1" alt="Kenangan 2">
            <p>"makin sini ternyata kita ada buat satu sama lain <br> (jiakkhhhhhh)."</p>
            <button class="btn" onclick="nextSlide(4)">Lanjut →</button>
        </div>
        <div class="slide" id="slide4">
            <img src="https://www.dropbox.com/scl/fi/o0me56gc82hug54eg6990/DSC_0401.jpg?rlkey=n2d0rzayoutrxnnpo2ne6kp1b&st=wwqu6dn7&raw=1" alt="Foto Wisuda">
            <h1>HBD, Rustandi Sidik Permana</h1>
            <div class="message">
                "Serta mulia bersama kita...<br><br>
                Di hari ini, makasih banyak udah hadir yaa. Makasih banyak udah jadi sosok yang selalu bisa aku andelin di tiap situasi. Di tahun ke 23 ini, semoga kamu makin dewasa, makin lebih baik lagi ke depannya. Semoga semua doa baikmu dikabulkan satu-satu, Aamiiin ❤️"
            </div>
            <small style="color: #5d6d7e; display: block;">— Dari Orang Favoritmu</small>
            <a href="https://wa.me/6285703394900?text=Makasih%20sayang%20kadonya!%20Aku%20baper%20parah%20❤️" class="btn btn-wa">Bales Pesan Ini ✨</a>
        </div>
    </div>
    <script>
        function createStars() {
            const container = document.getElementById('stars-container');
            for (let i = 0; i < 50; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                star.style.animationDelay = `${Math.random() * 5}s`;
                star.style.animationDuration = `${5 + Math.random() * 5}s`;
                container.appendChild(star);
            }
        }
        createStars();
        var audio = document.getElementById("myAudio");
        function start() { audio.play(); nextSlide(2); }
        function nextSlide(n) {
            var slides = document.getElementsByClassName("slide");
            for (var i = 0; i < slides.length; i++) { slides[i].classList.remove("active"); }
            document.getElementById("slide" + n).classList.add("active");
        }
    </script>
</body>
</html>
