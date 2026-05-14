<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Wild Root Home Services</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Lato:wght@300;400;700&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bark:    #2b1d0e;
      --moss:    #3a5c2f;
      --fern:    #587d4a;
      --sage:    #8aab7a;
      --cream:   #f5f0e8;
      --parchment: #ede5d4;
      --soil:    #6b4c2a;
      --ivory:   #faf7f1;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Lato', sans-serif;
      background: var(--ivory);
      color: var(--bark);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 1.1rem 2.5rem;
      background: rgba(43, 29, 14, 0.92);
      backdrop-filter: blur(8px);
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.35rem;
      color: var(--cream);
      letter-spacing: 0.03em;
    }
    .nav-logo span { color: var(--sage); }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      color: var(--cream);
      text-decoration: none;
      font-size: 0.85rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      opacity: 0.8;
      transition: opacity 0.2s;
    }
    .nav-links a:hover { opacity: 1; }
    .nav-cta {
      background: var(--fern);
      color: #fff !important;
      padding: 0.55rem 1.3rem;
      border-radius: 100px;
      opacity: 1 !important;
      transition: background 0.2s !important;
    }
    .nav-cta:hover { background: var(--moss) !important; }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding: 8rem 2.5rem 5rem;
      position: relative;
      background: var(--bark);
      overflow: hidden;
    }
    /* organic texture overlay */
    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background:
        radial-gradient(ellipse 60% 60% at 80% 30%, rgba(88,125,74,0.35) 0%, transparent 70%),
        radial-gradient(ellipse 50% 80% at 10% 80%, rgba(58,92,47,0.4) 0%, transparent 65%);
      pointer-events: none;
    }
    /* subtle grain */
    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='0.05'/%3E%3C/svg%3E");
      opacity: 0.5;
      pointer-events: none;
    }
    .hero-inner {
      max-width: 780px;
      position: relative;
      z-index: 2;
    }
    .hero-eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      font-size: 0.78rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
      color: var(--sage);
      margin-bottom: 1.6rem;
    }
    .hero-eyebrow::before {
      content: '';
      display: block;
      width: 36px; height: 1px;
      background: var(--sage);
    }
    h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 7vw, 5.8rem);
      font-weight: 900;
      line-height: 1.05;
      color: var(--cream);
      margin-bottom: 1.6rem;
    }
    h1 em {
      font-style: italic;
      color: var(--sage);
    }
    .hero-sub {
      font-size: 1.1rem;
      line-height: 1.85;
      color: rgba(245,240,232,0.75);
      max-width: 560px;
      margin-bottom: 2.8rem;
      font-weight: 300;
    }
    .btn-group { display: flex; flex-wrap: wrap; gap: 1rem; }
    .btn-primary {
      background: var(--fern);
      color: #fff;
      padding: 1rem 2.2rem;
      border-radius: 6px;
      font-size: 0.95rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      text-decoration: none;
      transition: background 0.25s, transform 0.2s;
    }
    .btn-primary:hover { background: var(--moss); transform: translateY(-2px); }
    .btn-outline {
      border: 1.5px solid rgba(138,171,122,0.6);
      color: var(--sage);
      padding: 1rem 2.2rem;
      border-radius: 6px;
      font-size: 0.95rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      text-decoration: none;
      transition: border-color 0.25s, color 0.25s, transform 0.2s;
    }
    .btn-outline:hover { border-color: var(--sage); color: var(--cream); transform: translateY(-2px); }

    /* decorative leaf line */
    .leaf-divider {
      text-align: center;
      color: var(--sage);
      font-size: 1.4rem;
      letter-spacing: 0.5rem;
      padding: 1.5rem 0;
      opacity: 0.5;
    }

    /* ── ABOUT ── */
    .about {
      background: var(--parchment);
      padding: 6rem 2.5rem;
    }
    .about-inner {
      max-width: 1100px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
    }
    .section-label {
      font-size: 0.75rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--fern);
      font-weight: 700;
      margin-bottom: 1rem;
    }
    h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3.2rem);
      line-height: 1.15;
      color: var(--bark);
      margin-bottom: 1.4rem;
    }
    .about-body {
      font-size: 1.05rem;
      line-height: 1.9;
      color: #5a4535;
      font-weight: 300;
      margin-bottom: 2rem;
    }
    .pillars {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
    }
    .pillar {
      background: var(--cream);
      border: 1px solid rgba(88,125,74,0.2);
      border-radius: 10px;
      padding: 1.4rem;
    }
    .pillar-icon { font-size: 1.6rem; margin-bottom: 0.6rem; }
    .pillar h4 {
      font-family: 'Playfair Display', serif;
      font-size: 1.05rem;
      color: var(--moss);
      margin-bottom: 0.4rem;
    }
    .pillar p { font-size: 0.88rem; color: #6b5545; line-height: 1.6; }

    /* services panel */
    .services-panel {
      background: var(--bark);
      border-radius: 16px;
      padding: 3rem 2.5rem;
    }
    .services-panel h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.8rem;
      color: var(--cream);
      margin-bottom: 2rem;
    }
    .service-item {
      border-bottom: 1px solid rgba(245,240,232,0.12);
      padding: 1.5rem 0;
    }
    .service-item:last-child { border-bottom: none; padding-bottom: 0; }
    .service-item h4 {
      font-family: 'Playfair Display', serif;
      font-size: 1.25rem;
      color: var(--sage);
      margin-bottom: 0.4rem;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }
    .service-item p {
      font-size: 0.92rem;
      color: rgba(245,240,232,0.65);
      line-height: 1.7;
      font-weight: 300;
    }

    /* ── WHY US ── */
    .why {
      background: var(--ivory);
      padding: 6rem 2.5rem;
      text-align: center;
    }
    .why-inner { max-width: 900px; margin: 0 auto; }
    .why h2 { margin-bottom: 0.8rem; }
    .why-sub {
      font-size: 1.05rem;
      color: #7a6555;
      max-width: 540px;
      margin: 0 auto 3.5rem;
      line-height: 1.8;
      font-weight: 300;
    }
    .why-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5rem;
    }
    .why-card {
      background: var(--parchment);
      border: 1px solid rgba(88,125,74,0.15);
      border-radius: 12px;
      padding: 2.2rem 1.8rem;
      text-align: left;
    }
    .why-card-icon { font-size: 2rem; margin-bottom: 1rem; }
    .why-card h4 {
      font-family: 'Playfair Display', serif;
      font-size: 1.15rem;
      color: var(--moss);
      margin-bottom: 0.6rem;
    }
    .why-card p { font-size: 0.9rem; color: #6b5545; line-height: 1.7; }

    /* ── CTA BANNER ── */
    .cta {
      background: var(--moss);
      padding: 6rem 2.5rem;
      position: relative;
      overflow: hidden;
    }
    .cta::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(ellipse 70% 80% at 90% 50%, rgba(88,125,74,0.5) 0%, transparent 65%);
      pointer-events: none;
    }
    .cta-inner {
      max-width: 700px;
      margin: 0 auto;
      text-align: center;
      position: relative;
      z-index: 2;
    }
    .cta h2 {
      color: var(--cream);
      margin-bottom: 1rem;
    }
    .cta p {
      color: rgba(245,240,232,0.8);
      font-size: 1.05rem;
      line-height: 1.8;
      font-weight: 300;
      margin-bottom: 2.5rem;
    }
    .contact-buttons {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      align-items: center;
    }
    .contact-link {
      display: flex;
      align-items: center;
      gap: 0.8rem;
      background: rgba(245,240,232,0.12);
      border: 1.5px solid rgba(245,240,232,0.3);
      color: var(--cream);
      text-decoration: none;
      padding: 1rem 2.5rem;
      border-radius: 8px;
      font-size: 1.15rem;
      font-weight: 700;
      letter-spacing: 0.03em;
      transition: background 0.25s, transform 0.2s;
      width: 100%;
      max-width: 380px;
      justify-content: center;
    }
    .contact-link:hover { background: rgba(245,240,232,0.22); transform: translateY(-2px); }
    .contact-link.phone { background: var(--bark); border-color: var(--bark); }
    .contact-link.phone:hover { background: #3a2710; }

    /* ── FOOTER ── */
    footer {
      background: var(--bark);
      color: rgba(245,240,232,0.5);
      text-align: center;
      padding: 2rem;
      font-size: 0.82rem;
      letter-spacing: 0.06em;
    }
    footer a { color: var(--sage); text-decoration: none; }

    /* ── REVIEWS ── */
    .reviews {
      background: var(--parchment);
      padding: 6rem 2.5rem;
    }
    .reviews-inner { max-width: 1000px; margin: 0 auto; }
    .reviews-header { text-align: center; margin-bottom: 3rem; }
    .reviews-header h2 { margin-bottom: 0.6rem; }
    .reviews-header p { color: #7a6555; font-size: 1rem; font-weight: 300; }

    /* existing reviews grid */
    .reviews-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.2rem;
      margin-bottom: 3rem;
    }
    .review-card {
      background: var(--ivory);
      border: 1px solid rgba(88,125,74,0.15);
      border-radius: 14px;
      padding: 1.6rem;
    }
    .review-stars { color: #c8922a; font-size: 1rem; letter-spacing: 0.1em; margin-bottom: 0.8rem; }
    .review-text {
      font-size: 0.93rem;
      line-height: 1.75;
      color: #5a4535;
      font-style: italic;
      margin-bottom: 1rem;
      font-weight: 300;
    }
    .review-author {
      font-size: 0.82rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--fern);
    }

    /* leave a review form */
    .leave-review {
      background: var(--bark);
      border-radius: 16px;
      padding: 2.8rem;
    }
    .leave-review h3 {
      font-family: 'Playfair Display', serif;
      font-size: 1.6rem;
      color: var(--cream);
      margin-bottom: 0.4rem;
    }
    .leave-review .form-sub {
      font-size: 0.9rem;
      color: rgba(245,240,232,0.55);
      margin-bottom: 1.8rem;
      font-weight: 300;
    }
    .star-picker { display: flex; gap: 0.4rem; margin-bottom: 1.5rem; }
    .star-btn {
      background: none;
      border: none;
      font-size: 1.8rem;
      cursor: pointer;
      color: rgba(245,240,232,0.2);
      transition: color 0.15s, transform 0.15s;
      padding: 0;
      line-height: 1;
    }
    .star-btn.active, .star-btn:hover { color: #c8922a; transform: scale(1.15); }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1rem; }
    .form-field { display: flex; flex-direction: column; gap: 0.4rem; }
    .form-field label {
      font-size: 0.75rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: rgba(245,240,232,0.5);
      font-weight: 700;
    }
    .form-field input,
    .form-field textarea {
      background: rgba(245,240,232,0.07);
      border: 1px solid rgba(245,240,232,0.15);
      border-radius: 8px;
      padding: 0.8rem 1rem;
      color: var(--cream);
      font-family: 'Lato', sans-serif;
      font-size: 0.95rem;
      outline: none;
      transition: border-color 0.2s;
      width: 100%;
    }
    .form-field input::placeholder,
    .form-field textarea::placeholder { color: rgba(245,240,232,0.25); }
    .form-field input:focus,
    .form-field textarea:focus { border-color: var(--sage); }
    .form-field textarea { resize: vertical; min-height: 100px; }
    .form-full { grid-column: 1 / -1; }
    .btn-submit {
      margin-top: 1.2rem;
      background: var(--fern);
      color: #fff;
      border: none;
      padding: 0.9rem 2.2rem;
      border-radius: 8px;
      font-size: 0.95rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      cursor: pointer;
      transition: background 0.2s, transform 0.2s;
      font-family: 'Lato', sans-serif;
    }
    .btn-submit:hover { background: var(--moss); transform: translateY(-2px); }
    .submit-success {
      display: none;
      color: var(--sage);
      font-size: 0.95rem;
      margin-top: 1rem;
      font-weight: 700;
    }

    /* ── ANIMATE ON SCROLL ── */
    .fade-up {
      opacity: 0;
      transform: translateY(28px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .fade-up.visible { opacity: 1; transform: none; }

    /* ── RESPONSIVE ── */
    @media (max-width: 820px) {
      nav { padding: 1rem 1.4rem; }
      .nav-links { display: none; }
      .about-inner { grid-template-columns: 1fr; gap: 3rem; }
      .why-grid { grid-template-columns: 1fr 1fr; }
      .reviews-grid { grid-template-columns: 1fr 1fr; }
      .form-row { grid-template-columns: 1fr; }
    }
    @media (max-width: 520px) {
      .hero { padding: 7rem 1.4rem 4rem; }
      .about { padding: 4rem 1.4rem; }
      .why { padding: 4rem 1.4rem; }
      .reviews { padding: 4rem 1.4rem; }
      .cta { padding: 4rem 1.4rem; }
      .why-grid { grid-template-columns: 1fr; }
      .pillars { grid-template-columns: 1fr; }
      .reviews-grid { grid-template-columns: 1fr; }
      .leave-review { padding: 1.8rem 1.4rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">Wild <span>Root</span></div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#reviews">Reviews</a></li>
      <li><a href="#contact"><span class="nav-cta">Get a Free Estimate</span></a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-inner">
      <div class="hero-eyebrow">Wild Root Home Services</div>
      <h1>We Care For Your Home<br><em>Like It's Ours.</em></h1>
      <p class="hero-sub">
        A dependable local home service company built on honest work, clear communication,
        and quality results — from lawn care to pressure washing to flowerbed refresh.
      </p>
      <div class="btn-group">
        <a href="tel:2283860079" class="btn-primary">📞 Call For Free Estimate</a>
        <a href="mailto:wildrootservices@gmail.com" class="btn-outline">✉ Email Us</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="about" id="about">
    <div class="about-inner">

      <div class="fade-up">
        <div class="section-label">About Wild Root</div>
        <h2>Dependable Service.<br>Clean Professional Results.</h2>
        <p class="about-body">
          We believe good business starts with trust. At Wild Root, we focus on reliability, honest
          communication, and attention to detail. Whether we're pressure washing a driveway or refreshing
          your flowerbeds, we work hard to leave every property looking its best.
        </p>
        <div class="pillars">
          <div class="pillar">
            <div class="pillar-icon">🌿</div>
            <h4>Fast Response</h4>
            <p>Quick communication and dependable scheduling you can count on.</p>
          </div>
          <div class="pillar">
            <div class="pillar-icon">🪵</div>
            <h4>Trusted Work</h4>
            <p>Professional quality with genuine attention to every detail.</p>
          </div>
        </div>
      </div>

      <div class="services-panel fade-up" id="services">
        <h3>Our Services</h3>
        <div class="service-item">
          <h4>🌱 Lawn Care</h4>
          <p>Mowing, edging, trimming, seasonal cleanups, and dependable routine lawn maintenance.</p>
        </div>
        <div class="service-item">
          <h4>💧 Pressure Washing</h4>
          <p>Driveways, patios, sidewalks, fences, siding, and exterior surface cleaning.</p>
        </div>
        <div class="service-item">
          <h4>🌸 Flowerbeds & Landscaping</h4>
          <p>Mulching, planting, flowerbed cleanup, and curb appeal improvements.</p>
        </div>
      </div>

    </div>
  </section>

  <!-- WHY US -->
  <section class="why">
    <div class="why-inner">
      <div class="section-label fade-up">Why Wild Root</div>
      <h2 class="fade-up">A Local Team That Truly Cares</h2>
      <p class="why-sub fade-up">We show up on time, treat every property with respect, and don't leave until the job is done right.</p>
      <div class="why-grid">
        <div class="why-card fade-up">
          <div class="why-card-icon">📅</div>
          <h4>On-Time, Every Time</h4>
          <p>We respect your schedule. Clear communication from booking to job completion.</p>
        </div>
        <div class="why-card fade-up">
          <div class="why-card-icon">🔎</div>
          <h4>Detail Obsessed</h4>
          <p>Clean edges, thorough cleanup, no shortcuts. We sweat the small stuff so you don't have to.</p>
        </div>
        <div class="why-card fade-up">
          <div class="why-card-icon">🤝</div>
          <h4>Honest Pricing</h4>
          <p>Free estimates, no hidden fees. Just straightforward pricing for quality work.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- REVIEWS -->
  <section class="reviews" id="reviews">
    <div class="reviews-inner">

      <div class="reviews-header fade-up">
        <div class="section-label">What Customers Say</div>
        <h2>Real Reviews From Real Neighbors</h2>
        <p>Serving the Gulf Coast community with work we're proud to stand behind.</p>
      </div>

      <div class="reviews-grid">
        <div class="review-card fade-up">
          <div class="review-stars">★★★★★</div>
          <p class="review-text">"Wild Root did an amazing job on our yard. Showed up on time, cleaned everything up, and the edging was perfect. Will definitely be calling again."</p>
          <div class="review-author">— Sarah M., Gulfport</div>
        </div>
        <div class="review-card fade-up">
          <div class="review-stars">★★★★★</div>
          <p class="review-text">"Had my driveway and patio pressure washed — looks brand new. Fair price, great communication, no surprises. Highly recommend."</p>
          <div class="review-author">— James T., Biloxi</div>
        </div>
        <div class="review-card fade-up">
          <div class="review-stars">★★★★★</div>
          <p class="review-text">"They redid our flowerbeds and laid fresh mulch. The whole front yard looks completely transformed. Honest, hardworking guys."</p>
          <div class="review-author">— Linda K., Long Beach</div>
        </div>
      </div>

      <!-- Leave a Review Form -->
      <div class="leave-review fade-up">
        <h3>Leave Us a Review</h3>
        <p class="form-sub">Had us out recently? We'd love to hear how it went.</p>

        <div class="star-picker" id="starPicker">
          <button class="star-btn" data-val="1">★</button>
          <button class="star-btn" data-val="2">★</button>
          <button class="star-btn" data-val="3">★</button>
          <button class="star-btn" data-val="4">★</button>
          <button class="star-btn" data-val="5">★</button>
        </div>

        <div class="form-row">
          <div class="form-field">
            <label>Your Name</label>
            <input type="text" id="reviewName" placeholder="e.g. Sarah M." />
          </div>
          <div class="form-field">
            <label>City / Neighborhood</label>
            <input type="text" id="reviewCity" placeholder="e.g. Gulfport" />
          </div>
          <div class="form-field form-full">
            <label>Your Review</label>
            <textarea id="reviewText" placeholder="Tell us about your experience..."></textarea>
          </div>
        </div>

        <button class="btn-submit" onclick="submitReview()">Submit Review</button>
        <div class="submit-success" id="submitSuccess">✅ Thank you! Your review has been submitted.</div>
      </div>

    </div>
  </section>

  <!-- CTA BANNER -->
  <section class="cta" id="contact">
    <div class="cta-inner fade-up">
      <div class="section-label" style="color:var(--sage)">Get In Touch</div>
      <h2>Ready To Refresh Your Property?</h2>
      <p>Get reliable service, clear communication, and quality results from a local team that truly cares.</p>
      <div class="contact-buttons">
        <a href="tel:2283860079" class="contact-link phone">📞 (228) 386-0079</a>
        <a href="mailto:wildrootservices@gmail.com" class="contact-link">✉️ wildrootservices@gmail.com</a>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>&copy; 2025 Wild Root Home Services &nbsp;·&nbsp; Gulfport, MS &nbsp;·&nbsp; <a href="tel:2283860079">(228) 386-0079</a></p>
  </footer>

  <script>
    // Fade-up on scroll
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
    }, { threshold: 0.12 });
    document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));

    // Star picker
    let selectedStars = 0;
    const starBtns = document.querySelectorAll('.star-btn');
    starBtns.forEach(btn => {
      btn.addEventListener('click', () => {
        selectedStars = parseInt(btn.dataset.val);
        starBtns.forEach(b => b.classList.toggle('active', parseInt(b.dataset.val) <= selectedStars));
      });
      btn.addEventListener('mouseenter', () => {
        starBtns.forEach(b => b.classList.toggle('active', parseInt(b.dataset.val) <= parseInt(btn.dataset.val)));
      });
    });
    document.getElementById('starPicker').addEventListener('mouseleave', () => {
      starBtns.forEach(b => b.classList.toggle('active', parseInt(b.dataset.val) <= selectedStars));
    });

    // Submit review
    function submitReview() {
      const name = document.getElementById('reviewName').value.trim();
      const city = document.getElementById('reviewCity').value.trim();
      const text = document.getElementById('reviewText').value.trim();
      if (!name || !text || selectedStars === 0) {
        alert('Please fill in your name, a rating, and your review.');
        return;
      }
      // Add new card to the grid
      const grid = document.querySelector('.reviews-grid');
      const stars = '★'.repeat(selectedStars) + '☆'.repeat(5 - selectedStars);
      const card = document.createElement('div');
      card.className = 'review-card fade-up visible';
      card.innerHTML = `
        <div class="review-stars">${stars}</div>
        <p class="review-text">"${text}"</p>
        <div class="review-author">— ${name}${city ? ', ' + city : ''}</div>
      `;
      grid.appendChild(card);
      // Reset form
      document.getElementById('reviewName').value = '';
      document.getElementById('reviewCity').value = '';
      document.getElementById('reviewText').value = '';
      selectedStars = 0;
      starBtns.forEach(b => b.classList.remove('active'));
      document.getElementById('submitSuccess').style.display = 'block';
      setTimeout(() => document.getElementById('submitSuccess').style.display = 'none', 4000);
      card.scrollIntoView({ behavior: 'smooth', block: 'center' });
    }
  </script>

</body>
</html>
