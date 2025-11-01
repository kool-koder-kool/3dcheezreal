<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Cheese Collector Game</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        /* Custom CSS using Inter font and modern styling */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap');
        
        body {
            margin: 0;
            overflow: hidden;
            font-family: 'Inter', sans-serif;
            background-color: #1a1a2e; /* Dark theme background */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            color: #fff;
        }

        /* 3D Canvas Container */
        #game-container {
            width: 100%;
            height: 100%;
            display: block; /* Managed by JS */
        }
        
        /* Canvas will be controlled by Three.js */
        canvas {
            display: block;
            touch-action: none;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            max-width: 95vw;
            max-height: 95vh;
        }

        /* HUD for Score and Timer */
        #score-container {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 10px 20px;
            background: rgba(0, 0, 0, 0.4);
            border-radius: 12px;
            font-size: 1.5rem;
            font-weight: 700;
            z-index: 10;
            color: #f7a049; /* Cheese color */
            display: flex;
            gap: 20px;
        }

        .stat-label {
            color: #a0a0ff;
            font-weight: 400;
        }

        /* Message Box Styling (Game Over/Start) */
        #message-box {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 20;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.5s ease;
        }

        #message-box.visible {
            opacity: 1;
            pointer-events: auto;
        }

        #message-content {
            background: #2c2c4d;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.7);
            max-width: 90%;
            min-width: 300px;
        }

        #message-content h2 {
            font-size: 2.5rem;
            color: #ffcc00; 
            margin-bottom: 10px;
        }

        #message-content p {
            font-size: 1.2rem;
            margin-bottom: 25px;
        }

        .action-button, #start-button {
            background-color: #ff5757;
            color: white;
            border: none;
            padding: 12px 30px;
            font-size: 1.2rem;
            font-weight: 700;
            border-radius: 10px;
            cursor: pointer;
            transition: background-color 0.2s ease, transform 0.1s ease;
            margin: 5px;
        }

        .action-button:hover, #start-button:hover {
            background-color: #e64e4e;
            transform: translateY(-2px);
        }

        .action-button:disabled {
            background-color: #555;
            cursor: not-allowed;
        }

        /* --- Kitchen Mode Styles --- */
        #kitchen-container {
            display: none; /* Starts hidden */
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background-color: #3b3a5b; /* Slightly lighter purple background for contrast */
            padding: 20px;
            width: 90%;
            max-width: 600px;
            min-height: 400px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.7);
            text-align: center;
        }
        
        #kitchen-status {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: #ccffdd;
        }

        #kitchen-actions {
            display: flex;
            flex-direction: column;
            gap: 10px;
            width: 100%;
            max-width: 400px;
            margin-bottom: 30px;
        }

        #review-area {
            margin-top: 20px;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            min-height: 100px;
            text-align: left;
        }
        
        #review-area h3 {
            color: #ffcc00;
            margin-top: 0;
            font-size: 1.5rem;
        }
        
        #review-text {
            font-style: italic;
            color: #e0e0e0;
        }

    </style>
