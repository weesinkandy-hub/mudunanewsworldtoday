<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Muduna News | මුදුන පුවත්</title>
    <style>
        /* මූලික සැකසුම් */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        /* Header කොටස */
        header {
            background-color: #ffffff;
            border-bottom: 4px solid #cc0000; /* Red line */
            padding: 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo-area {
            display: flex;
            align-items: center;
        }

        .logo-area img {
            height: 60px; /* ලෝගෝ එකේ ප්‍රමාණය */
            margin-right: 15px;
        }

        .site-title {
            color: #003366; /* Blue color */
            margin: 0;
            font-size: 32px;
            font-weight: bold;
            text-transform: uppercase;
        }

        /* Navigation Bar */
        nav {
            background-color: #003366; /* Deep Blue */
            color: white;
            padding: 10px 0;
            text-align: center;
            position: sticky;
            top: 0;
        }

        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 20px;
            font-weight: bold;
        }

        nav a:hover {
            background-color: #cc0000; /* Red hover */
        }

        /* ප්‍රධාන පුවත් සැකසුම */
        .container {
            max-width: 1200px;
            margin: 20px auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            padding: 0 15px;
        }

        .news-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: 0.3s;
        }

        .news-card:hover {
            transform: translateY(-5px);
        }

        .news-image {
            width: 100%;
            height: 200px;
            background-color: #ddd;
            object-fit: cover;
        }

        .news-content {
            padding: 15px;
        }

        .news-tag {
            background-color: #cc0000;
            color: white;
            padding: 3px 8px;
            font-size: 12px;
            border-radius: 3px;
        }

        .news-title {
            font-size: 18px;
            color: #003366;
            margin: 10px 0;
            line-height: 1.4;
        }

        /* Read More Button */
        .read-more {
            display: inline-block;
            margin-top: 10px;
            padding: 8px 15px;
            background-color: #003366;
            color: rgb(255, 255, 255);
            text-decoration: none;
            border-radius: 5px;
            font-size: 14px;
            transition: background 0.3s;
        }

        .read-more:hover {
            background-color: #cc0000;
        }

        footer {
            background: #222;
            color: white;
            text-align: center;
            padding: 20px;
            margin-top: 40px;
        }
    </style>
<div class="derana-final-bar">
    
    <div class="bar-logo-section">
        <span class="m-box">M</span>UDUNA
    </div>

    <div class="bar-category" id="barCategory">
        <span id="barCategoryText">දේශීය</span>
        <div class="shine-effect"></div>
    </div>

    <div class="bar-news-area">
        <a href="#" id="newsLink" class="news-link-wrapper">
            <div id="barNewsText" class="slide-up-news">පුවත් පූරණය වෙමින් පවතී...</div>
        </a>
    </div>

    <div class="bar-time" id="barClock">00:00:00</div>
</div>

