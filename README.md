# test<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Finndei Frame</title>
    <style>
        body {
            background-color: white;
            color: #333;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }

        h1 {
            text-align: center;
            font-size: 2rem;
            margin: 20px 0;
            color: #333;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f0f0f0;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
        }

        label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
            color: #333;
        }

        input[type="file"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: #fff;
            color: #333;
        }

        button {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #007acc;
            color: #fff;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
            margin-bottom: 10px; /* Thêm margin để tách nút tải xuống */
        }

        button:hover {
            background-color: #005f99;
        }

        .results img {
            max-width: 100%;
            margin-top: 20px;
            border-radius: 10px;
        }

        .results {
            text-align: center;
        }

        #download-btn { /* Style cho nút tải xuống */
            background-color: #4CAF50;
        }

        #download-btn:hover {
            background-color: #3e8e41;
        }
    </style>
</head>
<body>
    <h1>Finndei Frame</h1>
    <div class="container">
        <label for="upload-images">Tải ảnh lên:</label>
        <input type="file" id="upload-images" accept="image/*" multiple>

        <label for="upload-frames">Tải khung lên:</label>
        <input type="file" id="upload-frames" accept="image/*" multiple>

        <button id="render-btn">Xử lý ảnh</button>
        <button id="download-btn" style="display: none;">Tải xuống</button>

        <div class="results" id="results"></div>
    </div>

    <script>
        document.getElementById('render-btn').addEventListener('click', () => {
            // ... (Mã xử lý ảnh giữ nguyên) ...

            // Sau khi hiển thị ảnh kết quả, hiển thị nút tải xuống
            document.getElementById('download-btn').style.display = 'block';
        });

        document.getElementById('download-btn').addEventListener('click', () => {
            const resultImg = document.querySelector('.results img');
            if (resultImg) {
                const link = document.createElement('a');
                link.href = resultImg.src;
                link.download = 'framed_image.png'; // Tên file tải xuống
                link.click();
            }
        });

        // ... (Phần còn lại của mã JavaScript giữ nguyên) ...
    </script>
</body>
</html>