</head>
<body>
    <div id="game-container">
        <!-- Three.js Canvas will be appended here -->
    </div>
    
    <div id="score-container">
        <div><span class="stat-label">Score:</span> <span id="score">0</span> / 10</div>
        <div><span class="stat-label">Time:</span> <span id="timer">30.0</span>s</div>
    </div>

    <div id="kitchen-container">
        <h2>🧀 Noodle Kitchen 🍜</h2>
        <p>You collected enough cheese! Now, let's turn it into a gourmet meal.</p>
        <div id="kitchen-status">Status: Preparing to boil water...</div>
        
        <div id="kitchen-actions">
            <button class="action-button" id="boil-button" onclick="handleKitchenAction('BOIL')">1. Boil Water</button>
            <button class="action-button" id="noodle-button" onclick="handleKitchenAction('ADD_NOODLES')" disabled>2. Add Noodles</button>
            <div style="display: flex; justify-content: space-between; gap: 10px;">
                <button class="action-button" id="cheese-normal-button" onclick="handleKitchenAction('ADD_CHEESE_NORMAL')" disabled style="flex-grow: 1;">3. Add Normal Cheese</button>
                <button class="action-button" id="cheese-extra-button" onclick="handleKitchenAction('ADD_CHEESE_EXTRA')" disabled style="flex-grow: 1;">3. Add Extra Cheese</button>
            </div>
            <button class="action-button" id="serve-button" onclick="serveNoodles()" disabled>4. Serve Meal</button>
        </div>
        
        <div id="review-area">
            <h3>Customer Review:</h3>
            <p id="review-text">Waiting for your delicious creation...</p>
        </div>
    </div>

    <div id="message-box">
        <div id="message-content">
            <h2 id="message-title">3D Cheese Collector (Timed Challenge)</h2>
            <p id="message-text">Goal: Collect <strong>10 cheese</strong> in <strong>30 seconds</strong>! Use <strong>W/A/S/D</strong> or <strong>Hold Mouse/Finger Drag</strong> to look around.</p>
            <button id="start-button">Start Game</button>
        </div>
    </div>

    <script>
        // --- Global Variables and Configuration ---
        const GAME_STATE = { START: 0, PLAYING: 1, KITCHEN: 2, GAME_OVER: 3 };
        const PLAYER_RADIUS = 0.5; // Explicit radius for player collision/clamping
        let gameState = GAME_STATE.START;
        let score = 0;
        let lastTime = 0;
        const TARGET_SCORE = 10;
        let timer = 30; // 30 seconds limit
        let isLooking = false; // Flag for hold-to-look control

        // Player Movement Control
        let moveState = { forward: false, backward: false, left: false, right: false };
        const movementSpeed = 10; // units per second
        const rotationSpeed = 0.005; 
        let previousClientX = 0; // For tracking mouse delta for rotation

        // Three.js elements
        let scene, camera, renderer;
        let player, ground;
        const cheeses = [];
        const BOUNDARY = 10; // The radius of the circular play area
        let animationFrameId; // To manage the animation loop
        let spawnTimer = 0; // Timer for cheese spawning

        // Kitchen Variables
        const KITCHEN_STEP = { BOIL: 0, NOODLE: 1, CHEESE: 2, SERVE: 3 };
        let currentKitchenStep = KITCHEN_STEP.BOIL;
        let noodleQuality = 'NORMAL'; // Can be 'NORMAL', 'RICH', or 'BLAND'

        // DOM elements
        const scoreDisplay = document.getElementById('score');
        const timerDisplay = document.getElementById('timer');
        const scoreContainer = document.getElementById('score-container');
        const messageBox = document.getElementById('message-box');
        const messageTitle = document.getElementById('message-title');
        const messageText = document.getElementById('message-text');
        const startButton = document.getElementById('start-button');
        const gameContainer = document.getElementById('game-container');
        const kitchenContainer = document.getElementById('kitchen-container');
        const kitchenStatus = document.getElementById('kitchen-status');
        const reviewText = document.getElementById('review-text');
        const kitchenButtons = {
            boil: document.getElementById('boil-button'),
            noodle: document.getElementById('noodle-button'),
            cheeseNormal: document.getElementById('cheese-normal-button'),
            cheeseExtra: document.getElementById('cheese-extra-button'),
            serve: document.getElementById('serve-button'),
        };


        // --- Utility Functions ---

        /**
         * Updates the score display.
         * @param {number} newScore - The current score.
         */
        function updateScore(newScore) {
            score = newScore;
            scoreDisplay.textContent = `${score}`;
        }
        
        /**
         * Updates the timer display.
         */
        function updateTimerDisplay() {
            const timeStr = Math.max(0, timer).toFixed(1);
            timerDisplay.textContent = timeStr;
        }

        /**
         * Sets up the message box for game state.
         * Note: 'text' content uses HTML for formatting.
         */
        function showMessageBox(show, title, text, buttonText = "Play Again") {
            messageBox.classList.toggle('visible', show);
            messageTitle.textContent = title;
            messageText.innerHTML = text;
            startButton.textContent = buttonText;
            
            // Re-wire start button to game start logic
            startButton.onclick = startGame;
        }

        // --- Three.js Initialization ---

        /**
         * Initializes the Three.js scene, camera, and renderer.
         */
        function init() {
            // Scene setup
            scene = new THREE.Scene();
            scene.background = new THREE.Color(0x3a3a5a);

            // Camera setup: First-person perspective
            camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            
            // Renderer setup
            renderer = new THREE.WebGLRenderer({ antialias: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(window.devicePixelRatio);
            gameContainer.appendChild(renderer.domElement);

            // Lighting
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
            scene.add(ambientLight);
            const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8);
            directionalLight.position.set(5, 10, 7.5);
            scene.add(directionalLight);

            // Ground/Play Area (a circular plane)
            const groundGeometry = new THREE.CircleGeometry(BOUNDARY, 64);
            const groundMaterial = new THREE.MeshLambertMaterial({ color: 0x4a4a8a });
            ground = new THREE.Mesh(groundGeometry, groundMaterial);
            ground.rotation.x = -Math.PI / 2; // Rotate to lie flat
            scene.add(ground);

            // Player (Invisible Sphere acting as the camera pivot/body)
            const playerGeometry = new THREE.SphereGeometry(PLAYER_RADIUS, 32, 32);
            const playerMaterial = new THREE.MeshLambertMaterial({ color: 0x4caf50, transparent: true, opacity: 0 });
            player = new THREE.Mesh(playerGeometry, playerMaterial);
            player.position.y = PLAYER_RADIUS; // Sit on the ground (eye level)
            scene.add(player);
            
            // Attach camera to the player object
            camera.position.set(0, 0.8 - PLAYER_RADIUS, 0); // Correct camera height relative to player center
            player.add(camera);

            // Event Listeners for movement and look control
            window.addEventListener('resize', onWindowResize, false);
            
            renderer.domElement.addEventListener('mousedown', onPointerDown, false);
            renderer.domElement.addEventListener('mouseup', onPointerUp, false);
            renderer.domElement.addEventListener('pointermove', onPointerMove, false);
            
            renderer.domElement.addEventListener('touchstart', onPointerDown, false);
            renderer.domElement.addEventListener('touchend', onPointerUp, false);
            renderer.domElement.addEventListener('touchmove', onPointerMove, false);
            
            window.addEventListener('keydown', onKeyDown, false);
            window.addEventListener('keyup', onKeyUp, false);
            startButton.addEventListener('click', startGame, false); // Initial button wiring

            // Start screen setup (Uses strong tags instead of markdown for reliability)
            showMessageBox(true, "3D Cheese Collector (Timed Challenge)", "Goal: Collect <strong>10 cheese</strong> in <strong>30 seconds</strong>! Use <strong>W/A/S/D</strong> or <strong>Hold Mouse/Finger Drag</strong> to look around.", "Start Game");
            
            // Initial UI State
            kitchenContainer.style.display = 'none';
        }

        // --- Object Creation ---

        /**
         * Creates a cheese block and adds it to the scene. (Spawns on the floor)
         */
        function createCheese() {
            const cheeseGeometry = new THREE.BoxGeometry(1, 1, 1);
            const cheeseMaterial = new THREE.MeshLambertMaterial({ color: 0xffcc00 });
            const cheeseMesh = new THREE.Mesh(cheeseGeometry, cheeseMaterial);

            // Spawn randomly within the playable area
            const radius = Math.random() * (BOUNDARY - 2); 
            const angle = Math.random() * Math.PI * 2;
            
            cheeseMesh.position.set(
                Math.cos(angle) * radius,
                0.5, // ON THE FLOOR 
                Math.sin(angle) * radius
            );

            cheeses.push(cheeseMesh);
            scene.add(cheeseMesh);
        }

        // --- Game Logic (3D Collector) ---

        /**
         * Handles the start of a new game.
         */
        function startGame() {
            gameState = GAME_STATE.PLAYING;
            showMessageBox(false);
            updateScore(0);
            timer = 30; // Reset timer
            spawnTimer = 0; // Reset spawn timer
            updateTimerDisplay();
            
            // Show 3D scene, hide kitchen
            gameContainer.style.display = 'block';
            renderer.domElement.style.display = 'block';
            scoreContainer.style.display = 'flex';
            kitchenContainer.style.display = 'none';
            
            // Clear existing cheese
            cheeses.forEach(cheese => scene.remove(cheese));
            cheeses.length = 0;
            
            // Reset player position and look direction
            player.position.set(0, PLAYER_RADIUS, 0); // Use explicit player radius
            player.rotation.y = 0; 
            
            // Spawn initial cheese pieces
            for(let i=0; i<5; i++) { 
                createCheese();
            }
            
            lastTime = performance.now();
            if (!animationFrameId) {
                // If animation loop was stopped (e.g., from game over), restart it.
                animate(lastTime); 
            }
        }
        
        /**
         * Handles the game win state, leading to the kitchen.
         */
        function gameWin(timeTaken) {
            // Stop 3D animation
            if (animationFrameId) {
                cancelAnimationFrame(animationFrameId);
                animationFrameId = null;
            }
            
            startKitchen(timeTaken);
        }

        /**
         * Handles the game over state (Time Out).
         */
        function gameOver() {
            gameState = GAME_STATE.GAME_OVER;
            
            // Stop 3D animation
            if (animationFrameId) {
                cancelAnimationFrame(animationFrameId);
                animationFrameId = null;
            }
            
            // Hide 3D scene, show message
            gameContainer.style.display = 'none';
            scoreContainer.style.display = 'none';
            showMessageBox(true, "TIME OUT!", `You only collected ${score} of the required ${TARGET_SCORE} pieces. Try again!`, "Play Again");
        }
        
        // --- Kitchen Logic (2D UI) ---

        /**
         * Transitions from the 3D game to the Kitchen.
         */
        function startKitchen(timeTaken) {
            gameState = GAME_STATE.KITCHEN;
            
            // Hide 3D scene elements
            renderer.domElement.style.display = 'none';
            scoreContainer.style.display = 'none';
            
            // Show Kitchen UI
            kitchenContainer.style.display = 'flex';
            
            // Reset kitchen state
            currentKitchenStep = KITCHEN_STEP.BOIL;
            noodleQuality = 'BLAND'; // Default to bland until cheese is added
            reviewText.textContent = 'Waiting for your delicious creation...';
            
            // Initial UI Update
            updateKitchenUI();
        }

        /**
         * Updates the kitchen status text and button availability.
         */
        function updateKitchenUI() {
            // Disable all buttons first
            Object.values(kitchenButtons).forEach(btn => btn.disabled = true);

            switch (currentKitchenStep) {
                case KITCHEN_STEP.BOIL:
                    kitchenStatus.textContent = "Status: Water is cold. Ready to boil!";
                    kitchenButtons.boil.disabled = false;
                    break;
                case KITCHEN_STEP.NOODLE:
                    kitchenStatus.textContent = "Status: Water is boiling! Ready for noodles.";
                    kitchenButtons.noodle.disabled = false;
                    break;
                case KITCHEN_STEP.CHEESE:
                    kitchenStatus.textContent = "Status: Noodles cooked! Time to add your fresh cheese. Choose wisely!";
                    kitchenButtons.cheeseNormal.disabled = false;
                    kitchenButtons.cheeseExtra.disabled = false;
                    break;
                case KITCHEN_STEP.SERVE:
                    kitchenStatus.textContent = "Status: Dish complete. Ready to serve the customer!";
                    kitchenButtons.serve.disabled = false;
                    break;
                default:
                    kitchenStatus.textContent = "Status: Something went wrong in the kitchen...";
            }
        }
        
        /**
         * Handles button clicks in the kitchen mode.
         */
        function handleKitchenAction(action) {
            if (gameState !== GAME_STATE.KITCHEN) return;

            switch (action) {
                case 'BOIL':
                    if (currentKitchenStep === KITCHEN_STEP.BOIL) {
                        currentKitchenStep = KITCHEN_STEP.NOODLE;
                    }
                    break;
                case 'ADD_NOODLES':
                    if (currentKitchenStep === KITCHEN_STEP.NOODLE) {
                        currentKitchenStep = KITCHEN_STEP.CHEESE;
                    }
                    break;
                case 'ADD_CHEESE_NORMAL':
                    if (currentKitchenStep === KITCHEN_STEP.CHEESE) {
                        noodleQuality = 'NORMAL';
                        currentKitchenStep = KITCHEN_STEP.SERVE;
                    }
                    break;
                case 'ADD_CHEESE_EXTRA':
                    if (currentKitchenStep === KITCHEN_STEP.CHEESE) {
                        noodleQuality = 'RICH';
                        currentKitchenStep = KITCHEN_STEP.SERVE;
                    }
                    break;
            }
            updateKitchenUI();
        }
        
        /**
         * Serves the noodles and gets a review. (FIXED: Avoids cloning the kitchen UI)
         */
        function serveNoodles() {
            if (currentKitchenStep !== KITCHEN_STEP.SERVE) return;
            gameState = GAME_STATE.GAME_OVER;
            
            // Disable all buttons after serving
            Object.values(kitchenButtons).forEach(btn => btn.disabled = true);
            
            kitchenStatus.textContent = "Status: Meal served. Awaiting review...";
            
            const review = generateReview(noodleQuality);
            reviewText.innerHTML = review;
            
            const reviewTitle = (noodleQuality === 'RICH' || noodleQuality === 'NORMAL') ? "A Chef's Triumph!" : "Needs More Cheese!";
            const reviewSnippet = review.split('<br>')[1] || 'No detailed review available.'; 

            // Wait a moment for the user to register the review in the kitchen UI, then switch to the final message box.
            setTimeout(() => {
                // Hide the kitchen UI
                kitchenContainer.style.display = 'none';

                // Show the final game over message incorporating the review
                showMessageBox(
                    true, 
                    reviewTitle, 
                    `<p class="text-lg mb-2">Your final dish quality: <strong>${noodleQuality}</strong></p>
                    <p class="text-sm italic">${reviewSnippet}</p>`, 
                    "Play New Game"
                );
            }, 1500); 
        }
        
        /**
         * Generates a review based on the final noodle quality.
         */
        function generateReview(quality) {
            let reviewTextContent = '';
            
            if (quality === 'RICH') {
                reviewTextContent = "⭐⭐⭐⭐⭐\n\"The richness of the cheese is simply overwhelming! Every bite is a decadent symphony. This is the definition of comfort food. My compliments to the chef for their generous hand with the finest collected ingredients!\"";
            } else if (quality === 'NORMAL') {
                reviewTextContent = "⭐⭐⭐⭐\n\"A perfectly balanced dish. The cheese flavor is noticeable but doesn't overpower the noodles. It's warm, savory, and exactly what I needed. Solid, professional work!\"";
            } else { // BLAND (if they didn't add cheese)
                reviewTextContent = "⭐⭐\n\"It's... fine. The noodles are cooked, and the water was boiled, but where is the cheese? It tasted a little bland and the main ingredient was missing. A missed opportunity!\"";
            }
            
            return reviewTextContent.replace(/\n/g, '<br>');
        }

        // --- Event Handlers (Input) ---

        /**
         * Handles window resize for responsive canvas.
         */
        function onWindowResize() {
            const width = window.innerWidth;
            const height = window.innerHeight;
            if (camera) {
                camera.aspect = width / height;
                camera.updateProjectionMatrix();
            }
            if (renderer) {
                renderer.setSize(width, height);
            }
        }
        
        /**
         * Enables looking when pointer/mouse is held down.
         */
        function onPointerDown(event) {
            if (gameState === GAME_STATE.PLAYING) {
                isLooking = true;
                const clientX = event.touches ? event.touches[0].clientX : event.clientX;
                previousClientX = clientX;
            }
        }

        /**
         * Disables looking when pointer/mouse is released.
         */
        function onPointerUp(event) {
            isLooking = false;
        }

        /**
         * Handles keyboard down press to set movement state.
         */
        function onKeyDown(event) {
            if (gameState !== GAME_STATE.PLAYING) return;
            switch (event.key.toUpperCase()) {
                case 'W': case 'ARROWUP': moveState.forward = true; break;
                case 'S': case 'ARROWDOWN': moveState.backward = true; break;
                case 'A': case 'ARROWLEFT': moveState.left = true; break;
                case 'D': case 'ARROWRIGHT': moveState.right = true; break;
            }
        }

        /**
         * Handles keyboard up press to clear movement state.
         */
        function onKeyUp(event) {
            if (gameState !== GAME_STATE.PLAYING) return;
            switch (event.key.toUpperCase()) {
                case 'W': case 'ARROWUP': moveState.forward = false; break;
                case 'S': case 'ARROWDOWN': moveState.backward = false; break;
                case 'A': case 'ARROWLEFT': moveState.left = false; break;
                case 'D': case 'ARROWRIGHT': moveState.right = false; break;
            }
        }


        /**
         * Handles mouse or touch movement to control the player's rotation (look).
         */
        function onPointerMove(event) {
            if (gameState !== GAME_STATE.PLAYING || !isLooking) return;
            
            const clientX = event.touches ? event.touches[0].clientX : event.clientX;
            const deltaX = clientX - previousClientX;

            player.rotation.y -= deltaX * rotationSpeed;
            
            previousClientX = clientX;
        }


        // --- Animation Loop ---

        /**
         * Main game and rendering loop.
         */
        function animate(time) {
            animationFrameId = requestAnimationFrame(animate);

            const deltaTime = (time - lastTime) / 1000; // Convert to seconds
            lastTime = time;

            if (gameState === GAME_STATE.PLAYING) {
                
                // 1. Timer Update and Check
                timer -= deltaTime;
                updateTimerDisplay();

                if (timer <= 0) {
                    timer = 0;
                    updateTimerDisplay();
                    // If time runs out, check if they won on the last frame
                    if (score >= TARGET_SCORE) { gameWin(30.0); } 
                    else { gameOver(); }
                    return; 
                }
                
                // 2. Update Player Movement 
                const actualMoveSpeed = movementSpeed * deltaTime;

                if (moveState.forward) player.translateZ(-actualMoveSpeed);
                if (moveState.backward) player.translateZ(actualMoveSpeed);
                if (moveState.left) player.translateX(-actualMoveSpeed);
                if (moveState.right) player.translateX(actualMoveSpeed);

                // Clamp player position within the circular boundary
                const pos = player.position;
                const distance = Math.sqrt(pos.x * pos.x + pos.z * pos.z);
                
                if (distance > BOUNDARY - PLAYER_RADIUS) { // Using constant PLAYER_RADIUS
                    const normalizedX = pos.x / distance;
                    const normalizedZ = pos.z / distance;
                    
                    pos.x = normalizedX * (BOUNDARY - PLAYER_RADIUS);
                    pos.z = normalizedZ * (BOUNDARY - PLAYER_RADIUS);
                }
                pos.y = PLAYER_RADIUS; // Ensure player stays at ground level (using constant)


                // 3. Update Cheese Spawning
                // Don't spawn if we have too many pieces already (collected + on ground)
                if (score < TARGET_SCORE) {
                    const CHEESE_SPAWN_RATE = 0.5; // Cheese piece every 2 seconds
                    spawnTimer += deltaTime;
                    if (spawnTimer >= 1 / CHEESE_SPAWN_RATE && score + cheeses.length < TARGET_SCORE + 3) { 
                        createCheese();
                        spawnTimer = 0;
                    }
                }


                // 4. Update Cheese Positions and Check Collisions
                for (let i = cheeses.length - 1; i >= 0; i--) {
                    const cheese = cheeses[i];
                    
                    // Rotation for effect
                    cheese.rotation.x += 0.01;
                    cheese.rotation.y += 0.01;
                    
                    // Check for collection (collision with player) - Distance less than the sum of radii (0.5 + 0.5 = 1.0)
                    const distance = player.position.distanceTo(cheese.position);
                    
                    if (distance < 1.0) { 
                        updateScore(score + 1);
                        scene.remove(cheese);
                        cheeses.splice(i, 1);
                        
                        // Check for win condition immediately
                        if (score >= TARGET_SCORE) {
                            gameWin(30 - timer); // Pass the exact time taken
                            return; 
                        }
                        
                        continue; 
                    }
                }
            }
            
            renderer.render(scene, camera);
        }

        // Initialize the game when the window loads
        window.onload = function() {
            init();
            animate(performance.now()); // Start the animation loop right away
        }

    </script>
</body>
</html>
