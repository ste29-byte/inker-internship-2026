<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>115 Inker Internship</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700;900&family=Playfair+Display:ital,wght@1,500&display=swap" rel="stylesheet">
    <style>
        /* 全域背景設定 */
        body {
            margin: 0;
            padding: 0;
            background-color: #1a1a1a; /* 網頁深色背景 */
            font-family: 'Noto Serif TC', serif;
            
            /* 讓海報在電腦螢幕正中間 */
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        /* 海報容器 - 電腦版設定 */
        .poster-container {
            width: 100%;
            max-width: 600px;  /* 鎖定寬度 */
            height: 800px;     /* 🔴 關鍵修改：鎖定高度 800px，恢復海報原本比例 */
            
            position: relative;
            overflow: hidden;
            background-color: #333;
            box-shadow: 0 0 40px rgba(0,0,0,0.7); /* 加強陰影，讓它像懸浮的卡片 */
            
            /* 背景圖設定 */
            background-image: url('https://images.pexels.com/photos/7972555/pexels-photo-7972555.jpeg');
            background-size: cover;
            background-position: center bottom;
        }

        /* 漸層遮罩 */
        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            /* 調整漸層，讓底部文字更清楚 */
            background: linear-gradient(to top, rgba(0,0,0,0.9) 15%, rgba(0,0,0,0.5) 50%, rgba(0,0,0,0.2) 100%);
            
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 40px 20px;
            box-sizing: border-box;
        }

        /* 上方評價區 */
        .reviews-section {
            text-align: center;
            margin-top: 30px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.8);
        }
        .review-item {
            margin-bottom: 20px;
        }
        .stars {
            color: #ffd700;
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

        /* 下方內容區 */
        .content-section {
            text-align: center;
            margin-bottom: 20px;
            width: 100%;
        }

        /* Slogan - 強制不換行 */
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
            white-space: nowrap; 
        }

        /* 主標題 */
        .main-title {
            color: #ffffff;
            font-size: 46px;
            font-weight: 900;
            margin: 0;
            line-height: 1.1;
            letter-spacing: 4px;
            text-transform: uppercase;
            text-shadow: 0 0 20px rgba(0,0,0,0.8);
            white-space: nowrap;
        }
        .sub-title {
            color: #dddddd;
            font-size: 18px;
            letter-spacing: 4px;
            margin-top: 5px;
            margin-bottom: 25px;
            font-weight: 400;
        }

        /* 資訊區塊 */
        .info-details {
            font-family: Arial, sans-serif;
            color: #aaaaaa;
            font-size: 13px;
            line-height: 1.8;
            letter-spacing: 1px;
            margin-bottom: 30px;
            text-transform: uppercase;
        }
        .highlight-red { color: #ff6b6b; font-weight: bold; }
        .highlight-white { color: #ffffff; font-weight: bold; }
        .tag-box {
            border: 1px solid #999;
            padding: 1px 5px;
            font-size: 11px;
            border-radius: 2px;
            color: #ccc;
            margin-right: 5px;
        }

        /* 按鈕 */
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
            backdrop-filter: blur(4px);
        }
        .cta-button:hover {
            background-color: #ffffff;
            color: #000000;
        }

        /* 🔴 手機版專用設定 (RWD) */
        /* 只有當螢幕寬度小於 600px 時，才會執行這裡的程式碼 */
        @media screen and (max-width: 600px) {
            .poster-container {
                height: 100vh; /* 手機上才填滿全螢幕 */
                border-radius: 0;
            }
            body {
                align-items: flex-start; /* 手機上靠上對齊 */
            }
            
            /* 手機字體微調 */
            .main-title { font-size: 38px; }
            .slogan { font-size: 13px; }
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
                    單位報名 <span class="highlight-red">115/01/19 - 02/05</span> &nbsp;|&nbsp; 
                    實習期間 <span class="highlight-white">暑假 7-9月</span><br>
                    招募期間 3-5月 &nbsp;|&nbsp; 
                    <span class="tag-box">特別說明</span> 實習生不佔員額
                </div>

                <a href="https://forms.gle/59GgxGZdz41LV6AW9" target="_blank" class="cta-button">
                    立即預約名額
                </a>
            </div>

        </div>
    </div>

</body>
</html>