<style>
    .derana-final-bar {
        position: fixed;
        bottom: 15px;
        left: 50%;
        transform: translateX(-50%);
        width: 95%;
        max-width: 1200px;
        height: 50px;
        background: rgba(0, 0, 0, 0.9);
        backdrop-filter: blur(10px);
        display: flex;
        align-items: center;
        border-radius: 5px; /* පොඩ්ඩක් Square ස්ටයිල් එකට */
        border-left: 5px solid #cc0000;
        box-shadow: 0 5px 20px rgba(0,0,0,0.5);
        z-index: 10000;
        overflow: hidden;
        font-family: 'Segoe UI', sans-serif;
    }

    /* Logo Section */
    .bar-logo-section {
        background: #222;
        color: white;
        height: 100%;
        display: flex;
        align-items: center;
        padding: 0 15px;
        font-weight: 900;
        font-size: 14px;
        letter-spacing: 1px;
    }

    .m-box {
        background: #cc0000;
        padding: 0 5px;
        margin-right: 3px;
    }

    /* Category Label */
    .bar-category {
        height: 100%;
        min-width: 110px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        font-weight: bold;
        font-size: 14px;
        position: relative;
        transition: 0.5s;
    }

    .shine-effect {
        position: absolute;
        top: 0; left: -100%;
        width: 100%; height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
        animation: shineLoop 3s infinite;
    }

    @keyframes shineLoop { 0% { left: -100%; } 100% { left: 100%; } }

    /* News Link Area */
    .bar-news-area {
        flex: 1;
        overflow: hidden;
        padding: 0 20px;
    }

    .news-link-wrapper {
        text-decoration: none;
        color: white;
        display: block;
        width: 100%;
    }

    .slide-up-news {
        font-size: 17px;
        font-weight: 500;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
    }

    .news-link-wrapper:hover .slide-up-news {
        color: #ffd700; /* Hover කළ විට රන්වන් පැහැ වේ */
        text-decoration: underline;
    }

    /* Animation */
    .anim-up { animation: barUp 0.5s ease-out forwards; }
    @keyframes barUp { 0% { transform: translateY(20px); opacity: 0; } 100% { transform: translateY(0); opacity: 1; } }

    /* Time Section */
    .bar-time {
        background: #333;
        height: 100%;
        padding: 0 15px;
        display: flex;
        align-items: center;
        color: #aaa;
        font-size: 13px;
        font-family: monospace;
    }

    /* Category Colors */
    .local { background: #cc0000; }
    .sport { background: #28a745; }
    .world { background: #8b0000; }
    .weather { background: #007bff; }
</style>

<script>
    // පුවත් දත්ත (Link එක සහිතව)
    const finalNewsData = [
        { label: "දේශීය", color: "local", text: "ඉරාන විදෙස් ඇමෙතිගෙන් ශ්‍රි ලංකාව පිළිබද පැසසුම්", },
        { label: "දේශීය", color: "local", text: "අද සිට ඉන්ධන QR ක්‍රමවේදය ඔස්සේ.", },
        { label: "දේශීය", color: "local", text: "මාරක අනතුරු දෙකකින් පුද්ගලයන් දෙදෙනෙකුට දිවි අහිමි වෙයි!",},
        { label: "දේශීය", color: "local", text: "මත් ජාවාරම්කරුවෙකුගේ දේපළ ක්‍රියා විරහිත කෙරේ",},
        { label: "දේශීය", color: "local", text: "හෙද හෙදියන් 43,553 දෙනෙකු මෙරට සෞඛ්‍ය සේවයේ ",}, 
        { label: "ක්‍රීඩා", color: "sport", text: "බංගලාදේශය සමඟ පැවැති දෙවන එක්දින ක්‍රිකට් තරගයේදී පාකිස්තාන පිතිකරු සල්මන් අලි අගා අන්තර්ජාතික ක්‍රිකට් කවුන්සිලයේ චර්යාධර්ම සංග්‍රහයේ පළමු මට්ටම උල්ලංඝනය කර තිබේ.",},
        { label: "ක්‍රීඩා", color: "sport", text: "පාකිස්තාන ක්‍රීඩක සල්මන් අලි අගාව බංග්ලාදේශ නායක මෙහිදි හසන් මිරාස් විසින් දුවද්දී දවාගැනීමට ලක්කළ ආකාරය ගැන ක්‍රීඩා ක්ෂේත්‍රයේ බොහෝ දෙනෙකු බංග්ලාදේශ කණ්ඩායමට අප්‍රසාදය පළකර තිබේ.",},
        { label: "ක්‍රීඩා", color: "sport", text: "කන්ද උඩරට නිල් මහා සටනේ ජය ත්‍රිත්ව විද්‍යාලයට", },
        { label: "විදෙස්", color: "world", text: "ස්විට්සර්ලන්තයට ඉහළින් පියාසර කරන්න ඉල්ලූ අමෙරිකානු හමුදාවේ ඉල්ලීම ඉවතට", },
        { label: "විදෙස්", color: "world", text: "ඉරානයේ ඉස්ෆහන් නගරයට එල්ල වූ ප්‍රහාරයකින් කර්මාන්තශාලා සේවකයින් 15දෙනෙකු මරු", },
        { label: "විදෙස්", color: "world", text: "ඉරානය සමග ගිවිසුමකට එළැඹීමට සූදානම් නැති බව ට්‍රම්ප් කියයි",},
        { label: "විදෙස්", color: "world", text: "ඉන්දීය නෞකා දෙකකට හෝමූස් පසු කිරීමට අවසර.", },
        { label: "කාළගුණය", color: "weather", text: "බස්නාහිරට සබරගමුවට ගාල්ලට මාතරට බක්මහ අකුණු කල්තියාම", },
        { label: "කාළගුණය", color: "weather", text: "අදත් දිවයිනේ ප්‍රදේශ කිහිපයකට වැසි", },
        
    ];

    let barIndex = 0;

    function refreshBar() {
        const catBox = document.getElementById('barCategory');
        const catText = document.getElementById('barCategoryText');
        const newsText = document.getElementById('barNewsText');
        const newsLink = document.getElementById('newsLink');

        const current = finalNewsData[barIndex];

        // Slide Up Animation Reset
        newsText.classList.remove('anim-up');
        void newsText.offsetWidth; 
        newsText.classList.add('anim-up');

        // Update Content
        catText.innerText = current.label;
        catBox.className = "bar-category " + current.color;
        newsText.innerText = current.text;
        newsLink.href = current.link; // Link එක Update කිරීම

        barIndex = (barIndex + 1) % finalNewsData.length;
    }

    // Time Clock
    function updateBarClock() {
        const now = new Date();
        document.getElementById('barClock').innerText = now.toLocaleTimeString();
    }

    setInterval(refreshBar, 5000);
    setInterval(updateBarClock, 1000);
    window.onload = refreshBar;
</script>
<header class="main-branding">
    <div class="logo-bg-container">
        <div class="liquid-glow"></div>
        
        <a href="file:///C:/Users/user/Desktop/web/muduna.html" class="official-logo">
            <span class="m-box">M</span>UDUNA <span class="news-tag">NEWS</span>
        </a>
    </div>
    
    <div class="header-right">
        <div class="live-pulse-box">
            <span class="pulse-dot"></span> MUDUNA PLUS 
        </div>
        <div id="dateDisplay" class="current-date">Saturday, March 14, 2026</div>
    </div>
</header>

<style>
    /* මුළු Header එකම */
    .main-branding {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background: #001a33; /* තද නිල් පසුබිම */
        padding: 10px 5%;
        border-bottom: 4px solid #cc0000;
        position: relative;
        overflow: hidden;
    }

    /* Logo එක තියෙන විශේෂ පසුබිම */
    .logo-bg-container {
        position: relative;
        padding: 15px 40px;
        background: linear-gradient(135deg, #003366 0%, #001a33 100%);
        border-radius: 0 50px 50px 0; /* වම් පැත්ත square, දකුණු පැත්ත round */
        margin-left: -5%; /* ඇලවෙන්න */
        z-index: 1;
        overflow: hidden;
        box-shadow: 10px 0 20px rgba(0,0,0,0.5);
    }

    /* පසුපසින් දුවන Glow එක */
    .liquid-glow {
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: radial-gradient(circle, rgba(204, 0, 0, 0.2) 0%, transparent 70%);
        animation: rotateGlow 6s linear infinite;
        z-index: -1;
    }

    @keyframes rotateGlow {
        from { transform: rotate(0deg); }
        to { transform: rotate(360deg); }
    }

    /* Logo Style */
    .official-logo {
        color: white;
        text-decoration: none;
        font-size: 32px;
        font-weight: 900;
        letter-spacing: 2px;
        display: flex;
        align-items: center;
    }

    .m-box {
        background: #cc0000;
        padding: 0 12px;
        margin-right: 10px;
        border-radius: 5px;
        box-shadow: 0 0 15px rgba(204, 0, 0, 0.6);
    }

    .news-tag {
        font-weight: 300;
        margin-left: 10px;
        font-size: 20px;
        color: #aaa;
    }

    /* දකුණු පස කොටස */
    .header-right {
        text-align: right;
        color: white;
    }

    .live-pulse-box {
        color: #ff0000;
        font-weight: bold;
        font-size: 14px;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: 8px;
    }

    .pulse-dot {
        width: 10px;
        height: 10px;
        background: #ff0000;
        border-radius: 50%;
        box-shadow: 0 0 10px #ff0000;
        animation: pulseEffect 1.2s infinite;
    }

    @keyframes pulseEffect {
        0% { transform: scale(1); opacity: 1; }
        100% { transform: scale(1.5); opacity: 0; }
    }

    .current-date {
        font-size: 13px;
        color: #888;
        margin-top: 5px;
    }
</style>

<script>
    // අද දවස පෙන්වීමට
    const d = new Date();
    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    document.getElementById('dateDisplay').innerHTML = d.toLocaleDateString('en-US', options);
</script>
<div class="social-links-container">
    <span class="connect-text">අප සමඟ එක්වන්න:</span>
    
    <div class="social-icons-wrapper">
        <a href="https://web.facebook.com/mudunanews" target="_blank" class="social-icon fb" title="Facebook">
            <i class="icon-text">FB</i>
            <div class="hover-glow"></div>
        </a>

        <a href="https://www.youtube.com/@valueinfosl1218" target="_blank" class="social-icon yt" title="YouTube">
            <i class="icon-text">YT</i>
            <div class="hover-glow"></div>
        </a>

        <a href="https://wa.me/94716236710" target="_blank" class="social-icon wa" title="WhatsApp">
            <i class="icon-text">WA</i>
            <div class="hover-glow"></div>
        </a>
    </div>
</div>

<style>
    .social-links-container {
        display: flex;
        align-items: center;
        gap: 15px;
        font-family: 'Segoe UI', sans-serif;
        padding: 10px;
    }

    .connect-text {
        color: #ddd;
        font-size: 13px;
        font-weight: bold;
        text-transform: uppercase;
        letter-spacing: 1px;
    }

    .social-icons-wrapper {
        display: flex;
        gap: 10px;
    }

    .social-icon {
        position: relative;
        width: 40px;
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
        text-decoration: none;
        border-radius: 8px;
        overflow: hidden;
        transition: 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        border: 1px solid rgba(255,255,255,0.1);
        background: rgba(255, 255, 255, 0.05);
    }

    .icon-text {
        color: white;
        font-size: 14px;
        font-weight: 900;
        font-style: normal;
        z-index: 2;
    }

    /* Hover Glow Effect */
    .hover-glow {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0;
        transition: 0.3s;
        z-index: 1;
    }

    /* Facebook Colors */
    .fb:hover { transform: translateY(-5px); border-color: #1877F2; }
    .fb:hover .hover-glow { background: #1877F2; opacity: 0.8; box-shadow: 0 0 15px #1877F2; }

    /* YouTube Colors */
    .yt:hover { transform: translateY(-5px); border-color: #FF0000; }
    .yt:hover .hover-glow { background: #FF0000; opacity: 0.8; box-shadow: 0 0 15px #FF0000; }

    /* WhatsApp Colors */
    .wa:hover { transform: translateY(-5px); border-color: #25D366; }
    .wa:hover .hover-glow { background: #25D366; opacity: 0.8; box-shadow: 0 0 15px #25D366; }

    .social-icon:hover .icon-text {
        transform: scale(1.1);
    }
</style>
    <nav>
        <a href="file:///C:/Users/user/Desktop/web/muduna.html">මුල් පිටුව</a>
        <a href="file:///C:/Users/user/Desktop/WEBSITE/world.html">විදේශීය</a>
        <a href="file:///C:/Users/user/Desktop/web/thebigstory.html">කියන කථා</a>
        <a href="https://www.youtube.com/@valueinfosl1218">VIDEO STORIES</a>
    </nav>

    <div class="container">
        
        <article class="news-card">
            <img src="https://scontent-bom2-4.xx.fbcdn.net/v/t39.30808-6/653712964_122146926038986599_7882187370399995981_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=7b2446&_nc_eui2=AeGAlPMw9M4UW8vAb1Y1uHwVgRStph2sQ0aBFK2mHaxDRgRYm0VulYlKnmKnfAP99DNf035TEKejUVXPF2OAGsTg&_nc_ohc=xaPGZeyYdOgQ7kNvwF4TQ5-&_nc_oc=Adp0fsd8PBrg_ZkcIIirUOlhhdxheg8CE9fNfqJdE4HwbDAKG0Q95UkwDfs5Hp_o9k0&_nc_zt=23&_nc_ht=scontent-bom2-4.xx&_nc_gid=dsm6IxvtKC552Gds2OZWDA&_nc_ss=8&oh=00_AfwB0XwWbc3DdV-NTP4i1H_1y7bG3Dv_x5LScDfrIvDyxw&oe=69C1C598" alt="News Image" class="news-image">
            <div class="news-content">
                <span class="news-tag">THE BIG STORY</span>
                <h3 class="news-title">විදේශ අමාත්‍යාංශයේ ප්‍රකාශක ලින් ජියන් දිනපතා මාධ්‍ය හමුවකදී වාර්තාකරුවන්ට මෙසේ පැවසීය:...</h3>
                <p>ඊශ්‍රායලය විසින් ඉරාන නායකයින් ඝා!ත!න!ය කිරීම පිළිගත නොහැකි බව චීන විදේශ අමාත්‍යාංශය ප්‍රකාශ කරයි.</p>
                <a href="file:///C:/Users/user/Desktop/ARTICLES/7.html" class="read-more">වැඩිදුර කියවන්න</a>
            </div>
        </article>

        <article class="news-card">
            <img src="https://static.toiimg.com/thumb/imgsize-107964,msid-129668261,width-400,resizemode-4/129668261.jpg" alt="News Image" class="news-image">
            <div class="news-content">
                <span class="news-tag">THE BIG STORY</span>
                <h3 class="news-title">කටාර්හි ගෑස් පිරිපහදු වෙත එල්ල වූ ප්‍රහාරයෙන් යුරෝපයේ ගෑස් මිල 30%කින් ඉහළට</h3>
                <p>කටාර් රාජ්‍යයේ බලශක්ති මධ්‍යස්ථාන වෙත එල්ල වූ ඉරාන ප්‍රහාරවලින් සිදුවූ හානිය ගණනය කිරීමත් සමඟ, යුරෝපයේ ස්වභාවික වායු මිල එක රැයකින් 30% කින් ඉහළ ගොස් ඇති බව වාර්තා වේ.​.</p>
                <a href="file:///C:/Users/user/Desktop/ARTICLES/6.html" class="read-more">වැඩිදුර කියවන්න</a>
            </div>
        </article>

        <article class="news-card">
            <img src="https://scontent-bom2-3.xx.fbcdn.net/v/t39.30808-6/652674504_1992584175023378_3706079922621459900_n.jpg?stp=cp6_dst-jpg_tt6&_nc_cat=103&ccb=1-7&_nc_sid=7b2446&_nc_eui2=AeFgDxFL9Af48tDgSncSlKdWAWPH3HXTcugBY8fcddNy6NzX98a4JL1QtINfeL_KawkPcVJ7yho3bmIwcIIsnfCY&_nc_ohc=7fuIwkDyz0YQ7kNvwF7QWq9&_nc_oc=Adq6oROkJfQ76f7NbmCXatKmgnlD3RC6HAApqxgxzAQlsTmne8Bhdmt-35GJ6-QaBIc&_nc_zt=23&_nc_ht=scontent-bom2-3.xx&_nc_gid=Ko-UcbXct43MHzPNyG71lQ&_nc_ss=8&oh=00_AfzhdudJS-8zxi-tFkvCIC-lBS0QcoIbR2R7rsyiZ2hymA&oe=69C1C00B" alt="News Image" class="news-image">
            <div class="news-content">
                <span class="news-tag">කියන කථා</span>
                <h3 class="news-title">අලි ලලිජානි ගැන ඇමෙරිකාවේ ලොක්කෙක් කියන කථාව</h3>
                <p>අලි ලරිජානි සාමය සාකච්ඡා කරමින් සිටියේ. ඊශ්‍රායලය ඔහුව ඝාතනය කලා..</p>
                <a href="file:///C:/Users/user/Desktop/ARTICLES/5.HTML" class="read-more">වැඩිදුර කියවන්න</a>
            </div>
        </article>

    </div>


<style>
    /* පුවත් තීරුවල සැකසුම */
    .news-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 25px;
        max-width: 1200px;
        margin: 30px auto;
        padding: 0 15px;
    }

    /* News Card එකේ අලුත් පෙනුම */
    .news-card {
        background: #fff;
        border-bottom: 3px solid #003366; /* Blue border */
        border-radius: 5px;
        overflow: hidden;
        transition: all 0.3s ease;
        display: flex;
        flex-direction: column;
    }

    .news-card:hover {
        box-shadow: 0 10px 20px rgba(0,0,0,0.15);
        transform: translateY(-8px);
        border-bottom-color: #cc0000; /* Hover කරද්දී රතු පාට වෙනවා */
    }

    .news-image-wrapper {
        position: relative;
        overflow: hidden;
    }

    .news-image-wrapper img {
        width: 100%;
        height: 180px;
        object-fit: cover;
        transition: transform 0.5s ease;
    }

    .news-card:hover .news-image-wrapper img {
        transform: scale(1.1); /* Image එක zoom වෙනවා */
    }

    .news-content {
        padding: 15px;
        flex-grow: 1;
    }

    .news-date {
        font-size: 12px;
        color: #777;
        display: block;
        margin-bottom: 8px;
    }

    .news-title {
        font-size: 17px;
        color: #003366;
        font-weight: bold;
        text-decoration: none;
        line-height: 1.4;
    }

    .news-title:hover {
        color: #cc0000;
    }

    /* Read More එක ලස්සනට */
    .read-more-btn {
        margin-top: 15px;
        display: inline-block;
        color: #cc0000;
        font-weight: bold;
        text-decoration: none;
        font-size: 14px;
        transition: 0.2s;
    }

    .read-more-btn:hover {
        text-decoration: underline;
        color: #003366;
    }
</style>

<div class="news-grid">
    <div class="news-card">
        <div class="news-image-wrapper">
            <img src="https://joshuafund.com/wp-content/uploads/2026/02/ChatGPT-Image-Feb-28-2026-03_47_01-PM-1024x683.png" alt="News">
        </div>
        <div class="news-content">
            <span class="news-date">2026 මාර්තු 19</span>
            <a href="news-1.html" class="news-title">යුද්දෙට යට කල සල්ලි</a>
            <p>එක්සත් ජනපදය විසින් ඉරානයට එරෙහිව කරන හමුදා මෙහෙයුම් සඳහා දැනටමත් අවම වශයෙන් ඩොලර් බිලියන 06 පමණ වියදම් කර ඇති</p>
            <a href="file:///C:/Users/user/Desktop/ARTICLES/4.HTML" class="read-more-btn">වැඩිදුර කියවන්න ➔</a>
        </div>
    </div>

    <div class="news-card">
        <div class="news-image-wrapper">
            <img src="https://scontent-bom5-1.xx.fbcdn.net/v/t39.30808-6/653913360_122146913156986599_4928567911301588544_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=7b2446&_nc_eui2=AeFuvYEH18jysmojx1eBGD9bEhQBTgxKlmsSFAFODEqWa01N3w1cF-QcRvWSz1ih-4lVDNmRt1K9W6P9bl4Nokos&_nc_ohc=CvLzArsnI8IQ7kNvwEAqFko&_nc_oc=AdoZUEHsVeEAn-81DezJP1JUGz_UYl41h2n7BMS-J7NU9HicqQreN0tcI4HIk98McTc&_nc_zt=23&_nc_ht=scontent-bom5-1.xx&_nc_gid=XXYfSFFF52qwKyhYPwoP0g&_nc_ss=8&oh=00_AfxY9SAwI4bDKgV4GKgq5GzwwyucQFRhrthjAT4fOeThug&oe=69C1B819" alt="News">
        </div>
        <div class="news-content">
            <span class="news-date">2026 මාර්තු 19</span>
            <a href="news-2.html" class="news-title">පාකිස්ථානය තර්ජනයක් - එක්සත් ජනපද පෙන්ටගන් වාර්තාවකින් එළි වෙයි.</a>
            <p>පකිස්ථානය න්‍යෂ්ටික තර්ජනයක් ලෙස එක්සත් ජනපදය සලකුණු කර ඇති අතර පාකිස්ථානය එක්සත් ජනපදයේ ඉහළම පෙළේ ගැටළු අතරට ඇතුළත් කර ඇත.</p>
            <a href="file:///C:/Users/user/Desktop/web/5.HTML" class="read-more-btn">වැඩිදුර කියවන්න ➔</a>
        </div>
    </div>

    <div class="news-card">
        <div class="news-image-wrapper">
            <img src="https://scontent-bom2-1.xx.fbcdn.net/v/t51.82787-15/654198734_17931588495210072_1483713738799895198_n.webp?stp=dst-jpg_s720x720_tt6&_nc_cat=1&ccb=1-7&_nc_sid=13d280&_nc_eui2=AeH6oJcqeHRklQRZkEGLSRP3JlHiXjVqhuwmUeJeNWqG7FAqtNLFVwuVwXUG1XnStDQiubUmuqcQupApV_PWAWuZ&_nc_ohc=SeMNvJUfpQkQ7kNvwEGdzA1&_nc_oc=Adqe_UpczTv2rmh-EWjgzyC8d0pQK6tYpyOjK1aoQHtW1XcO1xU5Tezolp7czfQXxTk&_nc_zt=23&_nc_ht=scontent-bom2-1.xx&_nc_gid=jAj-0HTMzAtNrw4ig5ZxSA&_nc_ss=8&oh=00_Afy_5chffGeoiUHsWsnP1Ky7RuH9wxX7UEyP4uW4IMO5pw&oe=69C1BDFE" alt="News">
        </div>
        <div class="news-content">
            <span class="news-date">2026 මාර්තු 19</span>
            <a href="news-3.html" class="news-title"> </a>
            <p>4 වෙනි මාසය දක්වා නැව් ස්ථීර කරලා තියෙන්නේ. </p>
            <a href="file:///C:/Users/user/Desktop/ARTICLES/2.HTML" class="read-more-btn">වැඩිදුර කියවන්න ➔</a>
        </div>
    </div>

    <div class="news-card">
        <div class="news-image-wrapper">
            <img src="https://eu-images.contentstack.com/v3/assets/bltdcfe6aab5515629e/blt006cd4b89433b61c/69b127f0de5844322e3a7b6f/bulker-fire-credit-UKMTO.jpg" alt="News">
        </div>
        <div class="news-content">
            <span class="news-date">2026 මාර්තු  19</span>
            <a href="news-4.html" class="news-title">බලපෑම් රැසක් මැද හොර්මුස් සමුද්‍ර සන්ධිය උණුසුම් වෙයි
</a>
            <p>ඉරානය විසින් හොර්මුස් සමුද්‍ර සන්ධිය හරහා ගමන් කරන නෞකාවලට නව ගාස්තුවක් හඳුන්වා දීමට සූදානම් වේ.</p>
            <a href="file:///C:/Users/user/Desktop/web/7.HTML" class="read-more-btn">වැඩිදුර කියවන්න ➔</a>
        </div>
    </div>
</div>



<style>
    /* පුවත් තීරුවල සැකසුම */
    .news-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 25px;
        max-width: 1200px;
        margin: 30px auto;
        padding: 0 15px;
    }

    /* News Card එකේ අලුත් පෙනුම */
    .news-card {
        background: #fff;
        border-bottom: 3px solid #003366; /* Blue border */
        border-radius: 5px;
        overflow: hidden;
        transition: all 0.3s ease;
        display: flex;
        flex-direction: column;
    }

    .news-card:hover {
        box-shadow: 0 10px 20px rgba(0,0,0,0.15);
        transform: translateY(-8px);
        border-bottom-color: #cc0000; /* Hover කරද්දී රතු පාට වෙනවා */
    }

    .news-image-wrapper {
        position: relative;
        overflow: hidden;
    }

    .news-image-wrapper img {
        width: 100%;
        height: 180px;
        object-fit: cover;
        transition: transform 0.5s ease;
    }

    .news-card:hover .news-image-wrapper img {
        transform: scale(1.1); /* Image එක zoom වෙනවා */
    }

    .news-content {
        padding: 15px;
        flex-grow: 1;
    }

    .news-date {
        font-size: 12px;
        color: #777;
        display: block;
        margin-bottom: 8px;
    }

    .news-title {
        font-size: 17px;
        color: #003366;
        font-weight: bold;
        text-decoration: none;
        line-height: 1.4;
    }

    .news-title:hover {
        color: #cc0000;
    }

    /* Read More එක ලස්සනට */
    .read-more-btn {
        margin-top: 15px;
        display: inline-block;
        color: #cc0000;
        font-weight: bold;
        text-decoration: none;
        font-size: 14px;
        transition: 0.2s;
    }

    .read-more-btn:hover {
        text-decoration: underline;
        color: #003366;
    }
</style>


<style>
    /* පුවත් තීරුවල සැකසුම */
    .news-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 25px;
        max-width: 1200px;
        margin: 30px auto;
        padding: 0 15px;
    }

    /* News Card එකේ අලුත් පෙනුම */
    .news-card {
        background: #fff;
        border-bottom: 3px solid #003366; /* Blue border */
        border-radius: 5px;
        overflow: hidden;
        transition: all 0.3s ease;
        display: flex;
        flex-direction: column;
    }

    .news-card:hover {
        box-shadow: 0 10px 20px rgba(0,0,0,0.15);
        transform: translateY(-8px);
        border-bottom-color: #cc0000; /* Hover කරද්දී රතු පාට වෙනවා */
    }

    .news-image-wrapper {
        position: relative;
        overflow: hidden;
    }

    .news-image-wrapper img {
        width: 100%;
        height: 180px;
        object-fit: cover;
        transition: transform 0.5s ease;
    }

    .news-card:hover .news-image-wrapper img {
        transform: scale(1.1); /* Image එක zoom වෙනවා */
    }

    .news-content {
        padding: 15px;
        flex-grow: 1;
    }

    .news-date {
        font-size: 12px;
        color: #777;
        display: block;
        margin-bottom: 8px;
    }

    .news-title {
        font-size: 17px;
        color: #003366;
        font-weight: bold;
        text-decoration: none;
        line-height: 1.4;
    }

    .news-title:hover {
        color: #cc0000;
    }

    /* Read More එක ලස්සනට */
    .read-more-btn {
        margin-top: 15px;
        display: inline-block;
        color: #cc0000;
        font-weight: bold;
        text-decoration: none;
        font-size: 14px;
        transition: 0.2s;
    }

    .read-more-btn:hover {
        text-decoration: underline;
        color: #003366;
    }
</style>


<style>
    /* Section Layout */
    .health-section {
        max-width: 1100px;
        margin: 40px auto;
        padding: 20px;
        font-family: 'Segoe UI', sans-serif;
    }

    .section-title {
        display: flex;
        align-items: center;
        margin-bottom: 25px;
        border-bottom: 2px solid #ddd;
        padding-bottom: 10px;
    }

    .title-red-bar {
        width: 10px;
        height: 35px;
        background: #007bff; /* Health Blue */
        margin-right: 15px;
    }

    .section-title h2 {
        margin: 0;
        font-size: 24px;
        color: #1a1a1a;
    }

    .en-sub {
        color: #888;
        font-size: 16px;
        font-weight: normal;
    }

    /* Health Cards Grid */
    .health-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        gap: 25px;
    }

    .health-card {
        background: white;
        border-radius: 12px;
        overflow: hidden;
        box-shadow: 0 4px 15px rgba(0,0,0,0.05);
        cursor: pointer;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
        border: 1px solid #eee;
    }

    .health-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 25px rgba(0,0,0,0.1);
    }

    .health-img-box {
        position: relative;
        height: 200px;
    }

    .health-img-box img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .health-tag {
        position: absolute;
        bottom: 10px;
        left: 10px;
        background: #28a745; /* Success Green */
        color: white;
        padding: 5px 12px;
        font-size: 12px;
        font-weight: bold;
        border-radius: 4px;
    }

    .health-info {
        padding: 20px;
    }

    .health-info h3 {
        font-size: 19px;
        margin: 0 0 10px 0;
        line-height: 1.4;
        color: #111;
        transition: 0.3s;
    }

    .health-card:hover h3 {
        color: #007bff;
    }

    .health-info p {
        font-size: 15px;
        color: #555;
        line-height: 1.6;
        margin-bottom: 15px;
    }

    .read-more-link {
        color: #007bff;
        font-weight: bold;
        font-size: 14px;
    }
</style>



<footer class="muduna-footer">
    <div class="footer-container">
        
        <div class="footer-col">
            <a href="#" class="footer-logo"><span>M</span>UDUNA NEWS</a>
            <p class="footer-desc">
                ශ්‍රී ලංකාවේ සහ ලෝකයේ උණුසුම් පුවත්, දේශපාලන විග්‍රහයන් සහ විශ්වාසනීය තොරතුරු සැණින් ඔබ වෙත ගෙන එන ප්‍රමුඛතම පුවත් සේවාව.
            </p>
            <div class="social-icons">
                <a href="https://web.facebook.com/mudunanews">FB</a>
                <a href="https://www.youtube.com/@valueinfosl1218">YT</a>
                <a href="https://wa.me/94716236710">WA</a>
            </div>
        </div>

        <div class="footer-col">
            <h4>ප්‍රධාන අංශ</h4>
            <ul class="footer-links">
                <li><a href="#">දේශීය පුවත්</a></li>
                <li><a href="#">විදෙස් පුවත්</a></li>
                <li><a href="#">ක්‍රිකට් උණුසුම</a></li>
                <li><a href="#">සෞඛ්‍ය ලිපි</a></li>
                <li><a href="#">Live TV</a></li>
            </ul>
        </div>

        <div class="footer-col">
            <h4>අපව අමතන්න</h4>
            <p class="contact-info">📍 අංක 102,ග්‍රීන් හෙරිටේජ් සිටි,මාළිගාතැන්න,ගුරුදෙණිය</p>
            <p class="contact-info">📞 +94 75 077 3137</p>
            <p class="contact-info">✉️ weesin.kandy@gmail.com</p>
            
         
    </div>

    <div class="footer-bottom">
        <p>&copy; 2026 MUDUNA NEWS - All Rights Reserved. | සකස් කළේ: Thisaja Dulneth Weerasinghe</p>
    </div>
</footer>

<style>
    .muduna-footer {
        background: #001a33; /* Dark Navy Blue */
        color: white;
        padding: 60px 20px 20px 20px;
        font-family: 'Segoe UI', sans-serif;
        border-top: 5px solid #cc0000;
    }

    .footer-container {
        max-width: 1200px;
        margin: 0 auto;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 40px;
    }

    .footer-logo {
        font-size: 28px;
        font-weight: 900;
        text-decoration: none;
        color: white;
        display: block;
        margin-bottom: 20px;
    }

    .footer-logo span {
        background: #cc0000;
        padding: 0 10px;
        border-radius: 5px;
    }

    .footer-desc {
        font-size: 14px;
        line-height: 1.8;
        color: #b3c6ff;
        margin-bottom: 20px;
    }

    .footer-col h4 {
        font-size: 18px;
        margin-bottom: 25px;
        position: relative;
        padding-bottom: 10px;
    }

    .footer-col h4::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: 0;
        width: 50px;
        height: 2px;
        background: #cc0000;
    }

    .footer-links {
        list-style: none;
        padding: 0;
    }

    .footer-links li {
        margin-bottom: 12px;
    }

    .footer-links li a {
        color: #b3c6ff;
        text-decoration: none;
        transition: 0.3s;
        font-size: 15px;
    }

    .footer-links li a:hover {
        color: white;
        padding-left: 10px;
    }

    .contact-info {
        font-size: 14px;
        margin-bottom: 15px;
        color: #b3c6ff;
    }

    .social-icons {
        display: flex;
        gap: 15px;
    }

    .social-icons a {
        width: 35px;
        height: 35px;
        background: rgba(255,255,255,0.1);
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        color: white;
        text-decoration: none;
        font-size: 12px;
        font-weight: bold;
        transition: 0.3s;
    }

    .social-icons a:hover {
        background: #cc0000;
    }

    .app-buttons {
        margin-top: 20px;
    }

    .app-placeholder {
        background: #000;
        padding: 10px;
        border-radius: 5px;
        font-size: 12px;
        margin-bottom: 10px;
        border: 1px solid #333;
        cursor: pointer;
        text-align: center;
    }

    .footer-bottom {
        text-align: center;
        margin-top: 50px;
        padding-top: 20px;
        border-top: 1px solid rgba(255,255,255,0.1);
        font-size: 13px;
        color: #777;
    }
</style>
