<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Nasim Ahmad Personal</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {font-family: Arial, sans-serif; background: #f9f9f9; color: #222;}
        .container {max-width: 600px; margin: 40px auto; background: #fff; padding: 24px; border-radius: 12px; box-shadow: 0 2px 12px #ccc;}
        h1 {text-align: center; color: #333;}
        .social-links a {margin: 0 10px; text-decoration: none;}
        .section {margin: 24px 0;}
        label {display: block; margin-top: 12px;}
        input, textarea {width: 100%; padding: 8px; margin-top: 4px;}
        .media-list img, .media-list video {max-width: 100%; margin: 10px 0;}
        .media-list {margin-top: 10px;}
    </style>
</head>
<body>
<div class="container">
    <h1>Nasim Ahmad Personal</h1>
    <div class="section">
        <strong>WhatsApp:</strong> <a href="https://wa.me/YourNumberHere" target="_blank">Your WhatsApp Number</a><br>
        <strong>Facebook:</strong> <a href="https://facebook.com/YourFacebookID" target="_blank">Your Facebook</a><br>
        <strong>Instagram:</strong> <a href="https://instagram.com/YourInstagramID" target="_blank">Your Instagram</a><br>
        <strong>Email:</strong> <a href="mailto:your.email@gmail.com">your.email@gmail.com</a>
    </div>

    <div class="section">
        <h2>Upload Photo or Video</h2>
        <input type="file" id="mediaInput" accept="image/*,video/*" multiple>
        <div class="media-list" id="mediaList"></div>
    </div>

    <div class="section">
        <h2>Soch (Thoughts)</h2>
        <textarea id="sochInput" placeholder="Apni soch likhein..." rows="4"></textarea>
        <button onclick="addSoch()">Text Karain</button>
        <div id="sochList"></div>
    </div>
</div>
<script>
    // Display uploaded photos/videos (local only)
    document.getElementById('mediaInput').addEventListener('change', function(event) {
        const list = document.getElementById('mediaList');
        list.innerHTML = '';
        Array.from(event.target.files).forEach(file => {
            const url = URL.createObjectURL(file);
            if (file.type.startsWith('image/')) {
                const img = document.createElement('img');
                img.src = url;
                list.appendChild(img);
            } else if (file.type.startsWith('video/')) {
                const video = document.createElement('video');
                video.src = url;
                video.controls = true;
                list.appendChild(video);
            }
        });
    });

    // Add "soch" text
    function addSoch() {
        const input = document.getElementById('sochInput');
        const list = document.getElementById('sochList');
        if (input.value.trim()) {
            const p = document.createElement('p');
            p.textContent = input.value;
            list.prepend(p);
            input.value = '';
        }
    }
</script>
</body>
</html>
