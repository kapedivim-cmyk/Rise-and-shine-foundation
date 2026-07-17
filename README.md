<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
  <title>Rise and Shine Fondation | Lubumbashi</title>
  <!-- Google Fonts : Poppins + Playfair Display -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Playfair+Display:ital,wght@0,500;0,600;0,700;1,500&display=swap" rel="stylesheet">
  <!-- Font Awesome 6 pour icônes -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* ===== VARIABLES THEME ===== */
    :root {
      --bg-primary: #0a0a0a;
      --bg-secondary: #141414;
      --bg-card: rgba(20,20,20,0.85);
      --bg-header: rgba(10,10,10,0.88);
      --text-primary: #e8e6e0;
      --text-secondary: #c4c0b8;
      --gold: #d4af37;
      --gold-dark: #b8860b;
      --gold-light: #f5e6b0;
      --border-gold: rgba(212,175,55,0.25);
      --shadow-color: rgba(0,0,0,0.6);
      --whatsapp: #25D366;
      --transition-speed: 0.4s;
    }

    [data-theme="light"] {
      --bg-primary: #f5f2ed;
      --bg-secondary: #e8e4dd;
      --bg-card: rgba(255,255,255,0.92);
      --bg-header: rgba(245,242,237,0.92);
      --text-primary: #1a1a1a;
      --text-secondary: #3a3a3a;
      --gold: #b8860b;
      --gold-dark: #8b6b0a;
      --gold-light: #d4af37;
      --border-gold: rgba(184,134,11,0.3);
      --shadow-color: rgba(0,0,0,0.15);
    }

    /* ===== RESET & BASE ===== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-primary);
      color: var(--text-primary);
      font-family: 'Poppins', sans-serif;
      line-height: 1.7;
      font-weight: 400;
      overflow-x: hidden;
      transition: background-color var(--transition-speed) ease, color var(--transition-speed) ease;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
    }

    h1, h2, h3, .playfair {
      font-family: 'Playfair Display', serif;
      font-weight: 600;
      letter-spacing: -0.02em;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* ===== ANIMATIONS ===== */
    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(40px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes slideInLeft {
      from { opacity: 0; transform: translateX(-60px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes slideInRight {
      from { opacity: 0; transform: translateX(60px); }
      to { opacity: 1; transform: translateX(0); }
    }
    @keyframes scaleIn {
      from { opacity: 0; transform: scale(0.85); }
      to { opacity: 1; transform: scale(1); }
    }
    @keyframes pulseGold {
      0%, 100% { box-shadow: 0 0 0 0 rgba(212,175,55,0.4); }
      50% { box-shadow: 0 0 0 15px rgba(212,175,55,0); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    @keyframes shimmer {
      0% { background-position: -200% center; }
      100% { background-position: 200% center; }
    }
    @keyframes glowPulse {
      0%, 100% { opacity: 0.6; }
      50% { opacity: 1; }
    }

    .animate-fade-up {
      animation: fadeInUp 0.8s ease forwards;
    }
    .animate-slide-left {
      animation: slideInLeft 0.8s ease forwards;
    }
    .animate-slide-right {
      animation: slideInRight 0.8s ease forwards;
    }
    .animate-scale {
      animation: scaleIn 0.7s ease forwards;
    }
    .animate-float {
      animation: float 3s ease-in-out infinite;
    }
    .animate-glow {
      animation: glowPulse 2s ease-in-out infinite;
    }

    .delay-1 { animation-delay: 0.1s; }
    .delay-2 { animation-delay: 0.2s; }
    .delay-3 { animation-delay: 0.3s; }
    .delay-4 { animation-delay: 0.4s; }
    .delay-5 { animation-delay: 0.5s; }

    /* ===== HEADER ===== */
    .site-header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background-color: var(--bg-header);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border-gold);
      padding: 0.7rem 0;
      transition: background-color var(--transition-speed) ease, border-color var(--transition-speed) ease;
    }
    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 0.5rem;
    }
    .logo img {
      height: 46px;
      width: auto;
      display: block;
    }
    .nav-menu {
      display: flex;
      align-items: center;
      gap: 1.8rem;
    }
    .nav-menu a {
      color: var(--text-primary);
      text-decoration: none;
      font-weight: 500;
      font-size: 0.9rem;
      transition: color 0.25s, transform 0.2s;
      letter-spacing: 0.3px;
      position: relative;
    }
    .nav-menu a::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: var(--gold);
      transition: width 0.3s ease;
    }
    .nav-menu a:hover::after {
      width: 100%;
    }
    .nav-menu a:hover {
      color: var(--gold);
      transform: translateY(-1px);
    }
    .btn-donate {
      background-color: var(--gold);
      color: #0a0a0a;
      font-weight: 600;
      padding: 0.5rem 1.5rem;
      border-radius: 30px;
      text-decoration: none;
      font-size: 0.85rem;
      transition: background 0.25s, transform 0.2s, box-shadow 0.3s;
      border: none;
      cursor: pointer;
      letter-spacing: 0.4px;
    }
    .btn-donate:hover {
      background-color: var(--gold-dark);
      transform: translateY(-2px) scale(1.02);
      box-shadow: 0 6px 25px rgba(212,175,55,0.35);
    }

    /* Theme Toggle Button */
    .theme-toggle {
      background: var(--bg-secondary);
      border: 2px solid var(--border-gold);
      color: var(--gold);
      width: 42px;
      height: 42px;
      border-radius: 50%;
      cursor: pointer;
      font-size: 1.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s ease;
      position: relative;
      overflow: hidden;
    }
    .theme-toggle:hover {
      transform: rotate(30deg) scale(1.1);
      background: var(--gold);
      color: var(--bg-primary);
      border-color: var(--gold);
    }
    .theme-toggle i {
      transition: transform 0.5s ease;
    }
    .theme-toggle:hover i {
      transform: rotate(90deg);
    }

    .mobile-menu-toggle {
      display: none;
      background: none;
      border: none;
      color: var(--gold);
      font-size: 1.8rem;
      cursor: pointer;
      transition: transform 0.3s;
    }
    .mobile-menu-toggle:hover {
      transform: rotate(90deg);
    }

    /* ===== HERO ===== */
    .hero {
      position: relative;
      width: 100%;
      min-height: 92vh;
      background: url('https://i.postimg.cc/1gBhVHsr/IMG-20260414-WA0077.jpg') center center / cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 4rem;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse at center, rgba(10,10,10,0.3) 0%, rgba(10,10,10,0.75) 100%);
      z-index: 1;
    }
    .hero-overlay {
      position: absolute;
      inset: 0;
      background: rgba(10, 10, 10, 0.5);
      z-index: 1;
    }
    [data-theme="light"] .hero-overlay {
      background: rgba(245, 242, 237, 0.4);
    }
    .hero-content {
      position: relative;
      z-index: 2;
      text-align: center;
      max-width: 850px;
      padding: 2rem;
    }
    .hero-content h1 {
      font-size: clamp(2.8rem, 7vw, 4.8rem);
      color: var(--gold-light);
      line-height: 1.1;
      margin-bottom: 1.2rem;
      text-shadow: 0 4px 30px rgba(0,0,0,0.5);
      animation: fadeInUp 1s ease;
    }
    .hero-content .subtitle {
      font-size: 1.2rem;
      margin-bottom: 2.5rem;
      font-weight: 300;
      color: var(--text-primary);
      animation: fadeInUp 1s ease 0.2s both;
    }
    .hero-buttons {
      display: flex;
      gap: 1.2rem;
      justify-content: center;
      flex-wrap: wrap;
      margin-bottom: 2.5rem;
      animation: fadeInUp 1s ease 0.4s both;
    }
    .btn-gold {
      background: var(--gold);
      color: #0a0a0a;
      padding: 0.9rem 2.4rem;
      border-radius: 30px;
      font-weight: 600;
      text-decoration: none;
      transition: all 0.3s ease;
      box-shadow: 0 4px 20px rgba(212,175,55,0.3);
    }
    .btn-gold:hover {
      background: var(--gold-dark);
      transform: translateY(-3px) scale(1.03);
      box-shadow: 0 8px 35px rgba(212,175,55,0.5);
    }
    .btn-outline {
      border: 2px solid var(--gold);
      color: var(--gold);
      padding: 0.9rem 2.4rem;
      border-radius: 30px;
      font-weight: 600;
      text-decoration: none;
      background: transparent;
      transition: all 0.3s ease;
    }
    .btn-outline:hover {
      background: var(--gold);
      color: #0a0a0a;
      transform: translateY(-3px);
      box-shadow: 0 8px 30px rgba(212,175,55,0.3);
    }
    .countdown {
      display: flex;
      justify-content: center;
      gap: 1.8rem;
      font-family: 'Poppins', sans-serif;
      margin-top: 1rem;
      animation: fadeInUp 1s ease 0.6s both;
    }
    .countdown-item {
      background: rgba(10,10,10,0.6);
      backdrop-filter: blur(8px);
      padding: 0.8rem 1.4rem;
      border-radius: 14px;
      min-width: 75px;
      border: 1px solid var(--border-gold);
      transition: all 0.3s ease;
    }
    .countdown-item:hover {
      transform: translateY(-5px);
      border-color: var(--gold);
      box-shadow: 0 8px 30px rgba(212,175,55,0.15);
    }
    .countdown-number {
      font-size: 2.2rem;
      font-weight: 700;
      color: var(--gold-light);
    }
    .countdown-label {
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      font-weight: 400;
      color: var(--text-secondary);
    }

    /* ===== SECTIONS ===== */
    section {
      padding: 4.5rem 0;
    }
    .section-title {
      font-size: 2.8rem;
      color: var(--gold);
      margin-bottom: 2.5rem;
      text-align: center;
      font-weight: 600;
      position: relative;
    }
    .section-title::after {
      content: '';
      display: block;
      width: 80px;
      height: 3px;
      background: var(--gold);
      margin: 0.8rem auto 0;
      border-radius: 4px;
      animation: pulseGold 2s infinite;
    }

    /* ===== MISSION ===== */
    .mission-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2.5rem;
      text-align: center;
    }
    .mission-item {
      background: var(--bg-card);
      padding: 2.5rem 1.8rem;
      border-radius: 16px;
      border: 1px solid var(--border-gold);
      transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      backdrop-filter: blur(4px);
    }
    .mission-item:hover {
      transform: translateY(-10px) scale(1.02);
      border-color: var(--gold);
      box-shadow: 0 15px 50px rgba(212,175,55,0.12);
    }
    .mission-item i {
      font-size: 2.8rem;
      color: var(--gold);
      margin-bottom: 1.2rem;
      display: inline-block;
      transition: transform 0.4s;
    }
    .mission-item:hover i {
      transform: scale(1.2) rotate(5deg);
    }
    .mission-item h3 {
      font-size: 1.6rem;
      margin-bottom: 0.8rem;
      color: var(--gold-light);
    }
    .mission-item p {
      font-size: 0.95rem;
      font-weight: 300;
      color: var(--text-secondary);
    }

    /* ===== EVENT ===== */
    .event-details {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      justify-content: center;
      background: var(--bg-card);
      padding: 2rem;
      border-radius: 16px;
      margin: 2rem 0;
      border-left: 5px solid var(--gold);
      backdrop-filter: blur(4px);
      transition: all 0.3s ease;
    }
    .event-details:hover {
      box-shadow: 0 8px 40px rgba(212,175,55,0.08);
    }
    .event-card {
      display: flex;
      align-items: center;
      gap: 1rem;
      font-size: 1.1rem;
    }
    .event-card i {
      transition: transform 0.3s;
    }
    .event-card:hover i {
      transform: scale(1.2) rotate(-10deg);
    }

    .map-container {
      margin-top: 2rem;
      border-radius: 16px;
      overflow: hidden;
      height: 320px;
      width: 100%;
      border: 2px solid var(--border-gold);
      transition: all 0.4s ease;
      box-shadow: 0 8px 30px rgba(0,0,0,0.2);
    }
    .map-container:hover {
      border-color: var(--gold);
      box-shadow: 0 12px 50px rgba(212,175,55,0.15);
      transform: scale(1.005);
    }
    .map-container iframe {
      width: 100%;
      height: 100%;
      border: 0;
    }
    .map-link {
      display: inline-block;
      text-align: center;
      margin-top: 1.2rem;
      color: var(--gold);
      text-decoration: none;
      font-weight: 500;
      transition: all 0.3s ease;
      padding: 0.5rem 1.5rem;
      border-radius: 30px;
      border: 1px solid var(--border-gold);
    }
    .map-link:hover {
      background: var(--gold);
      color: var(--bg-primary);
      transform: translateY(-2px);
      box-shadow: 0 6px 25px rgba(212,175,55,0.3);
    }

    /* ===== GALERIE ===== */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.2rem;
    }
    .gallery-item {
      position: relative;
      overflow: hidden;
      aspect-ratio: 4 / 3;
      border-radius: 12px;
      box-shadow: 0 4px 20px var(--shadow-color);
      cursor: pointer;
      transition: all 0.4s ease;
    }
    .gallery-item:hover {
      transform: scale(1.03);
      box-shadow: 0 12px 45px var(--shadow-color);
      z-index: 5;
    }
    .gallery-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: block;
      transition: transform 0.6s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    }
    .gallery-item:hover img {
      transform: scale(1.1);
    }
    .gallery-caption {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: rgba(10,10,10,0.8);
      backdrop-filter: blur(6px);
      color: var(--gold-light);
      padding: 0.9rem 1.2rem;
      font-size: 0.85rem;
      font-weight: 500;
      transform: translateY(100%);
      transition: transform 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
      letter-spacing: 0.3px;
    }
    .gallery-item:hover .gallery-caption {
      transform: translateY(0);
    }

    /* ===== DONATION ===== */
    .donation-box {
      background: var(--bg-card);
      padding: 2.8rem 2.5rem;
      border-radius: 20px;
      text-align: center;
      border: 1px solid var(--border-gold);
      margin-bottom: 2rem;
      backdrop-filter: blur(4px);
      transition: all 0.4s ease;
    }
    .donation-box:hover {
      box-shadow: 0 8px 45px rgba(212,175,55,0.06);
    }
    .community-box {
      background: var(--bg-card);
      padding: 2.5rem;
      border-radius: 20px;
      text-align: center;
      border: 1px solid rgba(37, 211, 102, 0.3);
      margin-top: 2rem;
      backdrop-filter: blur(4px);
      transition: all 0.4s ease;
    }
    .community-box:hover {
      box-shadow: 0 8px 45px rgba(37, 211, 102, 0.06);
      border-color: rgba(37, 211, 102, 0.6);
    }
    .amount-options {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      margin: 2rem 0;
    }
    .amount-btn {
      background: transparent;
      border: 2px solid var(--gold);
      color: var(--gold);
      padding: 0.8rem 2rem;
      border-radius: 30px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      font-family: 'Poppins', sans-serif;
      min-width: 120px;
    }
    .amount-btn:hover {
      background: var(--gold);
      color: var(--bg-primary);
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(212,175,55,0.25);
    }
    .amount-btn.active {
      background: var(--gold);
      color: var(--bg-primary);
      box-shadow: 0 4px 20px rgba(212,175,55,0.3);
    }
    .whatsapp-btn {
      background: var(--whatsapp);
      color: white;
      padding: 1rem 2.8rem;
      border-radius: 40px;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      text-decoration: none;
      margin-top: 1rem;
      transition: all 0.3s ease;
      box-shadow: 0 4px 20px rgba(37, 211, 102, 0.3);
    }
    .whatsapp-btn:hover {
      background: #1da851;
      transform: translateY(-3px) scale(1.02);
      box-shadow: 0 8px 35px rgba(37, 211, 102, 0.4);
    }
    .whatsapp-group-btn {
      background: transparent;
      border: 2px solid var(--whatsapp);
      color: var(--whatsapp);
      padding: 0.9rem 2.4rem;
      border-radius: 40px;
      font-weight: 600;
      display: inline-flex;
      align-items: center;
      gap: 0.7rem;
      text-decoration: none;
      transition: all 0.3s ease;
    }
    .whatsapp-group-btn:hover {
      background: var(--whatsapp);
      color: white;
      transform: translateY(-3px);
      box-shadow: 0 8px 30px rgba(37, 211, 102, 0.25);
    }
    .phone-number {
      font-size: 2rem;
      color: var(--gold);
      font-weight: 700;
      margin: 1rem 0;
      letter-spacing: 1px;
    }

    /* ===== FOOTER ===== */
    footer {
      background: var(--bg-secondary);
      padding: 2.5rem 0;
      border-top: 1px solid var(--border-gold);
      text-align: center;
      transition: background var(--transition-speed) ease;
    }
    footer p {
      font-weight: 300;
      line-height: 2;
      color: var(--text-secondary);
    }
    footer .fas {
      color: var(--gold);
    }

    /* ===== RESPONSIVE ===== */
    @media (max-width: 992px) {
      .mission-grid { grid-template-columns: repeat(2, 1fr); }
    }
    @media (max-width: 768px) {
      .nav-menu {
        display: none;
        flex-direction: column;
        width: 100%;
        background: var(--bg-primary);
        padding: 1.2rem 0;
        margin-top: 0.8rem;
        border-radius: 12px;
        border: 1px solid var(--border-gold);
      }
      .nav-menu.active {
        display: flex;
      }
      .mobile-menu-toggle {
        display: block;
      }
      .mission-grid { grid-template-columns: 1fr; }
      .gallery-grid { grid-template-columns: repeat(2, 1fr); }
      .hero { min-height: 80vh; }
      .countdown { gap: 0.8rem; flex-wrap: wrap; }
      .countdown-item { min-width: 60px; padding: 0.5rem 1rem; }
      .countdown-number { font-size: 1.6rem; }
      .section-title { font-size: 2rem; }
    }
    @media (max-width: 480px) {
      .gallery-grid { grid-template-columns: 1fr; }
      .container { padding: 0 1.2rem; }
      .hero-content h1 { font-size: 2.2rem; }
      .event-details { flex-direction: column; align-items: center; }
    }
    /* ===== RESEAUX SOCIAUX ===== */
.social-section { background: var(--bg-card); padding: 4rem 2rem; border-radius: 20px; border: 1px solid var(--border-gold); text-align: center; }
.social-grid { display: flex; gap: 2rem; justify-content: center; flex-wrap: wrap; margin-top: 2.5rem; }
.social-card {
  background: var(--bg-primary); padding: 2.5rem 2rem; border-radius: 16px;
  border: 2px solid var(--border-gold); text-decoration: none; min-width: 300px;
  transition: all 0.4s ease; display: flex; flex-direction: column; align-items: center; gap: 1rem;
}
.social-card:hover { transform: translateY(-10px); border-color: var(--gold); box-shadow: 0 15px 50px rgba(212,175,55,0.15); }
.s
