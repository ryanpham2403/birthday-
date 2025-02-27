<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quà Sinh Nhật</title>
    <style>
        body {
            text-align: center;
            background: url('https://i.postimg.cc/DfrN8nw1/Form-Titelbild-Logo-1.png') no-repeat center center;
            background-size: cover;
            font-family: Arial, sans-serif;
            color: black;
            margin: 0;
            padding: 0;
        }
        .container {
            margin-top: 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
        }
        .gift-button {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 5px;
            margin: 5px;
            cursor: pointer;
            border-radius: 10px;
            width: 60px;
            height: 60px;
            font-size: 16px;
            font-weight: bold;
        }
        #result {
            margin-top: 10px;
            font-size: 24px;
            font-weight: bold;
        }
        .gift-container {
            margin-top: 10px;
        }
        .gift-container img {
            max-width: 200px;
            margin-top: 5px;
        }
    </style>
</head>
<body>
    <h1>Quà Sinh Nhật</h1>
    <div class="container" id="buttons-container"></div>
    <div id="result">Phần thưởng sẽ hiện ở đây</div>
    <div class="gift-container" id="gift-container"></div>
    
    <script>
        const gifts = ["USB", "Sạc dự phòng", "loa bluetooth", "Dây nhảy", "Vớ thể thao", "Vợt cầu lông", "Bìa hộ chiếu", "Túi đựng đồ cá nhân", "Thẻ cá nhân", "Dấu sách", "Đèn kẹp bàn", "Sổ ghi chú"];
        const giftImages = [
            "https://i.imgur.com/UioyyID.jpg", "https://i.imgur.com/new_image_1.jpg", "https://example.com/banh_kem.jpg",
            "https://example.com/voucher.jpg", "https://example.com/du_lich.jpg", "https://example.com/dong_ho.jpg",
            "https://example.com/laptop.jpg", "https://example.com/tai_nghe.jpg", "https://example.com/dien_thoai.jpg",
            "https://example.com/sach.jpg", "https://example.com/balo.jpg", "https://example.com/but_ky.jpg"
        ];
        
        function createButtons() {
            const container = document.getElementById('buttons-container');
            for (let i = 0; i < 12; i++) {
                let btn = document.createElement('button');
                btn.className = 'gift-button';
                btn.innerText = i + 1;
                btn.onclick = function () { revealGift(i); };
                container.appendChild(btn);
            }
        }
        
        function revealGift(index) {
            const result = document.getElementById('result');
            const giftContainer = document.getElementById('gift-container');
            
            result.innerText = "🎁 Bạn nhận được: " + gifts[index] + "!";
            giftContainer.innerHTML = `<a href="${giftImages[index]}" target="_blank">
                                           <img src="${giftImages[index]}" alt="${gifts[index]}">
                                       </a>`;
        }
        
        createButtons();
    </script>
</body>
</html>
