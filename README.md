<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>José Rizal | Bayaning Pilipino</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
:root {
    --bg: #070b16;
    --panel: rgba(255, 255, 255, 0.08);
    --panel-strong: rgba(255, 255, 255, 0.14);
    --gold: #f5c242;
    --text: #eef2ff;
    --muted: #b8c2d3;
    --shadow: 0 30px 80px rgba(0, 0, 0, 0.45);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(rgba(20, 12, 6, 0.22), rgba(20, 12, 6, 0.22)),
                url('jose.png') center 30%/cover no-repeat fixed;
    background-blend-mode: multiply;
    background-attachment: fixed;
    color: var(--text);
    line-height: 1.8;
}

img {
    max-width: 100%;
    display: block;
}

a {
    color: inherit;
    text-decoration: none;
}

.container {
    width: min(1200px, calc(100% - clamp(20px, 4vw, 40px)));
    margin: 0 auto;
}

header {
    position: relative;
    min-height: 100vh;
    background: transparent;
    overflow: hidden;
}

header::before {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 12% 22%, rgba(245,194,66,0.14), transparent 18%),
                radial-gradient(circle at 85% 60%, rgba(225, 210, 168, 0.06), transparent 20%);
    pointer-events: none;
}

header::after {
    content: "";
    position: absolute;
    inset: -20% 0 -20% 0;
    background: radial-gradient(circle, rgba(255,255,255,0.18) 0%, transparent 20%);
    opacity: 0.35;
    transform: translateX(-40%);
    pointer-events: none;
    animation: floatLight 18s linear infinite;
}

.navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: clamp(12px, 2vw, 18px) clamp(16px, 3vw, 40px);
    z-index: 20;
    background: none;
    backdrop-filter: none;
}

.navbar .brand {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.2rem, 3vw, 1.5rem);
    letter-spacing: 1px;
    color: var(--gold);
    text-shadow: 0 0 18px rgba(245,194,66,0.32);
}

.nav-links {
    display: flex;
    gap: clamp(16px, 2vw, 28px);
    flex-wrap: wrap;
}

.nav-links a {
    color: rgba(236, 241, 255, 0.92);
    font-size: clamp(0.85rem, 1.5vw, 0.95rem);
    position: relative;
    transition: color 0.25s ease;
}

.nav-links a::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -6px;
    width: 0;
    height: 2px;
    background: var(--gold);
    transition: width 0.3s ease;
}

.nav-links a:hover,
.nav-links a.active {
    color: var(--gold);
}

.nav-links a:hover::after,
.nav-links a.active::after {
    width: 100%;
}

.menu-toggle {
    display: none;
    align-items: center;
    justify-content: center;
    width: 46px;
    height: 46px;
    border-radius: 14px;
    border: 1px solid rgba(255,255,255,0.14);
    background: rgba(255,255,255,0.05);
    color: var(--text);
    cursor: pointer;
    transition: background 0.25s ease, transform 0.25s ease;
}

.menu-toggle:hover {
    background: rgba(255,255,255,0.12);
}

.menu-toggle span {
    display: block;
    width: 18px;
    height: 2px;
    background: currentColor;
    border-radius: 999px;
    transition: transform 0.25s ease, opacity 0.25s ease;
}

.menu-toggle span + span {
    margin-top: 5px;
}

.menu-toggle.open span:first-child {
    transform: translateY(7px) rotate(45deg);
}

.menu-toggle.open span:nth-child(2) {
    opacity: 0;
}

.menu-toggle.open span:last-child {
    transform: translateY(-7px) rotate(-45deg);
}

.hero-content {
    min-height: calc(100vh - clamp(40px, 8vw, 112px));
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: clamp(60px, 10vw, 120px) clamp(16px, 3vw, 24px) clamp(40px, 8vw, 60px);
    position: relative;
    z-index: 1;
    border-radius: 24px;
    box-shadow: 0 28px 70px rgba(0,0,0,0.28);
}

