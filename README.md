<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>115 Inker Internship</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700;900&family=Playfair+Display:ital,wght@1,500&display=swap" rel="stylesheet">
    <style>
        /* 全域設定 */
        body {
            margin: 0;
            padding: 0;
            background-color: #1a1a1a; /* 網頁背景深灰 */
            font-family: 'Noto Serif TC', serif;
            display: flex;
            justify-content: center;
            min-height: 100vh; /* 確保畫面高度足夠 */
        }

        /* 海報主容器 */
        .poster-container {
            width: 100%;
            max-width: 600px; /* 限制最大寬度，模擬手機/海報比例 */
            height: 800px;    /* 設定固定高度，保持海報長寬感 */
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 30px rgba(0,0,0,0.5); /* 讓海報浮起來的陰影 */
            
            /* 關鍵修改：使用 CSS 背景圖，避免白塊問題 */
            background-image: url('https://images.pexels.com/photos/7972555/pexels-photo-7972555.jpeg');
            background-size: cover;     /* 讓圖片填滿 */
            background-position: center bottom; /* 圖片對齊下方 */
            background-color: #333;     /* 圖片載入前的底色 */
        }

        /* 漸層遮罩：確保文字清晰可見 */
        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            /* 由下往上的黑色漸層，底部較黑以襯托文字 */
            background: linear-gradient(to top, rgba(0,0,0,0.9) 10%, rgba(0,0,0,0.5) 50%, rgba(0,0,0,0.1) 100%);
            display: flex;
            flex-direction: column;
            justify-content: space-between; /* 讓評價在上面，資訊在下面 */
            padding: 40px 20px;
            box-sizing: border-box;
        }

        /* 頂部：評價區 */
        .reviews-section {
            text-align: center;
            margin-top: 20px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.8);
        }
        .review-item {
            margin-bottom: 20px;
        }
        .stars {
            color: #ffd700; /* 金色星星 */
            font-size: 14px;
            letter-spacing: 3px;
            margin-bottom: 5px;
            display: block;
        }
        .quote {
            color: #f0f0f0;
            font-size: 14px;
            font-style: italic;
            line-height: 1.4;
            opacity: 0.9;
        }

        /* 底部：主要資訊區 */
        .content-section {
            text-align: center;
            margin-bottom: 20px;
        }

        /* Slogan */
        .slogan {
            font-family: 'Playfair Display', serif;
            color: #ccc;
            font-size: 15px;
            letter-spacing: 2px;
            text-transform: uppercase;
            border-bottom: 1px solid rgba(255,255,255,0.4);
            display: inline-block;
            padding-bottom: 8px;
            margin-bottom: 15px;
        }

        /* 主標題 */
        .main-title {
            color: #ffffff;
            font-size: 46px; /* 稍微加大 */
            font-weight: 900;
            margin: 0;
            line-height: 1.1;
            letter-spacing: 4px;
            text-transform: uppercase;
            text-shadow: 0 0 20px rgba(0,0,0,0.8);
        }
        .sub-title {
            color: #dddddd;
            font-size: 18px;
            letter-spacing: 4px;
            margin-top: 5px;
            margin-bottom: 25px;
            font-weight: 400;
        }

        /* 資訊細節 */
        .info-details {
            font-family: Arial, sans-serif; /* 資訊類文字用無襯線體較易讀 */
            color: #aaaaaa;
            font-size: 13px;
            line-height: 1.8;
            letter-spacing: 1px;
            margin-bottom: 30px;
            text-transform: uppercase;
        }
        .highlight-red {
            color: #ff6b6b;
            font-weight: bold;
        }
        .highlight-white {
            color: #ffffff;
            font-weight: bold;
        }
        .tag-box {
            border: 1px solid #999;
            padding: 1px 5px;
            font-size: 11px;
            border-radius: 2px;
            color: #ccc;
            margin-right: 5px;
        }

        /* 按鈕樣式 */
        .cta-button {
            display: inline-block;
            color: #ffffff;
            border: 1px solid rgba(255,255,255,0.8);
            font-size: 16px;
            font-weight: bold;
            letter-spacing: 3px;
            padding: 12px 40px;
            text-decoration: none;
            transition: all 0.3s ease;
            background-color: rgba(0,0,0,0.2);
            backdrop-filter: blur(4px); /* 磨砂玻璃效果 */
        }
        
        .cta-button:hover {
            background-color: #ffffff;
            color: #000000;
            box-shadow: 0 0 15px rgba(255,255,255,0.5);
        }

        /* 手機版微調 */
        @media screen and (max-width: 480px) {
            .poster-container {
                height: 100vh; /* 手機上填滿整個螢幕 */
                max-width: 100%;
            }
            .main-title { font-size: 36px; }
        }
    </style>
</head>
<body>

    <div class="poster-container">
        <div class="overlay">
            
            <div class="reviews-section">
                <div class="review-item">
                    <span class="stars">★★★★★</span>
                    <div class="quote">"有了年輕新血的加入，讓團隊氣氛更為融洽了！"</div>
                </div>
                <div class="review-item">
                    <span class="stars">★★★★★</span>
                    <div class="quote">"打破刻板印象，很高興能成功獲取不同角度思維"</div>
                </div>
            </div>

            <div class="content-section">
                <div class="slogan">用Ｚ世代的眼睛，看見未來的商業契機</div>
                
                <h1 class="main-title">115 INKER</h1>
                <div class="sub-title">樹人實習名額搶先登記</div>

                <div class="info-details">
                    單位報名 <span class="highlight-red">115/01/08 - 01/22</span> &nbsp;|&nbsp; 
                    實習期間 <span class="highlight-white">暑假 7-9月</span><br>
                    招募期間 3-5月 &nbsp;|&nbsp; 
                    <span class="tag-box">特別說明</span> 實習生不佔原有員額
                </div>

                <a href="https://forms.gle/59GgxGZdz41LV6AW9" target="_blank" class="cta-button">
                    立即預約名額
                </a>
            </div>

        </div>
        </div>

</body>
</html>
