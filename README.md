<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
    /* General styles */
    body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #f0f0f0;
        margin: 0;
        transition: background-color 0.5s, color 0.5s;
        overflow: hidden; /* Prevent scrolling on the body */
    }

    .container {
        background-color: white;
        padding: 30px;
        border-radius: 8px;
        box-shadow: 0 0 15px rgba(0,0,0,0.2);
        text-align: center;
        width: 100%;
        max-width: 1000px;
        transition: background-color 0.5s, color 0.5s;
        overflow-y: auto; /* Enable vertical scrolling */
        max-height: 90vh; /* Limit the height to fit in the viewport */
    }

    .container img {
        width: 160px;
        height: auto;
        margin-bottom: 10px;
        background-color: #fff;
        padding: 10px;
        border-radius: 8px;
    }

    .container h2, .container h1 {
        margin-bottom: 20px;
    }

    .container input {
        width: 100%;
        padding: 12px;
        margin: 12px 0;
        border: 1px solid #ccc;
        border-radius: 4px;
        box-sizing: border-box;
    }

    .container button {
        width: 100%;
        padding: 12px;
        background-color: #9f54d9;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        position: relative;
        overflow: hidden;
        transition: background-color 0.3s, transform 0.3s;
    }

    .container button:before,
    .container button:after,
    .container button .button_reflection-1,
    .container button .button_reflection-2,
    .container button .button_circle-2 {
        content: "";
        position: absolute;
        top: 0;
        bottom: 0;
        width: 100%;
        background: rgba(255, 255, 255, 0.3);
        transition: all 0.3s ease;
    }

    .container button:before {
        left: -120%;
        transform: skewX(-30deg);
    }

    .container button:after {
        left: 100%;
        transform: skewX(30deg);
    }

    .container button:hover:before {
        left: 100%;
    }

    .container button:hover:after {
        left: -100%;
    }

    .container button:hover {
        transform: rotate(-4deg) scale(1.1);
    }

    .container button .button_reflection-1 {
        left: 120%;
    }

    .container button .button_reflection-2 {
        left: -70%;
    }

    .container button:hover .button_circle-2 {
        transform: translate(-20px, 20px) scale(1.1);
    }

    .container button.button_diamond:hover {
        transform: translateY(7px) rotate(-24deg) scale(1.1);
    }

    .hidden {
        display: none;
    }

    .icon {
        width: 50px;
        height: 50px;
        cursor: pointer;
        margin-top: 20px;
    }

    .footer-text {
        margin-top: 20px;
        font-size: 16px;
        color: #888;
    }

    .contact-icons {
        margin-top: 10px;
    }

    .contact-icons a {
        display: inline-block;
        margin: 0 10px;
    }

    .contact-icons img {
        width: 30px;
        height: 30px;
    }

    .contact-message {
        font-size: 18px;
        color: black;
        margin-bottom: 10px;
    }

    body.dark-mode .contact-message {
        color: #f0f0f0;
    }

    body.dark-mode {
        background-color: #2c2c2c;
        color: #f0f0f0;
    }

    body.dark-mode .container {
        background-color: #3c3c3c;
        color: #f0f0f0;
    }

    body.dark-mode .container img {
        background-color: #3c3c3c;
    }

    body.dark-mode input {
        background-color: #5c5c5c;
        color: #f0f0f0;
        border: 1px solid #7c7c7c;
    }

    body.dark-mode .container button {
        background-color: #8c4aad;
    }

    body.dark-mode .container button:hover {
        background-color: #9f54d9;
    }

    .video-container {
        padding: 10px 0;
        position: relative;
        margin-bottom: 15px;
        text-align: center;
        max-height: 70vh; /* Limit the height to fit in the viewport */
        overflow: auto; /* Enable scrolling if content overflows */
    }

    .video-title {
        font-size: 17px;
        margin-bottom: 10px;
    }

    .video-container iframe {
        border-radius: 8px;
        width: 100%;
        height: auto;
        max-height: 100%;
    }

    .video-footer-text {
        margin-top: 5px;
        font-size: 16px;
        color: #888;
    }

    body.dark-mode .video-footer-text {
        color: #f0f0f0;
    }

    .theme-switch-wrapper {
        position: absolute;
        top: 20px;
        right: 20px;
        display: flex;
        align-items: center;
    }

    .theme-switch {
        display: none;
    }

    .theme-switch-label {
        display: flex;
        align-items: center;
        cursor: pointer;
    }

    .theme-switch-label .sun-icon,
    .theme-switch-label .moon-icon {
        font-size: 24px;
        transition: opacity 0.5s;
    }

    .theme-switch:checked + .theme-switch-label .sun-icon {
        opacity: 0;
    }

    .theme-switch:not(:checked) + .theme-switch-label .moon-icon {
        opacity: 0;
    }

    .menu-content {
        background-color: #2c2c2c;
        color: white;
        padding: 10px;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .menu-button {
        background-color: #4CAF50;
        color: white;
        border: none;
        padding: 10px 20px;
        cursor: pointer;
        border-radius: 4px;
        margin-bottom: 20px;
    }

    .menu-button:hover {
        background-color: #45a049;
    }

    .menu-content ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
    }

    .menu-content ul li {
        padding: 10px 15px;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .menu-content ul li:hover {
        background-color: #444;
        border-radius: 4px;
    }

    .user-info {
        display: flex;
        align-items: center;
        margin-bottom: 20px;
        padding: 10px;
        background-color: #f9f9f9;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    body.dark-mode .user-info {
        background-color: #444;
    }

    .user-info img {
        border-radius: 50%;
        width: 50px;
        height: 50px;
        margin-right: 15px;
    }

    .user-info p {
        margin: 0;
        font-size: 16px;
        font-weight: bold;
    }
</style>

</head>
<body>
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/G2dH87P/Clipped-image-20240718-232638.png" alt="Medal Image">
        <h2>The Process platform</h2>
        <input type="text" id="username" placeholder="Enter Username" onkeydown="handleEnterKey(event)">
        <button onclick="login()">Login</button>
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
            <a href="http://t.me/Mora_mo1" target="_blank" title="Telegram">
                <img src="https://i.ibb.co/9TGmH7c/cropped-image.png" alt="Telegram Icon">
            </a>
        </div>
        <p class="footer-text">Developed by Eng: Amr Mohamed</p>
    </div>

    <div class="container hidden" id="video-container">
        <div class="user-info">
            <img id="user-icon" src="" alt="User Icon">
            <p id="user-name">Username</p>
        </div>
        <img src="https://i.ibb.co/G2dH87P/Clipped-image-20240718-232638.png" alt="Medal Image" class="medallion">
        <h2 id="video-heading">The Process platform</h2>
        <button class="menu-button" onclick="document.getElementById('video-menu').classList.toggle('hidden')">Select Video</button>
        <div id="video-menu" class="menu-content hidden">
            <ul>
                <li onclick="showVideo('video1')">حصة التأهيل</li>
                
            </ul>
        </div>
        <div id="video1" class="video-container hidden">
    <h1 class="video-title">حصة التأهيل</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1mwmNKYtvwn318OhJEIC6nFOHnaOCr1ne/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    <iframe src="https://drive.google.com/file/d/16YuK8K7SUWaVGd_d1ac4Fo8PS1vl3Pls/preview" width="800" height="600" allow="autoplay" scrolling="no"></iframe>
</div>

        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
            <a href="http://t.me/Mora_mo1" target="_blank" title="Telegram">
                <img src="https://i.ibb.co/9TGmH7c/cropped-image.png" alt="Telegram Icon">
            </a>
        </div>
        <p class="video-footer-text">Developed by Eng: Amr Mohamed</p>
    </div>

    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch">
        <label class="theme-switch-label" for="theme-switch">
            <span class="moon-icon">🌚</span>
            <span class="sun-icon">🌞</span>
        </label>
    </div>

    <script>
        const userDetails = {
            '35598': { name: 'ادم عمرو', icon: 'https://api.multiavatar.com/Ebenezer%20Dimmsdale.svg' },
            '21451': { name: 'نور عبدالرحمن', icon: 'https://api.multiavatar.com/Bugzilla.svg' },
            '35958': { name: 'إيمان', icon: 'https://api.multiavatar.com/Avocado.svg' },
            '43297': { name: 'محمد ايهاب عبد الفتاح ', icon: 'https://api.multiavatar.com/Jean%20Valjean.svg' },
            '32011': { name: 'نيفين حمدي محمد', icon: 'https://api.multiavatar.com/Emma%20Watson.svg' },
            '74626': { name: 'رحمه ماجد', icon: 'https://api.multiavatar.com/Lucas.svg' },
            '45454': { name: 'teto', icon: 'https://api.multiavatar.com/Lucas.svg' },
            '87093': { name: 'حبيبه شعبان محمد', icon: 'https://api.multiavatar.com/Chris%20Evans.svg' },
            '42776': { name: 'عبدالرحمن شعبان', icon: 'https://api.multiavatar.com/Tony%20Stark.svg' },
            '57186': { name: 'حنين السيد سليمان', icon: 'https://api.multiavatar.com/Steve%20Rogers.svg' },
            '82910': { name: 'بسنت محمد', icon: 'https://api.multiavatar.com/Clark%20Kent.svg' },
            '73697': { name: 'عمر وليد جمال', icon: 'https://api.multiavatar.com/Peter%20Parker.svg' },
            '45043': { name: 'عبدالله احمد محمود', icon: 'https://api.multiavatar.com/Wade%20Wilson.svg' },
            '42601': { name: 'حاتم امين محمد', icon: 'https://api.multiavatar.com/Leonardo%20DiCaprio.svg' }
        };

        const activeUsers = {}; // Define activeUsers

        function login() {
            const username = document.getElementById('username').value.trim();
            const videoHeading = document.getElementById('video-heading');
            const userIcon = document.getElementById('user-icon');
            const userName = document.getElementById('user-name');

            if (username === '') {
                alert('Please enter a username.');
                return;
            }

            if (userDetails[username]) {
                if (Object.keys(activeUsers).length > 0) {
                    alert('Another user is already logged in. Please log out first.');
                    return;
                }

                activeUsers[username] = true;
                document.getElementById('login-container').classList.add('hidden');
                document.getElementById('video-container').classList.remove('hidden');

                const userDetail = userDetails[username];
                videoHeading.innerHTML = 'The Process platform';
                userIcon.src = userDetail.icon;  // Set user's icon
                userName.textContent = userDetail.name;  // Set user's name
            } else {
                alert('Invalid username');
            }
        }

        function handleEnterKey(event) {
            if (event.key === 'Enter') {
                login();
            }
        }

        function showVideo(videoId) {
            document.querySelectorAll('.video-container').forEach(video => {
                video.classList.add('hidden');
            });
            document.getElementById(videoId).classList.remove('hidden');
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
        }

        document.getElementById('theme-switch').addEventListener('change', toggleDarkMode);
    </script>

