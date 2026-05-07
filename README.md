<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>KENYA LIFE RADIO</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:Arial, sans-serif;
    background:#000;
    color:white;
    overflow-x:hidden;
}

/* HEADER */

header{
    background:rgba(0,0,0,0.85);
    backdrop-filter:blur(10px);
    padding:15px 40px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    position:fixed;
    width:100%;
    top:0;
    z-index:999;
    border-bottom:2px solid red;
}

.logo{
    display:flex;
    align-items:center;
    gap:15px;
}

.logo img{
    width:70px;
    height:70px;
    border-radius:50%;
    object-fit:cover;
    border:2px solid #00ff55;
}

.logo h2{
    font-size:24px;
    color:white;
}

nav a{
    color:white;
    text-decoration:none;
    margin-left:20px;
    font-weight:bold;
    transition:0.3s;
}

nav a:hover{
    color:#00ff55;
}

/* HERO SECTION */

.hero{
    height:100vh;
    background:
    linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.85)),
    url("kenyalife-bg.jpg");
    background-size:cover;
    background-position:center;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    padding:20px;
}

.hero-content{
    max-width:900px;
}

.hero-logo{
    width:280px;
    max-width:90%;
    margin-bottom:25px;
    animation:float 4s ease-in-out infinite;
}

@keyframes float{
    0%{transform:translateY(0px);}
    50%{transform:translateY(-10px);}
    100%{transform:translateY(0px);}
}

.hero h1{
    font-size:70px;
    margin-bottom:15px;
    text-shadow:0 0 20px red;
}

.tagline{
    font-size:24px;
    color:#00ff55;
    margin-bottom:30px;
}

/* LIVE INDICATOR */

.live-indicator{
    display:inline-block;
    background:red;
    padding:10px 25px;
    border-radius:30px;
    font-weight:bold;
    margin-bottom:25px;
    animation:pulse 1.5s infinite;
}

@keyframes pulse{
    0%{opacity:1;}
    50%{opacity:0.4;}
    100%{opacity:1;}
}

/* BUTTONS */

.btn{
    background:linear-gradient(90deg, red, green);
    border:none;
    padding:18px 40px;
    border-radius:40px;
    color:white;
    font-size:20px;
    font-weight:bold;
    cursor:pointer;
    transition:0.3s;
    box-shadow:0 0 20px rgba(255,0,0,0.5);
}

.btn:hover{
    transform:scale(1.05);
}

/* PLAYER */

.player-box{
    margin-top:30px;
    display:none;
}

audio{
    width:100%;
    max-width:500px;
}

/* SECTIONS */

.section{
    padding:90px 20px;
    max-width:1200px;
    margin:auto;
}

.section h2{
    font-size:40px;
    margin-bottom:25px;
    color:#00ff55;
    text-align:center;
}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:25px;
}

.card{
    background:#111;
    padding:30px;
    border-radius:20px;
    border:1px solid #222;
    transition:0.3s;
    text-align:center;
}

.card:hover{
    transform:translateY(-10px);
    border-color:red;
}

.card h3{
    margin-bottom:15px;
    color:#00ff55;
}

/* CONTACT */

.contact p{
    margin:15px 0;
    font-size:20px;
}

.contact a{
    color:#00ff55;
    text-decoration:none;
}

/* FOOTER */

footer{
    background:#111;
    padding:30px;
    text-align:center;
    border-top:2px solid red;
}

/* MOBILE */

@media(max-width:768px){

    header{
        flex-direction:column;
        gap:15px;
    }

    .hero h1{
        font-size:45px;
    }

    .tagline{
        font-size:18px;
    }

    nav{
        text-align:center;
    }

    nav a{
        margin:10px;
        display:inline-block;
    }

}

</style>
</head>

<body>

<!-- HEADER -->

<header>

<div class="logo">

<!-- ADD YOUR LOGO IMAGE HERE -->
<img src="kenya-life-logo.png" alt="Kenya Life Radio Logo">

<h2>KENYA LIFE RADIO</h2>

</div>

<nav>
<a href="#">Home</a>
<a href="#about">About</a>
<a href="#shows">Shows</a>
<a href="#contact">Contact</a>
</nav>

</header>

<!-- HERO -->

<section class="hero">

<div class="hero-content">

<!-- BIG LOGO -->
<img src="kenya-life-logo.png" class="hero-logo" alt="Kenya Life Radio">

<h1>KENYA LIFE RADIO</h1>

<p class="tagline">
LIVE THE MUSIC • LIVE THE VIBE • LIVE THE LIFE
</p>

<div class="live-indicator">
🔴 LIVE NOW
</div>

<br>

<!-- PLAY BUTTON -->
<button class="btn" onclick="startRadio()">
▶ LISTEN LIVE
</button>

<!-- PLAYER -->
<div class="player-box" id="playerBox">

<br><br>

<audio id="radioPlayer" controls autoplay>

<source
src="https://goliveafrica.media/live/1/KENYALIFERADIO"
type="audio/mpeg">

</audio>

</div>

</div>

</section>

<!-- ABOUT -->

<section class="section" id="about">

<h2>About Kenya Life Radio</h2>

<p style="text-align:center; line-height:1.8; font-size:20px; max-width:900px; margin:auto;">
Kenya Life Radio is a modern online radio station bringing
the best of Kenyan music, entertainment, culture, news and
African vibes to listeners around the world. Stay connected
24/7 with nonstop music and live shows.
</p>

</section>

<!-- SHOWS -->

<section class="section" id="shows">

<h2>Featured Shows</h2>

<div class="cards">

<div class="card">
<h3>Morning Drive</h3>
<p>Start your day with energy, motivation and breaking news.</p>
</div>

<div class="card">
<h3>Afrobeat Vibes</h3>
<p>The hottest African music and trending hits.</p>
</div>

<div class="card">
<h3>Night Chill</h3>
<p>Relax with smooth vibes and late-night sessions.</p>
</div>

</div>

</section>

<!-- YOUTUBE -->

<section class="section">

<h2>Watch Us On YouTube</h2>

<div style="text-align:center;">

<a href="https://www.youtube.com/@KingsandQueensStudios" target="_blank">

<button class="btn">
🎥 VISIT YOUTUBE CHANNEL
</button>

</a>

</div>

</section>

<!-- CONTACT -->

<section class="section contact" id="contact">

<h2>Contact Us</h2>

<div style="text-align:center;">

<p>
📞 WhatsApp:
<a href="https://wa.me/254725822639">
+254725822639
</a>
</p>

<p>
📧 info@kenyaliferadio.com
</p>

</div>

</section>

<!-- FOOTER -->

<footer>

© 2026 Kenya Life Radio | All Rights Reserved

</footer>

<!-- SCRIPT -->

<script>

function startRadio(){

    // SHOW PLAYER
    document.getElementById("playerBox").style.display = "block";

    // PLAY RADIO
    const radio = document.getElementById("radioPlayer");

    radio.play();

    // AUTO SCROLL TO PLAYER
    document.getElementById("playerBox")
    .scrollIntoView({behavior:"smooth"});

}

</script>

</body>
</html>
