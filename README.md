<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Free Diamond Now - Redeem Simulator</title>
    <link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@400;600;700&family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #8a2be2;
            --secondary: #ff1493;
            --accent: #00ffff;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --success: #00ff7f;
            --warning: #ffcc00;
            --danger: #ff4757;
            --gradient: linear-gradient(135deg, var(--primary), var(--secondary));
            --gradient-light: linear-gradient(135deg, #a45ee5, #ff5ca8);
            --shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            --border-radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: var(--dark);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(138, 43, 226, 0.2) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(255, 20, 147, 0.2) 0%, transparent 20%);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: rgba(26, 26, 46, 0.8);
            backdrop-filter: blur(10px);
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .logo i {
            font-size: 2rem;
        }

        /* Page Styles */
        .page {
            display: none;
            min-height: 80vh;
            padding: 40px 0;
            animation: fadeIn 0.5s ease;
        }

        .page.active {
            display: block;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--shadow);
            border: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 30px;
        }

        h1 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 20px;
            background: var(--gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 700;
        }

        h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--accent);
        }

        p {
            line-height: 1.6;
            margin-bottom: 15px;
            font-size: 1.1rem;
        }

        .bengali-text {
            font-family: 'Hind Siliguri', sans-serif;
        }

        /* Button Styles */
        .btn {
            display: inline-block;
            padding: 14px 30px;
            background: var(--gradient);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            text-decoration: none;
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
            background: var(--gradient-light);
        }

        .btn:active {
            transform: translateY(1px);
        }

        .btn-large {
            padding: 18px 40px;
            font-size: 1.3rem;
            margin: 20px auto;
            display: block;
            width: 100%;
            max-width: 300px;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        /* Form Styles */
        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--accent);
        }

        input, select {
            width: 100%;
            padding: 14px;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: var(--border-radius);
            color: white;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        input:focus, select:focus {
            outline: none;
            border-color: var(--accent);
            box-shadow: 0 0 0 2px rgba(0, 255, 255, 0.2);
        }

        .radio-group {
            display: flex;
            gap: 20px;
            margin-top: 10px;
        }

        .radio-option {
            flex: 1;
            text-align: center;
        }

        .radio-option input {
            display: none;
        }

        .radio-option label {
            display: block;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: var(--border-radius);
            cursor: pointer;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        .radio-option input:checked + label {
            background: rgba(0, 255, 255, 0.2);
            border-color: var(--accent);
            color: var(--accent);
        }

        /* Loading Animation */
        .loading-container {
            text-align: center;
            padding: 40px 0;
        }

        .progress-bar {
            height: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin: 30px 0;
            overflow: hidden;
            position: relative;
        }

        .progress {
            height: 100%;
            width: 0%;
            background: var(--gradient);
            border-radius: 10px;
            transition: width 0.1s linear;
        }

        .progress-text {
            margin-top: 10px;
            font-size: 1.1rem;
            color: var(--accent);
        }

        .activity-messages {
            margin-top: 30px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: var(--border-radius);
            max-height: 200px;
            overflow-y: auto;
        }

        .activity-item {
            padding: 10px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            animation: slideIn 0.5s ease;
        }

        .activity-item:last-child {
            border-bottom: none;
        }

        /* Tips & Messages */
        .tips-container {
            margin: 30px 0;
            padding: 20px;
            background: rgba(0, 255, 255, 0.1);
            border-radius: var(--border-radius);
            border-left: 4px solid var(--accent);
        }

        .tip-text {
            font-style: italic;
            color: var(--accent);
        }

        /* Redeem Options */
        .redeem-options {
            display: flex;
            gap: 20px;
            margin: 30px 0;
        }

        .redeem-option {
            flex: 1;
            text-align: center;
            padding: 25px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--border-radius);
            transition: all 0.3s ease;
        }

        .redeem-option:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-5px);
        }

        .redeem-option i {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--accent);
        }

        /* Confirmation Page */
        .confirmation-details {
            margin: 30px 0;
            padding: 20px;
            background: rgba(0, 255, 255, 0.05);
            border-radius: var(--border-radius);
        }

        .detail-row {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .detail-row:last-child {
            border-bottom: none;
        }

        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            animation: fadeIn 0.3s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: var(--dark);
            padding: 30px;
            border-radius: var(--border-radius);
            max-width: 500px;
            width: 90%;
            text-align: center;
            box-shadow: var(--shadow);
            border: 1px solid var(--accent);
            animation: scaleIn 0.3s ease;
        }

        .modal-icon {
            font-size: 4rem;
            color: var(--success);
            margin-bottom: 20px;
        }

        /* Ads */
        .ad-container {
            margin: 20px 0;
            text-align: center;
        }

        .ad-banner {
            width: 100%;
            max-width: 728px;
            height: 90px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--border-radius);
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }

        .social-bar {
            position: fixed;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: 10px;
            z-index: 99;
        }

        .social-ad {
            width: 120px;
            height: 120px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--border-radius);
            display: flex;
            align-items: center;
            justify-content: center;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.8rem;
            text-align: center;
            padding: 10px;
        }

        /* Error Message */
        .error-message {
            color: var(--danger);
            font-size: 0.9rem;
            margin-top: 5px;
            display: none;
        }

        .error-message.show {
            display: block;
        }

        /* Footer */
        footer {
            background: rgba(0, 0, 0, 0.5);
            padding: 20px 0;
            text-align: center;
            margin-top: 50px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes scaleIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        @keyframes slideIn {
            from { transform: translateY(10px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .pulse {
            animation: pulse 2s infinite;
        }

        /* Responsive Styles */
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .card {
                padding: 20px;
            }
            
            .redeem-options {
                flex-direction: column;
            }
            
            .social-bar {
                display: none;
            }
            
            .radio-group {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="logo">
                <i>💎</i>
                <span>Free Diamond Now</span>
            </div>
        </div>
    </header>

    <!-- Ad Banner Top -->
    <div class="ad-container">
        <div class="ad-banner" id="top-ad">
            <!-- <script type="text/javascript">
	atOptions = {
		'key' : 'da5cdd1d332d3032394c6dd6e6224ecc',
		'format' : 'iframe',
		'height' : 90,
		'width' : 728,
		'params' : {}
	};
</script>
<script type="text/javascript" src="//www.highperformanceformat.com/da5cdd1d332d3032394c6dd6e6224ecc/invoke.js"></script> -->
            <div style="width: 100%; height: 100%; background: linear-gradient(135deg, #4ecdc4, #556270); border-radius: 8px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold;">
                LIMITED TIME OFFER: GET FREE DIAMONDS NOW!
            </div>
        </div>
    </div>

    <!-- Social Bar Ad -->
    <div class="social-bar">
        <div class="social-ad" id="social-ad-1">
            <!-- <script type='text/javascript' src='//pl26987417.effectivegatecpm.com/43/5d/62/435d62c15267ad8ac72876a00ea204bb.js'></script> -->
            <div style="text-align: center; padding: 10px; background: linear-gradient(135deg, #ff6b6b, #ffa726); border-radius: 8px; color: white; font-weight: bold;">
                FOLLOW US FOR 500 DIAMONDS!
            </div>
        </div>
        <div class="social-ad" id="social-ad-2">
            Special Offer: Limited Time!
        </div>
    </div>

    <!-- Home Page -->
    <section id="home-page" class="page active">
        <div class="container">
            <div class="card">
                <h1>Free Diamond Now</h1>
                <p class="bengali-text">বিনামূল্যে ডায়মন্ড পেতে এখনই ক্লিক করুন! সহজ প্রক্রিয়ায় গেম ডায়মন্ড সংগ্রহ করুন।</p>
                <p>Get free diamonds for your favorite games in just a few simple steps. Thousands of players have already claimed their rewards!</p>
                
                <div class="tips-container">
                    <p class="tip-text" id="home-tip">Tip: Make sure you have a stable internet connection before starting the process.</p>
                </div>
                
                <button id="start-btn" class="btn btn-large pulse">
                    Free Diamond Now
                </button>
            </div>
            
            <div class="card">
                <h2>Recent Activity</h2>
                <div class="activity-messages" id="activity-feed">
                    <!-- Activity messages will be populated by JavaScript -->
                </div>
            </div>
        </div>
    </section>

    <!-- Loading Page -->
    <section id="loading-page" class="page">
        <div class="container">
            <div class="card">
                <h1>Processing Your Request</h1>
                <p class="bengali-text">আপনার অনুরোধ প্রক্রিয়া করা হচ্ছে, অনুগ্রহ করে অপেক্ষা করুন...</p>
                <p>Please wait while we process your request. This usually takes about 10 seconds.</p>
                
                <div class="loading-container">
                    <div class="progress-bar">
                        <div class="progress" id="progress-bar"></div>
                    </div>
                    <div class="progress-text" id="progress-text">0%</div>
                </div>
                
                <div class="activity-messages" id="loading-activity">
                    <!-- Loading activity messages will be populated by JavaScript -->
                </div>
            </div>
        </div>
    </section>

    <!-- Step 1 - Create Account -->
    <section id="step1-page" class="page">
        <div class="container">
            <div class="card">
                <h1>Step 1: Account Information</h1>
                <p class="bengali-text">আপনার গেম অ্যাকাউন্টের তথ্য প্রদান করুন</p>
                
                <div class="tips-container">
                    <p class="tip-text" id="step1-tip">Tip: Make sure your game UID is correct to receive diamonds.</p>
                </div>
                
                <form id="account-form">
                    <div class="form-group">
                        <label for="game-uid">Game UID</label>
                        <input type="text" id="game-uid" placeholder="Enter your Game UID" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="game-name">Game Name</label>
                        <input type="text" id="game-name" placeholder="Enter your Game Name" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="game-level">Level</label>
                        <input type="number" id="game-level" placeholder="Enter your Level" min="1" required>
                    </div>
                    
                    <div class="form-group">
                        <label>Account Type</label>
                        <div class="radio-group">
                            <div class="radio-option">
                                <input type="radio" id="gmail" name="account-type" value="Gmail" checked>
                                <label for="gmail">Gmail</label>
                            </div>
                            <div class="radio-option">
                                <input type="radio" id="facebook" name="account-type" value="Facebook">
                                <label for="facebook">Facebook</label>
                            </div>
                        </div>
                    </div>
                    
                    <button type="submit" class="btn btn-large">Continue</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Step 2 - Redeem Code -->
    <section id="step2-page" class="page">
        <div class="container">
            <div class="card">
                <h1>Step 2: Redeem Code</h1>
                <p class="bengali-text">আপনার রিডিম কোডটি প্রবেশ করুন</p>
                
                <div class="tips-container">
                    <p class="tip-text" id="step2-tip">Tip: Make sure to enter the code exactly as shown, including any dashes.</p>
                </div>
                
                <form id="redeem-form">
                    <div class="form-group">
                        <label for="redeem-code">Redeem Code</label>
                        <input type="text" id="redeem-code" placeholder="Enter your redeem code" required>
                        <div class="error-message" id="code-error">Invalid redeem code. Please enter the correct code.</div>
                    </div>
                    
                    <button type="submit" class="btn btn-large">Submit Code</button>
                </form>
                
                <div class="redeem-options">
                    <div class="redeem-option">
                        <i>🔑</i>
                        <h3>Get Redeem Code</h3>
                        <p>Don't have a code? Get one now!</p>
                        <button class="btn" id="get-code-btn">Get Code</button>
                    </div>
                    
                    <div class="redeem-option">
                        <i>🎥</i>
                        <h3>Tutorial Video</h3>
                        <p>Watch how to get and use redeem codes</p>
                        <button class="btn btn-secondary" id="tutorial-btn">Watch Tutorial</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Step 3 - Final Confirmation -->
    <section id="step3-page" class="page">
        <div class="container">
            <div class="card">
                <h1>Step 3: Confirmation</h1>
                <p class="bengali-text">আপনার তথ্য নিশ্চিত করুন এবং প্রক্রিয়া সম্পন্ন করুন</p>
                
                <div class="confirmation-details">
                    <div class="detail-row">
                        <span>Game UID:</span>
                        <span id="confirm-uid">-</span>
                    </div>
                    <div class="detail-row">
                        <span>Game Name:</span>
                        <span id="confirm-name">-</span>
                    </div>
                    <div class="detail-row">
                        <span>Level:</span>
                        <span id="confirm-level">-</span>
                    </div>
                    <div class="detail-row">
                        <span>Account Type:</span>
                        <span id="confirm-type">-</span>
                    </div>
                    <div class="detail-row">
                        <span>Redeem Code:</span>
                        <span id="confirm-code">-</span>
                    </div>
                </div>
                
                <button id="final-continue-btn" class="btn btn-large">Complete Process</button>
            </div>
        </div>
    </section>

    <!-- Ad Banner Bottom -->
    <div class="ad-container">
        <div class="ad-banner" id="bottom-ad">
            <!-- Advertisement will be loaded here -->
            Loading advertisement...
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; <span id="current-year">2023</span> Free Diamond Now. All rights reserved.</p>
        </div>
    </footer>

    <!-- Modal -->
    <div class="modal" id="success-modal">
        <div class="modal-content">
            <div class="modal-icon">✅</div>
            <h2>Success!</h2>
            <p class="bengali-text">আপনার অনুরোধ সফলভাবে জমা হয়েছে। ২৪ ঘন্টার মধ্যে আপনার ডায়মন্ড পেয়ে যাবেন।</p>
            <p>Your request has been submitted successfully. You will receive your diamonds within 24 hours.</p>
            <button class="btn" id="modal-close-btn">Close</button>
        </div>
    </div>

    <script>
        // DOM Elements
        const pages = document.querySelectorAll('.page');
        const homePage = document.getElementById('home-page');
        const loadingPage = document.getElementById('loading-page');
        const step1Page = document.getElementById('step1-page');
        const step2Page = document.getElementById('step2-page');
        const step3Page = document.getElementById('step3-page');
        
        const startBtn = document.getElementById('start-btn');
        const accountForm = document.getElementById('account-form');
        const redeemForm = document.getElementById('redeem-form');
        const getCodeBtn = document.getElementById('get-code-btn');
        const tutorialBtn = document.getElementById('tutorial-btn');
        const finalContinueBtn = document.getElementById('final-continue-btn');
        const modalCloseBtn = document.getElementById('modal-close-btn');
        
        const progressBar = document.getElementById('progress-bar');
        const progressText = document.getElementById('progress-text');
        const activityFeed = document.getElementById('activity-feed');
        const loadingActivity = document.getElementById('loading-activity');
        
        const homeTip = document.getElementById('home-tip');
        const step1Tip = document.getElementById('step1-tip');
        const step2Tip = document.getElementById('step2-tip');
        
        const confirmUid = document.getElementById('confirm-uid');
        const confirmName = document.getElementById('confirm-name');
        const confirmLevel = document.getElementById('confirm-level');
        const confirmType = document.getElementById('confirm-type');
        const confirmCode = document.getElementById('confirm-code');
        
        const successModal = document.getElementById('success-modal');
        const codeError = document.getElementById('code-error');
        
        // Your specific redeem code
        const VALID_REDEEM_CODE = "FFIT2025YTBD";
        
        // Your redirect links (replace with your actual links)
        const REDIRECT_LINKS = {
            step1: "https://www.effectivegatecpm.com/d1zc5436?key=a6217b80de5ed263514d2d191e346653", // Replace with your actual link
            getCode: "https://droplink.co/B5Co58", // Replace with your actual link
            tutorial: "https://your-tutorial-link.com", // Replace with your actual link
            final: "https://www.effectivegatecpm.com/d1zc5436?key=a6217b80de5ed263514d2d191e346653", // Replace with your actual link
            submitRedirect: "https://linulade.lv/M3o4QTBHMGM2TDFpN0c=" // আপনার লিংকটি এখানে বসান
        };

        // Data for random messages
        const homeTips = [
            "Tip: Make sure you have a stable internet connection before starting the process.",
            "Tip: Complete all steps to successfully receive your free diamonds.",
            "Tip: This process works for all popular mobile games.",
            "Tip: Thousands of players have successfully claimed diamonds using our service."
        ];
        
        const step1Tips = [
            "Tip: Make sure your game UID is correct to receive diamonds.",
            "Tip: Your game level must be at least 10 to qualify for diamond rewards.",
            "Tip: Double-check your account type selection before continuing.",
            "Tip: We never ask for your password or sensitive account information."
        ];
        
        const step2Tips = [
            "Tip: Make sure to enter the code exactly as shown, including any dashes.",
            "Tip: Redeem codes are case-sensitive, so check capitalization.",
            "Tip: If your code doesn't work, try getting a new one.",
            "Tip: Each redeem code can only be used once per account."
        ];
        
        const activityMessages = [
            "ID-874393 just redeemed 310 diamonds",
            "Player-129102 claimed 150 diamonds",
            "User-482910 received 200 diamonds",
            "Gamer-572039 redeemed 500 diamonds",
            "Player-839201 claimed 100 diamonds",
            "ID-294810 just got 350 diamonds",
            "User-672940 redeemed 250 diamonds",
            "Gamer-183920 claimed 400 diamonds"
        ];
        
        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Set current year in footer
            document.getElementById('current-year').textContent = new Date().getFullYear();
            
            // Initialize random tips
            updateRandomTips();
            
            // Initialize activity feed
            initializeActivityFeed();
            
            // Load ads
            loadAds();
            
            // Check if we need to show step 3 after redirect
            checkRedirectStatus();
            
            // Event Listeners
            startBtn.addEventListener('click', startProcess);
            accountForm.addEventListener('submit', goToStep2);
            redeemForm.addEventListener('submit', validateRedeemCode);
            getCodeBtn.addEventListener('click', getRedeemCode);
            tutorialBtn.addEventListener('click', showTutorial);
            finalContinueBtn.addEventListener('click', completeProcess);
            modalCloseBtn.addEventListener('click', closeModal);
        });
        
        // Functions
        function showPage(page) {
            pages.forEach(p => p.classList.remove('active'));
            page.classList.add('active');
        }
        
        function updateRandomTips() {
            homeTip.textContent = homeTips[Math.floor(Math.random() * homeTips.length)];
            step1Tip.textContent = step1Tips[Math.floor(Math.random() * step1Tips.length)];
            step2Tip.textContent = step2Tips[Math.floor(Math.random() * step2Tips.length)];
        }
        
        function initializeActivityFeed() {
            // Clear existing activities
            activityFeed.innerHTML = '';
            loadingActivity.innerHTML = '';
            
            // Add 5 random activities to home page
            for (let i = 0; i < 5; i++) {
                const message = activityMessages[Math.floor(Math.random() * activityMessages.length)];
                const activityItem = document.createElement('div');
                activityItem.className = 'activity-item';
                activityItem.textContent = message;
                activityFeed.appendChild(activityItem);
            }
            
            // Add 3 random activities to loading page
            for (let i = 0; i < 3; i++) {
                const message = activityMessages[Math.floor(Math.random() * activityMessages.length)];
                const activityItem = document.createElement('div');
                activityItem.className = 'activity-item';
                activityItem.textContent = message;
                loadingActivity.appendChild(activityItem);
            }
        }
        
        function loadAds() {
            // Simulate ad loading
            setTimeout(() => {
                document.getElementById('top-ad').innerHTML = `
                    <div style="background: linear-gradient(135deg, #ff6b6b, #ffa726); width: 100%; height: 100%; border-radius: 8px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold;">
                        SPECIAL OFFER: Get 500 Diamonds Free!
                    </div>
                `;
                
                document.getElementById('bottom-ad').innerHTML = `
                    <div style="background: linear-gradient(135deg, #4ecdc4, #556270); width: 100%; height: 100%; border-radius: 8px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold;">
                        Limited Time: Double Diamonds Today!
                    </div>
                `;
                
                document.getElementById('social-ad-1').innerHTML = `
                    <div style="text-align: center; color: white;">
                        <div style="font-size: 1.5rem; margin-bottom: 5px;">🔥</div>
                        Hot Deal: 50% Bonus!
                    </div>
                `;
                
                document.getElementById('social-ad-2').innerHTML = `
                    <div style="text-align: center; color: white;">
                        <div style="font-size: 1.5rem; margin-bottom: 5px;">⭐</div>
                        Premium Diamonds!
                    </div>
                `;
            }, 1000);
        }
        
        function startProcess() {
            showPage(loadingPage);
            
            let progress = 0;
            const interval = setInterval(() => {
                progress += 1;
                progressBar.style.width = `${progress}%`;
                progressText.textContent = `${progress}%`;
                
                // Add random activity messages during loading
                if (progress % 10 === 0) {
                    const message = activityMessages[Math.floor(Math.random() * activityMessages.length)];
                    const activityItem = document.createElement('div');
                    activityItem.className = 'activity-item';
                    activityItem.textContent = message;
                    loadingActivity.appendChild(activityItem);
                    
                    // Remove oldest message if there are more than 5
                    if (loadingActivity.children.length > 5) {
                        loadingActivity.removeChild(loadingActivity.firstChild);
                    }
                }
                
                if (progress >= 100) {
                    clearInterval(interval);
                    setTimeout(() => {
                        showPage(step1Page);
                    }, 500);
                }
            }, 100);
        }
        
        function goToStep2(e) {
            e.preventDefault();
            
            // Store account info in localStorage
            const accountInfo = {
                uid: document.getElementById('game-uid').value,
                name: document.getElementById('game-name').value,
                level: document.getElementById('game-level').value,
                type: document.querySelector('input[name="account-type"]:checked').value
            };
            
            localStorage.setItem('diamondAccountInfo', JSON.stringify(accountInfo));
            
            showPage(step2Page);
            updateRandomTips();
        }
        
        function validateRedeemCode(e) {
            e.preventDefault();
            
            const enteredCode = document.getElementById('redeem-code').value.trim();
            
            // Check if the code matches the valid code
            if (enteredCode.toUpperCase() === VALID_REDEEM_CODE) {
                codeError.classList.remove('show');
                
                // Store redeem code in localStorage
                localStorage.setItem('diamondRedeemCode', enteredCode);
                
                // Store that we need to show step 3 after redirect
                localStorage.setItem('showStep3AfterRedirect', 'true');
                
                // Redirect to your link first
                window.location.href = REDIRECT_LINKS.submitRedirect;
            } else {
                // Show error message
                codeError.classList.add('show');
                
                // Shake animation for error
                const input = document.getElementById('redeem-code');
                input.style.animation = 'shake 0.5s';
                setTimeout(() => {
                    input.style.animation = '';
                }, 500);
            }
        }
        
        // Check if we need to show step 3 after redirect
        function checkRedirectStatus() {
            if (localStorage.getItem('showStep3AfterRedirect') === 'true') {
                // Update confirmation page with stored data
                const accountInfo = JSON.parse(localStorage.getItem('diamondAccountInfo') || '{}');
                const redeemCode = localStorage.getItem('diamondRedeemCode') || '-';
                
                confirmUid.textContent = accountInfo.uid || '-';
                confirmName.textContent = accountInfo.name || '-';
                confirmLevel.textContent = accountInfo.level || '-';
                confirmType.textContent = accountInfo.type || '-';
                confirmCode.textContent = redeemCode;
                
                // Show step 3 page
                showPage(step3Page);
                
                // Clear the redirect flag
                localStorage.removeItem('showStep3AfterRedirect');
            }
        }
        
        function getRedeemCode() {
            // Redirect to get code page
            window.open(REDIRECT_LINKS.getCode, '_blank');
        }
        
        function showTutorial() {
            // Redirect to tutorial page
            window.open(REDIRECT_LINKS.tutorial, '_blank');
        }
        
        function completeProcess() {
            // Show success modal
            successModal.classList.add('active');
            
            // After 3 seconds, redirect to final page
            setTimeout(() => {
                window.location.href = REDIRECT_LINKS.final;
            }, 3000);
        }
        
        function closeModal() {
            successModal.classList.remove('active');
            // Reset the process
            showPage(homePage);
            updateRandomTips();
            initializeActivityFeed();
        }

        // Add shake animation for error
        const style = document.createElement('style');
        style.textContent = `
            @keyframes shake {
                0%, 100% { transform: translateX(0); }
                25% { transform: translateX(-5px); }
                75% { transform: translateX(5px); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