.hero-copy {
    max-width: 720px;
    position: relative;
    opacity: 0;
    transform: translateY(24px);
    animation: fadeInUp 0.9s ease both 0.2s;
}

.hero-copy h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 5vw, 5.5rem);
    color: var(--gold);
    margin-bottom: clamp(12px, 2vw, 18px);
    line-height: 0.95;
    text-shadow: 0 0 18px rgba(245,194,66,0.18), 0 0 32px rgba(245,194,66,0.08);
}

.eyebrow {
    display: inline-block;
    text-transform: uppercase;
    letter-spacing: 0.22em;
    font-size: clamp(0.75rem, 2vw, 0.9rem);
    color: rgba(245,194,66,0.9);
    margin-bottom: clamp(12px, 2vw, 18px);
}

.hero-copy p {
    color: var(--text);
    font-size: clamp(0.95rem, 2vw, 1.1rem);
    margin-bottom: clamp(18px, 3vw, 28px);
    max-width: 640px;
    margin-left: auto;
    margin-right: auto;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 0.9s ease both 0.35s;
}

.cta-group {
    display: inline-flex;
    gap: 16px;
    flex-wrap: wrap;
    justify-content: center;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 0.9s ease both 0.5s;
}

.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    padding: clamp(12px, 1.5vw, 14px) clamp(24px, 4vw, 30px);
    border-radius: 999px;
    font-weight: 600;
    font-size: clamp(0.9rem, 1.5vw, 1rem);
    transition: transform 0.25s ease, box-shadow 0.25s ease, background-color 0.25s ease, border-color 0.25s ease;
}

.btn-primary {
    background: linear-gradient(135deg, #f5c242, #e3a63d);
    color: #08101e;
    box-shadow: 0 16px 30px rgba(245,194,66,0.18);
}

.btn-secondary {
    border: 1px solid rgba(245, 194, 66, 0.35);
    background: rgba(255,255,255,0.06);
    color: var(--text);
}

.btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 22px 42px rgba(245, 194, 66, 0.18);
}

.section {
    padding: clamp(50px, 10vw, 90px) 0;
    scroll-margin-top: 100px;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 0.9s ease both;
    position: relative;
}

.section:nth-of-type(2) {
    animation-delay: 0.1s;
}

.section:nth-of-type(3) {
    animation-delay: 0.2s;
}

.section:nth-of-type(4) {
    animation-delay: 0.3s;
}

.section:nth-of-type(5) {
    animation-delay: 0.4s;
}

.section:nth-of-type(6) {
    animation-delay: 0.5s;
}

.section:nth-of-type(odd) {
    background: rgba(255, 255, 255, 0.01);
}

.section h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 4vw, 2.4rem);
    color: var(--gold);
    margin-bottom: clamp(16px, 2vw, 22px);
    position: relative;
    z-index: 1;
}

.section h2::after {
    content: "";
    display: block;
    width: 80px;
    height: 3px;
    background: rgba(245,194,66,0.85);
    margin-top: 12px;
    border-radius: 999px;
}

.section p,
.section li {
    color: var(--muted);
}

.section-intro {
    max-width: 820px;
    margin-bottom: clamp(22px, 2vw, 28px);
    color: var(--muted);
}

.grid {
    display: grid;
    gap: clamp(16px, 2vw, 24px);
}

.grid-2 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
}

.grid-3 {
    grid-template-columns: repeat(3, minmax(0, 1fr));
}

.card {
    background: rgba(12, 10, 8, 0.9);
    border: 1px solid rgba(245, 194, 66, 0.18);
    border-radius: 24px;
    overflow: hidden;
    box-shadow: 0 26px 60px rgba(0, 0, 0, 0.22);
    transition: transform 0.35s ease, box-shadow 0.35s ease, border-color 0.35s ease, background 0.35s ease;
    display: flex;
    flex-direction: column;
    text-decoration: none;
}

