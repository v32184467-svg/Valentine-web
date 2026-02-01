
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Devi Jii ❤️</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;1,700&family=Satoshi:wght@300;400;700&display=swap" rel="stylesheet">

    <style>
        :root {
            --aurora-1: hsla(333, 70%, 55%, 0.4);
            --aurora-2: hsla(282, 82%, 54%, 0.3);
            --aurora-3: hsla(210, 89%, 60%, 0.3);
            --aurora-4: hsla(35, 90%, 60%, 0.3);
        }

        body {
            margin: 0;
            padding: 0;
            background-color: #0c0a09;
            color: #f5f5f5;
            font-family: 'Satoshi', sans-serif;
            overflow: hidden;
            height: 100vh;
        }

        /* Layer 1: Animated Aurora Gradient */
        .aurora-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            filter: blur(100px);
            animation: drift 20s ease-in-out infinite alternate;
        }

        .aurora-blob {
            position: absolute;
            width: 60vw;
            height: 60vw;
            border-radius: 50%;
            mix-blend-mode: screen;
        }

        @keyframes drift {
            from { transform: scale(1) rotate(0deg); }
            to { transform: scale(1.2) rotate(10deg); }
        }

        /* Step Styling */
        .glass-card {
            background: rgba(12, 10, 9, 0.6);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
            display: none;
            opacity: 0;
            transform: translateY(30px);
        }

        .glass-card.active {
            display: block;
        }

        .text-gradient {
            background: linear-gradient(to right, #ffffff, #f472b6, #fb7185);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: 'Playfair Display', serif;
        }

        .btn-primary {
            background: linear-gradient(135deg, #ec4899, #e11d48);
            box-shadow: 0 10px 20px -5px rgba(225, 29, 72, 0.5);
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .btn-primary:hover {
            transform: translateY(-4px) scale(1.05);
            box-shadow: 0 15px 25px -5px rgba(225, 29, 72, 0.7);
        }

        .btn-primary:active {
            transform: translateY(1px);
        }

        .progress-track {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 6px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            z-index: 100;
        }

        #progress-bar {
            width: 20%;
            height: 100%;
            background: linear-gradient(to right, #ec4899, #e11d48);
            transition: width 0.6s ease;
        }

        .polaroid {
            background: white;
            padding: 10px 10px 30px 10px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.4);
            transform: rotate3d(1, 1, 1, 10deg);
            transition: transform 0.1s ease-out;
        }

        .final-pop {
            position: fixed;
            font-weight: 900;
            color: #e11d48;
            pointer-events: none;
            z-index: 1000;
            text-shadow: 0 0 10px rgba(255,255,255,0.5);
        }
    </style>
</head>
<body>

    <div class="aurora-container">
        <div class="aurora-blob" style="background: var(--aurora-1); top: -10%; left: -10%;"></div>
        <div class="aurora-blob" style="background: var(--aurora-2); bottom: -10%; right: -10%;"></div>
        <div class="aurora-blob" style="background: var(--aurora-3); top: 20%; right: 20%;"></div>
        <div class="aurora-blob" style="background: var(--aurora-4); bottom: 10%; left: 30%;"></div>
    </div>

    <div id="three-canvas-container" style="position: fixed; top:0; left:0; z-index: -1;"></div>

    <div class="progress-track">
        <div id="progress-bar"></div>
    </div>

    <div class="flex items-center justify-center min-h-screen p-6">
        
        <div id="step-1" class="glass-card active max-w-md w-full p-10 text-center">
            <div class="text-6xl mb-6 animate-pulse">❤️</div>
            <h1 class="text-5xl font-bold mb-4 text-gradient">DEVI JII</h1>
            <p class="text-lg text-gray-300 mb-8">I built a little world for you, just to bring a smile to your face on your special day.</p>
            <button onclick="nextStep(2)" class="btn-primary px-8 py-3 rounded-full text-white font-bold text-lg">Let's Begin</button>
        </div>

        <div id="step-2" class="glass-card max-w-md w-full p-10 text-center">
            <div class="text-6xl mb-6">💗</div>
            <h2 class="text-4xl font-bold mb-4 text-gradient">Happy Valentine's Day!</h2>
            <p class="text-lg text-gray-300 mb-8 italic">"To my love, Happy Valentine's Day. Our journey together has been amazing, filled with laughter, sprawl-brawl, and endless love."</p>
            <button onclick="nextStep(3)" class="btn-primary px-8 py-3 rounded-full text-white font-bold text-lg">There's more...</button>
        </div>

        <div id="step-3" class="glass-card max-w-2xl w-full p-10 text-center">
            <h2 class="text-3xl font-bold mb-8 text-gradient">A Few Things I Adore About You</h2>
            <div class="grid grid-cols-2 gap-4 text-left mb-8">
                <div class="col-span-2 bg-white/5 p-6 rounded-2xl border border-white/10">
                    <h3 class="text-pink-400 font-bold">✨ Your Unmatched Kindness</h3>
                    <p class="text-sm text-gray-290">The genuine warmth you show to everyone is something truly rare and beautiful.</p>
                </div>
                <div class="bg-white/5 p-6 rounded-2xl border border-white/10">
                    <h3 class="text-pink-400 font-bold">😊 That Smile</h3>
                    <p class="text-sm text-gray-290">It's a work of art.</p>
                </div>
                <div class="col-span-2 bg-white/5 p-6 rounded-2xl border border-white/10">
                    <h3 class="text-pink-400 font-bold">🌟 Your Radiant Spirit</h3>
                    <p class="text-sm text-gray-290">Your passion for life is infectious. Being around you makes everything feel more exciting.</p>
                </div>
            </div>
            <button onclick="nextStep(4)" class="btn-primary px-8 py-3 rounded-full text-white font-bold text-lg">Remember this?</button>
        </div>

        <div id="step-4" class="glass-card max-w-md w-full p-10 text-center">
            <h2 class="text-3xl font-bold mb-8 text-gradient">That One Time...</h2>
            <div id="polaroid-container" class="mb-8 flex justify-center">
                <div class="polaroid">
                    <img src="https://i.ibb.co/ymCm1W7M/IMG-20260131-235125-751.webp" class="w-64 h-64 object-cover mb-4">
                    <p class="text-gray-800 font-serif italic">Our favorite memory.</p>
                </div>
            </div>
            <p class="text-gray-300 mb-8 text-sm">Every moment with you feels like a scene from a movie I'd watch on repeat.</p>
            <button onclick="nextStep(5)" class="btn-primary px-8 py-3 rounded-full text-white font-bold text-lg">One last thing...</button>
        </div>

        <div id="step-5" class="glass-card max-w-lg w-full p-10 text-center">
            <div class="text-6xl mb-6">💞</div>
            <h2 class="text-3xl font-bold mb-6 text-gradient">This is for you</h2>
            <p class="text-md text-gray-300 leading-relaxed mb-6">
                mere pyaare kuchi puchi babuaa i love you bhot sara hum aapko bhot pyaar karti humko batane nhi aati aapko kaise dikhaye kitna pyaar karti lekin kahi bhi apni Kami na chodti kabhi aapko Aisa na lage ki hum aapse pyaar na karti aur kucch bhi ho jaye aapke liye mera pyaar kabhi khatam nhi hoga i really really lobeee youuu bhot thala bhot thala ummmahh 💋💋.
            </p>
            <h3 id="final-wish" class="text-2xl font-bold text-pink-500 opacity-0 transform translate-y-4">Happy Valentine day, Mehraru jii! ❤️</h3>
        </div>
    </div>

    <script>
        // --- THREE.JS BACKGROUND ---
        let scene, camera, renderer, hearts = [];
        const heartCount = 25;

        function initThree() {
            scene = new THREE.Scene();
            camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            document.getElementById('three-canvas-container').appendChild(renderer.domElement);

            const light = new THREE.PointLight(0xffffff, 1);
            light.position.set(10, 10, 10);
            scene.add(light);
            scene.add(new THREE.AmbientLight(0x404040));

            // Heart Shape
            const x = 0, y = 0;
            const heartShape = new THREE.Shape();
            heartShape.moveTo( x + 5, y + 5 );
            heartShape.bezierCurveTo( x + 5, y + 5, x + 4, y, x, y );
            heartShape.bezierCurveTo( x - 6, y, x - 6, y + 7,x - 6, y + 7 );
            heartShape.bezierCurveTo( x - 6, y + 11, x - 3, y + 15.4, x + 5, y + 19 );
            heartShape.bezierCurveTo( x + 12, y + 15.4, x + 16, y + 11, x + 16, y + 7 );
            heartShape.bezierCurveTo( x + 16, y + 7, x + 16, y, x + 10, y );
            heartShape.bezierCurveTo( x + 7, y, x + 5, y + 5, x + 5, y + 5 );

            const geometry = new THREE.ExtrudeGeometry(heartShape, { depth: 2, bevelEnabled: true, bevelThickness: 1, bevelSize: 1 });
            const material = new THREE.MeshPhongMaterial({ color: 0xe11d48, shininess: 100 });

            for(let i=0; i<heartCount; i++) {
                const heart = new THREE.Mesh(geometry, material);
                heart.position.set((Math.random()-0.5)*100, (Math.random()-0.5)*100, (Math.random()-1)*50);
                heart.rotation.z = Math.PI;
                heart.rotation.y = Math.random() * Math.PI;
                heart.scale.set(0.1, 0.1, 0.1);
                heart.userData = { 
                    speed: 0.01 + Math.random()*0.02, 
                    offset: Math.random() * 100 
                };
                hearts.push(heart);
                scene.add(heart);
            }
            camera.position.z = 50;
        }

        function animate() {
            requestAnimationFrame(animate);
            hearts.forEach(h => {
                h.position.y += Math.sin(Date.now() * 0.001 + h.userData.offset) * 0.05;
                h.rotation.y += 0.01;
            });
            renderer.render(scene, camera);
        }

        // --- NAVIGATION LOGIC ---
        function nextStep(stepNum) {
            const current = document.querySelector('.glass-card.active');
            const next = document.getElementById(`step-${stepNum}`);
            
            // Progress Bar
            document.getElementById('progress-bar').style.width = `${(stepNum / 5) * 100}%`;

            // GSAP Transition
            gsap.to(current, { 
                opacity: 0, 
                y: -20, 
                duration: 0.5, 
                onComplete: () => {
                    current.classList.remove('active');
                    next.classList.add('active');
                    gsap.fromTo(next, { opacity: 0, y: 30 }, { opacity: 1, y: 0, duration: 0.8, ease: "power2.out" });
                    
                    if(stepNum === 5) startFinale();
                }
            });
        }

        function startFinale() {
            setTimeout(() => {
                gsap.to("#final-wish", { opacity: 1, y: 0, duration: 1.5 });
                triggerConfetti();
                triggerHeartExit();
                triggerMassivePopups();
            }, 1000);
        }

        function triggerConfetti() {
            const end = Date.now() + 5000;
            const colors = ['#ec4899', '#e11d48', '#ffffff'];

            (function frame() {
                confetti({
                    particleCount: 3,
                    angle: 60,
                    spread: 55,
                    origin: { x: 0, y: 0.8 },
                    colors: colors
                });
                confetti({
                    particleCount: 3,
                    angle: 120,
                    spread: 55,
                    origin: { x: 1, y: 0.8 },
                    colors: colors
                });

                if (Date.now() < end) requestAnimationFrame(frame);
            }());
        }

        function triggerHeartExit() {
            hearts.forEach(h => {
                gsap.to(h.position, { 
                    x: (Math.random() - 0.5) * 200, 
                    y: 100, 
                    z: 100, 
                    duration: 3, 
                    ease: "power2.in" 
                });
            });
        }

        function triggerMassivePopups() {
            for(let i=0; i<100; i++) {
                setTimeout(() => {
                    const pop = document.createElement('div');
                    pop.className = 'final-pop';
                    pop.innerHTML = "I LOVE YOU 💋";
                    pop.style.left = Math.random() * 90 + 'vw';
                    pop.style.right = Math.random() * 90 + 'vw';
                    pop.style.top = Math.random() * 90 + 'vh';
                    pop.style.fontSize = (Math.random() * 10 + 10) + 'px';
                    document.body.appendChild(pop);
                    
                    gsap.from(pop, { scale: 1, rotation: Math.random()*20-10, duration: 0.8, ease: "back.out" });
                }, i * 50);
            }
        }

        // Parallax Polaroid
        document.getElementById('polaroid-container').addEventListener('mousemove', (e) => {
            const pol = e.currentTarget.querySelector('.polaroid');
            const rect = e.currentTarget.getBoundingClientRect();
            const x = (e.clientX - rect.left) / rect.width - 0.5;
            const y = (e.clientY - rect.top) / rect.height - 0.5;
            gsap.to(pol, { rotationY: x * 40, rotationX: -y * 40, duration: 0.5 });
        });

        // Initialize
        window.onload = () => {
            initThree();
            animate();
            gsap.to("#step-1", { opacity: 1, y: 0, duration: 1 });
        };

        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
    </script>
</body>
</html>
