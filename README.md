<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ernest & Rosemary Wedding</title>

  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:wght@400;600;700&family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Montserrat", sans-serif;
      background: #f4efe8;
      color: #171717;
      overflow-x: hidden;
    }

    .page {
      min-height: 100vh;
      width: 100%;
      display: none;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 30px;
    }

    .page.active {
      display: flex;
    }

    .script {
      font-family: "Great Vibes", cursive;
      font-weight: 400;
    }

    .serif {
      font-family: "Playfair Display", serif;
    }

    .cover-page {
      background: #f4efe8;
      flex-direction: column;
    }

    .tap-text {
      font-family: "Playfair Display", serif;
      font-size: 24px;
      margin-bottom: 35px;
    }

    .names-cover {
      font-family: "Great Vibes", cursive;
      font-size: clamp(54px, 9vw, 120px);
      color: #111;
      margin-bottom: 25px;
    }

    .monogram {
      width: 130px;
      height: 130px;
      border: 1px solid #111;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Playfair Display", serif;
      font-size: 48px;
      margin: 0 auto;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .monogram:hover {
      transform: scale(1.05);
      background: #3d2a5d;
      color: white;
    }

    .invite-page {
      background: #f4efe8;
      flex-direction: column;
    }

    .invite-title {
      font-family: "Great Vibes", cursive;
      font-size: clamp(56px, 8vw, 100px);
      margin-bottom: 10px;
    }

    .invite-sub {
      font-size: 22px;
      margin-bottom: 30px;
    }

    .envelope {
      position: relative;
      width: 310px;
      height: 230px;
      background: #5d3d8c;
      margin: 30px auto;
      cursor: pointer;
      box-shadow: 0 20px 40px rgba(0,0,0,0.18);
      overflow: hidden;
    }

    .envelope:before {
      content: "";
      position: absolute;
      top: -75px;
      left: 0;
      width: 310px;
      height: 180px;
      background: #6f4ca3;
      clip-path: polygon(50% 0, 0 100%, 100% 100%);
    }

    .letter {
      position: absolute;
      top: 20px;
      left: 35px;
      width: 240px;
      height: 155px;
      background: white;
      padding: 25px 15px;
      z-index: 2;
      box-shadow: 0 6px 14px rgba(0,0,0,0.18);
      transform: rotate(4deg);
    }

    .letter h3 {
      font-family: "Great Vibes", cursive;
      font-size: 36px;
      font-weight: 400;
    }

    .letter p {
      font-size: 13px;
    }

    .envelope:after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 310px;
      height: 130px;
      background: #4d3278;
      clip-path: polygon(0 0, 50% 65%, 100% 0, 100% 100%, 0 100%);
      z-index: 3;
    }

    .click-note {
      font-family: "Playfair Display", serif;
      font-size: 18px;
      margin-top: 20px;
    }

    .site {
      display: none;
      background: #f4efe8;
    }

    .site.active {
      display: block;
    }

    .hero {
      min-height: 100vh;
      background: linear-gradient(rgba(0,0,0,.35), rgba(0,0,0,.35)), #111;
      color: white;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      text-align: center;
      padding: 60px 20px;
    }

    .hero-content {
      max-width: 900px;
    }

    .hero h1 {
      font-family: "Great Vibes", cursive;
      font-size: clamp(64px, 12vw, 150px);
      font-weight: 400;
      line-height: 1;
    }

    .hero p {
      letter-spacing: 3px;
      font-size: 15px;
      margin-top: 15px;
    }

    .section {
      max-width: 1100px;
      margin: 0 auto;
      padding: 80px 22px;
      text-align: center;
    }

    .section-title {
      font-family: "Great Vibes", cursive;
      font-size: clamp(52px, 8vw, 88px);
      font-weight: 400;
      margin-bottom: 15px;
    }

    .small-heading {
      font-size: 13px;
      font-weight: 700;
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-bottom: 22px;
    }

    .date-line {
      font-family: "Playfair Display", serif;
      font-size: 20px;
      font-weight: 700;
      letter-spacing: 2px;
      margin-bottom: 10px;
    }

    .body-text {
      max-width: 760px;
      margin: 0 auto;
      line-height: 1.8;
      font-size: 16px;
    }

    .verse {
      margin: 25px auto;
      font-family: "Playfair Display", serif;
      font-size: 18px;
      max-width: 750px;
    }

    .photo-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 0;
      margin-bottom: 60px;
    }

    .photo-placeholder {
      min-height: 360px;
      background: #111;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Playfair Display", serif;
      font-size: 28px;
      padding: 20px;
    }

    .photo-placeholder.light {
      background: #ddd8d2;
      color: #111;
    }

    .details-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 25px;
      margin-top: 40px;
    }

    .card {
      background: white;
      padding: 30px;
      border: 1px solid #ddd3c9;
      box-shadow: 0 10px 25px rgba(0,0,0,0.05);
    }

    .card h3 {
      font-family: "Great Vibes", cursive;
      font-size: 48px;
      font-weight: 400;
      margin-bottom: 15px;
    }

    .card p {
      line-height: 1.7;
      font-size: 15px;
    }

    .button {
      display: inline-block;
      margin-top: 18px;
      padding: 12px 26px;
      background: #111;
      color: white;
      text-decoration: none;
      font-size: 13px;
      letter-spacing: 1px;
      text-transform: uppercase;
      transition: 0.3s ease;
    }

    .button:hover {
      background: #4d3278;
    }

    .timeline {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      margin-top: 35px;
    }

    .time-item {
      border-top: 1px solid #111;
      padding-top: 18px;
    }

    .time-item strong {
      display: block;
      font-family: "Playfair Display", serif;
      font-size: 22px;
      margin-bottom: 8px;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
      margin-top: 35px;
    }

    .gallery div {
      min-height: 220px;
      background: #222;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Playfair Display", serif;
      padding: 10px;
    }

    .dress-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 25px;
      margin-top: 35px;
      text-align: left;
    }

    .dress-box {
      background: white;
      padding: 30px;
      border: 1px solid #ddd3c9;
    }

    .dress-box h3 {
      font-family: "Playfair Display", serif;
      margin-bottom: 15px;
      font-size: 24px;
    }

    .rsvp-box {
      max-width: 700px;
      margin: 0 auto;
      background: white;
      padding: 45px 25px;
      border: 1px solid #ddd3c9;
    }

    .registry {
      background: #eee7df;
    }

    .culture {
      background: #f4efe8;
    }

    .thank-you {
      background: #111;
      color: white;
      padding-bottom: 100px;
    }

    .thank-you .body-text {
      color: #eee;
    }

    .hashtag {
      font-family: "Playfair Display", serif;
      letter-spacing: 2px;
      margin-top: 25px;
      font-weight: 700;
    }

    @media (max-width: 800px) {
      .photo-row,
      .details-grid,
      .timeline,
      .gallery,
      .dress-grid {
        grid-template-columns: 1fr;
      }

      .section {
        padding: 60px 18px;
      }

      .hero {
        min-height: 80vh;
      }

      .envelope {
        width: 270px;
        height: 205px;
      }

      .envelope:before {
        width: 270px;
      }

      .envelope:after {
        width: 270px;
      }

      .letter {
        width: 210px;
        left: 30px;
      }
    }
  </style>