.card:hover {
    transform: translateY(-6px);
    box-shadow: 0 32px 72px rgba(0, 0, 0, 0.28);
    background: rgba(22, 18, 14, 0.95);
    border-color: rgba(245, 194, 66, 0.28);
}

.card img {
    width: 100%;
    height: clamp(240px, 40vw, 340px);
    object-fit: cover;
    display: block;
    background: linear-gradient(135deg, rgba(245, 194, 66, 0.12), rgba(245, 194, 66, 0.04));
}

.card h3 {
    margin: clamp(18px, 2vw, 22px) clamp(20px, 3vw, 28px) clamp(8px, 1.5vw, 12px);
    color: #f5c242;
    font-size: clamp(1.1rem, 2vw, 1.35rem);
}

.card p {
    color: #d8dfe8;
    padding: 0 clamp(20px, 3vw, 28px) clamp(20px, 3vw, 28px);
    line-height: 1.8;
}

.card p:last-child {
    padding-bottom: clamp(24px, 4vw, 30px);
}

.member-section {
    position: relative;
    gap: clamp(18px, 2vw, 24px);
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    padding: clamp(24px, 3vw, 30px);
    background: transparent;
    border: 1px solid rgba(255, 143, 50, 0.18);
    border-radius: 36px;
    box-shadow: inset 0 0 0 1px rgba(255,255,255,0.08), 0 28px 80px rgba(255, 156, 74, 0.10);
}

.member-section::before {
    content: "";
    position: absolute;
    inset: 0;
    border-radius: 36px;
    background: radial-gradient(circle at top left, rgba(255, 205, 119, 0.10), transparent 28%),
                radial-gradient(circle at bottom right, rgba(255, 118, 51, 0.06), transparent 22%);
    pointer-events: none;
    z-index: -1;
}

.member-card {
    background: rgba(12, 10, 8, 0.6);
    border: 1px solid rgba(255, 156, 62, 0.16);
    border-radius: 28px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: clamp(24px, 3vw, 28px);
    backdrop-filter: blur(8px);
    box-shadow: 0 20px 50px rgba(255, 141, 37, 0.16);
    transition: transform 0.35s ease, box-shadow 0.35s ease, border-color 0.35s ease, background 0.35s ease;
}

.member-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 28px 70px rgba(255, 149, 44, 0.24);
    border-color: rgba(255, 156, 62, 0.3);
    background: rgba(12, 10, 8, 0.75);
}

.member-avatar {
    width: clamp(110px, 18vw, 140px);
    height: clamp(110px, 18vw, 140px);
    border-radius: 50%;
    margin-bottom: clamp(20px, 2vw, 24px);
    object-fit: cover;
    display: block;
    border: 2px solid rgba(255,255,255,0.18);
    box-shadow: 0 20px 50px rgba(255, 141, 37, 0.22);
}

.member-card h3 {
    margin: 0 0 clamp(10px, 1.5vw, 14px);
    color: #ffd27e;
    font-size: clamp(1.05rem, 1.8vw, 1.25rem);
}

.member-card p {
    color: #f5e9cf;
    font-size: clamp(0.95rem, 1.6vw, 1rem);
    line-height: 1.7;
}

a.card.card-link {
    color: inherit;
    text-decoration: none;
}

a.card.card-link:hover {
    text-decoration: none;
}

.detail-section {
    background: rgba(12, 10, 8, 0.95);
    border: 1px solid rgba(245,194,66,0.16);
    box-shadow: 0 30px 90px rgba(0,0,0,0.35);
    padding: clamp(50px, 10vw, 90px) clamp(24px, 4vw, 40px);
    margin-top: clamp(40px, 6vw, 60px);
}

.detail-section h2 {
    color: #ffffff;
    text-shadow: 0 0 18px rgba(245,194,66,0.18);
}

.detail-section p {
    color: #d8dfe8;
    line-height: 1.9;
    margin-bottom: 1.2rem;
}

