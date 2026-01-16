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
            background-color: #1a1a1a;
            font-family: 'Noto Serif TC', serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        /* 海報主容器 */
        .poster-container {
            width: 100%;
            max-width: 600px;
            /* 這裡設定高度為視窗高度，確保在手機上是滿版的 */
            height: 100vh; 
            max-height: 900px; /* 電腦版不要太長 */
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 30px rgba(0,0,0,0.5);
            
            /* 背景圖設定 */
            background-image: url('https://images.pexels.com/photos/7972555/pexels-photo-7972555.jpeg');
            background-size: cover;
            background-position: center bottom;
            background-color: #333;
        }

        /* 漸層遮罩 */
        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            /* 調整漸層濃度，讓文字更清楚 */
            background: linear-gradient(to top, rgba(0,0,0,0.9) 15%, rgba(0,0,0,0.5) 50%, rgba(0,0,0,0.2) 100%);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            padding: 40px 20px;
            box-sizing: border-box;
        }

        /* 頂部評價區 */
        .reviews-section {
            text-align: center;
            margin-top: 4vh; /* 使用 vh 單位，隨螢幕高度自動調整位置 */
            text-shadow: 0 2px 4px rgba(0,0,0,0.8);
        }
        .review-item {
            margin-bottom: 2vh;
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

        /* 底部資訊區 */
        .content-section {
            text-align: center;
            margin-bottom: 20px;
            width: 100%;
        }

        /* Slogan - 關鍵修改：強制不換行 */
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
            white-space: nowrap; /* 這行讓字死都不准換行 */
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
            white-space: nowrap; /* 標題也不准換行 */
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

        /* 🔴 針對手機螢幕的 RWD 自動縮放修正 */
        @media screen and (max-width: 480px) {
            .poster-container {
                height: 100vh; /* 手機上填滿全螢幕 */
                max-height: none;
                border-radius: 0;
            }
            
            /* 字體縮小，防止折行 */
            .slogan {
                font-size: 12px; /* 字變小 */
                letter-spacing: 1px; /* 間距變小 */
                width: 100%; /* 確保寬度足夠 */
                border-bottom: 1px solid rgba(255,255,255,0.3);
            }
            
            .main-title {
                font-size: 36px; /* 標題縮小 */
                letter-spacing: 2px;
            }
            
            .sub-title {
                font-size: 14px;
            }
            
            .info-details {
                font-size: 11px; /* 資訊字體縮小 */
            }
            
            .cta-button {
                width: 70%; /* 按鈕在手機上寬一點比較好按 */
                padding: 12px 0;
                text-align: center;
            }
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