</head>

<body>

  <section id="coverPage" class="page cover-page active">
    <p class="tap-text">(Tap on the envelope to open!)</p>
    <h1 class="names-cover">Ernest & Rosemary</h1>
    <div class="monogram" onclick="showInvite()">E<br>R</div>
  </section>

  <section id="invitePage" class="page invite-page">
    <h2 class="invite-title">You’re invited</h2>
    <p class="invite-sub">to the wedding!</p>

    <div class="envelope" onclick="showSite()">
      <div class="letter">
        <h3>You’re invited</h3>
        <p>to the wedding!</p>
      </div>
    </div>

    <p class="click-note">(Click on the letter to proceed!)</p>
  </section>

  <main id="mainSite" class="site">

    <section class="hero">
      <div class="hero-content">
        <h1>Ernest & Rosemary</h1>
        <p>OCTOBER 23, 2027 • TAMPA, FLORIDA</p>
      </div>
    </section>

    <section class="section">
      <h2 class="section-title">Venue</h2>
      <p class="date-line">OCTOBER 23, 2027 • TAMPA, FLORIDA</p>
      <p class="small-heading">THE VENETIAN EVENT CENTER</p>
      <p class="body-text">WE CAN’T WAIT TO CELEBRATE THIS SPECIAL DAY WITH THE PEOPLE WHO MEAN THE MOST TO US.</p>
      <p class="verse">Therefore, what God has joined together, let no one separate. <br> Mark 10:9</p>
    </section>

    <section class="section">
      <p class="small-heading">WE’RE GETTING MARRIED AND WE CAN’T WAIT TO CELEBRATE WITH YOU.</p>
      <h2 class="section-title">Our Story</h2>
      <p class="body-text">
        Ernest and I met in 2020 through mutual friends, and what started simply quickly turned into something real.
        By 2021, we had made it official, and from that moment on, everything just felt right.
        <br><br>
        We’ve grown through so much together, learning, evolving, and choosing each other every step of the way,
        while keeping God at the center of it all. Our journey hasn’t been perfect, but it’s been real, and through it all,
        we’ve built something strong, honest, and full of love.
        <br><br>
        In November 2025, Ernest planned the most beautiful proposal. Being surrounded by the people I love made it even more special.
        In that moment, I realized everything we had been building led to this. And of course, I said yes.
        <br><br>
        Our story is full of love, growth, laughter, and real moments. And this is just the beginning for us.
      </p>
      <p class="hashtag">IT IS OFFICIAL #RNE2027</p>
    </section>

    <section class="section">
      <h2 class="section-title">Details</h2>
      <p class="small-heading">HERE IS OUR WEDDING SCHEDULE</p>

      <div class="details-grid">
        <div class="card">
          <h3>Ceremony</h3>
          <p>October 23, 2027, 3:30 PM</p>
          <p>St. Mark Evangelist Catholic Church</p>
          <a href="#" class="button">View Map</a>
        </div>

        <div class="card">
          <h3>Reception</h3>
          <p>6:00 PM</p>
          <p>The Venetian Event Center</p>
          <a href="#" class="button">View Map</a>
        </div>
      </div>
    </section>

    <section class="section">
      <h2 class="section-title">Timeline</h2>
      <p class="small-heading">HERE IS OUR WEDDING SCHEDULE</p>

      <div class="timeline">
        <div class="time-item">
          <strong>1:00 PM</strong>
          <span>CEREMONY BEGINS</span>
        </div>
        <div class="time-item">
          <strong>5:30 PM</strong>
          <span>COCKTAIL HOUR</span>
        </div>
        <div class="time-item">
          <strong>6:00 PM</strong>
          <span>RECEPTION BEGINS</span>
        </div>
        <div class="time-item">
          <strong>8:30 PM</strong>
          <span>DANCING & CELEBRATION</span>
        </div>
      </div>

      <p class="verse">“From long-distance calls to building a life together, our journey has been full of love, growth, and laughter.”</p>
    </section>

    <section class="section">
      <h2 class="section-title">Gallery</h2>
      <p class="small-heading">A GLIMPSE INTO OUR JOURNEY TOGETHER</p>

      <div class="gallery">
        <div>Pre Wedding Look</div>
        <div>Couple Photo</div>
        <div>Traditional Look</div>
        <div>Love Story</div>
      </div>

      <p class="hashtag">#RNE2027</p>
    </section>

    <section class="section">
      <h2 class="section-title">Dress Code</h2>
      <p class="body-text">
        Guests are invited to dress elegantly in attire of their choice, paired with our designated wedding accessories.
      </p>

      <div class="dress-grid">
        <div class="dress-box">
          <h3>Ladies</h3>
          <p>Olive green gele/head-tie, $70.</p>
        </div>

        <div class="dress-box">
          <h3>Gentlemen</h3>
          <p>Olive green fila/cap, $50.</p>
          <p>Gentlemen must provide head measurements when ordering caps.</p>
        </div>
      </div>

      <p class="body-text" style="margin-top:25px;">
        Please contact Rosemary at +1 (813) 900-8751 for payment and orders.
      </p>
    </section>

    <section class="section">
      <div class="rsvp-box">
        <h2 class="section-title">RSVP</h2>
        <p class="small-heading">WE WOULD LOVE TO CELEBRATE THIS SPECIAL DAY WITH YOU.</p>
        <p class="body-text">
          Please let us know if you will be able to join us by May 15, 2027.
          Kindly confirm your attendance and number of guests by clicking the RSVP button below.
        </p>
        <a class="button" href="https://docs.google.com/forms/d/e/1FAIpQLSe3Bp1iCKwRicYL_Yu2TpTXWn4H9dq2u3qGnMYlrczKG3yrlw/viewform" target="_blank">
          Confirm Attendance
        </a>
      </div>
    </section>

    <section class="section registry">
      <h2 class="section-title">Registry</h2>
      <p class="small-heading">YOUR PRESENCE IS TRULY THE GREATEST GIFT TO US.</p>
      <p class="body-text">
        For those who would like to give, you’re welcome to bring your gift on the day of the celebration.
      </p>
    </section>

    <section class="section culture">
      <h2 class="section-title">Our Culture</h2>
      <p class="body-text">
        Our love story is not just about us, it’s also about where we come from. We’re proud to celebrate our Nigerian heritage through our traditions,
        our music, and the joy of bringing our families together.
        <br><br>
        From the aso ebi to the dancing and everything in between, this day will be a beautiful reflection of our culture,
        our love, and who we are.
      </p>

      <p class="hashtag">#RNE2027</p>

      <p class="body-text" style="margin-top:30px;">
        We’re excited to announce that both our church wedding and traditional ceremonies will take place on the same day.
        Group photos to follow immediately after the ceremony.
        <br><br>
        NO KIDS ALLOWED.
      </p>
    </section>

    <section class="section thank-you">
      <h2 class="section-title">Thank You</h2>
      <p class="small-heading">FOR BEING PART OF OUR STORY</p>
      <p class="body-text">
        We feel grateful to celebrate this special day with our family and friends.
        For any questions, feel free to contact us at Itohan185@gmail.com
      </p>
      <p class="hashtag">Our celebration hashtag: #RNE2027</p>
    </section>

  </main>

  <script>
    function showInvite() {
      document.getElementById("coverPage").classList.remove("active");
      document.getElementById("invitePage").classList.add("active");
    }

    function showSite() {
      document.getElementById("invitePage").classList.remove("active");
      document.getElementById("mainSite").classList.add("active");
      window.scrollTo(0, 0);
    }
  </script>

</body>
</html>
