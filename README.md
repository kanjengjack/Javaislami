# Javaislami
Aplikasi sholat
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JAVAISLAMI — Aplikasi Islam Modern</title>
<link href="https://fonts.googleapis.com/css2?family=Scheherazade+New:wght@400;700&family=Poppins:wght@300;400;500;600;700&family=Amiri:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
<style>
  :root {
    --primary: #1a4a7a;
    --primary-light: #2563a8;
    --primary-dark: #0f2d4e;
    --accent: #3b82c4;
    --accent-glow: rgba(59,130,196,0.3);
    --gold: #c9a84c;
    --gold-light: #e8c97a;
    --gray-100: #f8f9fa;
    --gray-200: #e9ecef;
    --gray-300: #dee2e6;
    --gray-400: #adb5bd;
    --gray-500: #6c757d;
    --gray-600: #495057;
    --gray-800: #2d3748;
    --white: #ffffff;
    --shadow-blue: 0 8px 32px rgba(26,74,122,0.25);
    --shadow-card: 0 4px 20px rgba(0,0,0,0.08);
  }

  * { margin:0; padding:0; box-sizing:border-box; }

  body {
    font-family: 'Poppins', sans-serif;
    background: #f0f4f8;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ─── SPLASH / HERO ─── */
  .app-wrapper {
    max-width: 420px;
    margin: 0 auto;
    background: #fff;
    min-height: 100vh;
    position: relative;
    box-shadow: 0 0 60px rgba(0,0,0,0.15);
    overflow: hidden;
  }

  /* ─── HEADER ─── */
  .header {
    background: linear-gradient(145deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
    padding: 0;
    position: relative;
    overflow: hidden;
  }

  /* Geometric Islamic pattern overlay */
  .header::before {
    content: '';
    position: absolute;
    inset: 0;
    background-image:
      repeating-linear-gradient(45deg, rgba(255,255,255,0.03) 0px, rgba(255,255,255,0.03) 1px, transparent 1px, transparent 20px),
      repeating-linear-gradient(-45deg, rgba(255,255,255,0.03) 0px, rgba(255,255,255,0.03) 1px, transparent 1px, transparent 20px);
    pointer-events: none;
  }

  /* Decorative circles */
  .header::after {
    content: '';
    position: absolute;
    top: -60px; right: -60px;
    width: 200px; height: 200px;
    border-radius: 50%;
    border: 2px solid rgba(201,168,76,0.25);
    pointer-events: none;
  }

  .header-inner {
    padding: 20px 20px 0;
    position: relative;
    z-index: 2;
  }

  .top-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 24px;
  }

  .logo-area {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .logo-icon {
    width: 40px; height: 40px;
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    box-shadow: 0 4px 12px rgba(201,168,76,0.4);
    position: relative;
    overflow: hidden;
  }

  .logo-icon::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(135deg, transparent 30%, rgba(255,255,255,0.3) 50%, transparent 70%);
  }

  .logo-text {
    display: flex;
    flex-direction: column;
  }

  .logo-text .brand {
    font-family: 'Poppins', sans-serif;
    font-weight: 700;
    font-size: 16px;
    color: white;
    letter-spacing: 1px;
    line-height: 1;
  }

  .logo-text .brand span {
    color: var(--gold-light);
  }

  .logo-text .tagline {
    font-size: 9px;
    color: rgba(255,255,255,0.6);
    letter-spacing: 1.5px;
    text-transform: uppercase;
  }

  .header-actions {
    display: flex;
    gap: 10px;
  }

  .icon-btn {
    width: 36px; height: 36px;
    border-radius: 50%;
    background: rgba(255,255,255,0.12);
    border: 1px solid rgba(255,255,255,0.15);
    display: flex; align-items: center; justify-content: center;
    cursor: pointer;
    transition: all 0.2s;
    font-size: 16px;
    color: white;
    backdrop-filter: blur(4px);
    text-decoration: none;
  }

  .icon-btn:hover { background: rgba(255,255,255,0.2); transform: scale(1.05); }

  /* ─── HERO CARD ─── */
  .hero-card {
    margin: 0 16px 0;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 20px;
    padding: 20px;
    backdrop-filter: blur(8px);
    position: relative;
    overflow: hidden;
  }

  .hero-card::before {
    content: '';
    position: absolute;
    top: -30px; left: 50%;
    transform: translateX(-50%);
    width: 300px; height: 300px;
    background: radial-gradient(circle, rgba(201,168,76,0.1) 0%, transparent 70%);
    pointer-events: none;
  }

  .greeting-row {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
  }

  .greeting-text .assalamu {
    font-family: 'Scheherazade New', serif;
    font-size: 22px;
    color: var(--gold-light);
    display: block;
    line-height: 1.2;
    text-shadow: 0 0 20px rgba(201,168,76,0.4);
    animation: shimmer 3s ease-in-out infinite;
  }

  @keyframes shimmer {
    0%,100% { opacity:1; }
    50% { opacity: 0.85; text-shadow: 0 0 30px rgba(201,168,76,0.6); }
  }

  .greeting-text .sub {
    font-size: 12px;
    color: rgba(255,255,255,0.7);
    margin-top: 2px;
  }

  .greeting-text .user-name {
    font-size: 15px;
    font-weight: 600;
    color: white;
    margin-top: 4px;
  }

  /* Prayer time display */
  .prayer-hero {
    margin-top: 16px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(255,255,255,0.06);
    border-radius: 14px;
    padding: 14px 16px;
    border: 1px solid rgba(255,255,255,0.1);
  }

  .prayer-now {
    display: flex;
    flex-direction: column;
  }

  .prayer-label {
    font-size: 10px;
    color: rgba(255,255,255,0.5);
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .prayer-name {
    font-size: 20px;
    font-weight: 700;
    color: white;
    margin: 2px 0;
  }

  .prayer-time-big {
    font-size: 32px;
    font-weight: 300;
    color: var(--gold-light);
    font-family: 'Poppins', sans-serif;
    letter-spacing: -1px;
  }

  .prayer-countdown {
    text-align: right;
  }

  .countdown-label {
    font-size: 10px;
    color: rgba(255,255,255,0.5);
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .countdown-time {
    font-size: 18px;
    font-weight: 600;
    color: white;
    margin-top: 4px;
  }

  .next-prayer {
    font-size: 11px;
    color: rgba(255,255,255,0.6);
  }

  /* Moon/decoration */
  .moon-deco {
    width: 60px; height: 60px;
    position: relative;
    flex-shrink: 0;
  }

  .moon-deco svg {
    width: 100%; height: 100%;
    filter: drop-shadow(0 0 8px rgba(201,168,76,0.5));
    animation: float 4s ease-in-out infinite;
  }

  @keyframes float {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
  }

  /* Date/hijri */
  .date-row {
    display: flex;
    gap: 8px;
    margin-top: 12px;
  }

  .date-badge {
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 20px;
    padding: 4px 12px;
    font-size: 11px;
    color: rgba(255,255,255,0.8);
    display: flex;
    align-items: center;
    gap: 5px;
  }

  .date-badge .dot {
    width: 5px; height: 5px;
    background: var(--gold-light);
    border-radius: 50%;
  }

  /* ─── PRAYER SCHEDULE ROW ─── */
  .prayer-schedule-strip {
    background: var(--white);
    padding: 0 16px;
    margin-bottom: 0;
  }

  .prayer-times-row {
    display: flex;
    gap: 8px;
    padding: 16px 0 8px;
    overflow-x: auto;
    scrollbar-width: none;
    -ms-overflow-style: none;
  }

  .prayer-times-row::-webkit-scrollbar { display: none; }

  .prayer-pill {
    flex-shrink: 0;
    background: var(--gray-100);
    border-radius: 14px;
    padding: 10px 14px;
    text-align: center;
    min-width: 66px;
    border: 1.5px solid transparent;
    cursor: pointer;
    transition: all 0.25s;
    position: relative;
  }

  .prayer-pill.active {
    background: linear-gradient(145deg, var(--primary), var(--primary-light));
    border-color: var(--accent);
    box-shadow: 0 4px 16px rgba(26,74,122,0.35);
  }

  .prayer-pill.active::after {
    content: '';
    position: absolute;
    bottom: -6px; left: 50%;
    transform: translateX(-50%);
    width: 6px; height: 6px;
    background: var(--gold);
    border-radius: 50%;
  }

  .pill-name {
    font-size: 10px;
    font-weight: 600;
    color: var(--gray-500);
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .prayer-pill.active .pill-name { color: rgba(255,255,255,0.8); }

  .pill-time {
    font-size: 13px;
    font-weight: 700;
    color: var(--gray-800);
    margin-top: 4px;
  }

  .prayer-pill.active .pill-time { color: white; }

  /* ─── SECTION ─── */
  .section {
    padding: 20px 16px 0;
    background: white;
  }

  .section-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 14px;
  }

  .section-title {
    font-size: 15px;
    font-weight: 700;
    color: var(--primary-dark);
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-title::before {
    content: '';
    display: inline-block;
    width: 3px; height: 16px;
    background: linear-gradient(to bottom, var(--gold), var(--primary-light));
    border-radius: 2px;
  }

  .section-link {
    font-size: 11px;
    color: var(--primary-light);
    text-decoration: none;
    font-weight: 500;
    display: flex;
    align-items: center;
    gap: 3px;
  }

  /* ─── MAIN FEATURE GRID ─── */
  .feature-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    padding: 0 16px 20px;
    background: white;
  }

  .feature-card {
    border-radius: 18px;
    padding: 18px 16px;
    cursor: pointer;
    transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
    position: relative;
    overflow: hidden;
    border: 1px solid rgba(0,0,0,0.05);
    text-decoration: none;
  }

  .feature-card:hover {
    transform: translateY(-4px) scale(1.01);
    box-shadow: var(--shadow-blue);
  }

  .feature-card.blue-card {
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
    color: white;
  }

  .feature-card.gray-card {
    background: linear-gradient(135deg, #3d4f63 0%, #556072 100%);
    color: white;
  }

  .feature-card.light-card {
    background: linear-gradient(135deg, #e8f0f8 0%, #dce9f5 100%);
  }

  .feature-card.white-card {
    background: white;
    box-shadow: var(--shadow-card);
  }

  .feature-card.wide {
    grid-column: 1 / -1;
  }

  /* Card pattern overlay */
  .feature-card::before {
    content: '';
    position: absolute;
    top: -20px; right: -20px;
    width: 80px; height: 80px;
    border-radius: 50%;
    background: rgba(255,255,255,0.08);
    pointer-events: none;
  }

  .feature-card::after {
    content: '';
    position: absolute;
    bottom: -30px; right: 20px;
    width: 70px; height: 70px;
    border-radius: 50%;
    background: rgba(255,255,255,0.05);
    pointer-events: none;
  }

  .feature-icon {
    width: 44px; height: 44px;
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    margin-bottom: 12px;
    position: relative;
    z-index: 1;
  }

  .blue-card .feature-icon { background: rgba(255,255,255,0.15); }
  .gray-card .feature-icon { background: rgba(255,255,255,0.12); }
  .light-card .feature-icon { background: rgba(26,74,122,0.1); }
  .white-card .feature-icon { background: var(--gray-100); }

  .feature-name {
    font-size: 13px;
    font-weight: 700;
    margin-bottom: 4px;
    position: relative;
    z-index: 1;
  }

  .blue-card .feature-name, .gray-card .feature-name { color: white; }
  .light-card .feature-name { color: var(--primary-dark); }
  .white-card .feature-name { color: var(--gray-800); }

  .feature-desc {
    font-size: 10px;
    line-height: 1.5;
    position: relative;
    z-index: 1;
  }

  .blue-card .feature-desc, .gray-card .feature-desc { color: rgba(255,255,255,0.7); }
  .light-card .feature-desc { color: var(--gray-500); }
  .white-card .feature-desc { color: var(--gray-400); }

  .feature-badge {
    display: inline-block;
    background: var(--gold);
    color: var(--primary-dark);
    font-size: 9px;
    font-weight: 700;
    padding: 2px 8px;
    border-radius: 10px;
    margin-top: 8px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    position: relative;
    z-index: 1;
  }

  /* ─── QURAN PROGRESS ─── */
  .quran-card {
    background: linear-gradient(135deg, var(--primary-dark) 0%, #1e3a5f 100%);
    border-radius: 18px;
    padding: 18px;
    margin: 0 16px 20px;
    position: relative;
    overflow: hidden;
    cursor: pointer;
    transition: transform 0.3s;
  }

  .quran-card:hover { transform: scale(1.01); }

  .quran-card::before {
    content: '﴾';
    position: absolute;
    top: -10px; right: 16px;
    font-family: 'Scheherazade New', serif;
    font-size: 80px;
    color: rgba(255,255,255,0.05);
    line-height: 1;
  }

  .quran-top {
    display: flex;
    align-items: flex-start;
    gap: 14px;
    margin-bottom: 14px;
  }

  .quran-icon-wrap {
    width: 48px; height: 48px;
    border-radius: 12px;
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    display: flex; align-items: center; justify-content: center;
    font-size: 24px;
    box-shadow: 0 4px 14px rgba(201,168,76,0.4);
    flex-shrink: 0;
  }

  .quran-info h3 {
    font-size: 14px;
    font-weight: 700;
    color: white;
  }

  .quran-info p {
    font-size: 11px;
    color: rgba(255,255,255,0.6);
    margin-top: 2px;
  }

  .quran-arabic {
    font-family: 'Scheherazade New', serif;
    font-size: 16px;
    color: var(--gold-light);
    margin-top: 6px;
    direction: rtl;
    text-align: right;
  }

  .progress-bar-wrap {
    background: rgba(255,255,255,0.1);
    border-radius: 10px;
    height: 6px;
    margin-bottom: 8px;
    overflow: hidden;
  }

  .progress-bar-fill {
    height: 100%;
    background: linear-gradient(to right, var(--gold), var(--gold-light));
    border-radius: 10px;
    width: 35%;
    position: relative;
    overflow: hidden;
  }

  .progress-bar-fill::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
    animation: slide 2s infinite;
  }

  @keyframes slide { 0% { transform: translateX(-100%); } 100% { transform: translateX(300%); } }

  .progress-text {
    display: flex;
    justify-content: space-between;
    font-size: 10px;
    color: rgba(255,255,255,0.5);
  }

  /* ─── QIBLA COMPASS ─── */
  .qibla-card {
    background: white;
    border-radius: 18px;
    padding: 18px;
    margin: 0 16px 20px;
    box-shadow: var(--shadow-card);
    display: flex;
    align-items: center;
    gap: 16px;
    cursor: pointer;
    transition: all 0.3s;
    border: 1px solid var(--gray-200);
  }

  .qibla-card:hover {
    border-color: var(--primary-light);
    box-shadow: 0 8px 30px rgba(26,74,122,0.15);
    transform: translateY(-2px);
  }

  .compass-wrap {
    flex-shrink: 0;
    position: relative;
    width: 80px; height: 80px;
  }

  .compass-ring {
    width: 80px; height: 80px;
    border-radius: 50%;
    border: 3px solid var(--gray-200);
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    background: linear-gradient(135deg, var(--gray-100), white);
    box-shadow: inset 0 2px 8px rgba(0,0,0,0.08), 0 4px 16px rgba(0,0,0,0.08);
  }

  .compass-ring::before {
    content: 'N';
    position: absolute;
    top: 2px;
    font-size: 9px;
    font-weight: 700;
    color: var(--primary);
  }

  .compass-needle {
    width: 4px; height: 32px;
    position: relative;
    transform: rotate(-42deg);
    transform-origin: center bottom;
  }

  .needle-north {
    width: 4px; height: 16px;
    background: linear-gradient(to top, var(--primary), var(--primary-light));
    border-radius: 2px 2px 0 0;
  }

  .needle-south {
    width: 4px; height: 16px;
    background: var(--gray-300);
    border-radius: 0 0 2px 2px;
  }

  .compass-center {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 8px; height: 8px;
    background: var(--gold);
    border-radius: 50%;
    box-shadow: 0 0 8px rgba(201,168,76,0.5);
    z-index: 1;
  }

  .qibla-info h3 {
    font-size: 15px;
    font-weight: 700;
    color: var(--primary-dark);
    margin-bottom: 4px;
  }

  .qibla-info p {
    font-size: 12px;
    color: var(--gray-500);
    line-height: 1.5;
  }

  .qibla-degree {
    margin-top: 8px;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    background: linear-gradient(135deg, var(--primary), var(--primary-light));
    color: white;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 600;
  }

  /* ─── COMMUNITY & BISNIS ─── */
  .community-section {
    background: var(--gray-100);
    padding: 20px 16px;
  }

  .community-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-top: 14px;
  }

  .community-card {
    background: white;
    border-radius: 16px;
    padding: 16px;
    cursor: pointer;
    transition: all 0.3s;
    border: 1px solid var(--gray-200);
    text-decoration: none;
  }

  .community-card:hover {
    border-color: var(--primary-light);
    box-shadow: 0 4px 20px rgba(26,74,122,0.12);
    transform: translateY(-2px);
  }

  .community-card .c-icon {
    width: 40px; height: 40px;
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
    margin-bottom: 10px;
  }

  .c-blue { background: rgba(26,74,122,0.1); }
  .c-gold { background: rgba(201,168,76,0.12); }
  .c-gray { background: rgba(61,79,99,0.1); }
  .c-green { background: rgba(39,174,96,0.1); }

  .community-card h4 {
    font-size: 12px;
    font-weight: 700;
    color: var(--gray-800);
    margin-bottom: 4px;
  }

  .community-card p {
    font-size: 10px;
    color: var(--gray-400);
    line-height: 1.4;
  }

  .member-count {
    margin-top: 8px;
    font-size: 10px;
    font-weight: 600;
    color: var(--primary-light);
  }

  /* ─── HUKUM ISLAM ─── */
  .hukum-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin-top: 14px;
  }

  .hukum-item {
    background: white;
    border-radius: 14px;
    padding: 14px 16px;
    display: flex;
    align-items: flex-start;
    gap: 14px;
    cursor: pointer;
    transition: all 0.25s;
    border: 1px solid var(--gray-200);
  }

  .hukum-item:hover {
    border-color: var(--primary-light);
    box-shadow: 0 4px 16px rgba(26,74,122,0.1);
    transform: translateX(4px);
  }

  .hukum-cat {
    flex-shrink: 0;
    width: 40px; height: 40px;
    border-radius: 10px;
    background: linear-gradient(135deg, var(--primary), var(--primary-light));
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
  }

  .hukum-content h4 {
    font-size: 13px;
    font-weight: 600;
    color: var(--gray-800);
    margin-bottom: 3px;
  }

  .hukum-content p {
    font-size: 11px;
    color: var(--gray-400);
    line-height: 1.4;
  }

  .hukum-tag {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 10px;
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 0.3px;
    margin-top: 6px;
  }

  .tag-wajib { background: rgba(26,74,122,0.1); color: var(--primary-light); }
  .tag-sunnah { background: rgba(201,168,76,0.15); color: #9a7a2a; }
  .tag-haram { background: rgba(220,38,38,0.1); color: #dc2626; }
  .tag-mubah { background: rgba(39,174,96,0.1); color: #1a8a4a; }

  /* ─── CALLIGRAPHY DIVIDER ─── */
  .calligraphy-divider {
    text-align: center;
    padding: 20px 16px;
    background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 100%);
    position: relative;
    overflow: hidden;
  }

  .calligraphy-divider::before {
    content: '';
    position: absolute;
    inset: 0;
    background:
      radial-gradient(ellipse at 20% 50%, rgba(201,168,76,0.12) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 50%, rgba(59,130,196,0.15) 0%, transparent 60%);
  }

  .calligraphy-text {
    font-family: 'Scheherazade New', serif;
    font-size: 28px;
    color: var(--gold-light);
    direction: rtl;
    text-shadow: 0 0 30px rgba(201,168,76,0.4);
    position: relative;
    z-index: 1;
    animation: glow 3s ease-in-out infinite;
  }

  @keyframes glow {
    0%,100% { text-shadow: 0 0 20px rgba(201,168,76,0.4); }
    50% { text-shadow: 0 0 40px rgba(201,168,76,0.7), 0 0 60px rgba(201,168,76,0.3); }
  }

  .calligraphy-sub {
    font-size: 11px;
    color: rgba(255,255,255,0.5);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 8px;
    position: relative;
    z-index: 1;
  }

  /* Ornament lines */
  .ornament {
    display: flex;
    align-items: center;
    gap: 12px;
    justify-content: center;
    margin-bottom: 10px;
    position: relative;
    z-index: 1;
  }

  .ornament-line {
    flex: 1;
    max-width: 60px;
    height: 1px;
    background: linear-gradient(to right, transparent, var(--gold));
  }

  .ornament-line.right {
    background: linear-gradient(to left, transparent, var(--gold));
  }

  .ornament-diamond {
    width: 6px; height: 6px;
    background: var(--gold);
    transform: rotate(45deg);
  }

  /* ─── BOTTOM NAV ─── */
  .bottom-nav {
    position: sticky;
    bottom: 0;
    background: white;
    border-top: 1px solid var(--gray-200);
    display: flex;
    padding: 8px 0 16px;
    z-index: 100;
    box-shadow: 0 -8px 32px rgba(0,0,0,0.06);
  }

  .nav-item {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
    cursor: pointer;
    padding: 8px 4px;
    transition: all 0.25s;
    text-decoration: none;
  }

  .nav-icon {
    width: 36px; height: 36px;
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px;
    transition: all 0.3s;
  }

  .nav-item.active .nav-icon {
    background: linear-gradient(135deg, var(--primary), var(--primary-light));
    box-shadow: 0 4px 14px rgba(26,74,122,0.35);
  }

  .nav-label {
    font-size: 9px;
    font-weight: 600;
    color: var(--gray-400);
    letter-spacing: 0.3px;
    text-transform: uppercase;
  }

  .nav-item.active .nav-label { color: var(--primary-light); }
  .nav-item:not(.active):hover .nav-icon { background: var(--gray-100); }

  /* ─── FLOATING ACTION ─── */
  .fab {
    position: fixed;
    bottom: 80px;
    right: calc(50% - 210px + 16px);
    width: 52px; height: 52px;
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 22px;
    box-shadow: 0 6px 24px rgba(201,168,76,0.5);
    cursor: pointer;
    transition: all 0.3s;
    z-index: 99;
    animation: pulse-fab 3s ease-in-out infinite;
  }

  @keyframes pulse-fab {
    0%,100% { box-shadow: 0 6px 24px rgba(201,168,76,0.5); }
    50% { box-shadow: 0 6px 32px rgba(201,168,76,0.7), 0 0 0 8px rgba(201,168,76,0.1); }
  }

  .fab:hover { transform: scale(1.1) rotate(15deg); }

  /* ─── SPACER ─── */
  .spacer { height: 20px; background: var(--gray-100); }

  /* ─── SCROLLABLE CONTENT ─── */
  .scrollable-content {
    height: calc(100vh - 80px);
    overflow-y: auto;
    scroll-behavior: smooth;
    scrollbar-width: none;
    -ms-overflow-style: none;
  }

  .scrollable-content::-webkit-scrollbar { display: none; }

  /* ─── VERSE HIGHLIGHT ─── */
  .verse-card {
    background: linear-gradient(135deg, #f0f6ff 0%, #e8f0f8 100%);
    border-radius: 18px;
    padding: 20px;
    margin: 0 16px 20px;
    border: 1px solid rgba(26,74,122,0.1);
    position: relative;
    overflow: hidden;
    cursor: pointer;
  }

  .verse-card::before {
    content: '❝';
    position: absolute;
    top: 10px; left: 16px;
    font-size: 40px;
    color: rgba(26,74,122,0.08);
    font-family: serif;
    line-height: 1;
  }

  .verse-arabic {
    font-family: 'Scheherazade New', serif;
    font-size: 22px;
    color: var(--primary-dark);
    direction: rtl;
    text-align: right;
    line-height: 1.8;
    margin-bottom: 12px;
    text-shadow: 0 1px 3px rgba(26,74,122,0.1);
  }

  .verse-translation {
    font-size: 12px;
    color: var(--gray-600);
    line-height: 1.7;
    font-style: italic;
    border-top: 1px solid rgba(26,74,122,0.1);
    padding-top: 10px;
  }

  .verse-source {
    font-size: 11px;
    font-weight: 600;
    color: var(--primary-light);
    margin-top: 8px;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  .verse-source::before {
    content: '';
    display: inline-block;
    width: 16px; height: 1.5px;
    background: var(--primary-light);
  }

  /* ─── STATS ─── */
  .stats-row {
    display: flex;
    gap: 10px;
    padding: 0 16px 20px;
    background: white;
  }

  .stat-card {
    flex: 1;
    background: var(--gray-100);
    border-radius: 14px;
    padding: 14px;
    text-align: center;
    border: 1px solid var(--gray-200);
  }

  .stat-num {
    font-size: 22px;
    font-weight: 700;
    color: var(--primary-dark);
    line-height: 1;
  }

  .stat-label {
    font-size: 10px;
    color: var(--gray-400);
    margin-top: 4px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  /* ─── HEADER BOTTOM SPACING ─── */
  .header-bottom-curve {
    height: 24px;
    background: linear-gradient(145deg, var(--primary-dark) 0%, var(--primary) 50%, var(--primary-light) 100%);
    border-radius: 0 0 28px 28px;
    margin-bottom: 20px;
  }

</style>
</head>
<body>

<div class="app-wrapper">

  <!-- HEADER -->
  <div class="header">
    <div class="header-inner">

      <!-- Top Bar -->
      <div class="top-bar">
        <div class="logo-area">
          <div class="logo-icon">☪</div>
          <div class="logo-text">
            <span class="brand">JAVA<span>ISLAMI</span></span>
            <span class="tagline">Panduan Islam Lengkap</span>
          </div>
        </div>
        <div class="header-actions">
          <a class="icon-btn" title="Notifikasi">🔔</a>
          <a class="icon-btn" title="Profil">👤</a>
        </div>
      </div>

      <!-- Hero Card -->
      <div class="hero-card">
        <div class="greeting-row">
          <div class="greeting-text">
            <span class="assalamu">السَّلَامُ عَلَيْكُمْ</span>
            <span class="sub">Selamat datang kembali,</span>
            <span class="user-name">Ustadz Ahmad Fauzi</span>
          </div>
          <div class="moon-deco">
            <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
              <circle cx="45" cy="50" r="38" fill="#c9a84c" opacity="0.9"/>
              <circle cx="60" cy="38" r="28" fill="#0f2d4e"/>
              <!-- Stars -->
              <polygon points="85,20 87,27 94,27 88,31 90,38 85,34 80,38 82,31 76,27 83,27" fill="#e8c97a" opacity="0.9"/>
              <circle cx="78" cy="15" r="2" fill="#e8c97a" opacity="0.7"/>
              <circle cx="70" cy="55" r="1.5" fill="#e8c97a" opacity="0.5"/>
            </svg>
          </div>
        </div>

        <!-- Current Prayer -->
        <div class="prayer-hero">
          <div class="prayer-now">
            <span class="prayer-label">Waktu Sholat Kini</span>
            <span class="prayer-name">Ashar</span>
            <span class="prayer-time-big">15:32</span>
          </div>
          <div class="prayer-countdown">
            <span class="countdown-label">Menuju Sholat</span>
            <div class="countdown-time">01:28:44</div>
            <div class="next-prayer">Maghrib 17:01</div>
          </div>
        </div>

        <!-- Date Row -->
        <div class="date-row">
          <div class="date-badge">
            <div class="dot"></div>
            Senin, 9 Maret 2026
          </div>
          <div class="date-badge">
            <div class="dot"></div>
            9 Ramadhan 1447 H
          </div>
        </div>

      </div>
    </div>
    <div style="height:20px; background: linear-gradient(145deg, #0f2d4e 0%, #1a4a7a 50%, #2563a8 100%); border-radius: 0 0 28px 28px; margin-top: -1px;"></div>
  </div>

  <!-- SCROLLABLE CONTENT -->
  <div class="scrollable-content" id="mainScroll">

    <!-- Prayer Schedule Strip -->
    <div class="prayer-schedule-strip">
      <div style="padding-top:16px; padding-bottom:4px;">
        <div class="section-header" style="margin-bottom:8px;">
          <span class="section-title">Jadwal Sholat Hari Ini</span>
          <a href="#" class="section-link">Lengkap ›</a>
        </div>
      </div>
      <div class="prayer-times-row">
        <div class="prayer-pill"><span class="pill-name">Subuh</span><span class="pill-time">04:38</span></div>
        <div class="prayer-pill"><span class="pill-name">Syuruq</span><span class="pill-time">05:58</span></div>
        <div class="prayer-pill"><span class="pill-name">Dzuhur</span><span class="pill-time">12:05</span></div>
        <div class="prayer-pill active"><span class="pill-name">Ashar</span><span class="pill-time">15:32</span></div>
        <div class="prayer-pill"><span class="pill-name">Maghrib</span><span class="pill-time">17:01</span></div>
        <div class="prayer-pill"><span class="pill-name">Isya</span><span class="pill-time">18:15</span></div>
      </div>
    </div>

    <!-- Stats Row -->
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num">114</div>
        <div class="stat-label">Surah Al-Qur'an</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">12K+</div>
        <div class="stat-label">Anggota Aktif</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">500+</div>
        <div class="stat-label">Kajian Hukum</div>
      </div>
    </div>

    <!-- CALLIGRAPHY DIVIDER 1 -->
    <div class="calligraphy-divider">
      <div class="ornament">
        <div class="ornament-line"></div>
        <div class="ornament-diamond"></div>
        <div class="ornament-diamond" style="opacity:0.5; width:4px;height:4px;"></div>
        <div class="ornament-diamond"></div>
        <div class="ornament-line right"></div>
      </div>
      <div class="calligraphy-text">بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيمِ</div>
      <div class="calligraphy-sub">Fitur Utama Aplikasi</div>
    </div>

    <!-- MAIN FEATURES -->
    <div class="section">
      <div class="section-header">
        <span class="section-title">Menu Utama</span>
      </div>
    </div>
    <div class="feature-grid">

      <!-- Al-Quran -->
      <div class="feature-card blue-card">
        <div class="feature-icon">📖</div>
        <div class="feature-name">Al-Qur'an</div>
        <div class="feature-desc">114 Surah lengkap dengan terjemahan & tajwid</div>
        <div class="feature-badge">✦ Terlengkap</div>
      </div>

      <!-- Jadwal Sholat -->
      <div class="feature-card gray-card">
        <div class="feature-icon">🕌</div>
        <div class="feature-name">Jadwal Sholat</div>
        <div class="feature-desc">Akurat berdasar GPS lokasi Anda saat ini</div>
        <div class="feature-badge">⚡ Realtime</div>
      </div>

      <!-- Arah Kiblat -->
      <div class="feature-card light-card">
        <div class="feature-icon">🧭</div>
        <div class="feature-name">Arah Kiblat</div>
        <div class="feature-desc">Kompas presisi & AR Kiblat Finder</div>
      </div>

      <!-- Hukum Islam -->
      <div class="feature-card white-card">
        <div class="feature-icon">⚖️</div>
        <div class="feature-name">Hukum Islam</div>
        <div class="feature-desc">Panduan fiqih 4 Mazhab terlengkap</div>
      </div>

      <!-- Komunitas Bisnis - Wide -->
      <div class="feature-card blue-card wide" style="background: linear-gradient(135deg, #1a4a7a 0%, #2563a8 60%, #3d79be 100%);">
        <div style="display:flex; align-items:center; gap:16px;">
          <div class="feature-icon" style="width:56px;height:56px;font-size:28px;flex-shrink:0;">🤝</div>
          <div>
            <div class="feature-name" style="font-size:15px; margin-bottom:6px;">Komunitas Bisnis Islam</div>
            <div class="feature-desc" style="font-size:11px;">Platform networking muslimpreneur, halal marketplace, & forum bisnis syariah terpercaya</div>
            <div class="feature-badge" style="margin-top:10px;">🌟 12.400 Anggota Aktif</div>
          </div>
        </div>
      </div>

    </div>

    <!-- ARAH KIBLAT CARD -->
    <div class="section">
      <div class="section-header">
        <span class="section-title">Arah Kiblat</span>
        <a href="#" class="section-link">Buka Kompas ›</a>
      </div>
    </div>
    <div class="qibla-card">
      <div class="compass-wrap">
        <div class="compass-ring">
          <div class="compass-needle">
            <div class="needle-north"></div>
            <div class="needle-south"></div>
          </div>
          <div class="compass-center"></div>
        </div>
      </div>
      <div class="qibla-info">
        <h3>Arah Kiblat Terdeteksi</h3>
        <p>Lokasi: Semarang, Jawa Tengah<br>Menghadap Ka'bah Makkah Al-Mukarramah</p>
        <div class="qibla-degree">
          <span>⬆</span>
          <span>292.4° Barat Laut</span>
        </div>
      </div>
    </div>

    <!-- AL-QURAN PROGRESS -->
    <div class="section">
      <div class="section-header">
        <span class="section-title">Lanjutkan Membaca</span>
        <a href="#" class="section-link">Semua Surah ›</a>
      </div>
    </div>
    <div class="quran-card">
      <div class="quran-top">
        <div class="quran-icon-wrap">📖</div>
        <div class="quran-info">
          <h3>Surah Al-Baqarah</h3>
          <p>Ayat 135 dari 286 · Juz 1-2</p>
          <div class="quran-arabic">وَلَقَدْ يَسَّرْنَا ٱلْقُرْءَانَ لِلذِّكْرِ</div>
        </div>
      </div>
      <div class="progress-bar-wrap">
        <div class="progress-bar-fill"></div>
      </div>
      <div class="progress-text">
        <span>Ayat 135 / 286</span>
        <span>47% Selesai</span>
      </div>
    </div>

    <!-- AYAT HARI INI -->
    <div class="section">
      <div class="section-header">
        <span class="section-title">Ayat Pilihan Hari Ini</span>
        <a href="#" class="section-link">Bagikan ›</a>
      </div>
    </div>
    <div class="verse-card">
      <div class="verse-arabic">
        وَمَن يَتَوَكَّلْ عَلَى اللَّهِ فَهُوَ حَسْبُهُ ۚ إِنَّ اللَّهَ بَالِغُ أَمْرِهِ
      </div>
      <div class="verse-translation">
        "Dan barangsiapa bertawakal kepada Allah, niscaya Allah akan mencukupkan (keperluan)-nya. Sesungguhnya Allah melaksanakan urusan-Nya."
      </div>
      <div class="verse-source">QS. At-Talaq: 3</div>
    </div>

    <!-- KOMUNITAS BISNIS -->
    <div class="community-section">
      <div class="section-header" style="margin-bottom:0;">
        <span class="section-title">Komunitas Bisnis Islam</span>
        <a href="#" class="section-link">Gabung ›</a>
      </div>
      <div class="community-grid">
        <div class="community-card">
          <div class="c-icon c-blue">💼</div>
          <h4>Forum Bisnis Syariah</h4>
          <p>Diskusi usaha halal & investasi</p>
          <div class="member-count">👥 4.200 Anggota</div>
        </div>
        <div class="community-card">
          <div class="c-icon c-gold">🛒</div>
          <h4>Halal Marketplace</h4>
          <p>Jual beli produk halal bersertifikat</p>
          <div class="member-count">🏪 800+ Toko</div>
        </div>
        <div class="community-card">
          <div class="c-icon c-gray">📊</div>
          <h4>Investasi Syariah</h4>
          <p>Reksa dana & saham halal</p>
          <div class="member-count">📈 2.100 Investor</div>
        </div>
        <div class="community-card">
          <div class="c-icon c-green">🎓</div>
          <h4>Kelas Wirausaha</h4>
          <p>Workshop & mentoring bisnis</p>
          <div class="member-count">🎯 350 Kelas</div>
        </div>
      </div>
    </div>

    <!-- HUKUM ISLAM -->
    <div class="section">
      <div class="section-header">
        <span class="section-title">Hukum Islam</span>
        <a href="#" class="section-link">Selengkapnya ›</a>
      </div>
      <div class="hukum-list">

        <div class="hukum-item">
          <div class="hukum-cat">🕌</div>
          <div class="hukum-content">
            <h4>Fiqih Ibadah (Thaharah & Shalat)</h4>
            <p>Panduan lengkap bersuci, syarat & rukun shalat 4 mazhab</p>
            <span class="hukum-tag tag-wajib">Wajib</span>
          </div>
        </div>

        <div class="hukum-item">
          <div class="hukum-cat">🤝</div>
          <div class="hukum-content">
            <h4>Muamalah & Ekonomi Islam</h4>
            <p>Hukum jual beli, riba, akad, dan transaksi syariah</p>
            <span class="hukum-tag tag-mubah">Mubah</span>
          </div>
        </div>

        <div class="hukum-item">
          <div class="hukum-cat">💍</div>
          <div class="hukum-content">
            <h4>Pernikahan & Keluarga</h4>
            <p>Hukum nikah, talak, warisan, dan hak anak</p>
            <span class="hukum-tag tag-sunnah">Sunnah</span>
          </div>
        </div>

        <div class="hukum-item">
          <div class="hukum-cat">🍽️</div>
          <div class="hukum-content">
            <h4>Halal & Haram Makanan</h4>
            <p>Panduan makanan halal, syubhat, dan cara penyembelihan</p>
            <span class="hukum-tag tag-haram">Haram</span>
          </div>
        </div>

      </div>
    </div>

    <!-- CALLIGRAPHY FOOTER -->
    <div class="calligraphy-divider" style="margin-top:20px; padding:24px 16px;">
      <div class="ornament">
        <div class="ornament-line"></div>
        <div class="ornament-diamond"></div>
        <div class="ornament-line right"></div>
      </div>
      <div class="calligraphy-text" style="font-size:22px;">سُبْحَانَ اللَّهِ وَبِحَمْدِهِ</div>
      <div class="calligraphy-sub" style="margin-top:6px;">JAVAISLAMI — Islam Modern & Terpercaya</div>
    </div>

    <div style="height:80px;"></div>

  </div><!-- end scrollable -->

  <!-- BOTTOM NAV -->
  <div class="bottom-nav">
    <div class="nav-item active">
      <div class="nav-icon">🏠</div>
      <span class="nav-label">Beranda</span>
    </div>
    <div class="nav-item">
      <div class="nav-icon">📖</div>
      <span class="nav-label">Qur'an</span>
    </div>
    <div class="nav-item">
      <div class="nav-icon">🧭</div>
      <span class="nav-label">Kiblat</span>
    </div>
    <div class="nav-item">
      <div class="nav-icon">🤝</div>
      <span class="nav-label">Komunitas</span>
    </div>
    <div class="nav-item">
      <div class="nav-icon">⚖️</div>
      <span class="nav-label">Hukum</span>
    </div>
  </div>

</div><!-- end app-wrapper -->

<!-- FAB -->
<div class="fab" title="Tanya Ustadz AI">🤖</div>

<script>
  // Countdown Timer
  function updateCountdown() {
    const el = document.querySelector('.countdown-time');
    if (!el) return;
    const parts = el.textContent.split(':').map(Number);
    let [h, m, s] = parts;
    if (s > 0) s--;
    else if (m > 0) { m--; s = 59; }
    else if (h > 0) { h--; m = 59; s = 59; }
    el.textContent = `${String(h).padStart(2,'0')}:${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}`;
  }
  setInterval(updateCountdown, 1000);

  // Nav switching
  document.querySelectorAll('.nav-item').forEach(item => {
    item.addEventListener('click', () => {
      document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
      item.classList.add('active');
    });
  });

  // Compass animation
  let angle = -42;
  function animateCompass() {
    const needle = document.querySelector('.compass-needle');
    if (needle) {
      angle += (Math.sin(Date.now() / 2000) * 0.3);
      needle.style.transform = `rotate(${angle}deg)`;
    }
    requestAnimationFrame(animateCompass);
  }
  animateCompass();

  // Scroll entrance animations
  const cards = document.querySelectorAll('.feature-card, .community-card, .hukum-item, .qibla-card, .quran-card, .verse-card');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = e.target.style.transform || 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  cards.forEach(card => {
    card.style.opacity = '0';
    card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
    card.style.transform = 'translateY(20px)';
    observer.observe(card);
  });
</script>

</body>
</html>