.detail-section .detail-highlight {
    background: rgba(245,194,66,0.08);
    border-left: 4px solid rgba(245,194,66,0.9);
    padding: 18px 22px;
    border-radius: 18px;
}

.footer-note {
    max-width: 700px;
    margin: 0 auto;
}

footer {
    border-top: 1px solid rgba(255,255,255,0.08);
    padding: clamp(20px, 3vw, 30px) 0 clamp(10px, 2vw, 16px);
    text-align: center;
    color: var(--muted);
    font-size: clamp(0.85rem, 1.5vw, 0.95rem);
}

@media (max-width: 1024px) {
    .container {
        width: min(900px, calc(100% - 30px));
    }

    .grid {
        gap: clamp(16px, 3vw, 24px);
    }

    .navbar {
        padding: clamp(12px, 2vw, 18px) 0;
        gap: clamp(12px, 2vw, 28px);
    }

    .nav-links {
        gap: clamp(16px, 2vw, 28px);
        font-size: 0.9rem;
    }
}

@media (max-width: 768px) {
    .container {
        width: min(700px, calc(100% - 24px));
    }

    .menu-toggle {
        display: flex;
    }

    .navbar {
        padding: clamp(12px, 2vw, 18px) clamp(16px, 3vw, 20px);
    }

    .nav-links {
        position: absolute;
        top: 100%;
        right: 0;
        left: 0;
        margin: 0 clamp(16px, 3vw, 24px);
        background: rgba(12, 10, 8, 0.96);
        border-bottom-left-radius: 24px;
        border-bottom-right-radius: 24px;
        flex-direction: column;
        gap: 10px;
        padding: 18px 18px 22px;
        max-height: 0;
        overflow: hidden;
        opacity: 0;
        visibility: hidden;
        transition: max-height 0.32s ease, opacity 0.32s ease, visibility 0.32s ease;
        box-shadow: 0 25px 60px rgba(0,0,0,0.28);
        border: 1px solid rgba(245,194,66,0.12);
    }

    .nav-links.open {
        max-height: 520px;
        opacity: 1;
        visibility: visible;
    }

    .nav-links a {
        padding: 12px 0;
    }

    .grid-2 {
        grid-template-columns: 1fr;
    }

    .grid-3 {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .navbar {
        flex-direction: column;
        align-items: flex-start;
        gap: 12px;
        padding: 12px 0;
    }

    .nav-links {
        flex-direction: column;
        gap: 10px;
    }

    .hero-content {
        padding: clamp(80px, 15vw, 120px) clamp(16px, 3vw, 24px) clamp(40px, 10vw, 60px);
    }
}

@media (max-width: 640px) {
    .container {
        width: min(100%, calc(100% - 20px));
    }

    .grid-2,
    .grid-3 {
        grid-template-columns: 1fr;
    }

    .hero-copy h1 {
        font-size: clamp(1.8rem, 6vw, 3.4rem);
    }

    .eyebrow {
        font-size: clamp(0.65rem, 1.5vw, 0.8rem);
    }

    .hero-copy p {
        font-size: clamp(0.9rem, 2vw, 1rem);
    }

    .cta-group {
        width: 100%;
        flex-direction: column;
    }

    .cta-group .btn {
        width: 100%;
        padding: clamp(12px, 2vw, 14px) clamp(20px, 4vw, 30px);
        font-size: clamp(0.9rem, 2vw, 1rem);
    }

    .navbar .brand {
        font-size: clamp(1.2rem, 3vw, 1.5rem);
    }
}

@media (max-width: 480px) {
    .container {
        width: calc(100% - 16px);
    }

    .hero-copy h1 {
        font-size: clamp(1.6rem, 5vw, 2.8rem);
    }

    .btn {
        padding: clamp(10px, 2vw, 12px) clamp(16px, 3vw, 24px);
    }

    .section {
        padding: clamp(30px, 8vw, 50px) 0;
    }

    .nav-links {
        font-size: 0.85rem;
    }
}

@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(24px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.hero-copy {
    opacity: 0;
    transform: translateY(24px);
    animation: fadeInUp 0.9s ease both 0.2s;
}

.hero-copy h1 {
    animation: glowPulse 4s ease-in-out infinite;
}

@keyframes glowPulse {
    0%, 100% {
        text-shadow: 0 0 12px rgba(245,194,66,0.18), 0 0 28px rgba(245,194,66,0.08);
    }
    50% {
        text-shadow: 0 0 18px rgba(245,194,66,0.28), 0 0 34px rgba(245,194,66,0.12);
    }
}

@keyframes floatLight {
    0% {
        transform: translateX(-40%) translateY(-10%);
        opacity: 0.3;
    }
    50% {
        transform: translateX(40%) translateY(10%);
        opacity: 0.45;
    }
    100% {
        transform: translateX(-40%) translateY(-10%);
        opacity: 0.3;
    }
}

.course-panel {
    background: linear-gradient(135deg, rgba(12, 10, 8, 0.9), rgba(20, 12, 6, 0.9));
    border: 3px solid #f5c242;
    border-radius: 24px;
    padding: 40px;
    max-width: 800px;
    margin: 0 auto;
    box-shadow: 0 28px 70px rgba(0,0,0,0.28), inset 0 0 0 2px rgba(245,194,66,0.3), 0 0 30px rgba(245,194,66,0.3);
    position: relative;
}

.course-panel::before {
    content: '';
    position: absolute;
    top: -3px;
    left: -3px;
    right: -3px;
    bottom: -3px;
    background: linear-gradient(45deg, #f5c242, #ffd700, #f5c242);
    border-radius: 27px;
    z-index: -1;
    opacity: 0.7;
}

.course-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}

.course-item {
    display: flex;
    flex-direction: column;
    gap: 8px;
    background: rgba(245, 194, 66, 0.05);
    border: 1px solid rgba(245, 194, 66, 0.2);
    border-radius: 12px;
    padding: 16px;
    transition: transform 0.3s ease, box-shadow 0.3s ease, background 0.3s ease;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
}

.course-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.3), 0 0 15px rgba(245,194,66,0.4);
    background: rgba(245, 194, 66, 0.1);
}

