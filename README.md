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
    background-color: #302967; /* Updated background color */
    margin: 0;
    transition: background-color 0.5s, color 0.5s;
    overflow: hidden; /* Prevent scrolling on the body */
}
{
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
    max-height: 200px; /* Set the maximum height of the menu */
    overflow-y: auto;  /* Enable vertical scrolling */
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
        <input type="password" id="username" placeholder="Enter Username" onkeydown="handleEnterKey(event)">
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
        <li onclick="showVideo('video2')">حل واجب حصة 1</li>
        <li onclick="showVideo('video3')">حل واجب حصة 2</li>
        <li onclick="showVideo('video4')">باقي حل اسئلة حصة 2</li>
        <li onclick="showVideo('video5')">حل واجب حصة 3</li>
        <li onclick="showVideo('video6')">حل واجب حصة 4</li>
        <li onclick="showVideo('video7')">شرح حصة 4 (سنتر)</li>
        <li onclick="showVideo('video8')">مراجعة على الفصل الاول</li>
        <li onclick="showVideo('video9')">حل واجب حصة 5</li>
        <li onclick="showVideo('video10')">تدريبات الدرس الاول </li>
        <li onclick="showVideo('video11')">تدريبات الدرس الثاني </li>
        <li onclick="showVideo('video12')">تدريبات الدرس الثالث </li>
        <li onclick="showVideo('video13')">تدريبات الدرس الرابع </li>
        <li onclick="showVideo('video14')">حل واجب حصة 6 </li>
        <li onclick="showVideo('video15')">حل واجب حصة 7 </li>
        <li onclick="showVideo('video16')">حل واجب حصة 8 </li>
        <li onclick="showVideo('video17')">حل واجب حصة 9 </li>
        <li onclick="showVideo('video18')">حل واجب حصة 10 </li>
        <li onclick="showVideo('video19')">حل واجب حصة 11 </li>
        <li onclick="showVideo('video20')">حل واجب حصة 12 </li>



    </ul>
</div>
<div id="video1" class="video-container hidden">
    <h1 class="video-title">حصة التأهيل</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1mwmNKYtvwn318OhJEIC6nFOHnaOCr1ne/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
</div>
<div id="video2" class="video-container hidden">
    <h1 class="video-title">حل واجب حصة 1</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1k03hdmxGtL6Vfd9O-cxuywaVrINwdJJp/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    <iframe src="https://drive.google.com/file/d/1G3Oq-lDSpLcnaCRyLgd7x0CcamC-rjBY/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video3" class="video-container hidden">
    <h1 class="video-title">حل واجب حصة 2</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1Y0s1hTTgV-8drqiN_05yVOM6NiKvb2x2/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    <iframe src="https://drive.google.com/file/d/1HdGZJTZ4SDURmuIaEZyMLqLrzNuvpqPP/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video4" class="video-container hidden">
    <h1 class="video-title">باقي حل اسئلة حصة 2</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1Awo0t3OaoAwpESJCJG56MED6dZEXrsZ7/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    
</div>
<div id="video5" class="video-container hidden">
    <h1 class="video-title">حل واجب حصة 3 (part1)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/12bMN-bgiBlK9uMKfHmqa8tDE8jKgo0E_/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    <h1 class="video-title">حل واجب حصة 3 (part2)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;">
        <iframe src="https://drive.google.com/file/d/1x9PSxhLsS4nuh7VyiwAU9O5F-vtHz9Pe/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
        <h1 class="video-title">الاجابات</h1>

    <iframe src="https://drive.google.com/file/d/1IQginzp4eLmf-vZStHctMx4qoR9cVwSt/preview" width="640" height="480" allow="autoplay"></iframe>
  </div>
  
  
  <div id="video6" class="video-container hidden">
  
    <h1 class="video-title">حل واجب حصة 4 (part1)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Sypz3MCjVIdFTSaG9-0zXTPRNwREZ2cN/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
    <h1 class="video-title">حل واجب حصة 4 (part2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Z-5eAdOYtZEz-g3u2k81Wf68AZFqCbLD/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
    <h1 class="video-title">حل واجب حصة 4 (part3)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1tNf7NtlcBJUkk7bF8U3asxfzWmwZGwUt/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
        <h1 class="video-title">الاجابات</h1>

<iframe src="https://drive.google.com/file/d/13bAtoKJj-2I6BiLz13gAupFPk5hlYqd7/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video7" class="video-container hidden">
    <h1 class="video-title">شرح حصة 4 (part1)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1-VIltXMBLLQNwbVbwhTHO2ovmYSsT0wU/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
    <h1 class="video-title">شرح حصة 4 (part)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/15Mo7htyDhT7f9Beu9TwCiIMuxGO-dNRc/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
</div>
   <div id="video8" class="video-container hidden">
    <h1 class="video-title">مراجعة على الفصل الاول (part1)</h1>
    <script src="https://fast.wistia.com/embed/medias/g9naj7rxz9.jsonp" async></script><script src="https://fast.wistia.com/assets/external/E-v1.js" async></script><div class="wistia_responsive_padding" style="padding:60.0% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_g9naj7rxz9 seo=true videoFoam=true" style="height:100%;position:relative;width:100%"><div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;"><img src="https://fast.wistia.com/embed/medias/g9naj7rxz9/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" /></div></div></div></div>
  
       <h1 class="video-title">مراجعة على الفصل الاول (part2)</h1>
       <script src="https://fast.wistia.com/embed/medias/am7s6g2d3y.jsonp" async></script><script src="https://fast.wistia.com/assets/external/E-v1.js" async></script><div class="wistia_responsive_padding" style="padding:60.0% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_am7s6g2d3y seo=true videoFoam=true" style="height:100%;position:relative;width:100%"><div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;"><img src="https://fast.wistia.com/embed/medias/am7s6g2d3y/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" /></div></div></div></div>
          <h1 class="video-title">شرح كيرشوف</h1>
          <script src="https://fast.wistia.com/embed/medias/9ewjx7dlc4.jsonp" async></script><script src="https://fast.wistia.com/assets/external/E-v1.js" async></script><div class="wistia_responsive_padding" style="padding:60.0% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_9ewjx7dlc4 seo=true videoFoam=true" style="height:100%;position:relative;width:100%"><div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;"><img src="https://fast.wistia.com/embed/medias/9ewjx7dlc4/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" /></div></div></div></div>
</div>
  
   
<div id="video9" class="video-container hidden">
    <h1 class="video-title">حل واجب حصة 5 </h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/122NLtPEJMa1YCiUa-Y89Ro-W8AwwF6k_/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
        <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1xzD3Ruv20pJw8zJ9ah75Ryg9EjpwPq0e/preview" width="640" height="480" allow="autoplay"></iframe>   
   </div>
   
   <div id="video10" class="video-container hidden">
    <h1 class="video-title">تدريبات الدرس الاول part 1 </h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/16t3A4UF-VpZVnrw9ddR8M-unHtgY7Vb2/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">تدريبات الدرس الاول part 2 </h1>
        <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/12ZoKSUMdDLrRzH9TqJwWG6do7vWIxwA5/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
        </div>
        </div>
<div id="video11" class="video-container hidden">
    <h1 class="video-title">تدريبات الدرس ثاني </h1>
   <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/13K5pRTKJurRmXFpcD18-wbZLGNSLdZor/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
   </div>
      </div>
<div id="video12" class="video-container hidden">
    <h1 class="video-title">تدريبات الدرس الثالث </h1>
   <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1-RNGfZ0kxFiwSlTBcC6Kl6AFD_tNegoM/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
   </div>
         </div>
        
   <div id="video13" class="video-container hidden">
    <h1 class="video-title">تدريبات الدرس الرابع part 1 </h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1RDXJMFgrU5jgTyHr5s6KRrCQJ1rgA99r/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
       <h1 class="video-title">تدريبات الدرس الرابع part 2 </h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1myy8xQ2gSvSoBreZK1DfpmzDQGqXVF-i/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
   </div>

   <div id="video14" class="video-container hidden">
    <h1 class="video-title">حل واجب حصة 6 (part1)</h1>
    <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1oB4cYVmLvZwYT1kzkHWp4B1IgWh4Lw3Q/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
    </div>
        <h1 class="video-title">حل واجب حصة 6 (part2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1Cg7qYRF0weN2lGt1g4646I1a5kYvOheT/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
       <h1 class="video-title">حل واجب حصة 6 (part3)</h1>
       <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1-RTnIp68sHw7U5m1TiAXviWh_1nOfgMf/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">الاجابات</h1>
   <iframe src="https://drive.google.com/file/d/1hg11yXNrmuVlkg3yBKqj4MftUQffBQqS/preview" width="640" height="480" allow="autoplay"></iframe>
   </div>
  
  
   <div id="video15" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 7 (part1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1fdjCqGTXWbeY1i9Bdu9qsipZC6jn22jX/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
             <h1 class="video-title">حل واجب حصة 7 (part2)</h1>
             <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1kQZrgRazZbjfc1Avn7252Xj_ftoIlsPi/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
             </div>
        <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1AybPqTYHCz_KkaZtQrz0ggvLUiLv9zx2/preview" width="640" height="480" allow="autoplay"></iframe>   
</div>


<div id="video16" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 8 (part1)</h1>
          <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1_HrbQ1CJDyy5cn3TGRVCEP9oqWxkAGMT/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title"> (part2)</h1>
          <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1YMmcl1NqIdJBvxVacbJsmLt-sYTiAPU3/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title"> (part3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1lNSmM5bKHzRqpvCD69i7YJR8a5mBszyp/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1P0avXQpoAZxMtSIn_OmxyMAUj6RfS3Di/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video17" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 9 (part1)</h1>
          <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1R_DTAyxvhT32iXqgzDJFHQvhTVLum9xE/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title">حل واجب حصة 9 (part2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1dQavkTyXAUAd3YSVJDm57AV_9iyn5TNh/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1dViunIRkzBj6muMwDSXFFa9OaleE0Rhm/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video18" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 10 (part1)</h1>
          <div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1NdOZGwMEhd6EjhJZTd-NL0Upl413333o/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title">حل واجب حصة 10 (part1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1MWaJdpHWnkPQLSyoRB82N2TDXSrxJg8J/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe>
</div>
<iframe src="https://drive.google.com/file/d/1m6UiJEUFayb4isIx-Gpx21kqV2frBUoe/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video19" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 11 (part1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1akDAjOT_IVE2FC9RsHe9KxpXpl1bMzln/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title">حل واجب حصة 11 (part2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1itxxX0LU8-wpk3DO98xwfyjpN0VkgBK-/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">الاجابات</h1>
<iframe src="https://drive.google.com/file/d/1OAwwqU4w-4sP5el529mIno_R7JyIcWvD/preview" width="640" height="480" allow="autoplay"></iframe>
</div>
<div id="video20" class="video-container hidden">
          <h1 class="video-title">حل واجب حصة 12 (part1)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1r91rnCm-4EZi8mRd2JOAVVyEAv_99bC7/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title">حل واجب حصة 12 (part2)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/1MKYgXDJOUhBP1clU20frZRjduEefZt98/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
          <h1 class="video-title">حل واجب حصة 12 (part3)</h1>
<div style="left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.25%;"><iframe src="https://drive.google.com/file/d/15NnMk6KQQd-4G_JaeUt_QDfIIhNColjo/preview" style="top: 0; left: 0; width: 100%; height: 100%; position: absolute; border: 0;" allowfullscreen scrolling="no" allow="encrypted-media;"></iframe></div>
        <h1 class="video-title">الاجابات</h1>
        <iframe src="https://drive.google.com/file/d/1dAHdV5eZ6jM1VvM8J5QveD_XpTtkTTUk/preview" width="640" height="480" allow="autoplay"></iframe>
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
            'mora': { name: 'administrator', icon: 'https://ibb.co/MMzym0Y'},
            
            '86554o': { name: 'الاء محمود محمد', icon: 'https://api.multiavatar.com/155a84d30e3e3cca7e.svg '},       
            '48261': { name: 'زياد احمد يوسف', icon: 'https://api.multiavatar.com/12ac8e37b20a4556f1.svg'},
            '75934': { name: 'ضي عبدالعليم', icon: 'https://api.multiavatar.com/54c54768ceb0c3f83a.svg'},
            '21687': { name: 'روان إيهاب', icon: 'https://api.multiavatar.com/155a84d30e3e3cca7e.svg'},
            '39472': { name: 'محمد عبدالعظيم', icon: 'https://api.multiavatar.com/147b5eefb657e22dc2.svg'},
            '58210o': { name: 'سلمى وائل', icon: 'https://api.multiavatar.com/95bf4a24efb7c2748c.svg'},
            '70493o': { name: 'فيروز محمد', icon: 'https://api.multiavatar.com/59e284ef4c6c59b44b.svg'},
            '13856o': { name: 'نورهان محمد', icon: 'https://api.multiavatar.com/d6698e2ee87a543c08.svg'},
            '23849o': { name: 'فرح عماد', icon: 'https://api.multiavatar.com/5d1715c8c5266ef8fa.svg'},
            '94720o': { name: 'سندس محمد', icon: 'https://api.multiavatar.com/19b4a93ea61f0b650e.svg'},
            '58391': { name: 'ملك محمد', icon: 'https://api.multiavatar.com/2422f12d6e1bb1d40b.svg'},
            '62047o': { name: 'منه الله جمال', icon: 'https://api.multiavatar.com/12de69a625c83e5ca8.svg'},
            '86284o': { name: 'حبيبية شعبان', icon: 'https://api.multiavatar.com/1eae35ecc479f6edd1.svg'},
            '49696': { name: 'ادم عمرو', icon: 'https://api.multiavatar.com/f84f24bcc7b72eebf0.svg' },
            '81659': { name: 'نور عبدالرحمن', icon: 'https://api.multiavatar.com/20ba7ccc9a755d9743.svg' },
            '10781': { name: 'ياسمين السيد', icon: 'https://api.multiavatar.com/2422f12d6e1bb1d40b.svg' },
            '44889': { name: 'محمد سليم', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg' },
            '39639': { name: 'ايمان محمد ', icon: 'https://api.multiavatar.com/e736fdd76d2f8bb555.svg' },
            '29474': { name: 'محمد ايهاب عبد الفتاح ', icon: 'https://api.multiavatar.com/7995823da6025e8a33.svg' },
            '95731': { name: 'رودينا محمد نصر', icon: 'https://api.multiavatar.com/e736fdd76d2f8bb555.svg' },
            '86074o': { name: 'نيفين حمدي محمد', icon: 'https://api.multiavatar.com/12de69a625c83e5ca8.svg' },
            '30693': { name: 'رحمه ماجد', icon: 'https://api.multiavatar.com/1eae35ecc479f6edd1.svg' },
            '99'   : { name: 'teto', icon: 'https://api.multiavatar.com/Lucas.svg' },
            '41715': { name: 'احمد حسام', icon: 'https://api.multiavatar.com/Guadalajara.svg' },
            '58471': { name: 'عبدالرحمن شعبان', icon: 'https://api.multiavatar.com/ba66683f68073901ea.svg' },
            '18054': { name: 'حنين السيد سليمان', icon: 'https://api.multiavatar.com/9b8b2ae7d917ccd9ce.svg' },
            '20321o': { name: 'بسنت محمد', icon: 'https://api.multiavatar.com/240315fc1890fd05ae.svg' },
            '73349': { name: 'محمود هشام', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg' },
            '64561o': { name: 'ايه محمد نادي', icon: 'https://api.multiavatar.com/1eae35ecc479f6edd1.svg' },
            '46721o': { name: 'ياسمين احمد محمود', icon: 'https://api.multiavatar.com/19b4a93ea61f0b650e.svg'},
            '37144': { name: 'عبدالله احمد صلاح', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg' },
             '47916': { name: 'عبدالله احمد محمود', icon: 'https://api.multiavatar.com/94a0dd6577ca3c7291.svg' },



            '55844': { name: 'eng.tarek saeed', icon: 'https://api.multiavatar.com/9b8b2ae7d917ccd9ce.svg' },
            '52182': { name: 'عمر وليد جمال', icon: 'https://api.multiavatar.com/4db29acccc604fe610.svg' }
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

                // Replace numeric username with a placeholder or masked string
                document.getElementById('username').value = '********'; 
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
