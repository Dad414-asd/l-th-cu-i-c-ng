# l-th-cu-i-c-ng
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lá thư · Cảm ơn</title>
  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Allura&family=Poppins:wght@400;600;700&family=Be+Vietnam+Pro:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: #EDE4D5;
      background-image: 
        /* noise texture */
        url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.04'/%3E%3C/svg%3E");
      background-size: 300px 300px;
      padding: 2rem;
      position: relative;
      font-family: 'Be Vietnam Pro', sans-serif;
    }

    /* Vintage paper background with subtle shading & stains */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background: 
        radial-gradient(circle at 20% 20%, rgba(200, 180, 160, 0.08) 0%, transparent 50%),
        radial-gradient(circle at 80% 80%, rgba(160, 140, 120, 0.06) 0%, transparent 50%),
        radial-gradient(circle at 30% 70%, rgba(190, 170, 150, 0.04) 0%, transparent 40%),
        radial-gradient(circle at 70% 30%, rgba(180, 160, 140, 0.05) 0%, transparent 40%);
      pointer-events: none;
      z-index: 0;
    }

    /* Vintage corner ornaments (very subtle) */
    .corner-decor {
      position: fixed;
      opacity: 0.22;
      pointer-events: none;
      z-index: 0;
      font-family: 'Great Vibes', cursive;
      color: #8a7a6a;
      font-size: 2.8rem;
      line-height: 1;
      letter-spacing: 0.05em;
    }
    .corner-decor--tl {
      top: 1.2rem;
      left: 1.8rem;
      transform: rotate(-6deg);
      font-size: 3.6rem;
      opacity: 0.18;
    }
    .corner-decor--tr {
      top: 1.2rem;
      right: 1.8rem;
      transform: rotate(8deg);
      font-size: 3.2rem;
      opacity: 0.15;
    }
    .corner-decor--bl {
      bottom: 1.2rem;
      left: 1.8rem;
      transform: rotate(4deg);
      font-size: 3.4rem;
      opacity: 0.2;
    }
    .corner-decor--br {
      bottom: 1.2rem;
      right: 1.8rem;
      transform: rotate(-5deg);
      font-size: 3rem;
      opacity: 0.16;
    }
    /* small botanical drawings using unicode/characters */
    .corner-decor span {
      display: inline-block;
      filter: drop-shadow(0 1px 2px rgba(0,0,0,0.03));
    }

    /* Main letter – the paper */
    .letter {
      position: relative;
      z-index: 2;
      width: 100%;
      max-width: 720px;
      background: #ffffff;
      background-image: 
        linear-gradient(180deg, rgba(245, 240, 235, 0.2) 0%, transparent 10%),
        radial-gradient(circle at 30% 40%, rgba(230, 220, 210, 0.08) 0%, transparent 50%);
      box-shadow: 
        0 12px 40px rgba(0, 0, 0, 0.06),
        0 4px 20px rgba(0, 0, 0, 0.04),
        inset 0 0 0 1px rgba(255, 255, 255, 0.5);
      padding: 3.2rem 3.8rem 3.8rem 3.8rem;
      border-radius: 0px;
      transition: opacity 0.8s ease, transform 0.8s ease;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeUp 0.9s ease forwards;
      margin: 1.5rem auto;
    }

    /* torn edge effect (right side) */
    .letter::after {
      content: '';
      position: absolute;
      top: 0;
      right: -4px;
      width: 12px;
      height: 100%;
      background: 
        repeating-linear-gradient(170deg, 
          transparent 0px, 
          rgba(210, 200, 190, 0.2) 2px, 
          transparent 4px,
          rgba(200, 185, 170, 0.15) 6px,
          transparent 9px,
          rgba(220, 210, 200, 0.1) 12px
        );
      pointer-events: none;
      opacity: 0.3;
      border-right: 1px solid rgba(200, 185, 170, 0.2);
      filter: blur(0.3px);
    }

    @keyframes fadeUp {
      0% { opacity: 0; transform: translateY(24px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    /* Typography */
    .letter__title {
      font-family: 'Great Vibes', cursive;
      font-size: 3.8rem;
      font-weight: 400;
      color: #5B5548;
      letter-spacing: 0.02em;
      margin-bottom: 0.1rem;
      line-height: 1.1;
      position: relative;
      display: inline-block;
    }

    .letter__title-wrapper {
      display: flex;
      align-items: flex-end;
      gap: 0.8rem;
      margin-bottom: 0.2rem;
      flex-wrap: wrap;
    }

    .letter__title-ornament {
      font-family: 'Great Vibes', cursive;
      font-size: 2.6rem;
      color: #D8C8B5;
      letter-spacing: 0.12em;
      opacity: 0.6;
      margin-left: 0.2rem;
      line-height: 1.2;
      white-space: nowrap;
      font-weight: 300;
    }

    .letter__greeting {
      font-family: 'Poppins', sans-serif;
      font-weight: 600;
      font-size: 1.9rem;
      color: #3d3a34;
      margin-top: 0.8rem;
      margin-bottom: 1.4rem;
      letter-spacing: -0.01em;
    }

    .letter__body {
      font-family: 'Be Vietnam Pro', sans-serif;
      font-weight: 400;
      font-size: 1.05rem;
      line-height: 2.0;
      color: #4a4742;
      text-align: justify;
      word-break: break-word;
    }

    .letter__body p {
      margin-bottom: 1.4rem;
      text-indent: 0;
    }

    .letter__body p:last-of-type {
      margin-bottom: 2.2rem;
    }

    /* decorative dried flower (bottom left) */
    .letter__flower {
      position: absolute;
      bottom: 2.2rem;
      left: 2.2rem;
      font-size: 2.8rem;
      line-height: 1;
      color: #D8C8B5;
      opacity: 0.35;
      pointer-events: none;
      font-family: 'Great Vibes', cursive;
      transform: rotate(-6deg);
      letter-spacing: 0.1rem;
      filter: drop-shadow(0 1px 3px rgba(0,0,0,0.03));
      white-space: nowrap;
    }

    /* closing */
    .letter__closing {
      margin-top: 2rem;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      text-align: right;
    }

    .letter__closing-sincerely {
      font-family: 'Be Vietnam Pro', sans-serif;
      font-weight: 400;
      font-size: 1rem;
      color: #5f5b55;
      letter-spacing: 0.02em;
      margin-bottom: 0.3rem;
    }

    .letter__closing-signature {
      font-family: 'Great Vibes', cursive;
      font-size: 2.6rem;
      font-weight: 400;
      color: #4f4a42;
      line-height: 1.1;
      margin-top: -0.2rem;
      margin-bottom: 0.1rem;
      letter-spacing: 0.02em;
    }

    .letter__closing-name {
      font-family: 'Poppins', sans-serif;
      font-weight: 600;
      font-size: 1.05rem;
      color: #3d3a34;
      letter-spacing: 0.02em;
      opacity: 0.85;
    }

    /* responsiveness */
    @media (max-width: 700px) {
      .letter {
        padding: 2.2rem 1.8rem 2.8rem 1.8rem;
        max-width: 100%;
      }
      .letter__title {
        font-size: 2.8rem;
      }
      .letter__title-ornament {
        font-size: 1.8rem;
      }
      .letter__greeting {
        font-size: 1.5rem;
      }
      .letter__body {
        font-size: 0.98rem;
        line-height: 1.9;
      }
      .letter__closing-signature {
        font-size: 2.2rem;
      }
      .letter__flower {
        font-size: 2rem;
        bottom: 1.4rem;
        left: 1.4rem;
        opacity: 0.3;
      }
      .corner-decor {
        display: none;
      }
      .letter__title-wrapper {
        flex-direction: column;
        align-items: flex-start;
        gap: 0.1rem;
      }
    }

    @media (max-width: 450px) {
      .letter {
        padding: 1.8rem 1.2rem 2.4rem 1.2rem;
      }
      .letter__title {
        font-size: 2.2rem;
      }
      .letter__greeting {
        font-size: 1.3rem;
      }
      .letter__body {
        font-size: 0.92rem;
        line-height: 1.8;
      }
      .letter__closing-signature {
        font-size: 2rem;
      }
      .letter__flower {
        font-size: 1.6rem;
        bottom: 1rem;
        left: 1rem;
      }
    }
  </style>
</head>
<body>
  <!-- Corner decorations (vintage botanical illustrations) -->
  <div class="corner-decor corner-decor--tl" aria-hidden="true">
    <span>🌸</span> <span style="font-size:0.8em; opacity:0.7;">✿</span>
  </div>
  <div class="corner-decor corner-decor--tr" aria-hidden="true">
    <span>🦋</span> <span style="font-size:0.7em; opacity:0.6;">🌿</span>
  </div>
  <div class="corner-decor corner-decor--bl" aria-hidden="true">
    <span>🌾</span> <span style="font-size:0.9em; opacity:0.7;">🍂</span>
  </div>
  <div class="corner-decor corner-decor--br" aria-hidden="true">
    <span>🌱</span> <span style="font-size:0.8em; opacity:0.6;">✧</span>
  </div>

  <!-- Letter -->
  <div class="letter" role="article" aria-label="Lá thư cảm ơn">
    
    <!-- Title: Thank You + botanical ornament -->
    <div class="letter__title-wrapper">
      <h1 class="letter__title">Thank You</h1>
      <span class="letter__title-ornament">—  ✿  —</span>
    </div>

    <!-- Greeting -->
    <div class="letter__greeting">Dear Lan Chi,</div>

    <!-- Body content -->
    <div class="letter__body">
      <p>Anh cảm ơn em vì đã luôn hỗ trợ và đồng hành cùng anh trong suốt thời gian qua.</p>
      <p>Anh cũng muốn gửi đến em một lời xin lỗi. Trước đây có vài lần anh cư xử chưa thật sự khéo, có những hành động vô tình làm em cảm thấy không thoải mái. Anh chưa bao giờ có ý làm em buồn, nhưng anh hiểu rằng những gì mình làm đã khiến em tổn thương và anh thật lòng xin lỗi vì điều đó.</p>
      <p>Gần đây lịch làm việc cũng bị xáo trộn, anh biết điều đó ít nhiều đã ảnh hưởng đến em nên anh càng thấy áy náy hơn.</p>
      <p>Về chuyện hôm đó, do Hiếu cũng đã có ý định nghỉ từ trước nên mọi thứ diễn ra khá căng thẳng. Anh Điển thì chưa nắm được việc đổi lịch nên lúc đó có hơi nóng tính, vô tình ảnh hưởng đến em và Nhi. Anh thật lòng xin lỗi em và cả Nhi vì những gì đã xảy ra.</p>
      <p>Hôm nay là ngày cuối anh đi làm rồi. Anh cảm ơn em rất nhiều vì đã đồng hành cùng anh trong suốt quãng thời gian vừa qua. Anh nghĩ em là người chứng kiến rõ nhất sự thay đổi của anh từ những ngày đầu đến bây giờ.</p>
      <p>Cảm ơn người đồng đội đã cùng anh "chiến" hết mình vì doanh số. Anh luôn trân trọng những khoảng thời gian mình được làm việc cùng em.</p>
      <p>Chúc em luôn thuận lợi, học tập thật tốt, công việc suôn sẻ và lúc nào cũng giữ được thật nhiều năng lượng tích cực nhé!</p>
      <p>Cảm ơn em rất nhiều. Hy vọng sau này nếu có dịp, anh em mình vẫn sẽ gặp lại nhau, cùng ngồi cà phê, ăn uống và quẩy hết mình như những người đồng đội từng sát cánh với nhau.</p>
      <p>Chúc em luôn vui, luôn gặp nhiều điều tốt đẹp và sớm đạt được tất cả những điều mình mong muốn nhé!</p>
    </div>

    <!-- Decorative dried flower (bottom left) -->
    <div class="letter__flower" aria-hidden="true">
      ✿  🌾  ✿  🍂
    </div>

    <!-- Closing -->
    <div class="letter__closing">
      <div class="letter__closing-sincerely">Your sincerely,</div>
      <div class="letter__closing-signature">Lê Nguyễn Phương Nam</div>
      <div class="letter__closing-name">Lê Nguyễn Phương Nam</div>
    </div>

  </div>
</body>
</html>
