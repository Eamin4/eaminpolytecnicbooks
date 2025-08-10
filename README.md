<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <title>Eamin Polytecnic Books</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        #user-float-btn:hover, #support-float-btn:hover {
            box-shadow: 0 4px 16px #43e97b66, 0 2px 8px #1877f233;
            transform: scale(1.08) rotate(-6deg);
            background: #e3f0ff;
        }
        #user-float-btn svg, #support-float-btn svg {
            transition: transform 0.2s;
        }
        #user-float-btn:hover svg, #support-float-btn:hover svg {
            transform: scale(1.18) rotate(6deg);
        }
        body {
            margin: 0;
            font-family: 'Segoe UI', 'SolaimanLipi', Arial, sans-serif;
            background: linear-gradient(120deg, #e3f0ff 0%, #f4f7fb 100%);
            color: #222b45;
        }
        .topnav {
            background: #ff4fa3;
            color: #fff;
            box-shadow: 0 2px 8px rgba(24,119,242,0.04);
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            z-index: 1000;
        }
        .topnav-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 16px 18px;
        }
        .site-title {
            font-size: 2em;
            font-weight: 700;
            letter-spacing: 1.5px;
            color: #fff200;
            text-shadow: 1px 1px 6px #1877f2, 0 2px 8px #0002;
        }
        .nav-links {
            display: flex;
            gap: 22px;
        }
        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            font-size: 1.08em;
            padding: 6px 10px;
            border-radius: 6px;
            transition: background 0.2s, color 0.2s;
            position: relative;
        }
        .nav-links a.active, .nav-links a:hover {
            background: #fff;
            color: #1877f2;
        }
        .nav-links a.active::after {
            content: '';
            position: absolute;
            left: 50%;
            bottom: -6px;
            transform: translateX(-50%);
            width: 60%;
            height: 3px;
            background: linear-gradient(90deg, #43e97b, #ffb300);
            border-radius: 2px;
        }
        .banner {
            position: relative;
            min-height: 340px;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            background: #222b45;
        }
        .banner-bg-img {
            position: absolute;
            left: 0; top: 0;
            width: 100vw;
            height: 100%;
            object-fit: contain;
            z-index: 1;
            opacity: 1;
            max-height: 95vh;
            display: block;
            margin: 0 auto;
        }
        .banner-text {
            position: relative;
            z-index: 2;
            font-size: 2.2em;
            font-weight: 700;
            letter-spacing: 2px;
            text-align: left;
            width: 100vw;
            background: linear-gradient(90deg, #ff5252, #ffb300, #43e97b, #40c4ff, #7c4dff, #e040fb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-fill-color: transparent;
            filter: drop-shadow(0 2px 6px #222b45);
            white-space: nowrap;
            overflow: hidden;
            animation: bannerMarqueeRTL 10s linear infinite;
        }

        @keyframes bannerMarqueeRTL {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }
        @keyframes bannerMarquee {
            0% { transform: translateX(0);}
            100% { transform: translateX(-100%);}
        }
        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 32px 18px;
            display: flex;
            gap: 32px;
            margin-top: 80px;
        }
        .sidebar {
            width: 260px;
            background: #fff;
            border-radius: 14px;
            box-shadow: 0 2px 12px rgba(24,119,242,0.07);
            padding: 28px 18px;
            min-height: 320px;
        }
        .sidebar h3 {
            font-size: 1.18em;
            margin-bottom: 16px;
            color: #1877f2;
            letter-spacing: 1px;
        }
        .genre-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .genre-btn {
            background: #e3f0ff;
            color: #1877f2;
            border: none;
            border-radius: 8px;
            padding: 10px 0;
            font-size: 1em;
            font-weight: 500;
            cursor: pointer;
            transition: background 0.2s, color 0.2s;
        }
        .genre-btn.active, .genre-btn:hover {
            background: #1877f2;
            color: #fff;
        }
        .content-area {
            flex: 1;
        }
        .feature-section {
            display: none;
            background: #fff;
            border-radius: 14px;
            box-shadow: 0 2px 12px rgba(24,119,242,0.07);
            padding: 32px 24px;
            margin-bottom: 24px;
            animation: fadeIn 0.5s;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px);}
            to { opacity: 1; transform: translateY(0);}
        }
        .feature-section.active {
            display: block;
        }
        .page-title {
            font-size: 2.2em;
            font-weight: 700;
            color: #43e97b;
            margin-bottom: 12px;
            letter-spacing: 1.5px;
        }
        .desc {
            font-size: 1.08em;
            color: #444;
            margin-bottom: 24px;
            background: #e3f0ff;
            padding: 12px 18px;
            border-radius: 8px;
            box-shadow: 0 1px 4px rgba(24,119,242,0.04);
        }
        .filter-bar {
            display: flex;
            gap: 10px;
            margin-bottom: 18px;
        }
        .filter-btn {
            background: #e3f0ff;
            color: #1877f2;
            border: none;
            border-radius: 8px;
            padding: 10px 18px;
            font-size: 1em;
            font-weight: 500;
            cursor: pointer;
            transition: background 0.2s, color 0.2s;
        }
        .filter-btn.active, .filter-btn:hover {
            background: #43e97b;
            color: #fff;
        }
        .search-bar {
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 18px;
            background: #e3f0ff;
            border-radius: 18px;
            padding: 8px 16px;
            max-width: 350px;
            box-shadow: 0 1px 4px rgba(24,119,242,0.04);
        }
        .search-bar input[type="text"] {
            border: none;
            background: transparent;
            font-size: 1em;
            color: #1877f2;
            outline: none;
            flex: 1;
            padding: 8px 0;
        }
        .search-bar .search-icon {
            cursor: pointer;
            display: flex;
            align-items: center;
            transition: transform 0.2s;
        }
        .search-bar .search-icon:hover {
            transform: scale(1.1);
        }
        .book-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 22px;
        }
        .book-card {
            background: #fff;
            border-radius: 12px;
            box-shadow: 0 2px 8px rgba(24,119,242,0.07);
            padding: 18px;
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: box-shadow 0.2s;
        }
        .book-card:hover {
            box-shadow: 0 4px 16px rgba(24,119,242,0.13);
        }
        .book-cover {
            width: 120px;
            height: 160px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 12px;
            background: #e3f0ff;
        }
        .book-title {
            font-size: 1.08em;
            font-weight: 600;
            color: #1877f2;
            margin-bottom: 6px;
            text-align: center;
        }
        .book-author {
            font-size: 0.98em;
            color: #444;
            margin-bottom: 8px;
            text-align: center;
        }
        .book-actions {
            display: flex;
            gap: 10px;
            margin-top: 8px;
        }
        .book-btn {
            background: #43e97b;
            color: #fff;
            border: none;
            border-radius: 8px;
            padding: 8px 14px;
            font-size: 0.98em;
            font-weight: 500;
            cursor: pointer;
            transition: background 0.2s;
        }
        .book-btn:hover {
            background: #1877f2;
            color: #fff;
        }
        @media (max-width: 900px) {
            .main-content { flex-direction: column; gap: 0; }
            .sidebar { width: 100%; margin-bottom: 24px; }
        }
        @media (max-width: 600px) {
            .topnav-content { flex-direction: column; gap: 10px; }
            .main-content { padding: 12px 4px; }
            .sidebar { padding: 12px 6px; }
            .banner-text { font-size: 1.1em; }
        }
    </style>
    <style>
    .subject-icons-row {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 48px;
        margin: 0 0 -18px 0;
        min-height: 0;
        background: none;
        box-shadow: none;
        padding: 0;
    }
    .subject-icon {
        width: 90px;
        height: 90px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        background: linear-gradient(135deg, #ffb6ec 0%, #b4c5ff 100%);
        box-shadow: 0 4px 18px #0002, 0 1.5px 6px #ff4fa355;
        border: 2.5px solid #fff;
        font-size: 2.8em;
        color: #6c2eb7;
        animation: iconFloat 2.5s ease-in-out infinite alternate;
        transition: transform 0.2s, box-shadow 0.2s;
        cursor: pointer;
    }
    .subject-icon:hover {
        transform: scale(1.15) rotate(-8deg);
        box-shadow: 0 8px 32px #ff4fa355, 0 2px 8px #6c2eb755;
        background: linear-gradient(135deg, #fff1fa 0%, #e0e7ff 100%);
    }
    .subject-icon:nth-child(2) { animation-delay: 0.3s; }
    .subject-icon:nth-child(3) { animation-delay: 0.6s; }
    .subject-icon:nth-child(4) { animation-delay: 0.9s; }
    .subject-icon:nth-child(5) { animation-delay: 1.2s; }
    .subject-icon:hover {
        transform: scale(1.18) rotate(-8deg);
        background: #ffe3f3;
    }
    @keyframes iconFloat {
        0% { transform: translateY(0); }
        100% { transform: translateY(-22px); }
    }
    </style>
</head>
<body>
    <!-- Floating Support Chat Icon -->
    <div id="support-float-btn" style="position:fixed;bottom:28px;right:28px;z-index:9999;cursor:pointer;background:#43e97b;border-radius:50%;box-shadow:0 2px 8px #1877f233;width:54px;height:54px;display:flex;align-items:center;justify-content:center;transition:box-shadow 0.2s;">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="#fff"><path d="M12 3C6.48 3 2 6.92 2 12c0 2.08.8 3.97 2.13 5.47L2.1 21.9a1 1 0 0 0 1.27 1.27l4.43-2.03A10.02 10.02 0 0 0 12 21c5.52 0 10-3.92 10-9s-4.48-9-10-9zm0 16c-1.7 0-3.29-.44-4.62-1.2l-.28-.16-2.63 1.2 1.2-2.63-.16-.28A7.97 7.97 0 0 1 4 12c0-4.08 3.58-7 8-7s8 2.92 8 7-3.58 7-8 7zm-1-6h2v2h-2zm0-8h2v6h-2z"/></svg>
    </div>
    <!-- Notice Button Below Banner -->
    <div style="display:flex;justify-content:center;margin-top:12px;">
        <button id="notice-btn" style="background:#ff4fa3;color:#fff;font-weight:700;font-size:1.1em;padding:10px 32px;border:none;border-radius:8px;box-shadow:0 2px 8px #ff4fa355;cursor:pointer;transition:background 0.2s;">
            📢 Notice
        </button>
    </div>
    <!-- Support Modal -->
    <div id="support-modal" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:10000;justify-content:center;align-items:center;">
        <div style="background:#fff;padding:32px 24px;border-radius:16px;box-shadow:0 8px 32px rgba(24,119,242,0.18);min-width:320px;max-width:95vw;max-height:90vh;overflow:auto;">
            <div style="font-size:1.2em;font-weight:700;margin-bottom:10px;text-align:center;color:#43e97b;">Support Team</div>
            <form id="support-form">
                <input type="text" id="support-name" placeholder="Your Name" required style="width:100%;padding:8px;margin-bottom:10px;border-radius:6px;border:1px solid #43e97b;">
                <input type="email" id="support-email" placeholder="Your Email" required style="width:100%;padding:8px;margin-bottom:10px;border-radius:6px;border:1px solid #43e97b;">
                <textarea id="support-message" placeholder="Type your message..." required style="width:100%;min-height:80px;padding:10px;border-radius:8px;border:1px solid #43e97b;margin-bottom:12px;"></textarea>
                <button type="submit" style="background:#43e97b;color:#fff;font-weight:600;padding:8px 22px;border:none;border-radius:8px;cursor:pointer;width:100%;">Send Message</button>
            </form>
            <div id="support-success" style="display:none;color:#43e97b;font-weight:600;text-align:center;margin-top:12px;">Thank you! Your message has been sent to the support team.</div>
            <button id="close-support-modal" style="background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;margin-top:16px;">Close</button>
            <div style="margin-top:18px;text-align:center;font-size:0.98em;color:#1877f2;">
                Or contact us directly:<br>
                <a href="mailto:eyaminahmed166@gmail.com" style="color:#43e97b;text-decoration:underline;">eyaminahmed166@gmail.com</a> |
                <a href="https://www.facebook.com/share/16mAW16CMh/" target="_blank" style="color:#1877f2;text-decoration:underline;">Facebook</a>
            </div>
        </div>
    </div>
    <!-- Floating User Icon -->
    <!-- User Icon moved to top right nav -->
    <!-- User Modal -->
    <div id="user-modal" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:10000;justify-content:center;align-items:center;">
        <div style="background:#fff;padding:32px 24px;border-radius:16px;box-shadow:0 8px 32px rgba(24,119,242,0.18);min-width:320px;max-width:95vw;max-height:90vh;overflow:auto;">
            <div id="user-modal-content"></div>
            <button id="close-user-modal" style="background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;margin-top:16px;">বন্ধ করুন</button>
        </div>
    </div>
    <!-- Top Navigation Start -->
    <div class="topnav">
        <div class="topnav-content">
            <div id="user-signup-trigger" style="display:flex;align-items:center;gap:10px;cursor:pointer;">
                <img id="profile-img" src="c:/Users/MK/Desktop/my-shop/envato-labs-ai-8015763c-eae2-425f-9871-cf450ab7c664.jpg" alt="Profile" style="width:44px;height:44px;border-radius:50%;object-fit:cover;box-shadow:0 2px 8px #1877f233;transition:transform 0.25s, box-shadow 0.25s;">
    <style>
    #profile-img:hover {
        transform: scale(1.13) rotate(-4deg);
        box-shadow: 0 4px 24px #43e97b88, 0 2px 8px #1877f233;
        cursor: pointer;
    }
    </style>
            </div>
            <span class="site-title" style="font-weight: bold; font-family: 'Segoe UI', Arial, sans-serif;">Eamin</span>
            <div class="nav-links">
                <a href="#" class="active" onclick="showFeature('home', this)">হোম</a>
                <a href="#" onclick="showFeature('suggestion', this)" style="background:#fff;color:#1877f2;font-weight:600;padding:6px 10px;border-radius:6px;transition:background 0.2s, color 0.2s;">Suggestion</a>
            </div>
            <!-- Suggestion Section -->
            <div id="feature-suggestion" class="feature-section">
                <div class="page-title">Suggestion</div>
                <div class="desc">
                    আপনার সফলতার জন্য কিছু উপায়:
                    <ul style="margin-top:10px;">
                        <li>নিয়মিত পড়াশোনা ও সময়ের সঠিক ব্যবহার করুন।</li>
                        <li>নিজের লক্ষ্য নির্ধারণ করুন এবং সেই অনুযায়ী পরিকল্পনা করুন।</li>
                        <li>শিক্ষকদের পরামর্শ ও গাইডলাইন অনুসরণ করুন।</li>
                        <li>নতুন কিছু শেখার প্রতি আগ্রহী থাকুন এবং প্রযুক্তি ব্যবহার করুন।</li>
                        <li>পরিশ্রম ও ধৈর্য ধরে রাখুন, কখনো হাল ছাড়বেন না।</li>
                    </ul>
                    <hr style="margin:12px 0;">
                    আপনার যেকোনো পরামর্শ, মতামত বা ফিডব্যাক আমাদের জানান।
                </div>
                <form id="suggestion-form" style="max-width:400px;margin:0 auto;">
                    <textarea id="suggestion-text" placeholder="আপনার পরামর্শ লিখুন..." style="width:100%;min-height:80px;padding:10px;border-radius:8px;border:1px solid #43e97b;margin-bottom:12px;"></textarea>
                    <br>
                    <button type="submit" style="background:#43e97b;color:#fff;font-weight:600;padding:8px 22px;border:none;border-radius:8px;cursor:pointer;">Send</button>
                </form>
            </div>
    <script>
    // Support chat icon and modal logic
    document.addEventListener('DOMContentLoaded', function() {
        const supportBtn = document.getElementById('support-float-btn');
        const supportModal = document.getElementById('support-modal');
        const closeSupportBtn = document.getElementById('close-support-modal');
        const supportForm = document.getElementById('support-form');
        const supportSuccess = document.getElementById('support-success');
        if (supportBtn && supportModal && closeSupportBtn && supportForm && supportSuccess) {
            supportBtn.onclick = function() { supportModal.style.display = 'flex'; };
            closeSupportBtn.onclick = function() { supportModal.style.display = 'none'; supportSuccess.style.display = 'none'; supportForm.style.display = 'block'; };
            supportModal.addEventListener('click', function(e) { if (e.target === supportModal) supportModal.style.display = 'none'; });
            supportForm.onsubmit = function(e) {
                e.preventDefault();
                // For demo, just show success message
                supportForm.style.display = 'none';
                supportSuccess.style.display = 'block';
            };
        }
    });
    // Floating user icon and modal logic
    document.addEventListener('DOMContentLoaded', function() {
        const signupTrigger = document.getElementById('user-signup-trigger');
        const modal = document.getElementById('user-modal');
        const modalContent = document.getElementById('user-modal-content');

        function getUser() {
            try {
                return JSON.parse(localStorage.getItem('userProfile')) || null;
            } catch { return null; }
        }
        function setUser(user) {
            localStorage.setItem('userProfile', JSON.stringify(user));
        }
        function clearUser() {
            localStorage.removeItem('userProfile');
        }
        function renderProfile() {
            const user = getUser();
            if (!user) { renderSignUp(); return; }
            modalContent.innerHTML = `
                <div style="text-align:center;">
                    <svg width="54" height="54" viewBox="0 0 24 24" fill="#43e97b"><circle cx="12" cy="8" r="4"/><path d="M12 14c-4.418 0-8 1.79-8 4v2h16v-2c0-2.21-3.582-4-8-4z"/></svg>
                    <div style="font-size:1.2em;font-weight:700;margin:8px 0 2px 0;">${user.name}</div>
                    <div style="color:#1877f2;font-size:1em;">${user.email}</div>
                    <button id="logout-btn" style="margin-top:16px;background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;">Log Out</button>
                </div>
            `;
            document.getElementById('logout-btn').onclick = function() {
                clearUser();
                renderSignUp();
            };
        }
        function renderSignUp() {
            modalContent.innerHTML = `
                <div style="font-size:1.2em;font-weight:700;margin-bottom:10px;text-align:center;color:#43e97b;">Sign Up / Log In</div>
                <div style="display:flex;gap:10px;justify-content:center;margin-bottom:16px;">
                    <button id="google-signup" style="background:#fff;color:#222b45;border:1px solid #43e97b;padding:7px 16px;border-radius:6px;display:flex;align-items:center;gap:6px;cursor:pointer;font-weight:600;">
                        <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/google.svg" alt="Google" style="width:20px;height:20px;"> Google
                    </button>
                    <button id="facebook-signup" style="background:#1877f2;color:#fff;border:none;padding:7px 16px;border-radius:6px;display:flex;align-items:center;gap:6px;cursor:pointer;font-weight:600;">
                        <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/facebook.svg" alt="Facebook" style="width:20px;height:20px;filter:invert(1) sepia(1) saturate(5) hue-rotate(180deg);"> Facebook
                    </button>
                </div>
                <form id="user-form">
                    <input type="text" id="user-name" placeholder="Name" required style="width:100%;padding:8px;margin-bottom:10px;border-radius:6px;border:1px solid #43e97b;">
                    <input type="email" id="user-email" placeholder="Email" required style="width:100%;padding:8px;margin-bottom:10px;border-radius:6px;border:1px solid #43e97b;">
                    <input type="password" id="user-pass" placeholder="Password" required style="width:100%;padding:8px;margin-bottom:10px;border-radius:6px;border:1px solid #43e97b;">
                    <button type="submit" style="background:#43e97b;color:#fff;font-weight:600;padding:8px 22px;border:none;border-radius:8px;cursor:pointer;width:100%">Sign Up / Log In</button>
                </form>
            `;
            document.getElementById('user-form').onsubmit = function(e) {
                e.preventDefault();
                const name = document.getElementById('user-name').value.trim();
                const email = document.getElementById('user-email').value.trim();
                const pass = document.getElementById('user-pass').value.trim();
                if (!name || !email || !pass) { alert('সব তথ্য দিন'); return; }
                setUser({ name, email });
                renderProfile();
            };
            document.getElementById('google-signup').onclick = function() {
                setUser({ name: 'Google User', email: 'user@gmail.com' });
                renderProfile();
            };
            document.getElementById('facebook-signup').onclick = function() {
                setUser({ name: 'Facebook User', email: 'user@facebook.com' });
                renderProfile();
            };
        }
        // Make both image and button clickable
        signupTrigger.onclick = function() {
            modal.style.display = 'flex';
            if (getUser()) renderProfile();
            else renderSignUp();
        };
        // Also allow clicking the user icon
        const floatBtn = document.getElementById('user-float-btn');
        if (floatBtn) {
            floatBtn.onclick = function() {
                modal.style.display = 'flex';
                if (getUser()) renderProfile();
                else renderSignUp();
            };
        }
        // Use event delegation for close button inside modal
        modal.addEventListener('click', function(e) {
            if (e.target === modal) modal.style.display = 'none';
            if (e.target && e.target.id === 'close-user-modal') {
                modal.style.display = 'none';
            }
        });
    });

    // Require sign up before download
    document.addEventListener('DOMContentLoaded', function() {
        function getUser() {
            try { return JSON.parse(localStorage.getItem('userProfile')) || null; } catch { return null; }
        }
        document.body.addEventListener('click', function(e) {
            if (e.target.classList && e.target.classList.contains('book-btn')) {
                if (!getUser()) {
                    e.preventDefault();
                    document.getElementById('user-modal').style.display = 'flex';
                    document.getElementById('user-modal-content').innerHTML = '';
                    setTimeout(() => {
                        const floatBtn = document.getElementById('user-float-btn');
                        if (floatBtn) floatBtn.click();
                    }, 100);
                }
            }
        }, true);
    });
    // Suggestion form handler
    document.addEventListener('DOMContentLoaded', function() {
        const suggestionForm = document.getElementById('suggestion-form');
        if (suggestionForm) {
            suggestionForm.onsubmit = function(e) {
                e.preventDefault();
                const text = document.getElementById('suggestion-text').value.trim();
                if (!text) {
                    alert('পরামর্শ লিখুন!');
                    return;
                }
                let suggestions = [];
                try {
                    suggestions = JSON.parse(localStorage.getItem('suggestions')) || [];
                } catch (e) { suggestions = []; }
                suggestions.push({ text, time: new Date().toISOString() });
                localStorage.setItem('suggestions', JSON.stringify(suggestions));
                suggestionForm.reset();
                alert('ধন্যবাদ! আপনার পরামর্শ সংরক্ষিত হয়েছে।');
            };
        }
    });
    </script>
                <a href="#" onclick="showFeature('books', this)">বই</a>
                <a href="#" onclick="showFeature('result', this)">ডিপ্লোমা রেজাল্ট</a>
                <a href="#" onclick="showFeature('info', this)">শিক্ষা তথ্য</a>
                <a href="#" onclick="showFeature('guideline', this)">কমিউনিটি গাইডলাইন</a>
                <a href="#" onclick="showFeature('contact', this)">যোগাযোগ</a>
            </div>
        </div>
    </div>
    <!-- Top Navigation End -->

    <!-- Banner Start -->
    <div class="banner">
    <img src="c:/Users/MK/Desktop/my-shop/photo_2025-08-09_03-28-14.jpg"
         alt="Group Photo"
         class="banner-bg-img" style="object-fit:cover;width:100vw;height:420px;max-height:60vh;">
        <span class="banner-text">
            শিক্ষা মানুষকে আলোকিত করে, বই মানুষকে গড়ে তোলে
        </span>
    </div>
    <!-- Banner End -->

    <div class="main-content">
        <div class="sidebar">
            <div style="background:#e3f0ff;padding:0;border-radius:10px;margin-bottom:18px;display:flex;justify-content:center;align-items:center;min-height:180px;">
                <img src="c:/Users/MK/Desktop/my-shop/envato-labs-ai-a4790047-98bb-4074-a031-f17be3efae1c.jpg" alt="About Image" style="max-width:100%;max-height:220px;border-radius:10px;box-shadow:0 2px 12px #0002;object-fit:cover;">
            </div>
            <h3>বইয়ের বিভাগ</h3>
            <div class="genre-list">
                <button class="genre-btn active" onclick="showGenre('all', this)">সব বই</button>
                <button class="genre-btn" onclick="showGenre('computer', this)">কম্পিউটার টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('electrical', this)">ইলেকট্রিক্যাল টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('mechanical', this)">মেকানিক্যাল টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('civil', this)">সিভিল টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('electronics', this)">ইলেকট্রনিক্স টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('power', this)">পাওয়ার টেকনোলজি</button>
                <button class="genre-btn" onclick="showGenre('rac', this)">RAC টেকনোলজি</button>
            </div>
        </div>
        <div class="content-area">
            <!-- Community Guideline Section -->
            <div id="feature-guideline" class="feature-section">
                <div class="page-title">কমিউনিটি গাইডলাইন</div>
                <div class="desc" style="background:#e3f0ff;padding:18px 18px 18px 18px;border-radius:10px;max-width:700px;">
                    <b>Community Guidelines</b><br><br>
                    ১. <b>Respect Everyone:</b> সকল ব্যবহারকারীর প্রতি সম্মান দেখান। গালি, হুমকি, বা অপমানমূলক ভাষা ব্যবহার করবেন না।<br><br>
                    ২. <b>No Spam:</b> অপ্রাসঙ্গিক লিংক, বিজ্ঞাপন, বা স্প্যাম পোস্ট করা যাবে না।<br><br>
                    ৩. <b>Share Knowledge:</b> শিক্ষামূলক ও সহায়ক তথ্য শেয়ার করুন। ভুল তথ্য বা গুজব ছড়াবেন না।<br><br>
                    ৪. <b>Privacy:</b> কারো ব্যক্তিগত তথ্য অনুমতি ছাড়া প্রকাশ করবেন না।<br><br>
                    ৫. <b>Copyright:</b> কপিরাইটযুক্ত কনটেন্ট শেয়ার করার আগে অনুমতি নিন।<br><br>
                    ৬. <b>Help Moderators:</b> কোনো সমস্যা বা আপত্তিকর কনটেন্ট দেখলে মডারেটরদের জানান।<br><br>
                    <b>আমাদের লক্ষ্য একটি নিরাপদ, শিক্ষামূলক ও বন্ধুত্বপূর্ণ পরিবেশ তৈরি করা।</b>
                </div>
            </div>
            <!-- Home Section -->
            <div id="feature-home" class="feature-section active">
                <div class="page-title" style="color:#22b573;">Eamin Polytechnic Books</div>
                <div class="desc">
                    ইউনিক বাংলা পলিটেকনিক বইয়ের PDF সংগ্রহ। সকল টেকনোলজির বই, ল্যাব ম্যানুয়াল, প্রজেক্ট, গাইড, প্রশ্নপত্র ও আরও অনেক কিছু এক জায়গায়।
                </div>
                <div class="filter-bar">
                    <button class="filter-btn active" onclick="filterBooks('az', this)">A-Z</button>
                    <button class="filter-btn" onclick="filterBooks('top', this)">Top</button>
                    <button class="filter-btn" onclick="filterBooks('popular', this)">Popular</button>
                    <button class="filter-btn" onclick="filterBooks('recent', this)">Recent</button>
                </div>
                <div class="search-bar">
                    <input type="text" placeholder="বই খুঁজুন..." oninput="searchBooks(this.value)">
                    <span class="search-icon" title="Search">
                        <svg width="22" height="22" viewBox="0 0 24 24" fill="none">
                            <circle cx="11" cy="11" r="8" stroke="#43e97b" stroke-width="2"/>
                            <line x1="17" y1="17" x2="22" y2="22" stroke="#43e97b" stroke-width="2" stroke-linecap="round"/>
                        </svg>
                    </span>
                </div>
                <div class="book-grid" id="book-grid">
                    <!-- Book Card Example -->
                </div>
            </div>
            <!-- Books Section -->
            <div id="feature-books" class="feature-section">
                <div class="page-title">বই</div>
                <div class="desc">এখানে সকল বিভাগের বই পাবেন। বিভাগ সিলেক্ট করুন অথবা সার্চ করুন।</div>
                <div class="book-grid" id="book-grid-books"></div>
            </div>
            <!-- Result Section -->
            <div id="feature-result" class="feature-section">
                <div class="page-title">ডিপ্লোমা রেজাল্ট</div>
                <div class="desc">সর্বশেষ ডিপ্লোমা রেজাল্ট, রুটিন, মার্কশিট ও রেজাল্ট চেক করার লিংক পাবেন।</div>
                <ul>
                    <li><a href="https://btebresult.com/" target="_blank" rel="noopener">BTEB Result Official</a></li>
                    <li><a href="https://bteb.gov.bd/" target="_blank" rel="noopener">BTEB Website</a></li>
                    <li><a href="https://btebadmission.gov.bd/" target="_blank" rel="noopener">Diploma Admission</a></li>
                    <li><a href="https://btebresultszone.com/results" target="_blank" rel="noopener">BTEB Results Zone</a></li>
                </ul>
            </div>
            <!-- Info Section -->
            <div id="feature-info" class="feature-section">
                <div class="page-title">শিক্ষা তথ্য</div>
                <div class="desc">বাংলাদেশের পলিটেকনিক শিক্ষা, সিলেবাস, গাইডলাইন, ক্যারিয়ার, স্কলারশিপ, ও অন্যান্য তথ্য।</div>
                <ul>
                    <li>পলিটেকনিক সিলেবাস <a href="https://bteb.gov.bd/syllabus" target="_blank">দেখুন</a></li>
                    <li>ক্যারিয়ার গাইড <a href="#">শিগগির আসছে</a></li>
                    <li>স্কলারশিপ তথ্য <a href="#">শিগগির আসছে</a></li>
                </ul>
            </div>
            <!-- Contact Section -->
            <div id="feature-contact" class="feature-section">
                <div class="page-title">যোগাযোগ</div>
                <div class="desc" style="background:#1877f2;color:#fff;font-size:1.1em;padding:18px 18px 18px 18px;border-radius:10px;max-width:350px;">
                    <b>যোগাযোগ</b><br><br>
                    ইমেইল: <span style="color:#fff">eyaminahmed166@gmail.com</span><br><br>
                    ফোন: <span style="color:#fff">01784995957</span><br><br>
                    ঠিকানা: ঢাকা, বাংলাদেশ
                </div>
            </div>
        </div>
    </div>
    <!-- Main Content End -->

    <!-- Footer Start -->
    <footer style="background:#1877f2;color:#fff;padding:32px 0 18px 0;margin-top:48px;">
        <div style="max-width:1200px;margin:0 auto;padding:0 18px;">
            <div style="display:flex;flex-wrap:wrap;gap:32px;">
                <div style="flex:1;min-width:220px;">
                    <h3 style="margin-top:0;">Eaminali সম্পর্কে</h3>
                    <p>
                        Eamin পলিটেকনিক বইয়ের ডিজিটাল সংগ্রহশালা। এখানে আপনি পাবেন সকল বিভাগের বই, প্রশ্নপত্র, গাইড, রেজাল্ট, ও শিক্ষা বিষয়ক তথ্য এক জায়গায়।
                    </p>
                </div>
                <div style="flex:1;min-width:220px;">
                    <h3 style="margin-top:0;">দ্রুত লিংক</h3>
                    <ul style="list-style:none;padding:0;">
                        <li><a href="#" class="footer-link" data-feature="home" style="color:#fff;text-decoration:underline;">হোম</a></li>
                        <li><a href="#" class="footer-link" data-feature="books" style="color:#fff;text-decoration:underline;">বই</a></li>
                        <li><a href="#" class="footer-link" data-feature="result" style="color:#fff;text-decoration:underline;">রেজাল্ট</a></li>
                        <li><a href="#" class="footer-link" data-feature="contact" style="color:#fff;text-decoration:underline;">যোগাযোগ</a></li>
                    </ul>
                </div>
                <div style="flex:1;min-width:220px;">
                    <h3 style="margin-top:0;">যোগাযোগ</h3>
                    <p>ইমেইল: eyaminahmed166@gmail.com</p>
                    <p>ফোন: 01784995957</p>
                    <p>ঠিকানা: ঢাকা, বাংলাদেশ</p>
                </div>
            </div>
            <!-- ফিডব্যাক ফর্ম -->
            <div style="margin:32px 0 0 0;max-width:420px;">
                <form id="feedback-form" style="background:#fff;padding:16px 14px;border-radius:10px;box-shadow:0 1px 6px #43e97b22;">
                    <div style="font-weight:600;color:#1877f2;margin-bottom:8px;">আপনার মতামত/ফিডব্যাক দিন</div>
                    <input type="text" id="feedback-name" placeholder="নাম (ঐচ্ছিক)" style="width:100%;margin-bottom:8px;padding:8px;border-radius:6px;border:1px solid #e3f0ff;">
                    <input type="email" id="feedback-email" placeholder="ইমেইল (ঐচ্ছিক)" style="width:100%;margin-bottom:8px;padding:8px;border-radius:6px;border:1px solid #e3f0ff;">
                    <textarea id="feedback-message" placeholder="আপনার মতামত লিখুন..." required style="width:100%;margin-bottom:8px;padding:8px;border-radius:6px;border:1px solid #e3f0ff;height:60px;"></textarea>
                    <button type="submit" style="background:#43e97b;color:#fff;border:none;border-radius:8px;padding:8px 22px;font-size:1em;font-weight:600;cursor:pointer;">পাঠান</button>
                </form>
            </div>
            <hr style="border:0;border-top:1px solid #fff2;">
            <div style="text-align:center;margin-top:18px;font-size:0.98em;">
                &copy; 2025 Eamin | সকল স্বত্ব সংরক্ষিত | Developed by Eamin<br>
                <span style="color:#fff; font-size:1em;">Email: <a href="mailto:eyaminahmed166@gmail.com" style="color:#fff; text-decoration:underline;">eyaminahmed166@gmail.com</a> | Phone: <a href="tel:01784995957" style="color:#fff; text-decoration:underline;">01784995957</a></span>
                <br>
                <!-- Social Media Icons -->
                <div style="margin:18px 0 0 0;">
                    <a href="https://www.facebook.com/share/16mAW16CMh/" target="_blank" title="Facebook" style="display:inline-block;margin:0 8px;"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/facebook.svg" alt="Facebook" style="width:28px;height:28px;filter:invert(1);"></a>
                    <a href="https://youtube.com/@eaminlearneducation?si=oxmTSwePRE4p2w0Z" target="_blank" title="YouTube" style="display:inline-block;margin:0 8px;"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/youtube.svg" alt="YouTube" style="width:28px;height:28px;filter:invert(1);"></a>
                    <a href="https://www.tiktok.com/@eaminlearneducation?_t=ZS-8ykAIHdB9QV&_r=1" target="_blank" title="TikTok" style="display:inline-block;margin:0 8px;"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/tiktok.svg" alt="TikTok" style="width:28px;height:28px;filter:invert(1);"></a>
                </div>
                <button id="view-feedbacks-btn" style="margin-top:10px;background:#fff;color:#1877f2;border:none;border-radius:8px;padding:6px 18px;font-weight:600;cursor:pointer;">ফিডব্যাক দেখুন (শুধু অ্যাডমিন)</button>
                                <button id="view-userbooks-btn" style="margin-top:10px;background:#fff;color:#43e97b;border:none;border-radius:8px;padding:6px 18px;font-weight:600;cursor:pointer;">ইউজার বই দেখুন/ডিলিট (শুধু অ্যাডমিন)</button>
                                <button id="export-userbooks-btn" style="margin-top:10px;background:#fff;color:#ffb300;border:none;border-radius:8px;padding:6px 18px;font-weight:600;cursor:pointer;">এক্সপোর্ট (ডাউনলোড)</button>
                                <label for="import-userbooks-input" style="margin-top:10px;background:#fff;color:#40c4ff;border:none;border-radius:8px;padding:6px 18px;font-weight:600;cursor:pointer;display:inline-block;">ইম্পোর্ট (আপলোড)
                                    <input type="file" id="import-userbooks-input" accept="application/json" style="display:none;">
                                </label>
    <script>
    // Export user books as JSON
    document.addEventListener('DOMContentLoaded', function() {
        const exportBtn = document.getElementById('export-userbooks-btn');
        if (exportBtn) {
            exportBtn.onclick = function() {
                let userBooks = [];
                try {
                    userBooks = JSON.parse(localStorage.getItem('userBooks')) || [];
                } catch (e) { userBooks = []; }
                if (userBooks.length === 0) {
                    alert('কোনো ইউজার অ্যাড করা বই নেই!');
                    return;
                }
                const blob = new Blob([JSON.stringify(userBooks, null, 2)], {type: 'application/json'});
                const url = URL.createObjectURL(blob);
                const a = document.createElement('a');
                a.href = url;
                a.download = 'eaminali_userbooks.json';
                document.body.appendChild(a);
                a.click();
                setTimeout(() => { document.body.removeChild(a); URL.revokeObjectURL(url); }, 100);
            };
        }
        // Import user books from JSON
        const importInput = document.getElementById('import-userbooks-input');
        if (importInput) {
            importInput.onchange = function(e) {
                const file = e.target.files[0];
                if (!file) return;
                const reader = new FileReader();
                reader.onload = function(evt) {
                    try {
                        const imported = JSON.parse(evt.target.result);
                        if (!Array.isArray(imported)) throw new Error('Invalid format');
                        localStorage.setItem('userBooks', JSON.stringify(imported));
                        alert('ইম্পোর্ট সফল!');
                        // রিফ্রেশ book-grid
                        if (typeof renderBooks === 'function') {
                            renderBooks('book-grid', 'all');
                            renderBooks('book-grid-books', 'all');
                        }
                    } catch (err) {
                        alert('ইম্পোর্ট ব্যর্থ! ফাইলটি সঠিক কিনা দেখুন।');
                    }
                    importInput.value = '';
                };
                reader.readAsText(file);
            };
        }
    });
    </script>
    <!-- User Books Modal -->
    <div id="userbooks-modal" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:99999;justify-content:center;align-items:center;">
        <div style="background:#fff;padding:28px 18px;border-radius:14px;box-shadow:0 8px 32px rgba(24,119,242,0.18);min-width:320px;max-width:90vw;max-height:80vh;overflow:auto;">
            <div style="font-size:1.18em;font-weight:600;color:#43e97b;margin-bottom:12px;">ইউজার অ্যাড করা বই</div>
            <div id="userbooks-list"></div>
            <button id="close-userbooks-modal" style="background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;margin-top:16px;">বন্ধ করুন</button>
        </div>
    </div>
    <script>
    // User books view modal logic
    document.addEventListener('DOMContentLoaded', function() {
        const viewBtn = document.getElementById('view-userbooks-btn');
        const modal = document.getElementById('userbooks-modal');
        const closeBtn = document.getElementById('close-userbooks-modal');
        const listDiv = document.getElementById('userbooks-list');
        if (viewBtn && modal && closeBtn && listDiv) {
            function renderUserBooks() {
                let userBooks = [];
                try {
                    userBooks = JSON.parse(localStorage.getItem('userBooks')) || [];
                } catch (e) { userBooks = []; }
                if (userBooks.length === 0) {
                    listDiv.innerHTML = '<div style="color:#ff5252;">কোনো ইউজার অ্যাড করা বই নেই।</div>';
                } else {
                    listDiv.innerHTML = userBooks.map((b, i) => `
                        <div style="border-bottom:1px solid #e3f0ff;padding:8px 0;display:flex;align-items:center;gap:12px;">
                            <img src="${b.cover}" alt="cover" style="width:40px;height:56px;object-fit:cover;border-radius:4px;">
                            <div style="flex:1;">
                                <div style="font-weight:600;color:#1877f2;">${b.title}</div>
                                <div style="font-size:0.98em;">লেখক: ${b.author}</div>
                                <div style="font-size:0.95em;color:#43e97b;">বিভাগ: ${b.genre}, সেমিস্টার: ${b.semester}</div>
                            </div>
                            <button onclick="deleteUserBook(${i})" style="background:#ff5252;color:#fff;border:none;border-radius:6px;padding:4px 12px;cursor:pointer;">ডিলিট</button>
                        </div>
                    `).join('');
                }
            }
            viewBtn.onclick = function() {
                renderUserBooks();
                modal.style.display = 'flex';
            };
            closeBtn.onclick = function() {
                modal.style.display = 'none';
            };
            modal.addEventListener('click', function(e) {
                if (e.target === modal) modal.style.display = 'none';
            });
            // Make deleteUserBook globally accessible
            window.deleteUserBook = function(idx) {
                let userBooks = [];
                try {
                    userBooks = JSON.parse(localStorage.getItem('userBooks')) || [];
                } catch (e) { userBooks = []; }
                if (userBooks[idx] && confirm('আপনি কি নিশ্চিতভাবে এই বইটি ডিলিট করতে চান?')) {
                    userBooks.splice(idx, 1);
                    localStorage.setItem('userBooks', JSON.stringify(userBooks));
                    renderUserBooks();
                    // রিফ্রেশ book-grid
                    if (typeof renderBooks === 'function') {
                        renderBooks('book-grid', 'all');
                        renderBooks('book-grid-books', 'all');
                    }
                }
            };
        }
    });
    </script>
            </div>
        </div>
    </footer>
</footer>


    <!-- Footer End -->
    <script>
        // Navigation feature show/hide
        function showFeature(feature, el) {
            // Hide all sections
            document.querySelectorAll('.feature-section').forEach(s => s.classList.remove('active'));
            // Show selected section
            document.getElementById('feature-' + feature).classList.add('active');
            // Remove active from all nav links
            document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
            // Set active to clicked nav link (if exists)
            if (el) el.classList.add('active');
            // Books section reload genre
            if(feature === 'books') {
                let activeGenre = document.querySelector('.genre-btn.active');
                let genre = activeGenre ? activeGenre.getAttribute('data-genre') : 'all';
                renderBooks('book-grid-books', genre);
            }
        }
        // Sidebar genre filter
        function showGenre(genre, el) {
            document.querySelectorAll('.genre-btn').forEach(btn => btn.classList.remove('active'));
            el.classList.add('active');
            el.setAttribute('data-genre', genre);

            if(!document.getElementById('feature-books').classList.contains('active')) {
                showFeature('books', document.querySelector('.nav-links a[onclick*="books"]'));
            }

            // Custom modal for semester select
            if(genre !== 'all') {
                const modal = document.getElementById('semester-modal');
                const input = document.getElementById('semester-input');
                modal.style.display = 'flex';
                input.value = '';
                input.focus();

                // OK button handler
                document.getElementById('semester-ok').onclick = function() {
                    let semester = input.value.trim();
                    modal.style.display = 'none';
                    if(semester && /^[1-7]$/.test(semester)) {
                        renderBooks('book-grid-books', genre + '_sem' + semester);
                    } else {
                        renderBooks('book-grid-books', genre);
                    }
                };
                // Cancel button handler
                document.getElementById('semester-cancel').onclick = function() {
                    modal.style.display = 'none';
                    renderBooks('book-grid-books', genre);
                };
            } else {
                renderBooks('book-grid-books', genre);
            }
        }
        // Filter bar
        function filterBooks(type, el) {
            document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
            el.classList.add('active');
            renderBooks('book-grid', null, type);
        }
        // Search books
        function searchBooks(query) {
            renderBooks('book-grid', null, null, query);
        }
        // Book data
        const defaultBooks = [
            {
                title: "কম্পিউটার অ্যাপ্লিকেশন",
                author: "মোঃ রফিকুল ইসলাম",
                cover: "https://covers.openlibrary.org/b/id/10523338-L.jpg",
                genre: "computer",
                semester: "৭",
                desc: "কম্পিউটার অ্যাপ্লিকেশন বইটি পলিটেকনিক শিক্ষার্থীদের জন্য অত্যন্ত গুরুত্বপূর্ণ। এতে মাইক্রোসফট অফিস, ইন্টারনেট, ইমেইল, ওয়ার্ড প্রসেসিং, স্প্রেডশিট, প্রেজেন্টেশনসহ আধুনিক কম্পিউটার ব্যবহারিক বিষয় সহজ ভাষায় উপস্থাপন করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "প্রোগ্রামিং ইন সি",
                author: "মোঃ জাহিদুল ইসলাম",
                cover: "https://covers.openlibrary.org/b/id/11122233-L.jpg",
                genre: "computer",
                semester: "৫",
                desc: "এই বইয়ে C প্রোগ্রামিং ভাষার বেসিক থেকে অ্যাডভান্সড টপিক, লজিক, ফাংশন, অ্যারে, স্ট্রাকচার, ফাইল হ্যান্ডলিং ইত্যাদি উদাহরণসহ ব্যাখ্যা করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "ডিজিটাল ইলেকট্রনিক্স",
                author: "ইঞ্জি. মাহবুবুর রহমান",
                cover: "https://covers.openlibrary.org/b/id/11122234-L.jpg",
                genre: "electronics",
                semester: "৪",
                desc: "ডিজিটাল ইলেকট্রনিক্স বইটিতে লজিক গেইট, ফ্লিপ-ফ্লপ, কাউন্টার, মাল্টিপ্লেক্সার, এনকোডার, ডিকোডারসহ আধুনিক ডিজিটাল সার্কিটের বেসিক ও প্র্যাকটিক্যাল বিষয় রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "ইলেকট্রিক্যাল টেকনোলজি",
                author: "আব্দুল কাদের",
                cover: "https://covers.openlibrary.org/b/id/10909258-L.jpg",
                genre: "electrical",
                semester: "৬",
                desc: "ইলেকট্রিক্যাল টেকনোলজি বইটিতে বিদ্যুৎ, কারেন্ট, রেজিস্ট্যান্স, ওহম’স ল, AC/DC সার্কিট, ট্রান্সফরমার, মোটর, পাওয়ার সিস্টেম ইত্যাদি বিষয় সহজভাবে উপস্থাপন করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "ইলেকট্রিক্যাল মেশিন",
                author: "ইঞ্জি. সুমন আহমেদ",
                cover: "https://covers.openlibrary.org/b/id/11122235-L.jpg",
                genre: "electrical",
                semester: "৫",
                desc: "এই বইয়ে DC মেশিন, ট্রান্সফরমার, AC মোটর, জেনারেটর, কন্ট্রোল সার্কিট, মেইনটেন্যান্স ও ট্রাবলশুটিং নিয়ে বিস্তারিত আলোচনা রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "মেকানিক্যাল ডিজাইন",
                author: "মোঃ সাইফুল ইসলাম",
                cover: "https://covers.openlibrary.org/b/id/10523339-L.jpg",
                genre: "mechanical",
                semester: "৫",
                desc: "মেকানিক্যাল ডিজাইন বইটিতে মেশিন ডিজাইন, CAD ড্রয়িং, মেটেরিয়াল সিলেকশন, ফিটিং, ফোর্স অ্যানালাইসিস, ওয়ার্কশপ প্র্যাকটিস ইত্যাদি বিষয় রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "থার্মোডাইনামিক্স",
                author: "ইঞ্জি. রাকিব হাসান",
                cover: "https://covers.openlibrary.org/b/id/11122236-L.jpg",
                genre: "mechanical",
                semester: "৬",
                desc: "থার্মোডাইনামিক্স বইটিতে তাপ, শক্তি, গ্যাস ল, সাইকেল, ইঞ্জিন, রেফ্রিজারেশন, পাওয়ার প্ল্যান্ট ইত্যাদি বিষয় সহজ ভাষায় ব্যাখ্যা করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "সিভিল ইঞ্জিনিয়ারিং",
                author: "মোঃ কামরুল হাসান",
                cover: "https://covers.openlibrary.org/b/id/10909259-L.jpg",
                genre: "civil",
                semester: "৪",
                desc: "সিভিল ইঞ্জিনিয়ারিং বইটিতে বিল্ডিং ডিজাইন, কনস্ট্রাকশন, ম্যাটেরিয়াল, ফাউন্ডেশন, সাইট ম্যানেজমেন্ট, ড্রয়িং ও এস্টিমেটিং নিয়ে বিস্তারিত আলোচনা রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "স্ট্রাকচারাল ডিজাইন",
                author: "ইঞ্জি. ফারহানা ইয়াসমিন",
                cover: "https://covers.openlibrary.org/b/id/11122237-L.jpg",
                genre: "civil",
                semester: "৭",
                desc: "স্ট্রাকচারাল ডিজাইন বইটিতে RCC, স্টিল, ব্রিজ, বিল্ডিং, লোড ক্যালকুলেশন, সেফটি ফ্যাক্টর, ড্রয়িং ও প্র্যাকটিক্যাল ডিজাইন কেস রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "ইলেকট্রনিক্স সার্কিট",
                author: "মোঃ রাশেদুল ইসলাম",
                cover: "https://covers.openlibrary.org/b/id/10523340-L.jpg",
                genre: "electronics",
                semester: "৩",
                desc: "ইলেকট্রনিক্স সার্কিট বইটিতে ডায়োড, ট্রানজিস্টর, অপ-অ্যাম্প, ফিল্টার, এম্প্লিফায়ার, পাওয়ার সাপ্লাই, প্র্যাকটিক্যাল সার্কিট ডিজাইন রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "মাইক্রোকন্ট্রোলার",
                author: "ইঞ্জি. সাইদুর রহমান",
                cover: "https://covers.openlibrary.org/b/id/11122238-L.jpg",
                genre: "electronics",
                semester: "৬",
                desc: "এই বইয়ে 8051, AVR, Arduino, মাইক্রোকন্ট্রোলার প্রোগ্রামিং, ইন্টারফেসিং, প্রজেক্ট উদাহরণসহ ব্যাখ্যা করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "পাওয়ার টেকনোলজি",
                author: "মোঃ আব্দুল্লাহ",
                cover: "https://covers.openlibrary.org/b/id/10909260-L.jpg",
                genre: "power",
                semester: "২",
                desc: "পাওয়ার টেকনোলজি বইটিতে পাওয়ার সিস্টেম, সাবস্টেশন, ট্রান্সমিশন, ডিস্ট্রিবিউশন, সেফটি, মেইনটেন্যান্স ইত্যাদি বিষয় রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "পাওয়ার প্ল্যান্ট",
                author: "ইঞ্জি. মেহেদী হাসান",
                cover: "https://covers.openlibrary.org/b/id/11122239-L.jpg",
                genre: "power",
                semester: "৭",
                desc: "এই বইয়ে পাওয়ার প্ল্যান্টের ধরন, অপারেশন, কন্ট্রোল, সেফটি, পরিবেশগত বিষয়, ওয়ার্কিং প্রিন্সিপল ইত্যাদি আলোচনা করা হয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "RAC টেকনোলজি",
                author: "মোঃ রিয়াজুল ইসলাম",
                cover: "https://covers.openlibrary.org/b/id/10523341-L.jpg",
                genre: "rac",
                semester: "১",
                desc: "RAC (রেফ্রিজারেশন অ্যান্ড এয়ার কন্ডিশনিং) বইটিতে বেসিক কনসেপ্ট, কম্প্রেসার, কুলিং সিস্টেম, গ্যাস, ফ্রিজ, এসি মেইনটেন্যান্স ইত্যাদি রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            },
            {
                title: "রেফ্রিজারেশন অ্যান্ড এয়ার কন্ডিশনিং",
                author: "ইঞ্জি. তানভীর আহমেদ",
                cover: "https://covers.openlibrary.org/b/id/11122240-L.jpg",
                genre: "rac",
                semester: "৫",
                desc: "এই বইয়ে রেফ্রিজারেশন সাইকেল, এয়ার কন্ডিশনিং, কুলিং লোড ক্যালকুলেশন, ইনস্টলেশন, ফল্ট ফাইন্ডিং, প্র্যাকটিক্যাল গাইডলাইন রয়েছে।",
                downloadUrl: "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf"
            }
        ];

        // Get books from localStorage or use default
        function getBooks() {
            let userBooks = [];
            try {
                userBooks = JSON.parse(localStorage.getItem('userBooks')) || [];
            } catch (e) { userBooks = []; }
            return [...defaultBooks, ...userBooks];
        }

        // Add new book to localStorage
        function addBook(book) {
            let userBooks = [];
            try {
                userBooks = JSON.parse(localStorage.getItem('userBooks')) || [];
            } catch (e) { userBooks = []; }
            userBooks.push(book);
            localStorage.setItem('userBooks', JSON.stringify(userBooks));
        }
        // Render books
        function renderBooks(gridId, genre = null, filter = null, search = "") {
            let filtered = getBooks();
            if(genre && genre !== 'all') {
                // Check for semester filter (e.g. computer_sem7)
                const match = genre.match(/^(\w+)_sem(\d)$/);
                if(match) {
                    // Support both English and Bengali digits for semester
                    const semEng = match[2];
                    const semBn = ['০','১','২','৩','৪','৫','৬','৭','৮','৯'][parseInt(semEng,10)];
                    filtered = filtered.filter(b => b.genre === match[1] && (b.semester === semEng || b.semester === semBn));
                } else {
                    filtered = filtered.filter(b => b.genre === genre);
                }
            }
            if(search) filtered = filtered.filter(b =>
                b.title.includes(search) ||
                b.author.includes(search) ||
                (b.semester && (b.semester.includes(search) || (['০','১','২','৩','৪','৫','৬','৭','৮','৯'][parseInt(search,10)] === b.semester)))
            );
            if(filter === 'top') filtered = filtered.slice(0,3);
            if(filter === 'popular') filtered = filtered.reverse();
            if(filter === 'recent') filtered = filtered.slice(-3);

            // যদি কোনো বই না পাওয়া যায়
            if(filtered.length === 0) {
                document.getElementById(gridId).innerHTML = `
                    <div style="grid-column:1/-1;text-align:center;padding:48px 0;">
                        <div style="font-size:1.3em;color:#1877f2;font-weight:600;margin-bottom:12px;">
                            বই পাওয়া যায়নি!
                        </div>
                        <div style="font-size:1.08em;color:#43e97b;">
                            কাজ চলছে, দ্রুত চলে আসবে।
                        </div>
                    </div>
                `;
                return;
            }

            document.getElementById(gridId).innerHTML = filtered.map((b, idx) => `
                <div class="book-card" data-book-idx="${idx}">
                    <img src="${b.cover}" alt="Book Cover" class="book-cover">
                    <div class="book-title">${b.title}</div>
                    <div class="book-author">লেখক: ${b.author}</div>
                    <div style="font-size:0.98em;color:#43e97b;margin-bottom:8px;">সেমিস্টার: ${b.semester}</div>
                    <div class="book-actions">
                        ${b.downloadUrl ? `<a class='book-btn' href='${b.downloadUrl}' target='_blank'>ডাউনলোড</a>` : `<button class=\"book-btn\" onclick=\"alert('ডাউনলোড লিংক শিগগির আসছে!')\">ডাউনলোড</button>`}
                        <button class="book-btn" onclick="showBookDetail(${idx}, '${gridId}')">বিস্তারিত</button>
                    </div>
                </div>
            `).join('');
        // Book details modal
        if (!document.getElementById('book-detail-modal')) {
            const modal = document.createElement('div');
            modal.id = 'book-detail-modal';
            modal.style = 'display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:99999;justify-content:center;align-items:center;';
            modal.innerHTML = `
                <div id="book-detail-modal-content" style="background:#fff;padding:28px 18px;border-radius:14px;box-shadow:0 8px 32px rgba(24,119,242,0.18);min-width:320px;max-width:90vw;max-height:80vh;overflow:auto;">
                    <div id="book-detail-modal-body"></div>
                </div>
            `;
            document.body.appendChild(modal);
            modal.addEventListener('click', function(e) {
                if (e.target === modal) modal.style.display = 'none';
            });
        }

        window.showBookDetail = function(idx, gridId) {
            let booksArr = getBooks();
            // If grid is 'book-grid-books', filter by genre if needed
            if (gridId === 'book-grid-books') {
                // No extra filter, as renderBooks already filtered
            }
            const b = booksArr[idx];
            if (!b) return;
            const modal = document.getElementById('book-detail-modal');
            const body = document.getElementById('book-detail-modal-body');
            body.innerHTML = `
                <div style='display:flex;gap:18px;align-items:flex-start;flex-wrap:wrap;'>
                    <img src="${b.cover}" alt="Book Cover" style="width:120px;height:160px;object-fit:cover;border-radius:10px;box-shadow:0 2px 8px #43e97b22;">
                    <div style='flex:1;'>
                        <div style='font-size:1.3em;font-weight:700;color:#1877f2;margin-bottom:6px;'>${b.title}</div>
                        <div style='font-size:1.08em;color:#444;margin-bottom:6px;'>লেখক: ${b.author}</div>
                        <div style='font-size:1em;color:#43e97b;margin-bottom:6px;'>বিভাগ: ${b.genre} | সেমিস্টার: ${b.semester}</div>
                        <div style='margin-bottom:10px;color:#222;'>${b.desc ? b.desc : 'বিস্তারিত তথ্য নেই।'}</div>
                        <div style='margin-bottom:10px;'>
                        ${b.downloadUrl ? `<a class='book-btn' href='${b.downloadUrl}' target='_blank'>ডাউনলোড</a>` : ''}
                        </div>
                    </div>
                </div>
                <div style='margin-top:18px;display:flex;gap:12px;'>
                    <button id="close-book-detail-modal" style="background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;">বন্ধ করুন</button>
                    <button id="read-book-btn" style="background:#43e97b;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;">পড়ুন</button>
                </div>
            `;
            // Bind close button again (since modal content is replaced)
            document.getElementById('close-book-detail-modal').onclick = function() {
                modal.style.display = 'none';
            };
            // Read button: open downloadUrl if exists, else alert
            document.getElementById('read-book-btn').onclick = function() {
                if (b.downloadUrl) {
                    window.open(b.downloadUrl, '_blank');
               
                } else {
                    alert('এই বইটি পড়ার জন্য কোনো লিংক নেই।');
                }
            };
            modal.style.display = 'flex';
        };
            // Book card hover response (show tooltip or highlight)
            document.querySelectorAll('.book-card').forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.boxShadow = '0 6px 24px rgba(24,119,242,0.18)';
                    this.style.transform = 'scale(1.04)';
                    this.title = 'বিস্তারিত দেখতে ক্লিক করুন';
                });
                card.addEventListener('mouseleave', function() {
                    this.style.boxShadow = '';
                    this.style.transform = '';
                    this.title = '';
                });
                // Remove alert on click; only show details via button
            });
            // Book card search/filter by title or author (live search on hover)
            function enableBookCardSearch() {
                document.querySelectorAll('.book-card').forEach(card => {
                    card.addEventListener('mouseenter', function() {
                        // Show a small search input above the card
                        if (!this.querySelector('.book-search-hover')) {
                            const input = document.createElement('input');
                            input.type = 'text';
                            input.className = 'book-search-hover';
                            input.placeholder = 'এই বইয়ের মধ্যে খুঁজুন...';
                            input.style.position = 'absolute';
                            input.style.top = '-32px';
                            input.style.left = '50%';
                            input.style.transform = 'translateX(-50%)';
                            input.style.width = '160px';
                            input.style.padding = '4px 8px';
                            input.style.borderRadius = '6px';
                            input.style.border = '1px solid #43e97b';
                            input.style.background = '#fff';
                            input.style.fontSize = '0.98em';
                            input.style.zIndex = '10';
                            input.oninput = (e) => {
                                const val = e.target.value.trim();
                                const title = card.querySelector('.book-title').textContent;
                                const author = card.querySelector('.book-author').textContent;
                                if (
                                    title.includes(val) ||
                                    author.includes(val)
                                ) {
                                    card.style.opacity = '1';
                                } else {
                                    card.style.opacity = '0.4';
                                }
                            };
                            card.style.position = 'relative';
                            card.appendChild(input);
                        }
                    });
                    card.addEventListener('mouseleave', function() {
                        const input = this.querySelector('.book-search-hover');
                        if (input) input.remove();
                        this.style.opacity = '1';
                    });
                });
            }
            enableBookCardSearch();
        }


        // Initial render
        renderBooks('book-grid', 'all');
        renderBooks('book-grid-books', 'all');
        // Ensure correct feature shows on reload
        document.querySelectorAll('.nav-links a').forEach(a => {
            a.addEventListener('click', function(e){
                e.preventDefault();
                const feature = this.getAttribute('onclick')?.match(/showFeature\('(\w+)'/)?.[1];
                showFeature(feature, this);
            });
        });
        // Ensure genre buttons have data-genre attribute
        document.querySelectorAll('.genre-btn').forEach(btn => {
            if(!btn.hasAttribute('data-genre')) {
                btn.setAttribute('data-genre', btn.textContent.trim() === "সব বই" ? "all" : btn.textContent.trim().toLowerCase().replace(/ /g, ''));
            }
        });
        // Footer links click: show feature from any section
        document.querySelectorAll('.footer-link').forEach(link => {
            link.addEventListener('click', function(e){
                e.preventDefault();
                const feature = this.getAttribute('data-feature');
                showFeature(feature);
                // Fix: If books section, set active genre and re-render
                if(feature === 'books') {
                    let activeGenre = document.querySelector('.genre-btn.active');
                    let genre = activeGenre ? activeGenre.getAttribute('data-genre') : 'all';
                    renderBooks('book-grid-books', genre);
                }
            });
        });
    </script>
    <!-- Feedback Modal -->
    <div id="feedback-modal" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:99999;justify-content:center;align-items:center;">
        <div style="background:#fff;padding:28px 18px;border-radius:14px;box-shadow:0 8px 32px rgba(24,119,242,0.18);min-width:320px;max-width:90vw;max-height:80vh;overflow:auto;">
            <div style="font-size:1.18em;font-weight:600;color:#1877f2;margin-bottom:12px;">ইউজার ফিডব্যাক</div>
            <div id="feedback-list"></div>
            <button id="close-feedback-modal" style="background:#ff5252;color:#fff;font-weight:600;padding:6px 18px;border:none;border-radius:8px;cursor:pointer;margin-top:16px;">বন্ধ করুন</button>
        </div>
    </div>
    <script>
    // Feedback view modal logic
    document.addEventListener('DOMContentLoaded', function() {
        const viewBtn = document.getElementById('view-feedbacks-btn');
        const modal = document.getElementById('feedback-modal');
        const closeBtn = document.getElementById('close-feedback-modal');
        const listDiv = document.getElementById('feedback-list');
        if (viewBtn && modal && closeBtn && listDiv) {
            viewBtn.onclick = function() {
                let feedbacks = [];
                try {
                    feedbacks = JSON.parse(localStorage.getItem('feedbacks')) || [];
                } catch (e) { feedbacks = []; }
                if (feedbacks.length === 0) {
                    listDiv.innerHTML = '<div style="color:#ff5252;">কোনো ফিডব্যাক পাওয়া যায়নি।</div>';
                } else {
                    listDiv.innerHTML = feedbacks.map(f => `
                        <div style="border-bottom:1px solid #e3f0ff;padding:8px 0;">
                            <div style="font-weight:600;color:#43e97b;">${f.name ? f.name : 'নাম নেই'}</div>
                            <div style="color:#1877f2;font-size:0.98em;">${f.email ? f.email : ''}</div>
                            <div style="margin:6px 0;">${f.message}</div>
                            <div style="font-size:0.88em;color:#888;">${new Date(f.time).toLocaleString('bn-BD')}</div>
                        </div>
                    `).join('');
                }
                modal.style.display = 'flex';
            };
            closeBtn.onclick = function() {
                modal.style.display = 'none';
            };
            // Modal close on outside click
            modal.addEventListener('click', function(e) {
                if (e.target === modal) modal.style.display = 'none';
            });
        }
    });
    </script>
    <script>
    // Feedback form handler
    document.addEventListener('DOMContentLoaded', function() {
        const feedbackForm = document.getElementById('feedback-form');
        if (feedbackForm) {
            feedbackForm.onsubmit = function(e) {
                e.preventDefault();
                const name = document.getElementById('feedback-name').value.trim();
                const email = document.getElementById('feedback-email').value.trim();
                const message = document.getElementById('feedback-message').value.trim();
                if (!message) {
                    alert('মতামত লিখুন!');
                    return;
                }
                let feedbacks = [];
                try {
                    feedbacks = JSON.parse(localStorage.getItem('feedbacks')) || [];
                } catch (e) { feedbacks = []; }
                feedbacks.push({ name, email, message, time: new Date().toISOString() });
                localStorage.setItem('feedbacks', JSON.stringify(feedbacks));
                feedbackForm.reset();
                alert('ধন্যবাদ! আপনার মতামত সংরক্ষিত হয়েছে।');
            };
        }
    });
    </script>
    <!-- Semester Modal HTML (hidden by default) -->
    <div id="semester-modal" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(24,119,242,0.15);z-index:9999;justify-content:center;align-items:center;">
        <div style="background:linear-gradient(120deg,#43e97b,#1877f2,#ffb300);padding:32px 28px;border-radius:18px;box-shadow:0 8px 32px rgba(24,119,242,0.18);text-align:center;min-width:320px;">
            <div style="font-size:1.18em;font-weight:600;color:#fff;margin-bottom:18px;">আপনি কোন সেমিস্টারের বই দেখতে চান?</div>
            <input id="semester-input" type="number" min="1" max="7" placeholder="১-৭ লিখুন" style="padding:10px 16px;border-radius:8px;border:1px solid #fff;width:80%;font-size:1.08em;margin-bottom:18px;">
            <br>
            <button id="semester-ok" style="background:#fff;color:#1877f2;font-weight:600;padding:8px 22px;border:none;border-radius:8px;cursor:pointer;margin-right:10px;">OK</button>
            <button id="semester-cancel" style="background:#ff5252;color:#fff;font-weight:600;padding:8px 22px;border:none;border-radius:8px;cursor:pointer;">Cancel</button>
        </div>
    </div>
</body>
</body>
<!-- Contact Us Section (Bottom) -->
<div style="background:#e3f0ff;padding:28px 0 24px 0;text-align:center;">
    <div style="font-size:1.3em;font-weight:700;color:#22b573;margin-bottom:10px;">Contact Us</div>
    <div style="font-size:1.08em;color:#22b573;margin-bottom:10px;">
        For any questions, suggestions, or support, reach out to us:
    </div>
    <div style="margin-bottom:10px;">
        <a href="https://www.facebook.com/share/16mAW16CMh/" target="_blank" style="display:inline-block;margin:0 10px;vertical-align:middle;">
            <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/facebook.svg" alt="Facebook" style="width:28px;height:28px;filter:invert(27%) sepia(99%) saturate(749%) hue-rotate(186deg) brightness(95%) contrast(92%);vertical-align:middle;">
            <span style="color:#22b573;font-weight:600;margin-left:6px;vertical-align:middle;">Facebook</span>
        </a>
        <a href="mailto:eyaminahmed166@gmail.com" style="display:inline-block;margin:0 10px;vertical-align:middle;">
            <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/gmail.svg" alt="Email" style="width:28px;height:28px;filter:invert(27%) sepia(99%) saturate(749%) hue-rotate(186deg) brightness(95%) contrast(92%);vertical-align:middle;">
            <span style="color:#22b573;font-weight:600;margin-left:6px;vertical-align:middle;">eyaminahmed166@gmail.com</span>
        </a>
    </div>
</div>
</html>