.course-item.full-width {
    grid-column: 1 / -1;
}

.label {
    font-weight: 600;
    color: #f5c242;
    text-transform: uppercase;
    font-size: 0.9rem;
    letter-spacing: 0.5px;
}

.value {
    color: #fff;
    font-size: 1.1rem;
    font-weight: 600;
    line-height: 1.4;
}

.highlight {
    background: linear-gradient(90deg, #f5c242, #ffd700);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-weight: bold;
}

@media (max-width: 768px) {
    .course-grid {
        grid-template-columns: 1fr;
    }
    .course-panel {
        padding: 24px;
    }
}
</style>

</head>
<body>
<header id="home">
    <div class="container">
        <nav class="navbar">
            <div class="brand">José Rizal</div>
            <button class="menu-toggle" aria-label="Toggle navigation" type="button">
                <span></span>
                <span></span>
                <span></span>
            </button>
            <div class="nav-links">
                <a href="#home" class="active">Home</a>
                <a href="#about">About</a>
                <a href="#impact">Impact</a>
                <a href="#works">Works</a>
                <a href="#timeline">Timeline</a>
                <a href="#quotes">Quotes</a>
                <a href="#members">Members</a>
                <a href="#legacy">Legacy</a>
                <a href="#course">Course</a>
            </div>
        </nav>
        <div class="hero-content">
            <div class="hero-copy">
                <p class="eyebrow">National Hero of the Philippines</p>
                <h1>José Rizal: Writer, Doctor, Reformer</h1>
                <p>From a quiet town in Laguna to the great capitals of Europe, José Rizal carried the hopes of a nation. His words, ideas and peaceful courage continue to inspire Filipino pride and unity.</p>
                <div class="cta-group">
                    <a href="#about" class="btn btn-primary">Discover His Story</a>
                    <a href="#works" class="btn btn-secondary">Explore His Works</a>
                </div>
            </div>
        </div>
    </div>
</header>
<main class="container">
    <section id="about" class="section">
        <h2>About José Rizal</h2>
        <div class="grid grid-3">
            <a class="card card-link" href="early-life.html">
                <img src="bata.jpg" alt="Early Life">
                <h3>Early Life</h3>
                <p>José Protacio Rizal Mercado y Alonzo Realonda was born on June 19, 1861 in Calamba, Laguna. He was the seventh of eleven children and grew up in a family that valued education, language, and national pride.</p>
                <p>His parents, Francisco and Teodora, nurtured his talent and taught him that learning and discipline could empower his people.</p>
            </a>
            <a class="card card-link" href="education.html">
                <img src="binata.jpg" alt="Education and Europe">
                <h3>Education and Europe</h3>
                <p>Rizal studied at Ateneo Municipal in Manila and then pursued medicine at Universidad Central de Madrid. During his years in Europe he also studied languages, arts, and political science.</p>
                <p>His travels through Spain, France, Germany, and Belgium gave him a broader vision of reform and human rights.</p>
            </a>
            <a class="card card-link" href="artist.html">
                <img src="lagas.jpg" alt="Artist, Scientist, Reformer">
                <h3>Artist, Scientist, Reformer</h3>
                <p>Beyond writing, Rizal was an ophthalmologist, sculptor, linguist, and thinker. He used science and art in service of his people.</p>
                <p>His belief in education, civic duty, and peaceful reform made him a unique leader for the Philippine movement.</p>
            </a>
        </div>
    </section>
    <section id="impact" class="section">
        <h2>Impact and Influence</h2>
        <div class="grid grid-2">
            <a class="card card-link" href="voice.html">
                <img src="voice.png" alt="Voice of Reform">
                <h3>Voice of Reform</h3>
                <p>Rizal’s writings exposed the abuses of colonial authorities and encouraged Filipinos to seek justice and equal rights.</p>
                <p>His novels and essays helped persuade many to support peaceful reform rather than violent revolution.</p>
            </a>
            <a class="card card-link" href="national.html">
                <img src="national.png" alt="National Identity">
                <h3>National Identity</h3>
                <p>Rizal inspired a sense of Filipino identity, dignity, and independence. He reminded his countrymen that true freedom begins with knowledge and self-respect.</p>
                <p>His life continues to remind Filipinos that character, courage, and ideas can change history.</p>
            </a>
        </div>
    </section>
    <section id="works" class="section">
        <h2>Major Works</h2>
        <div class="grid grid-2">
            <a class="card card-link" href="noli.html">
                <img src="noli.png" alt="Noli Me Tangere book cover">
                <h3>Noli Me Tangere</h3>
                <p>This groundbreaking novel revealed the injustices of colonial society and sparked the awakening of Filipino national consciousness.</p>
            </a>
            <a class="card card-link" href="el-filibusterismo.html">
                <img src="elpi.png" alt="El Filibusterismo book cover">
                <h3>El Filibusterismo</h3>
                <p>The darker sequel to Noli, this work calls for deep social reform and warns against corruption and oppression.</p>
            </a>
            <a class="card card-link" href="letters-essays.html">
                <img src="letters.png" alt="Letters and Essays by Rizal">
                <h3>Letters and Essays</h3>
                <p>His letters and essays, including writings for La Solidaridad, expressed his social and political views with clarity and conviction.</p>
            </a>
            <a class="card card-link" href="poetry-journalism.html">
                <img src="poetry.png" alt="Rizal poetry and journalism">
                <h3>Poetry and Journalism</h3>
                <p>Rizal also wrote poetry and newspaper articles that expressed love for country, education, and the human spirit.</p>
            </a>
        </div>
    </section>
    <section id="timeline" class="section">
        <h2>Timeline</h2>
        <div class="course-panel">
            <div class="course-grid">
                <a class="course-item" href="1861-birth.html">
                    <span class="label">1861</span>
                    <span class="value"><span class="highlight">Birth in Calamba</span> - Born into a loving and educated family, Rizal showed early gifts in language and learning.</span>
                </a>
                <a class="course-item" href="1872-gomburza.html">
                    <span class="label">1872</span>
                    <span class="value"><span class="highlight">Gomburza Execution</span> - The execution of three Filipino priests inspired Rizal and his generation to fight for justice and reform.</span>
                </a>
                <a class="course-item" href="1887-noli.html">
                    <span class="label">1887</span>
                    <span class="value"><span class="highlight">Noli Me Tangere Published</span> - Rizal published his first novel in Berlin, exposing the corruption of colonial society and awakening national sentiment.</span>
                </a>
                <a class="course-item" href="1892-liga.html">
                    <span class="label">1892</span>
                    <span class="value"><span class="highlight">La Liga Filipina</span> - He established La Liga Filipina to promote education, unity, and peaceful reform among Filipinos.</span>
                </a>
                <a class="course-item full-width" href="1896-martyrdom.html">
                    <span class="label">1896</span>
                    <span class="value"><span class="highlight">Martyrdom</span> - Rizal was executed on December 30, 1896 at Bagumbayan, becoming a lasting symbol of freedom and sacrifice.</span>
                </a>
            </div>
        </div>
    </section>
    <section id="quotes" class="section">
        <h2>Famous Quotes</h2>
        <div class="course-panel">
            <div class="course-grid">
                <div class="course-item full-width">
                    <span class="value">“<span class="highlight">The youth is the hope of our future.</span>”</span>
                </div>
                <div class="course-item full-width">
                    <span class="value">“<span class="highlight">He who does not know how to look back at where he came from will never get to his destination.</span>”</span>
                </div>
                <div class="course-item full-width">
                    <span class="value">“<span class="highlight">Freedom has no meaning if it is only inherited and not defended and improved upon.</span>”</span>
                </div>
                <div class="course-item full-width">
                    <span class="value">“<span class="highlight">There can be no tyrants where there are no slaves.</span>”</span>
                </div>
            </div>
        </div>
    </section>
    <section id="legacy" class="section">
        <h2>His Legacy Today</h2>
        <p class="section-intro">Rizal’s legacy is more than a story from the past. It is a living inspiration that continues to shape education, national identity, and the values of generations who follow.</p>
        <div class="course-panel">
            <div class="course-grid">
                <div class="course-item">
                    <span class="label">A National Symbol</span>
                    <span class="value">Rizal’s life and letters continue to inspire Filipinos to value education, civic courage, and peaceful change.</span>
                </div>
                <div class="course-item">
                    <span class="label">An Enduring Vision</span>
                    <span class="value">From schools to monuments and national holidays, his message still guides the Philippines toward unity and progress.</span>
                </div>
                <div class="course-item">
                    <span class="label">A Legacy of Learning</span>
                    <span class="value">His belief in knowledge as the foundation of freedom has helped shape modern Filipino education and the pursuit of critical thinking.</span>
                </div>
                <div class="course-item">
                    <span class="label">Inspiring Future Leaders</span>
                    <span class="value">Rizal remains a model for young leaders who seek justice, dignity, and change through ideas and peaceful action.</span>
                </div>
            </div>
        </div>
    </section>
    <section id="course" class="section">
        <h2>Course Details</h2>
        <div class="course-panel">
            <div class="course-grid">
                <div class="course-item">
                    <span class="label">Subject</span>
                    <span class="value">Life and Works of <span class="highlight">Rizal</span></span>
                </div>
                <div class="course-item">
                    <span class="label">Course Code</span>
                    <span class="value"><span class="highlight">GE9</span></span>
                </div>
                <div class="course-item">
                    <span class="label">Section</span>
                    <span class="value"><span class="highlight">BSIT-3B</span></span>
                </div>
                <div class="course-item">
                    <span class="label">Institution</span>
                    <span class="value">Samar State <span class="highlight">University</span></span>
                </div>
                <div class="course-item">
                    <span class="label">Program</span>
                    <span class="value">Bachelor of Science in <span class="highlight">Information Technology</span></span>
                </div>
                <div class="course-item">
                    <span class="label">Academic Year</span>
                    <span class="value"><span class="highlight">2025-2026</span></span>
                </div>
                <div class="course-item full-width">
                    <span class="label">Instructor</span>
                    <span class="value"><span class="highlight">MS. Rachel R. Nacionales</span></span>
                </div>
            </div>
        </div>
    </section>
    <section id="members" class="section">
        <h2>Mga BIDA BIDA</h2>
        <p class="section-intro">A dedicated roster of students who created this tribute site through research, design, and teamwork.</p>
        <div class="member-section">
            <div class="member-card">
                <img class="member-avatar" src="https://ui-avatars.com/api/?name=Rex+Bismanos&background=F5C242&color=08101E&size=256" alt="Rex Bismanos">
                <h3>Rex Bismanos</h3>
                <p>Leader</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="https://ui-avatars.com/api/?name=Aron+Lan+Binas&background=F5C242&color=08101E&size=256" alt="Aron Lan Binas">
                <h3>Aron Lan Efraem A Binas</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="karen.jpg" alt="Karen Quebada">
                <h3>Karen Quebada</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="angel.jpg" alt="Angel Rose Sibugon">
                <h3>Angel Rose Sibugon</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="lordes.webp" alt="Ma. Lourdes Cajepe">
                <h3>Ma. Lourdes Cajepe</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="nadine.jpg" alt="Nadine Fedeles">
                <h3>Nadine Fedeles</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="rodeza.jpg" alt="Rodeza Enverzo">
                <h3>Rodeza Enverzo</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="kristel.jpg" alt="Ma. Kristelle Mabulac">
                <h3>Ma. Kristelle Mabulac</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="anna.jpg" alt="Ma. Anna Gabejan">
                <h3>Ma. Anna Gabejan</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="lilian.jpg" alt="Ma. Lilian Mabanan">
                <h3>Ma. Lilian Mabanan</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="allen.jpg" alt="Mark Allen Gabuay">
                <h3>Mark Allen Gabuay</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="lester.jpg" alt="John Lester Bacongan">
                <h3>John Lester Bacongan</h3>
                <p>Member</p>
            </div>
            <div class="member-card">
                <img class="member-avatar" src="trixie.jpg" alt="Trixie Hernandez">
                <h3>Trixie Hernandez</h3>
                <p>Member</p>
            </div>
        </div>
    </section>
</main>
<footer>
    <p class="footer-note">© 2026 A Tribute to the Legacy of José Rizal. This site aims to inspire and educate about the national hero.</p>
</footer>
<script>
const sections = document.querySelectorAll('section');
const navLinks = document.querySelectorAll('.nav-links a');
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    const id = entry.target.id;
    const link = document.querySelector(`.nav-links a[href="#${id}"]`);
    if (link) {
      link.classList.toggle('active', entry.isIntersecting);
    }
  });
}, { threshold: 0.45 });
sections.forEach(section => observer.observe(section));
</script>
<script>
const menuToggle = document.querySelector('.menu-toggle');
const navMenu = document.querySelector('.nav-links');
if (menuToggle && navMenu) {
  menuToggle.addEventListener('click', () => {
    navMenu.classList.toggle('open');
    menuToggle.classList.toggle('open');
  });
  document.querySelectorAll('.nav-links a').forEach(link => {
    link.addEventListener('click', () => {
      navMenu.classList.remove('open');
      menuToggle.classList.remove('open');
    });
  });
}
</script>
</body>
</html>
