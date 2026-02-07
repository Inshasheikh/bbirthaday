<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Pari!</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #fce4ec 0%, #f3e5f5 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            color: #5d4037;
        }
        
        .container {
            width: 100%;
            max-width: 900px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            padding: 20px;
            width: 100%;
        }
        
        h1 {
            color: #d81b60;
            font-size: 2.8rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #8d6e63;
            font-style: italic;
        }
        
        .nav-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .nav-btn {
            background: #d81b60;
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
            box-shadow: 0 4px 8px rgba(216, 27, 96, 0.3);
        }
        
        .nav-btn:hover {
            background: #ad1457;
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(216, 27, 96, 0.4);
        }
        
        .nav-btn:active {
            transform: translateY(0);
        }
        
        .page {
            display: none;
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            min-height: 500px;
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
        }
        
        .page.active {
            display: block;
            animation: fadeIn 0.8s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .photo-container {
            width: 300px;
            height: 300px;
            margin: 0 auto 30px;
            border-radius: 50%;
            overflow: hidden;
            border: 8px solid #f8bbd9;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            position: relative;
        }
        
        .photo-placeholder {
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #fce4ec, #f8bbd9);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: #d81b60;
            font-size: 1.2rem;
        }
        
        .photo-placeholder i {
            font-size: 4rem;
            margin-bottom: 15px;
        }
        
        .photo-upload {
            margin-top: 15px;
            background: rgba(255, 255, 255, 0.8);
            padding: 8px 15px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s;
        }
        
        .photo-upload:hover {
            background: white;
        }
        
        #photoInput {
            display: none;
        }
        
        .name-highlight {
            color: #d81b60;
            font-weight: bold;
            font-size: 2.2rem;
            text-align: center;
            margin-bottom: 30px;
            padding: 10px;
            border-bottom: 2px dashed #f8bbd9;
        }
        
        .birthday-message {
            font-size: 1.3rem;
            line-height: 1.8;
            text-align: center;
            margin-bottom: 30px;
            padding: 0 20px;
        }
        
        .heart {
            color: #d81b60;
            animation: heartbeat 1.5s infinite;
            display: inline-block;
        }
        
        @keyframes heartbeat {
            0% { transform: scale(1); }
            5% { transform: scale(1.2); }
            10% { transform: scale(1.1); }
            15% { transform: scale(1.3); }
            50% { transform: scale(1); }
            100% { transform: scale(1); }
        }
        
        .message-box {
            background: #fff9fc;
            border-left: 5px solid #d81b60;
            padding: 25px;
            border-radius: 10px;
            margin: 25px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .message-box p {
            margin-bottom: 15px;
            font-size: 1.1rem;
            line-height: 1.7;
        }
        
        .message-box p:last-child {
            margin-bottom: 0;
        }
        
        .gallery {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin-top: 30px;
        }
        
        .memory {
            width: 120px;
            height: 120px;
            border-radius: 15px;
            overflow: hidden;
            background: linear-gradient(135deg, #fce4ec, #f8bbd9);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #d81b60;
            font-size: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .footer {
            text-align: center;
            margin-top: 30px;
            color: #8d6e63;
            font-size: 1rem;
            padding: 20px;
            border-top: 1px dashed #f8bbd9;
            width: 100%;
        }
        
        .floating-hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 0;
        }
        
        .heart-icon {
            position: absolute;
            color: #f8bbd9;
            opacity: 0.7;
            font-size: 1.5rem;
            animation: float 6s infinite linear;
        }
        
        @keyframes float {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.7;
            }
            90% {
                opacity: 0.7;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        .instructions {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin-top: 30px;
            font-size: 0.95rem;
            color: #666;
            border-left: 4px solid #d81b60;
        }
        
        @media (max-width: 768px) {
            .page {
                padding: 25px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            .photo-container {
                width: 250px;
                height: 250px;
            }
            
            .birthday-message {
                font-size: 1.1rem;
                padding: 0;
            }
        }
        
        @media (max-width: 480px) {
            .page {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .photo-container {
                width: 200px;
                height: 200px;
            }
            
            .nav-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .nav-btn {
                width: 80%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Happy Birthday, My Love!</h1>
            <p class="subtitle">A special digital card for the most special person</p>
        </header>
        
        <div class="nav-buttons">
            <button class="nav-btn" id="page1Btn">
                <i class="fas fa-heart"></i> Page 1: Birthday Wishes
            </button>
            <button class="nav-btn" id="page2Btn">
                <i class="fas fa-images"></i> Page 2: Special Memories
            </button>
        </div>
        
        <!-- Page 1: Birthday Wishes -->
        <div class="page active" id="page1">
            <div class="floating-hearts" id="hearts1"></div>
            
            <div class="photo-container">
                <div class="photo-placeholder" id="photoPlaceholder">
                    <i class="fas fa-camera"></i>
                    <span>Pari's Photo</span>
                    <div class="photo-upload" id="uploadText">Click to upload photo</div>
                </div>
                <img id="uploadedPhoto" alt="Pari's photo" style="display: none; width: 100%; height: 100%; object-fit: cover;">
            </div>
            <input type="file" id="photoInput" accept="image/*">
            
            <div class="name-highlight">To My Dearest <span class="heart">❤</span> Pari <span class="heart">❤</span></div>
            
            <div class="birthday-message">
                Wishing the most amazing birthday to the most wonderful person in my life! May your day be filled with joy, laughter, and all the things that make you smile.
            </div>
            
            <div class="message-box">
                <p>My dear Pari,</p>
                <p>On your special day, I want you to know how incredibly grateful I am to have you in my life. You bring so much light, love, and happiness wherever you go.</p>
                <p>May this year bring you closer to your dreams, surround you with positivity, and fill your life with beautiful moments. You deserve all the happiness in the world!</p>
                <p>With all my love, on your birthday and always.</p>
            </div>
        </div>
        
        <!-- Page 2: Special Memories -->
        <div class="page" id="page2">
            <div class="floating-hearts" id="hearts2"></div>
            
            <div class="name-highlight">Happy Birthday, Pari!</div>
            
            <div class="birthday-message">
                Here's to celebrating you and all the wonderful memories we've created together. Each moment with you is precious and unforgettable.
            </div>
            
            <div class="message-box">
                <p>My dearest Pari,</p>
                <p>Thinking of you on your birthday brings back so many beautiful memories we've shared. From our laughter-filled moments to our quiet conversations, every memory with you is a treasure I hold close to my heart.</p>
                <p>As you celebrate another year of your amazing life, I want you to know that my love for you grows stronger with each passing day. You are not just my girlfriend, but my best friend, my confidant, and my greatest inspiration.</p>
                <p>Here's to creating countless more beautiful memories together. Happy birthday to the woman who makes every day brighter!</p>
            </div>
            
            <div class="gallery">
                <div class="memory"><i class="fas fa-birthday-cake"></i></div>
                <div class="memory"><i class="fas fa-heart"></i></div>
                <div class="memory"><i class="fas fa-star"></i></div>
                <div class="memory"><i class="fas fa-gift"></i></div>
                <div class="memory"><i class="fas fa-music"></i></div>
                <div class="memory"><i class="fas fa-smile"></i></div>
            </div>
            
            <div class="instructions">
                <p><i class="fas fa-lightbulb"></i> <strong>Tip:</strong> You can print this page as a keepsake or save it as a PDF to share with Pari.</p>
            </div>
        </div>
        
        <div class="footer">
            <p>Made with <span class="heart">❤</span> for Pari's Birthday | A digital card to cherish forever</p>
        </div>
    </div>

    <script>
        // DOM elements
        const page1Btn = document.getElementById('page1Btn');
        const page2Btn = document.getElementById('page2Btn');
        const page1 = document.getElementById('page1');
        const page2 = document.getElementById('page2');
        const photoInput = document.getElementById('photoInput');
        const photoPlaceholder = document.getElementById('photoPlaceholder');
        const uploadedPhoto = document.getElementById('uploadedPhoto');
        const uploadText = document.getElementById('uploadText');
        const hearts1 = document.getElementById('hearts1');
        const hearts2 = document.getElementById('hearts2');
        
        // Navigation between pages
        page1Btn.addEventListener('click', () => {
            page1.classList.add('active');
            page2.classList.remove('active');
            page1Btn.style.background = '#ad1457';
            page2Btn.style.background = '#d81b60';
        });
        
        page2Btn.addEventListener('click', () => {
            page2.classList.add('active');
            page1.classList.remove('active');
            page2Btn.style.background = '#ad1457';
            page1Btn.style.background = '#d81b60';
        });
        
        // Photo upload functionality
        photoPlaceholder.addEventListener('click', () => {
            photoInput.click();
        });
        
        photoInput.addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                
                reader.onload = function(e) {
                    uploadedPhoto.src = e.target.result;
                    uploadedPhoto.style.display = 'block';
                    photoPlaceholder.style.display = 'none';
                    
                    // Update the upload text on page 2 as well
                    uploadText.textContent = 'Photo uploaded! Click to change';
                };
                
                reader.readAsDataURL(file);
            }
        });
        
        // Create floating hearts animation
        function createFloatingHearts(container) {
            for (let i = 0; i < 15; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart-icon');
                heart.innerHTML = '❤';
                heart.style.left = `${Math.random() * 100}%`;
                heart.style.fontSize = `${Math.random() * 1 + 1}rem`;
                heart.style.animationDelay = `${Math.random() * 5}s`;
                heart.style.animationDuration = `${Math.random() * 4 + 4}s`;
                container.appendChild(heart);
            }
        }
        
        // Initialize floating hearts
        createFloatingHearts(hearts1);
        createFloatingHearts(hearts2);
        
        // Add some interactive birthday surprise
        const nameHighlight = document.querySelector('.name-highlight');
        nameHighlight.addEventListener('click', () => {
            const confetti = document.createElement('div');
            confetti.innerHTML = '🎉';
            confetti.style.position = 'fixed';
            confetti.style.fontSize = '2rem';
            confetti.style.zIndex = '1000';
            confetti.style.left = `${Math.random() * 80 + 10}%`;
            confetti.style.top = '10px';
            confetti.style.animation = 'fall 3s linear forwards';
            
            // Add CSS for falling animation
            const style = document.createElement('style');
            style.textContent = `
                @keyframes fall {
                    0% { transform: translateY(-100px) rotate(0deg); opacity: 1; }
                    100% { transform: translateY(100vh) rotate(360deg); opacity: 0; }
                }
            `;
            document.head.appendChild(style);
            
            document.body.appendChild(confetti);
            
            // Remove after animation completes
            setTimeout(() => {
                confetti.remove();
            }, 3000);
        });
        
        // Auto-switch pages every 15 seconds (optional)
        let currentPage = 1;
        setInterval(() => {
            if (currentPage === 1) {
                page2Btn.click();
                currentPage = 2;
            } else {
                page1Btn.click();
                currentPage = 1;
            }
        }, 15000);
    </script>
</body>
</html>
