Birthday Website for Phone:
[FINAL.html](https://github.com/user-attachments/files/28698772/FINAL.html)
birthday website for Laptop:
[Finalfordesktop.html](https://github.com/user-attachments/files/28699125/Finalfordesktop.html).
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Retro Pink Verification</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for pixel-art typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
    
    <style>
        /* Custom retro styles */
        body {
            font-family: 'Press Start 2P', monospace;
            background-color: #1a0b16;
            color: #ffb7df;
            overflow-x: hidden;
        }

        .vt323-text {
            font-family: 'VT323', monospace;
        }

        /* CRT Scanline & Screen Flicker Effect */
        .crt::after {
            content: " ";
            display: block;
            position: fixed;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            aspect-ratio: none;
            background-size: 100% 4px, 6px 100%;
            z-index: 999;
            pointer-events: none;
        }

        /* Scanline animation */
        @keyframes scanline {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100%); }
        }
        .crt-line {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 10px;
            background: rgba(255, 183, 223, 0.08);
            opacity: 0.8;
            z-index: 1000;
            pointer-events: none;
            animation: scanline 8s linear infinite;
        }

        /* Retro Pink Borders & Shadows */
        .retro-border {
            border: 4px solid #ff7ebd;
            box-shadow: 
                0 0 0 4px #1a0b16,
                0 0 0 8px #ff2a93,
                6px 6px 0px 8px rgba(255, 42, 147, 0.4);
        }

        .retro-button {
            border: 4px solid #ff7ebd;
            box-shadow: 0 4px 0px 0px #ff2a93, 0 6px 0px 0px #1a0b16;
            transition: all 0.1s ease;
            image-rendering: pixelated;
            cursor: pointer;
        }

        .retro-button:hover:not([disabled]) {
            background-color: #ff55a9;
            color: #ffffff;
            box-shadow: 0 6px 0px 0px #ff2a93, 0 8px 0px 0px #1a0b16;
            transform: translateY(-2px);
        }

        .retro-button:active:not([disabled]) {
            transform: translateY(4px);
            box-shadow: 0 0px 0px 0px #ff2a93;
        }

        .retro-button-disabled {
            border: 4px solid #8c5d75;
            box-shadow: 0 4px 0px 0px #5c384a;
            color: #8c5d75;
            cursor: not-allowed;
        }

        /* Grid Background pattern */
        .retro-grid {
            background-size: 40px 40px;
            background-image: 
                linear-gradient(to right, rgba(255, 42, 147, 0.15) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 42, 147, 0.15) 1px, transparent 1px);
        }

        /* Animations */
        @keyframes blink {
            0%, 49% { opacity: 1; }
            50%, 100% { opacity: 1; }
        }
        .blink {
            animation: blink 1s infinite;
        }

        @keyframes bounce-gentle {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        .bounce-pixel {
            animation: bounce-gentle 1s steps(4) infinite;
        }

        /* Screen Glitch Text effect */
        .glitch {
            position: relative;
            text-shadow: 0.05em 0 0 rgba(255, 0, 85, 0.75),
                         -0.025em -0.05em 0 rgba(0, 200, 255, 0.75);
        }

        /* Shake effect for wrong choices or hits */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-10px); }
            40%, 80% { transform: translateX(10px); }
        }
        .shake-element {
            animation: shake 0.3s steps(4) 1;
        }

        /* Grid pixel item */
        .pixel-card {
            image-rendering: pixelated;
            transition: all 0.2s steps(2);
        }
        .pixel-card:hover {
            transform: scale(1.05);
            border-color: #ffdf7e;
            box-shadow: 0 0 15px rgba(255, 223, 126, 0.4);
        }

        /* Whack-a-Mole Custom CSS Styles */
        .mole-hole {
            background: radial-gradient(circle, #0e050d 60%, #461439 100%);
            border: 4px solid #ff2a93;
            overflow: hidden;
            position: relative;
        }
        
        .mole {
            position: absolute;
            bottom: -100%;
            left: 0;
            right: 0;
            top: 0;
            transition: bottom 0.1s steps(4);
            cursor: pointer;
        }

        .mole.up {
            bottom: 0%;
        }

        /* Punch Machine Gauges Specific Layout */
        .punch-target {
            background: radial-gradient(circle, #ff2a93 10%, transparent 70%);
        }

        /* Text Typewriter Simulation Container */
        .typewriter-text {
            border-right: 4px solid #ff7ebd;
            white-space: normal;
            animation: blink 0.8s infinite;
        }

        /* Arcade Screen styling for Video Frame */
        .arcade-screen {
            background-color: #000;
            border: 10px solid #2d1226;
            outline: 4px solid #ff7ebd;
            box-shadow: inset 0 0 20px rgba(255, 42, 147, 0.6);
            transition: transform 0.6s cubic-bezier(0.34, 1.56, 0.64, 1), box-shadow 0.6s ease;
        }
    </style>
</head>
<body class="crt min-h-screen flex flex-col justify-between retro-grid relative selection:bg-[#ff2a93] selection:text-white p-4" onclick="initAudioContextOnInteraction()">
    <!-- Moving scanline -->
    <div class="crt-line"></div>

    <!-- Retro Audio SFX via Base64 -->
    <audio id="select-sound" src="data:audio/wav;base64,UklGRl9vT19XQVZFRm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YV92T18A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1v"></audio>
    <audio id="success-sound" src="data:audio/wav;base64,UklGRigBAABXQVZFRm10IBAAAAABAAEARKwAAIhYAQACAAgAZGF0YQQBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1v"></audio>
    <audio id="fail-sound" src="data:audio/wav;base64,UklGRmACAABXQVZFRm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YfQBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1p"></audio>
    <audio id="whack-sound" src="data:audio/wav;base64,UklGRlgBAABXQVZFRm10IBAAAAABAAEARKwAAIhYAQACAAgAZGF0YVEBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/z8="></audio>

    <!-- MANDATORY 7-SECOND STARTUP SCREEN WITH COUNTDOWN -->
    <div id="stage-preloader" class="fixed inset-0 z-[9999] bg-[#1a0b16] flex flex-col items-center justify-center p-4">
        <div class="absolute inset-0 retro-grid opacity-30"></div>
        <div class="z-10 text-center max-w-2xl w-full px-4">
            <!-- Animated Title Monitor Frame -->
            <div class="mb-6 text-center">
                <span class="inline-block bg-[#ff2a93] text-white px-8 py-3 border-4 border-white vt323-text text-3xl tracking-widest uppercase shadow-lg">SYSTEM INITIATION</span>
            </div>

            <!-- Preloader diagnostic console box -->
            <div class="text-left bg-[#0c040b] border-4 border-[#ff7ebd] p-5 mb-6 rounded-md shadow-2xl vt323-text text-xl md:text-2xl text-[#ffb7df] overflow-hidden max-h-64 leading-relaxed">
                <p class="text-[#7effa1]">⚡ PINK_OS TERMINAL SECURE BOOT v1.89...</p>
                <p id="loader-log-1" class="hidden">>> MOUNTING HARMONIOUS CONTROLLERS...</p>
                <p id="loader-log-2" class="hidden">>> MAPS: DHARWAD SECTOR LOCATED...</p>
                <p id="loader-log-3" class="hidden text-[#ff7ebd]">>> CHARACTER PARAMETERS FOUND: "CHARIS"</p>
                <p id="loader-log-4" class="hidden text-[#7effa1] blink">>> SUCCESS! READY TO TRANSCEND...</p>
            </div>

            <!-- Progress countdown bar and visual counter -->
            <div class="flex items-center gap-4 mb-6 bg-[#2d1226]/60 p-2 border-2 border-[#ff2a93] rounded w-full">
                <div class="w-full h-8 bg-[#1a0b16] border-2 border-[#ff7ebd] flex items-center p-1">
                    <div id="preloader-progress" class="h-full bg-[#ff2a93] w-0 transition-all duration-100 rounded-sm"></div>
                </div>
                <div class="vt323-text text-3xl font-bold text-[#ffdf7e] w-14 text-right shrink-0" id="preloader-counter">7s</div>
            </div>

            <!-- Required caption -->
            <div class="bg-[#2d1226]/85 border-4 border-dashed border-[#ff2a93] p-4 rounded-md">
                <h3 class="text-xs md:text-sm tracking-wider text-[#ffdf7e] uppercase font-bold">
                    [Made with love, care and Mostly HTML coding.]
                </h3>
            </div>
        </div>
    </div>

    <!-- Header bar -->
    <header class="w-full flex justify-between items-center px-6 py-3 bg-[#2d1226] border-b-4 border-[#ff7ebd] shadow-md z-10">
        <div class="flex items-center gap-3">
            <svg class="w-8 h-8 bounce-pixel text-[#ff2a93]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
            </svg>
            <span class="text-xs md:text-sm text-[#ff9ed2] tracking-wider">PINK_OS v1.89</span>
        </div>
        <div class="vt323-text text-xl md:text-3xl text-[#ffdf7e] tracking-widest flex items-center gap-6">
            <!-- Music Control Toggle -->
            <button id="bgm-toggle-btn" onclick="toggleMute()" class="px-3 py-1 bg-[#1a0b16] border-2 border-[#ff7ebd] hover:bg-[#ff2a93] text-xs transition duration-150 rounded cursor-pointer">
                🔊 BGM: ON
            </button>
            <span id="score-counter">SCORE: 00000</span>
            <div class="w-3.5 h-3.5 bg-[#7effa1] rounded-full animate-ping"></div>
        </div>
    </header>

    <!-- Main Game Stages Container -->
    <main class="flex-grow flex items-center justify-center p-6 z-10 w-full max-w-7xl mx-auto">
        
        <!-- Transition Overlay / Game Animation Stage -->
        <div id="stage-transition" class="hidden fixed inset-0 z-50 bg-[#1a0b16] flex flex-col items-center justify-center">
            <div id="transition-grid" class="absolute inset-0 retro-grid opacity-30"></div>
            <div class="relative w-48 h-48 mb-8 flex items-center justify-center">
                <div class="bounce-pixel">
                    <svg class="w-32 h-32 text-[#ff7ebd]" viewBox="0 0 100 100" fill="currentColor">
                        <rect x="20" y="20" width="60" height="50" rx="6" />
                        <rect x="35" y="35" width="8" height="8" fill="#1a0b16" />
                        <rect x="57" y="35" width="8" height="8" fill="#1a0b16" />
                        <rect x="25" y="47" width="8" height="4" fill="#ff2a93" />
                        <rect x="67" y="47" width="8" height="4" fill="#ff2a93" />
                        <rect x="44" y="52" width="12" height="4" fill="#1a0b16" />
                        <rect x="47" y="10" width="6" height="10" />
                        <circle cx="50" cy="8" r="6" fill="#ff2a93" />
                        <rect x="30" y="70" width="12" height="10" fill="#ff2a93" />
                        <rect x="58" y="70" width="12" height="10" fill="#ff2a93" />
                    </svg>
                </div>
            </div>
            <div class="text-center z-10">
                <h2 id="transition-text" class="text-xl md:text-2xl text-[#ffdf7e] mb-4 tracking-widest uppercase">LOADING LEVEL...</h2>
                <div class="w-72 h-8 bg-[#2d1226] border-4 border-[#ff7ebd] flex items-center p-1 mx-auto">
                    <div id="progress-bar" class="h-full bg-[#ff2a93] w-0 transition-all duration-100 rounded-sm"></div>
                </div>
            </div>
        </div>

        <!-- STAGE 1: Are you human? -->
        <div id="stage-1" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/90 p-8 md:p-12 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">PROMPT: 001</div>
            <h1 class="text-xl md:text-3xl font-bold mb-12 text-white leading-relaxed glitch">Are you a human?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage1(true)" class="retro-button w-full sm:w-48 bg-[#ff2a93] text-white font-bold py-4 px-6 text-sm md:text-base">
                    [ YES ]
                </button>
                <button onclick="handleStage1(false)" class="retro-button w-full sm:w-48 bg-[#1a0b16] text-[#ff7ebd] font-bold py-4 px-6 text-sm md:text-base">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- STAGE 2: Are you Charis? -->
        <div id="stage-2" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/90 p-8 md:p-12 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">PROMPT: 002</div>
            <h1 class="text-xl md:text-3xl font-bold mb-12 text-white leading-relaxed glitch">Are you Charis?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage2(true)" class="retro-button w-full sm:w-48 bg-[#ff2a93] text-white font-bold py-4 px-6 text-sm md:text-base">
                    [ YES ]
                </button>
                <button onclick="handleStage2(false)" class="retro-button w-full sm:w-48 bg-[#1a0b16] text-[#ff7ebd] font-bold py-4 px-6 text-sm md:text-base">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- STAGE 3: Are you awesome? -->
        <div id="stage-3" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/90 p-8 md:p-12 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">PROMPT: 003</div>
            <h1 class="text-xl md:text-3xl font-bold mb-12 text-white leading-relaxed glitch">Are you awesome?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage3()" class="retro-button w-full sm:w-56 bg-[#ff2a93] text-white font-bold py-4 px-4 text-xs md:text-sm">
                    [ YES ]
                </button>
                <button onclick="handleStage3()" class="retro-button w-full sm:w-56 bg-[#ff2a93] text-white font-bold py-4 px-4 text-xs md:text-sm">
                    [ ALSO YES ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 1: Long Long Ago -->
        <div id="stage-story-1" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-2xl">SCENE I: INTRODUCTION</div>
            <div class="w-24 h-24 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ff7ebd]" fill="currentColor">
                    <rect x="25" y="25" width="50" height="50" rx="8" />
                    <rect x="38" y="42" width="6" height="6" fill="#1a0b16" />
                    <rect x="56" y="42" width="6" height="6" fill="#1a0b16" />
                    <path d="M 40,58 Q 50,66 60,58" stroke="#1a0b16" stroke-width="4" fill="none" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="story-text-1" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-md mx-auto"></p>
            </div>
            <button onclick="handleStory1Next()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-10 text-xs md:text-sm tracking-widest">
                [ NEXT ]
            </button>
        </div>

        <!-- NARRATIVE STAGE 2: Charis was born -->
        <div id="stage-story-2" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-2xl">SCENE II: THE BIRTH OF AWESOMENESS</div>
            <div class="w-24 h-24 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ffe99e]" fill="currentColor">
                    <path d="M 20,60 L 80,60 L 70,80 L 30,80 Z" />
                    <circle cx="50" cy="45" r="14" fill="#ff7ebd" />
                    <polygon points="50,20 53,27 60,30 53,33 50,40 47,33 40,30 47,27" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="story-text-2" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-md mx-auto"></p>
            </div>
            <button onclick="handleStory2Next()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-10 text-xs md:text-sm tracking-widest">
                [ NEXT ]
            </button>
        </div>

        <!-- STAGE 4: Strawberry Captcha -->
        <div id="stage-captcha" class="stage-div hidden w-full max-w-3xl bg-[#2d1226]/95 p-6 md:p-10 retro-border text-center rounded-sm">
            <div class="mb-2 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">SECURITY MODULE: 004</div>
            <div class="flex justify-between items-center max-w-xl mx-auto mb-3 px-1">
                <span class="vt323-text text-2xl text-[#ffdf7e]">STATION VERIFICATION</span>
                <span id="captcha-round-tracker" class="bg-[#ff2a93] text-white text-xs md:text-sm px-3 py-1 tracking-widest rounded-sm font-sans font-bold">ROUND: 1/3</span>
            </div>
            <h1 class="text-sm md:text-base font-bold mb-2 text-white leading-relaxed uppercase">Select the cards that contain</h1>
            <div class="inline-block bg-[#ff2a93] text-white text-xs md:text-sm px-6 py-2.5 mb-6 tracking-widest rounded-sm">
                🍓 STRAWBERRIES 🍓
            </div>
            
            <!-- Dynamic Grid Shuffled on every Round -->
            <div id="captcha-cards-grid" class="grid grid-cols-3 gap-4 max-w-xl mx-auto mb-6">
                <!-- Dynamically populated in JavaScript -->
            </div>

            <div id="captcha-warning" class="vt323-text text-xl text-[#ff55a9] mb-4 h-6">Select all 3 strawberries to proceed!</div>
            <div class="flex justify-center">
                <button id="captcha-submit-btn" onclick="submitCaptcha()" class="retro-button-disabled cursor-not-allowed w-full sm:w-72 text-[#8c5d75] font-bold py-4 px-6 text-sm">
                    [ VERIFY SELECTION ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 3: Smarter than I thought -->
        <div id="stage-story-3" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-2xl">✓ PASS CODE ACTIVE</div>
            <div class="w-24 h-24 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ffdf7e]" fill="currentColor">
                    <rect x="30" y="20" width="40" height="60" rx="4" />
                    <circle cx="50" cy="45" r="10" fill="#ff2a93" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="story-text-3" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#7effa1] leading-relaxed tracking-wider text-left max-w-md mx-auto"></p>
            </div>
            <button onclick="handleStory3Next()" class="retro-button bg-[#7effa1] text-black font-bold py-3 px-10 text-xs md:text-sm tracking-widest hover:bg-[#a3ffbc]">
                [ NEXT ]
            </button>
        </div>

        <!-- ARCADE VIDEO PLAYER STAGE (CHAPTER I) -->
        <div id="stage-video" class="stage-div hidden w-full max-w-5xl bg-[#2d1226]/90 p-6 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl flex justify-between px-2">
                <span>ARCADE CINEMATICS: VOL. I</span>
                <span id="video-progress-tracker" class="text-[#ffdf7e]">CLIP: 1/4</span>
            </div>
            
            <div class="arcade-screen w-full aspect-video flex items-center justify-center relative mb-6">
                <!-- Fallback Info Overlay -->
                <div id="video-fallback-msg" class="absolute inset-0 z-10 flex flex-col items-center justify-center p-6 text-center bg-[#1a0b16]/95 border-2 border-[#ff2a93] hidden">
                    <svg class="w-16 h-16 text-[#ff3e3e] mb-4 animate-pulse" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                    </svg>
                    <span id="video-fallback-caption" class="text-white text-base md:text-xl font-bold mb-3"></span>
                    <p class="vt323-text text-xl text-[#ff9ed2]">Configure video paths inside JavaScript: <code>VIDEO_PLAYLIST</code></p>
                </div>

                <video id="retro-player" class="w-full h-full object-contain" playsinline preload="auto">
                    Your browser does not support retro video play.
                </video>
            </div>

            <!-- Dashboard -->
            <div class="bg-[#1a0b16] border-2 border-[#ff7ebd] p-4 rounded flex flex-col justify-center items-center">
                <span id="video-now-playing" class="vt323-text text-2xl md:text-3xl text-[#ffdf7e] mb-4">PLAYING...</span>
                
                <div class="flex gap-6 w-full justify-center">
                    <button id="video-replay-btn" onclick="replayCurrentVideo()" class="retro-button bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-8 text-xs md:text-sm">
                        [ REPLAY ]
                    </button>
                    <button id="video-next-btn" onclick="nextVideoOrStep()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-8 text-xs md:text-sm">
                        [ NEXT ]
                    </button>
                </div>
            </div>
        </div>

        <!-- STAGE MOLE: Whack-a-Mole Game -->
        <div id="stage-mole" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/90 p-6 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-2 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">CHALLENGE: MINI-GAME 01</div>
            <h1 class="text-lg md:text-2xl font-bold mb-2 text-white leading-relaxed glitch">WHACK-A-MOLE</h1>
            <p class="vt323-text text-lg md:text-xl text-[#ff9ed2] mb-3">Smack <span class="text-[#ffdf7e] font-bold">10 moles</span> to unlock the next level!</p>
            <p class="vt323-text text-base text-[#7effa1] mb-4 hidden md:block select-none">[ Keyboard Pro-Tip: Use Numpad / keys <span class="text-[#ffdf7e] font-bold">1-9</span> to whack instantly! ]</p>
            
            <div class="flex justify-between items-center bg-[#1a0b16] border-4 border-[#ff7ebd] px-6 py-2.5 mb-6 rounded-md">
                <div class="vt323-text text-xl md:text-3xl text-[#7effa1]">MOLES SMACKED: <span id="mole-score">0</span>/10</div>
                <div id="mole-timer" class="vt323-text text-xl md:text-3xl text-[#ff3e3e]">TIME: 30s</div>
            </div>

            <!-- Whack-a-mole 3x3 Arena -->
            <div id="mole-arena" class="grid grid-cols-3 gap-4 max-w-md mx-auto mb-6">
                <!-- 9 mole slots -->
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-1" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">1</div>
                    <div id="mole-1" onclick="whackMole(1)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-2" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">2</div>
                    <div id="mole-2" onclick="whackMole(2)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-3" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SLAM!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">3</div>
                    <div id="mole-3" onclick="whackMole(3)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-4" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">4</div>
                    <div id="mole-4" onclick="whackMole(4)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-5" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">5</div>
                    <div id="mole-5" onclick="whackMole(5)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-6" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SMACK!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">6</div>
                    <div id="mole-6" onclick="whackMole(6)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-7" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">7</div>
                    <div id="mole-7" onclick="whackMole(7)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-8" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">8</div>
                    <div id="mole-8" onclick="whackMole(8)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-9" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SLAM!</div>
                    <div class="absolute top-1 left-2 text-[10px] vt323-text text-[#ffb7df]/60 hidden md:block">9</div>
                    <div id="mole-9" onclick="whackMole(9)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
            </div>

            <!-- Controls (Unlocked at 10 Moles) - Next is placed ABOVE Play Again -->
            <div id="mole-control-panel" class="hidden flex flex-col gap-4 justify-center items-center pt-4 border-t-4 border-[#ff2a93]/50 max-w-sm mx-auto">
                <button onclick="handleMoleSuccess()" class="retro-button w-full bg-[#ff2a93] text-white font-bold py-3.5 px-4 text-xs md:text-sm">
                    [ NEXT ]
                </button>
                <button onclick="restartMoleGame()" class="retro-button w-full bg-[#1a0b16] text-[#ff7ebd] font-bold py-3.5 px-4 text-xs md:text-sm">
                    [ PLAY AGAIN ]
                </button>
            </div>
            
            <div id="mole-fail-panel" class="hidden text-center pt-2">
                <div class="text-[#ff3e3e] vt323-text text-xl md:text-2xl mb-3">⚠️ TIME'S UP!</div>
                <button onclick="restartMoleGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-56 font-bold py-3 px-4 text-xs">
                    [ RESTART GAME ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 4: And STRONGER?! -->
        <div id="stage-story-4" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff3e3e] text-xs uppercase tracking-widest vt323-text text-2xl">⚠️ POWER WARNING DETECTED</div>
            <div class="w-24 h-24 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ff2a93]" fill="currentColor">
                    <path d="M30 40 C30 20, 50 20, 60 30 C70 40, 70 65, 50 70 L35 70 C28 65, 25 50, 30 40 Z" />
                    <rect x="35" y="60" width="30" height="15" fill="#ffe99e" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="story-text-4" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#ff3e3e] leading-relaxed tracking-wider text-left max-w-md mx-auto"></p>
            </div>
            <button onclick="handleStory4Next()" class="retro-button bg-[#ff3e3e] text-white font-bold py-3 px-10 text-xs md:text-sm tracking-widest hover:bg-red-500">
                [ NEXT ]
            </button>
        </div>

        <!-- STAGE PUNCH: Arcade Punching Machine (BEST OF 3) -->
        <div id="stage-punch" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/90 p-6 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-1 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">CHALLENGE: MINI-GAME 02 [BEST OF 3]</div>
            <div class="flex justify-between items-center max-w-md mx-auto mb-3 px-1">
                <span id="punch-round-tracker" class="bg-[#ff2a93] text-white text-xs md:text-sm px-3 py-1 tracking-widest rounded-sm font-sans font-bold">ROUND: 1/3</span>
                <span id="punch-wins-tracker" class="text-[#7effa1] vt323-text text-xl md:text-2xl tracking-wider">WINS: 0/2</span>
            </div>
            <h1 class="text-lg md:text-2xl font-bold mb-2 text-white glitch">ARCADE PUNCH MACHINE</h1>
            <p class="vt323-text text-lg md:text-xl text-[#ff9ed2] mb-3">Time the moving gauges! Score <span class="text-[#ffdf7e] font-bold">over 850</span> in at least 2 rounds!</p>
            <p class="vt323-text text-base text-[#7effa1] mb-4 hidden md:block select-none">[ Keyboard Pro-Tip: Press <span class="text-[#ffdf7e] font-bold">Spacebar</span> or <span class="text-[#ffdf7e] font-bold">Enter</span> to Lock & Punch! ]</p>

            <!-- Scoreboard Display -->
            <div class="grid grid-cols-2 gap-4 bg-[#1a0b16] border-4 border-[#ff7ebd] px-6 py-3 mb-6 rounded-md vt323-text text-xl md:text-3xl text-center">
                <div class="text-[#ffdf7e]">PUNCH POWER: <span id="punch-result" class="font-bold text-white">----</span></div>
                <div id="punch-status-text" class="text-[#ff55a9]">READY TO HIT</div>
            </div>

            <!-- Custom Dual-Axis Targeting Matrix -->
            <div class="relative w-64 h-64 mx-auto bg-[#130710] border-4 border-[#ff2a93] mb-6 flex items-center justify-center rounded-sm overflow-hidden">
                <!-- Target Sweet-Spot Crosshair lines -->
                <div class="absolute inset-0 punch-target opacity-40"></div>
                <!-- X-Axis target zone window highlights -->
                <div class="absolute top-0 bottom-0 w-8 bg-[#7effa1]/20 border-l border-r border-[#7effa1]/40"></div>
                <!-- Y-Axis target zone window highlights -->
                <div class="absolute left-0 right-0 h-8 bg-[#7effa1]/20 border-t border-b border-[#7effa1]/40"></div>
                
                <!-- Dynamic Pointer Line indicators -->
                <!-- X Axis Arrow Pointer -->
                <div id="gauge-pointer-x" class="absolute top-0 w-2 h-full bg-[#ffdf7e]" style="left: 0%;">
                    <div class="w-0 h-0 border-l-[6px] border-l-transparent border-r-[6px] border-r-transparent border-t-[8px] border-t-[#ffdf7e] mx-auto -mt-1"></div>
                </div>

                <!-- Y Axis Arrow Pointer -->
                <div id="gauge-pointer-y" class="absolute left-0 h-2 w-full bg-[#ff3e3e]" style="top: 0%;">
                    <div class="w-0 h-0 border-t-[6px] border-t-transparent border-b-[6px] border-b-transparent border-l-[8px] border-l-[#ff3e3e] my-auto -ml-1"></div>
                </div>

                <!-- Decorative center punching bag icon graphics -->
                <div id="punch-bag-graphic" class="z-10 bounce-pixel">
                    <svg class="w-16 h-16 text-[#ff2a93]" viewBox="0 0 100 100" fill="currentColor">
                        <rect x="46" y="0" width="8" height="30" fill="#8c5d75" />
                        <ellipse cx="50" cy="55" rx="24" ry="30" />
                        <circle cx="50" cy="45" r="20" fill="#ff7ebd" />
                        <path d="M 40,45 Q 50,38 60,45" stroke="#1a0b16" stroke-width="4" fill="none" />
                    </svg>
                </div>
            </div>

            <!-- Interaction Buttons Layout -->
            <div class="flex flex-col justify-center items-center gap-4">
                <button id="punch-btn" onclick="triggerPunchAction()" class="retro-button w-full max-w-sm bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] tracking-widest text-sm md:text-base">
                    💥 [ PUNCH ] 💥
                </button>

                <!-- Next Round Trigger Button -->
                <button id="punch-next-round-btn" onclick="advancePunchRound()" class="hidden retro-button w-full max-w-sm bg-[#7effa1] text-black font-bold py-4 px-6 hover:bg-[#a3ffbc] tracking-widest text-sm md:text-base">
                    ⏩ [ NEXT ROUND ] ⏩
                </button>

                <!-- Controls revealed upon winning best of three series (Next is placed ABOVE Replay) -->
                <div id="punch-success-panel" class="hidden flex flex-col gap-4 w-full max-w-sm justify-center mt-2 border-t-4 border-[#ff2a93]/30 pt-4 mx-auto">
                    <button onclick="goToStageTuff()" class="retro-button w-full bg-[#7effa1] text-black font-bold py-4 px-4 hover:bg-[#a3ffbc] text-xs md:text-sm">
                        [ NEXT ]
                    </button>
                    <button onclick="resetPunchMachine()" class="retro-button w-full bg-[#1a0b16] text-[#ff7ebd] font-bold py-4 px-4 text-xs md:text-sm">
                        [ REPLAY ]
                    </button>
                </div>

                <!-- Try again response block if best of three fails -->
                <button id="punch-retry-btn" onclick="resetPunchMachine()" class="hidden retro-button w-full max-w-sm bg-[#3c0c1e] text-[#ff3e3e] border-[#ff3e3e] font-bold py-4 px-4 text-xs md:text-sm">
                    ⚠️ CRITERIA FAILED! [ RETRY SERIES ]
                </button>
            </div>
        </div>

        <!-- NEW STAGE: TUFF -->
        <div id="stage-tuff" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-2xl">CONSOLE EVALUATION</div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="tuff-text" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="goToStageRespect()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-10 text-xs md:text-sm tracking-widest hover:bg-[#ff55a9]">
                [ NEXT ]
            </button>
        </div>

        <!-- NEW STAGE: RESPECT -->
        <div id="stage-respect" class="stage-div hidden w-full max-w-2xl bg-black border-4 border-[#ff7ebd] p-8 md:p-12 text-center rounded-sm relative">
            <div class="mb-6 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-2xl">METRIC OBTAINED</div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-[140px] flex items-center justify-center rounded-sm">
                <p id="respect-text" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#7effa1] font-bold leading-relaxed tracking-widest text-center mx-auto"></p>
            </div>
            <button onclick="goToStageVideo2()" class="retro-button bg-[#7effa1] text-black font-bold py-3 px-10 text-xs md:text-sm tracking-widest hover:bg-[#a3ffbc]">
                [ NEXT ]
            </button>
        </div>

        <!-- NEW ARCADE VIDEO PLAYER STAGE (CHAPTER II) -->
        <div id="stage-video-2" class="stage-div hidden w-full max-w-5xl bg-[#2d1226]/90 p-6 md:p-8 retro-border text-center rounded-sm animate-fade-in">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl flex justify-between px-2">
                <span>ARCADE CINEMATICS: VOL. II</span>
                <span id="video2-progress-tracker" class="text-[#ffdf7e]">CLIP: 1/4</span>
            </div>
            
            <div id="arcade-screen-2" class="arcade-screen w-full aspect-video flex items-center justify-center relative mb-6">
                <!-- Fallback Info Overlay -->
                <div id="video2-fallback-msg" class="absolute inset-0 z-10 flex flex-col items-center justify-center p-6 text-center bg-[#1a0b16]/95 border-2 border-[#ff2a93] hidden">
                    <svg class="w-16 h-16 text-[#ff3e3e] mb-4 animate-pulse" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                    </svg>
                    <span id="video2-fallback-caption" class="text-white text-base md:text-xl font-bold mb-3"></span>
                    <p class="vt323-text text-xl text-[#ff9ed2]">Configure video paths inside JavaScript: <code>VIDEO_PLAYLIST_2</code></p>
                </div>

                <video id="retro-player-2" class="w-full h-full object-contain" playsinline preload="auto">
                    Your browser does not support retro video play.
                </video>
            </div>

            <!-- Control Deck -->
            <div class="bg-[#1a0b16] border-2 border-[#ff7ebd] p-4 rounded flex flex-col justify-center items-center">
                <span id="video2-now-playing" class="vt323-text text-2xl md:text-3xl text-[#ffdf7e] mb-4">PLAYING...</span>
                
                <div class="flex gap-6 w-full justify-center">
                    <button id="video2-replay-btn" onclick="replayCurrentVideo2()" class="retro-button bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-8 text-xs md:text-sm">
                        [ REPLAY ]
                    </button>
                    <button id="video2-next-btn" onclick="nextVideoOrStep2()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-8 text-xs md:text-sm">
                        [ NEXT ]
                    </button>
                </div>
            </div>
        </div>

        <!-- NEW STAGE: THE FINAL DIALOGUE CHOICE -->
        <div id="stage-final-question" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/95 p-8 md:p-12 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl md:text-2xl">FINAL CORE INQUIRY</div>
            <h1 class="text-xl md:text-3xl font-bold mb-12 text-white leading-relaxed glitch">There are still 393 days left. Do you want to continue?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleUltimateChoice(true)" class="retro-button w-full sm:w-48 bg-[#7effa1] text-black font-bold py-4 px-6 hover:bg-[#a3ffbc] text-sm md:text-base">
                    [ YES ]
                </button>
                <button onclick="handleUltimateChoice(false)" class="retro-button w-full sm:w-48 bg-black text-white font-bold py-4 px-6 hover:bg-neutral-900 border-[#ff3e3e] text-sm md:text-base">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- NEW STAGE: FINAL SUCCESS (YES Choice) -->
        <div id="stage-final-yes" class="stage-div hidden w-full max-w-2xl bg-[#1e2d22]/90 p-8 md:p-12 border-4 border-[#7effa1] shadow-[0_0_20px_rgba(126,255,161,0.5)] text-center rounded-sm">
            <div class="mb-4 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-3xl">CORE SYSTEM ACTIVE</div>
            <div class="w-36 h-36 mx-auto mb-6 flex items-center justify-center bounce-pixel">
                <svg class="w-full h-full text-[#7effa1]" viewBox="0 0 100 100">
                    <rect x="10" y="15" width="80" height="60" rx="8" />
                    <rect x="15" y="20" width="70" height="42" fill="#1e2d22" />
                    <path d="M 30,48 Q 50,60 70,48" stroke="#7effa1" stroke-width="4" fill="none" />
                </svg>
            </div>
            <h1 class="text-2xl md:text-4xl font-bold mb-4 text-[#7effa1]">GOOD TO KNOW.</h1>
            <p class="vt323-text text-4xl md:text-5xl text-[#ffdf7e] mb-8 animate-pulse font-bold">Happy 17th Birthday, Charis!</p>
            <button onclick="resetGame()" class="retro-button bg-[#1e2d22] border-[#7effa1] text-[#7effa1] w-full sm:w-56 font-bold py-4 px-6 text-sm">
                [ PLAY AGAIN ]
            </button>
        </div>

        <!-- NEW STAGE: FINAL REJECTION (NO Choice) -->
        <div id="stage-final-no" class="stage-div hidden fixed inset-0 z-50 bg-black flex flex-col items-center justify-center p-4 animate-fade-in">
            <h1 class="text-7xl md:text-9xl font-mono text-white tracking-widest text-center select-none animate-pulse">Oh.</h1>
            <button onclick="resetGame()" class="mt-16 px-6 py-3 border-2 border-white text-white bg-black hover:bg-white hover:text-black font-sans text-xs md:text-sm tracking-widest transition duration-200">
                [ RETURN TO THE GRID ]
            </button>
        </div>

        <!-- REJECT PANELS -->
        <div id="stage-reject-1" class="stage-div hidden w-full max-w-xl bg-[#3c0c1e]/90 p-8 text-center retro-border border-[#ff3e3e]">
            <h1 class="text-2xl md:text-4xl font-bold mb-8 text-[#ff3e3e] glitch">Get out Clanker!!</h1>
            <button onclick="resetGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-56 font-bold py-4 px-6 text-sm">[ REBOOT SYSTEM ]</button>
        </div>
        <div id="stage-reject-2" class="stage-div hidden w-full max-w-xl bg-[#3c0c1e]/90 p-8 text-center retro-border border-[#ff3e3e]">
            <h1 class="text-xl md:text-3xl font-bold mb-8 text-[#ff3e3e] glitch">Get out you scank!!</h1>
            <button onclick="resetGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-56 font-bold py-4 px-6 text-sm">[ RETRY ENTRY ]</button>
        </div>

    </main>

    <footer class="w-full text-center py-4 bg-[#1a0b16] text-[#ff7ebd] text-[10px] md:text-xs z-10 flex flex-col sm:flex-row justify-between items-center px-8 gap-2 border-t border-[#ff2a93]/20">
        <p>© 2007 DARSHI and CO. ALL RIGHTS RESERVED.</p>
        <div class="flex gap-6"><span class="blink">INSERT COIN</span><span class="text-[#ffdf7e]">HI-SCORE: 99999</span></div>
    </footer>

    <!-- Core Game Controller Script Engine -->
    <script>
        // ==========================================
        // 🚨 PLAYLIST I PATHS CONFIGURATION HERE 🚨
        // ==========================================
        const VIDEO_PLAYLIST = [
            { src: "videos/clip3.mp4", caption: "video1" },
            { src: "videos/clip3.mp4", caption: "Video2" },
            { src: "videos/clip3.mp4", caption: "video3" },
            { src: "videos/clip4.mp4", caption: "video4" }
        ];

        // ==========================================
        // 🚨 PLAYLIST II PATHS CONFIGURATION HERE 🚨
        // ==========================================
        const VIDEO_PLAYLIST_2 = [
            { src: "videos/clip5.mp4", caption: "video5" },
            { src: "videos/clip6.mp4", caption: "video6" },
            { src: "videos/clip7.mp4", caption: "video7" },
            { src: "videos/clip8.mp4", caption: "video8" }
        ];

        // DOM Handles
        const selectSound = document.getElementById('select-sound');
        const successSound = document.getElementById('success-sound');
        const failSound = document.getElementById('fail-sound');
        const whackSound = document.getElementById('whack-sound');
        const scoreCounter = document.getElementById('score-counter');
        const stageTransition = document.getElementById('stage-transition');
        const transitionText = document.getElementById('transition-text');
        const progressBar = document.getElementById('progress-bar');
        const retroPlayer = document.getElementById('retro-player');
        const retroPlayer2 = document.getElementById('retro-player-2');
        const bgmBtn = document.getElementById('bgm-toggle-btn');
        const arcadeScreen2 = document.getElementById('arcade-screen-2');
        
        let currentScore = 0;
        let selectedStrawberries = [];
        
        // Captcha State (Best of 3)
        let captchaRound = 1;

        // Video Stage State Variables
        let currentVideoIndex = 0;
        let currentVideoIndex2 = 0;

        // Mini-Game 1 (Mole) Variables
        let molePoints = 0;
        let activeMoleId = null;
        let moleTimerInterval = null;
        let moleSpawnTimeout = null;
        let moleTimeLeft = 30;
        let moleGameActive = false;

        // Mini-Game 2 (Punch Engine) Variables
        let punchGameActive = false;
        let activeAxis = 'X';
        let punchValX = 0;
        let punchValY = 0;
        let dirX = 0.5;
        let dirY = 0.6;
        let loopPunchGauge = null;
        const targetSweetSpot = 50;
        
        // Punch Game Best of 3 State
        let punchRound = 1;
        let punchWins = 0;

        // BGM Web Audio Synthesis Logic (Runs client-side dynamically)
        let audioCtx = null;
        let nextNoteTime = 0.0;
        let noteSeqIdx = 0;
        let melodyIntervalId = null;
        let isMuted = false;

        // Retro Pink 8-bit Synthesizer score
        const tempo = 120;
        const secondsPerBeat = 60.0 / tempo;
        const scaleFreqs = {
            'C4': 261.63, 'D4': 293.66, 'E4': 329.63, 'F4': 349.23, 'G4': 392.00, 'A4': 440.00, 'B4': 493.88,
            'C5': 523.25, 'D5': 587.33, 'E5': 659.25, 'F5': 698.46, 'G5': 783.99, 'A5': 880.00, 'B5': 987.77
        };
        const cuteMelody = [
            'E4', 'G4', 'A4', 'C5', 'A4', 'C5', 'D5', 'E5', 
            'D5', 'C5', 'A4', 'G4', 'E4', 'D4', 'E4', 'G4',
            'A4', 'A4', 'C5', 'C5', 'E5', 'D5', 'C5', 'A4',
            'G4', 'G4', 'A4', 'B4', 'C5', 'D5', 'C5', 'E5'
        ];

        // Global Desktop Keyboard Handler
        window.addEventListener('keydown', function(event) {
            // WHACK-A-MOLE Keyboard inputs: keys 1 to 9 (and Numpad 1 to 9)
            if (moleGameActive) {
                let targetId = null;
                if (event.key >= '1' && event.key <= '9') {
                    targetId = parseInt(event.key);
                }
                if (targetId !== null) {
                    whackMole(targetId);
                }
            }

            // PUNCH MACHINE Keyboard inputs: Spacebar or Enter
            if (punchGameActive) {
                if (event.key === ' ' || event.key === 'Enter') {
                    event.preventDefault(); // Prevent page scrolling
                    triggerPunchAction();
                }
            }
        });

        function initAudioContextOnInteraction() {
            if (audioCtx) return; // Already started
            
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            nextNoteTime = audioCtx.currentTime;
            
            // Loop Scheduler
            melodyIntervalId = setInterval(scheduleMelody, 25);
        }

        function scheduleMelody() {
            if (isMuted) return;
            while (nextNoteTime < audioCtx.currentTime + 0.1) {
                play8BitSynthNote(cuteMelody[noteSeqIdx], nextNoteTime);
                nextNoteTime += secondsPerBeat * 0.5; // Eighth note scheduling
                noteSeqIdx = (noteSeqIdx + 1) % cuteMelody.length;
            }
        }

        function play8BitSynthNote(noteName, time) {
            if (!audioCtx || isMuted) return;
            
            let osc = audioCtx.createOscillator();
            let gainNode = audioCtx.createGain();
            
            // Retro triangle/square sound wave
            osc.type = 'triangle';
            osc.frequency.value = scaleFreqs[noteName] || 440;
            
            // Cute soft envelope
            gainNode.gain.setValueAtTime(0.001, time);
            gainNode.gain.linearRampToValueAtTime(0.05, time + 0.05);
            gainNode.gain.exponentialRampToValueAtTime(0.001, time + 0.25);
            
            osc.connect(gainNode);
            gainNode.connect(audioCtx.destination);
            
            osc.start(time);
            osc.stop(time + 0.3);
        }

        function toggleMute() {
            isMuted = !isMuted;
            if (isMuted) {
                bgmBtn.textContent = "🔇 BGM: OFF";
                bgmBtn.classList.remove('bg-[#ff2a93]');
                bgmBtn.classList.add('bg-[#1a0b16]');
            } else {
                bgmBtn.textContent = "🔊 BGM: ON";
                bgmBtn.classList.add('bg-[#ff2a93]');
                bgmBtn.classList.remove('bg-[#1a0b16]');
            }
            playSound('select');
        }

        function playSound(type) {
            try {
                if (type === 'select') { selectSound.currentTime = 0; selectSound.play(); }
                else if (type === 'success') { successSound.currentTime = 0; successSound.play(); }
                else if (type === 'fail') { failSound.currentTime = 0; failSound.play(); }
                else if (type === 'whack') { whackSound.currentTime = 0; whackSound.play(); }
            } catch (e) {}
        }

        function addScore(amount) {
            currentScore += amount;
            scoreCounter.textContent = "SCORE: " + String(currentScore).padStart(5, '0');
        }

        function showStage(stageId) {
            document.querySelectorAll('.stage-div').forEach(s => s.classList.add('hidden'));
            document.getElementById(stageId).classList.remove('hidden');
        }

        function runTransition(message, nextStageCallback) {
            stageTransition.classList.remove('hidden');
            transitionText.textContent = message;
            progressBar.style.width = '0%';
            playSound('success');
            let p = 0;
            const inter = setInterval(() => {
                p += 10;
                progressBar.style.width = `${p}%`;
                if (p >= 100) {
                    clearInterval(inter);
                    setTimeout(() => {
                        stageTransition.classList.add('hidden');
                        nextStageCallback();
                    }, 300);
                }
            }, 100);
        }

        // STARTUP SCREEN WITH PERFECTLY ALIGNED COUNTDOWN BAR
        function startPreloader() {
            const preloader = document.getElementById('stage-preloader');
            const progress = document.getElementById('preloader-progress');
            const countdownText = document.getElementById('preloader-counter');
            
            // Diagnostics terminal log simulation
            setTimeout(() => { document.getElementById('loader-log-1').classList.remove('hidden'); playSound('select'); }, 1200);
            setTimeout(() => { document.getElementById('loader-log-2').classList.remove('hidden'); playSound('select'); }, 2800);
            setTimeout(() => { document.getElementById('loader-log-3').classList.remove('hidden'); playSound('select'); }, 4200);
            setTimeout(() => { document.getElementById('loader-log-4').classList.remove('hidden'); playSound('success'); }, 5800);

            let secondsLeft = 7;
            let currentWidth = 0;

            const countdownInterval = setInterval(() => {
                secondsLeft--;
                if (secondsLeft >= 0) {
                    countdownText.textContent = `${secondsLeft}s`;
                }
                if (secondsLeft <= 0) {
                    clearInterval(countdownInterval);
                }
            }, 1000);

            const barInterval = setInterval(() => {
                currentWidth += 1.43; // Reaches 100% over ~7 seconds
                if (currentWidth >= 100) currentWidth = 100;
                progress.style.width = `${currentWidth}%`;
                
                if (currentWidth >= 100) {
                    clearInterval(barInterval);
                    setTimeout(() => {
                        preloader.classList.add('opacity-0');
                        preloader.style.transition = "opacity 0.5s ease";
                        setTimeout(() => {
                            preloader.classList.add('hidden');
                            showStage('stage-1');
                        }, 500);
                    }, 200);
                }
            }, 100);
        }

        // TEXT TYPEWRITER ANIMATION ENGINE
        function typeWriterEffect(elementId, text, index = 0, callback = null) {
            const element = document.getElementById(elementId);
            if (index === 0) {
                element.innerHTML = "";
            }
            if (index < text.length) {
                element.innerHTML += text.charAt(index);
                if (index % 3 === 0) playSound('select');
                setTimeout(() => {
                    typeWriterEffect(elementId, text, index + 1, callback);
                }, 50);
            } else if (callback) {
                callback();
            }
        }

        // STAGE ROUTERS & EVENT HANDLERS
        function handleStage1(isHuman) {
            playSound('select');
            if (isHuman) { addScore(100); runTransition("HUMANITY CONFIRMED...", () => showStage('stage-2')); }
            else { playSound('fail'); showStage('stage-reject-1'); }
        }

        function handleStage2(isCharis) {
            playSound('select');
            if (isCharis) { addScore(200); runTransition("IDENTITY MATCHED...", () => showStage('stage-3')); }
            else { playSound('fail'); showStage('stage-reject-2'); }
        }

        // STAGE 3 -> STORY SCENE 1
        function handleStage3() {
            playSound('select'); addScore(300);
            runTransition("LOADING STORY SCENE I...", () => {
                showStage('stage-story-1');
                typeWriterEffect('story-text-1', "Long, Long Ago... In the distant and mystical land of Dharwad...");
            });
        }

        // STORY SCENE 1 -> STORY SCENE 2
        function handleStory1Next() {
            playSound('select');
            runTransition("LOADING STORY SCENE II...", () => {
                showStage('stage-story-2');
                typeWriterEffect('story-text-2', "...Charis was born.");
            });
        }

        // STORY SCENE 2 -> CAPTCHA (Round 1 Boot)
        function handleStory2Next() {
            playSound('select');
            captchaRound = 1;
            runTransition("BOOTING SECURITY PROTOCOLS...", () => {
                showStage('stage-captcha');
                buildRoundCaptcha();
            });
        }

        // CAPTCHA DYNAMIC SHUFFLED ROUND RENDERER
        const captchaFruitPool = {
            strawberry: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                            <path d="M16 4 H24 V8 H16 Z" fill="#7effa1"/>
                            <path d="M12 8 H28 V12 H12 Z" fill="#58c973"/>
                            <path d="M10 12 H30 V20 H10 Z" fill="#ff2a93"/>
                            <path d="M8 16 H32 V24 H8 Z" fill="#ff2a93"/>
                            <path d="M12 24 H28 V28 H12 Z" fill="#ff2a93"/>
                            <path d="M14 28 H26 V32 H14 Z" fill="#e01b7c"/>
                            <path d="M18 32 H22 V36 H18 Z" fill="#b0105e"/>
                            <rect x="14" y="16" width="2" height="2" fill="#ffdf7e" />
                            <rect x="24" y="16" width="2" height="2" fill="#ffdf7e" />
                            <rect x="18" y="22" width="2" height="2" fill="#ffdf7e" />
                            <rect x="28" y="22" width="2" height="2" fill="#ffdf7e" />
                            <rect x="12" y="24" width="2" height="2" fill="#ffdf7e" />
                            <rect x="22" y="26" width="2" height="2" fill="#ffdf7e" />
                        </svg>
                        <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">RED BERRY</span>`,
            apple: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <path d="M18 4 H22 V10 H18 Z" fill="#8c5d3a"/>
                        <path d="M22 6 H26 V8 H22 Z" fill="#7effa1"/>
                        <circle cx="20" cy="22" r="12" fill="#ff3e3e" />
                        <circle cx="16" cy="22" r="10" fill="#e62e2e" />
                        <rect x="15" y="15" width="3" height="3" fill="#ffffff" />
                    </svg>
                    <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">CRUNCHY APPLE</span>`,
            grape: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <path d="M18 6 H22 V10 H18 Z" fill="#7effa1"/>
                        <circle cx="16" cy="14" r="5" fill="#a83eff" />
                        <circle cx="24" cy="14" r="5" fill="#a83eff" />
                        <circle cx="20" cy="20" r="5" fill="#8d26e0" />
                        <circle cx="15" cy="26" r="5" fill="#8d26e0" />
                        <circle cx="25" cy="26" r="5" fill="#8d26e0" />
                        <circle cx="20" cy="31" r="5" fill="#6611ab" />
                    </svg>
                    <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">SOUR SACK</span>`,
            lemon: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <ellipse cx="20" cy="20" rx="14" ry="9" fill="#ffdf7e" />
                        <ellipse cx="20" cy="20" rx="11" ry="7" fill="#ffe99e" />
                        <rect x="6" y="18" width="3" height="3" fill="#e6c45e" />
                        <rect x="31" y="18" width="3" height="3" fill="#e6c45e" />
                    </svg>
                    <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">ZESTY SQUEEZE</span>`,
            orange: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <circle cx="20" cy="22" r="11" fill="#ffa23e" />
                        <circle cx="18" cy="20" r="9" fill="#ffb86b" />
                        <rect x="19" y="8" width="2" height="4" fill="#5c8c3a" />
                    </svg>
                    <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">TANGY PULP</span>`,
            blueberry: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <circle cx="20" cy="22" r="9" fill="#3e7bff" />
                        <circle cx="18" cy="20" r="7" fill="#6ba2ff" />
                        <rect x="18" y="10" width="4" height="3" fill="#1b3ea1" />
                    </svg>
                    <span class="vt323-text text-sm md:text-base text-[#ff9ed2]">BLUE GLOBULE</span>`
        };

        let currentShuffledLayout = [];

        function buildRoundCaptcha() {
            selectedStrawberries = [];
            document.getElementById('captcha-round-tracker').textContent = `ROUND: ${captchaRound}/3`;
            
            // Build temporary array: exactly 3 strawberries and 3 other unique random fruits
            const otherFruits = ['apple', 'grape', 'lemon', 'orange', 'blueberry'];
            shuffleArray(otherFruits);
            const selectedOthers = otherFruits.slice(0, 3);
            
            // 6 Items list
            const rawItems = [
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: selectedOthers[0], content: captchaFruitPool[selectedOthers[0]] },
                { type: selectedOthers[1], content: captchaFruitPool[selectedOthers[1]] },
                { type: selectedOthers[2], content: captchaFruitPool[selectedOthers[2]] }
            ];

            // Shuffle layout positions
            shuffleArray(rawItems);
            currentShuffledLayout = rawItems;

            const gridContainer = document.getElementById('captcha-cards-grid');
            gridContainer.innerHTML = '';

            currentShuffledLayout.forEach((item, idx) => {
                const card = document.createElement('div');
                card.id = `captcha-card-${idx}`;
                card.onclick = () => selectCaptchaItem(idx);
                card.className = "pixel-card bg-[#1a0b16] border-4 border-[#ff7ebd] p-3 aspect-square flex flex-col justify-between items-center cursor-pointer relative rounded-md select-none";
                card.innerHTML = item.content;
                gridContainer.appendChild(card);
            });

            updateVerifyButton();
        }

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        function selectCaptchaItem(index) {
            playSound('select');
            const card = document.getElementById(`captcha-card-${index}`);
            if (selectedStrawberries.includes(index)) {
                selectedStrawberries = selectedStrawberries.filter(item => item !== index);
                card.style.borderColor = "#ff7ebd";
                card.style.boxShadow = "none";
            } else {
                selectedStrawberries.push(index);
                card.style.borderColor = "#7effa1";
                card.style.boxShadow = "0 0 20px rgba(126, 255, 161, 0.7)";
            }
            updateVerifyButton();
        }

        function updateVerifyButton() {
            const btn = document.getElementById('captcha-submit-btn');
            const warn = document.getElementById('captcha-warning');
            if (selectedStrawberries.length > 0) {
                btn.className = "retro-button w-full sm:w-72 bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] text-sm md:text-base cursor-pointer";
                btn.removeAttribute('disabled');
                warn.textContent = `Selected: ${selectedStrawberries.length} element(s)`;
            } else {
                btn.className = "retro-button-disabled cursor-not-allowed w-full sm:w-72 text-[#8c5d75] font-bold py-4 px-6 text-sm md:text-base";
                btn.setAttribute('disabled', 'true');
                warn.textContent = "Select all 3 strawberries to proceed!";
            }
        }

        function submitCaptcha() {
            // Count selections
            const isAllCorrect = selectedStrawberries.every(idx => currentShuffledLayout[idx].type === 'strawberry') 
                                && selectedStrawberries.length === 3;

            if (isAllCorrect) {
                addScore(200); 
                playSound('success');
                if (captchaRound < 3) {
                    captchaRound++;
                    runTransition(`ROUND ${captchaRound - 1} CLEAR! LOADING NEXT...`, () => {
                        buildRoundCaptcha();
                    });
                } else {
                    // Passed all 3 rounds successfully
                    handleCaptchaSuccess();
                }
            } else {
                playSound('fail'); 
                addScore(-50);
                const box = document.getElementById('stage-captcha');
                box.classList.add('shake-element');
                document.getElementById('captcha-warning').textContent = "⚠️ REJECTED! Try again!";
                setTimeout(() => { 
                    box.classList.remove('shake-element'); 
                    captchaRound = 1; // Reset to round 1 of best of 3!
                    buildRoundCaptcha(); 
                }, 1000);
            }
        }

        // CAPTCHA -> STORY SCENE 3 ("Hmm? Smarter than I thought!!")
        function handleCaptchaSuccess() {
            runTransition("VALIDATING SECURITY CODE...", () => {
                showStage('stage-story-3');
                typeWriterEffect('story-text-3', "Hmm? Smarter than I thought!!");
            });
        }

        // STORY SCENE 3 -> NEW VIDEO PLAYER STAGE
        function handleStory3Next() {
            playSound('select');
            runTransition("PREPARING KINETIC MEMORIES...", () => {
                showStage('stage-video');
                currentVideoIndex = 0;
                playVideoPlaylist();
            });
        }

        // PLAYLIST CONTROLLER ENGINE (VOL 1)
        function playVideoPlaylist() {
            const item = VIDEO_PLAYLIST[currentVideoIndex];
            
            document.getElementById('video-progress-tracker').textContent = `CLIP: ${currentVideoIndex + 1}/4`;
            document.getElementById('video-now-playing').textContent = `NOW PLAYING: ${item.caption}`;

            document.getElementById('video-replay-btn').classList.add('hidden');
            document.getElementById('video-next-btn').classList.add('hidden');

            const fallbackBox = document.getElementById('video-fallback-msg');
            fallbackBox.classList.add('hidden');

            retroPlayer.pause();
            retroPlayer.src = item.src;
            retroPlayer.load();

            let loadTimer = setTimeout(() => {
                showVideoFallback(item.caption);
            }, 1500);

            retroPlayer.oncanplay = function() {
                clearTimeout(loadTimer);
                retroPlayer.play().catch(() => {
                    showVideoFallback(item.caption);
                });
            };

            retroPlayer.onerror = function() {
                clearTimeout(loadTimer);
                showVideoFallback(item.caption);
            };

            retroPlayer.onended = function() {
                revealPlaybackControls();
            };
        }

        function showVideoFallback(caption) {
            const fallbackBox = document.getElementById('video-fallback-msg');
            document.getElementById('video-fallback-caption').textContent = `🎥 COMPILING: "${caption}"`;
            fallbackBox.classList.remove('hidden');
            revealPlaybackControls();
        }

        function revealPlaybackControls() {
            document.getElementById('video-replay-btn').classList.remove('hidden');
            document.getElementById('video-next-btn').classList.remove('hidden');
            playSound('success');
        }

        function replayCurrentVideo() {
            playSound('select');
            const fallbackBox = document.getElementById('video-fallback-msg');
            
            if (fallbackBox.classList.contains('hidden')) {
                retroPlayer.currentTime = 0;
                retroPlayer.play();
                document.getElementById('video-replay-btn').classList.add('hidden');
                document.getElementById('video-next-btn').classList.add('hidden');
            } else {
                const videoBox = document.getElementById('stage-video');
                videoBox.classList.add('shake-element');
                setTimeout(() => { videoBox.classList.remove('shake-element'); }, 300);
            }
        }

        function nextVideoOrStep() {
            playSound('select');
            retroPlayer.pause();
            
            currentVideoIndex++;
            if (currentVideoIndex < VIDEO_PLAYLIST.length) {
                playVideoPlaylist();
            } else {
                runTransition("LOADING WHACK-A-MOLE...", () => {
                    showStage('stage-mole');
                    startMoleGame();
                });
            }
        }

        // WHACK-A-MOLE -> STORY SCENE 4 ("And... STRONGER?!")
        function handleMoleSuccess() {
            playSound('select');
            runTransition("UPDATING STRENGTH SCORE...", () => {
                showStage('stage-story-4');
                typeWriterEffect('story-text-4', "And... STRONGER?!");
            });
        }

        // STORY SCENE 4 -> PUNCHING MACHINE
        function handleStory4Next() {
            playSound('select');
            runTransition("LOADING ARCADE PUNCH MACHINE...", () => {
                showStage('stage-punch');
                // Reset whole Best of 3 parameters
                punchRound = 1;
                punchWins = 0;
                resetPunchMachine();
            });
        }

        // NEW STAGE TRIGGERS POST-PUNCH
        function goToStageTuff() {
            playSound('select');
            runTransition("EVALUATING DURABILITY CORE...", () => {
                showStage('stage-tuff');
                typeWriterEffect('tuff-text', "You really must be very Tuff...");
            });
        }

        function goToStageRespect() {
            playSound('select');
            runTransition("CONSOLIDATING RESPECT SCORE...", () => {
                showStage('stage-respect');
                typeWriterEffect('respect-text', "Respect 100%");
            });
        }

        function goToStageVideo2() {
            playSound('select');
            runTransition("PREPARING MOUNT VOL. II KINETICS...", () => {
                showStage('stage-video-2');
                currentVideoIndex2 = 0;
                playVideoPlaylist2();
            });
        }

        // PLAYLIST II CONTROLLER ENGINE
        function playVideoPlaylist2() {
            const item = VIDEO_PLAYLIST_2[currentVideoIndex2];
            const isLastVideo = (currentVideoIndex2 === VIDEO_PLAYLIST_2.length - 1);
            
            document.getElementById('video2-progress-tracker').textContent = `CLIP: ${currentVideoIndex2 + 1}/4`;
            document.getElementById('video2-now-playing').textContent = `NOW PLAYING: ${item.caption}`;

            document.getElementById('video2-replay-btn').classList.add('hidden');
            document.getElementById('video2-next-btn').classList.add('hidden');

            const fallbackBox = document.getElementById('video2-fallback-msg');
            fallbackBox.classList.add('hidden');

            // Apply special epic larger scaling effect for the LAST video of second playlist
            if (isLastVideo) {
                arcadeScreen2.classList.add('scale-105', 'md:scale-110', 'shadow-[0_0_40px_rgba(255,42,147,0.85)]');
                document.getElementById('video2-now-playing').innerHTML = `🌟 FINAL CLIP: <span class="blink text-white font-bold">${item.caption}</span> 🌟`;
            } else {
                arcadeScreen2.classList.remove('scale-105', 'md:scale-110', 'shadow-[0_0_40px_rgba(255,42,147,0.85)]');
            }

            retroPlayer2.pause();
            retroPlayer2.src = item.src;
            retroPlayer2.load();

            let loadTimer = setTimeout(() => {
                showVideo2Fallback(item.caption);
            }, 1500);

            retroPlayer2.oncanplay = function() {
                clearTimeout(loadTimer);
                retroPlayer2.play().catch(() => {
                    showVideo2Fallback(item.caption);
                });
            };

            retroPlayer2.onerror = function() {
                clearTimeout(loadTimer);
                showVideo2Fallback(item.caption);
            };

            retroPlayer2.onended = function() {
                revealPlaybackControls2();
            };
        }

        function showVideo2Fallback(caption) {
            const fallbackBox = document.getElementById('video2-fallback-msg');
            document.getElementById('video2-fallback-caption').textContent = `🎥 COMPILING: "${caption}"`;
            fallbackBox.classList.remove('hidden');
            revealPlaybackControls2();
        }

        function revealPlaybackControls2() {
            document.getElementById('video2-replay-btn').classList.remove('hidden');
            document.getElementById('video2-next-btn').classList.remove('hidden');
            playSound('success');
        }

        function replayCurrentVideo2() {
            playSound('select');
            const fallbackBox = document.getElementById('video2-fallback-msg');
            
            if (fallbackBox.classList.contains('hidden')) {
                retroPlayer2.currentTime = 0;
                retroPlayer2.play();
                document.getElementById('video2-replay-btn').classList.add('hidden');
                document.getElementById('video2-next-btn').classList.add('hidden');
            } else {
                const videoBox = document.getElementById('stage-video-2');
                videoBox.classList.add('shake-element');
                setTimeout(() => { videoBox.classList.remove('shake-element'); }, 300);
            }
        }

        function nextVideoOrStep2() {
            playSound('select');
            retroPlayer2.pause();
            
            currentVideoIndex2++;
            if (currentVideoIndex2 < VIDEO_PLAYLIST_2.length) {
                playVideoPlaylist2();
            } else {
                // Done playing volume 2 of video files -> final inquiry decision choice
                runTransition("CONSOLIDATING DATA...", () => {
                    showStage('stage-final-question');
                });
            }
        }

        // ULTIMATE CHOICE ROUTER (YES OR NO)
        function handleUltimateChoice(choice) {
            playSound('select');
            if (choice) {
                addScore(1000);
                runTransition("FINALIZING CONNECT...", () => {
                    showStage('stage-final-yes');
                });
            } else {
                // Drop out to empty pitch black screen with a single white "Oh."
                playSound('fail');
                showStage('stage-final-no');
            }
        }

        // WHACK-A-MOLE GAME LOGIC (CLASSIC EASY RETRACTION BUT CHALLENGING SPONTANEOUS DELAYS)
        function startMoleGame() {
            molePoints = 0; moleTimeLeft = 30; moleGameActive = true;
            document.getElementById('mole-score').textContent = molePoints;
            document.getElementById('mole-control-panel').classList.add('hidden');
            document.getElementById('mole-fail-panel').classList.add('hidden');
            document.getElementById('mole-timer').textContent = `TIME: ${moleTimeLeft}s`;
            
            for(let i=1; i<=9; i++) {
                const moleEl = document.getElementById(`mole-${i}`);
                if (moleEl) {
                    moleEl.querySelector('.normal-face').classList.remove('hidden');
                    moleEl.querySelector('.whacked-face').classList.add('hidden');
                    moleEl.classList.remove('up');
                }
            }

            clearInterval(moleTimerInterval);
            moleTimerInterval = setInterval(() => {
                if (!moleGameActive) return;
                moleTimeLeft--;
                document.getElementById('mole-timer').textContent = `TIME: ${moleTimeLeft}s`;
                if (moleTimeLeft <= 0) endMoleGame(false);
            }, 1000);

            clearTimeout(moleSpawnTimeout);
            tickMoleClassicSpeed();
        }

        function tickMoleClassicSpeed() {
            if (!moleGameActive) return;

            // Restored the original comfortable show duration so the mole doesn't go back in instantly
            const showDuration = 1000; 
            // Randomized, uneven intervals between moles appearing: 200ms to 950ms
            const nextSpawnDelay = Math.random() * 750 + 200;

            spawnMole();

            // Store current active ID locally to pull down after the classic show duration expires
            const activeIdAtSpawn = activeMoleId;
            setTimeout(() => {
                if (!moleGameActive) return;
                const moleToRetract = document.getElementById(`mole-${activeIdAtSpawn}`);
                if (moleToRetract && moleToRetract.classList.contains('up')) {
                    if (!moleToRetract.querySelector('.normal-face').classList.contains('hidden')) {
                        moleToRetract.classList.remove('up');
                    }
                }
            }, showDuration);

            // Recursively schedule next mole appearance using the classic duration + randomized delay
            moleSpawnTimeout = setTimeout(tickMoleClassicSpeed, showDuration + nextSpawnDelay);
        }

        function spawnMole() {
            if (activeMoleId) {
                const prevMole = document.getElementById(`mole-${activeMoleId}`);
                if (prevMole && !prevMole.querySelector('.normal-face').classList.contains('hidden')) {
                    prevMole.classList.remove('up');
                }
            }
            // Generate a random mole hole index
            const newId = Math.floor(Math.random() * 9) + 1;
            const newMole = document.getElementById(`mole-${newId}`);
            newMole.querySelector('.normal-face').classList.remove('hidden');
            newMole.querySelector('.whacked-face').classList.add('hidden');
            newMole.classList.add('up');
            activeMoleId = newId;
        }

        function whackMole(id) {
            if (!moleGameActive) return;
            const el = document.getElementById(`mole-${id}`);
            if (el.classList.contains('up') && el.querySelector('.whacked-face').classList.contains('hidden')) {
                playSound('whack');
                
                el.querySelector('.normal-face').classList.add('hidden');
                el.querySelector('.whacked-face').classList.remove('hidden');

                const bamText = document.getElementById(`bam-${id}`);
                bamText.classList.remove('hidden');
                
                const arena = document.getElementById('mole-arena');
                arena.classList.add('shake-element');

                setTimeout(() => {
                    arena.classList.remove('shake-element');
                    bamText.classList.add('hidden');
                    el.classList.remove('up');
                }, 400);

                molePoints++;
                document.getElementById('mole-score').textContent = molePoints;
                addScore(50);
                
                if (molePoints >= 10) {
                    setTimeout(() => { endMoleGame(true); }, 500);
                }
            }
        }

        function endMoleGame(success) {
            moleGameActive = false;
            clearInterval(moleTimerInterval); 
            clearTimeout(moleSpawnTimeout);
            
            // Retract remaining moles
            for (let i = 1; i <= 9; i++) {
                const mole = document.getElementById(`mole-${i}`);
                if (mole) mole.classList.remove('up');
            }

            if (success) { 
                playScoreFeedback(true); 
                document.getElementById('mole-control-panel').classList.remove('hidden'); 
            } else { 
                playSound('fail'); 
                document.getElementById('mole-fail-panel').classList.remove('hidden'); 
            }
        }

        function restartMoleGame() { playSound('select'); startMoleGame(); }
        function playScoreFeedback(s) { if(s) playSound('success'); else playSound('fail'); }

        // ARCADE PUNCHING MACHINE LOGIC (BEST OF 3 INTERFACE)
        function resetPunchMachine() {
            punchGameActive = true;
            activeAxis = 'X';
            punchValX = 0;
            punchValY = 0;
            dirX = 0.5;
            dirY = 0.6;
            
            // Update tracking counters in header UI
            document.getElementById('punch-round-tracker').textContent = `ROUND: ${punchRound}/3`;
            document.getElementById('punch-wins-tracker').textContent = `WINS: ${punchWins}/2`;
            
            document.getElementById('punch-result').textContent = "----";
            document.getElementById('punch-status-text').textContent = "LOCK X-AXIS";
            document.getElementById('punch-status-text').className = "text-[#ffdf7e]";
            
            document.getElementById('punch-btn').className = "retro-button w-full max-w-sm bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] tracking-widest text-sm md:text-base";
            document.getElementById('punch-btn').textContent = "💥 [ LOCK X ] 💥";
            document.getElementById('punch-btn').style.display = 'block';

            document.getElementById('punch-next-round-btn').classList.add('hidden');
            document.getElementById('punch-success-panel').classList.add('hidden');
            document.getElementById('punch-retry-btn').classList.add('hidden');

            cancelAnimationFrame(loopPunchGauge);
            animationGaugeLoop();
        }

        function animationGaugeLoop() {
            if (!punchGameActive) return;

            if (activeAxis === 'X') {
                punchValX += dirX;
                if (punchValX >= 100 || punchValX <= 0) dirX = -dirX;
                document.getElementById('gauge-pointer-x').style.left = `${punchValX}%`;
            } else if (activeAxis === 'Y') {
                punchValY += dirY;
                if (punchValY >= 100 || punchValY <= 0) dirY = -dirY;
                document.getElementById('gauge-pointer-y').style.top = `${punchValY}%`;
            }

            loopPunchGauge = requestAnimationFrame(animationGaugeLoop);
        }

        function triggerPunchAction() {
            if (!punchGameActive) return;
            playSound('select');

            if (activeAxis === 'X') {
                activeAxis = 'Y';
                document.getElementById('punch-status-text').textContent = "LOCK Y-AXIS";
                document.getElementById('punch-status-text').className = "text-[#ff3e3e]";
                document.getElementById('punch-btn').textContent = "💥 [ PUNCH ! ] 💥";
            } else if (activeAxis === 'Y') {
                punchGameActive = false;
                cancelAnimationFrame(loopPunchGauge);

                const diffX = Math.abs(punchValX - targetSweetSpot);
                const diffY = Math.abs(punchValY - targetSweetSpot);
                
                const accuracyRating = 100 - (diffX + diffY); 
                let finalCalculatedScore = Math.floor(accuracyRating * 10);
                
                if (finalCalculatedScore > 1000) finalCalculatedScore = 1000;
                if (finalCalculatedScore < 100) finalCalculatedScore = Math.floor(Math.random() * 150) + 50;

                document.getElementById('punch-result').textContent = String(finalCalculatedScore).padStart(3, '0');
                
                const structuralBag = document.getElementById('punch-bag-graphic');
                structuralBag.classList.add('shake-element');
                playSound('whack');

                setTimeout(() => { structuralBag.classList.remove('shake-element'); }, 400);

                // Round Success evaluation
                const isRoundWin = finalCalculatedScore >= 850;
                if (isRoundWin) {
                    playSound('success');
                    punchWins++;
                    addScore(finalCalculatedScore);
                    document.getElementById('punch-status-text').textContent = "🔥 POWER BONUS!";
                    document.getElementById('punch-status-text').className = "text-[#7effa1]";
                } else {
                    playSound('fail');
                    document.getElementById('punch-status-text').textContent = "❌ TOO WEAK!";
                    document.getElementById('punch-status-text').className = "text-[#ff3e3e]";
                }

                // Update trackers immediately
                document.getElementById('punch-wins-tracker').textContent = `WINS: ${punchWins}/2`;
                document.getElementById('punch-btn').style.display = 'none';

                // Evaluate Best of 3 parameters after completion of the hit animation
                setTimeout(() => {
                    if (punchRound < 3) {
                        // Show "Next Round" transitional action key
                        document.getElementById('punch-next-round-btn').classList.remove('hidden');
                        document.getElementById('punch-next-round-btn').textContent = `⏩ [ START ROUND ${punchRound + 1} ] ⏩`;
                    } else {
                        // End of Round 3. Evaluate Series result.
                        if (punchWins >= 2) {
                            // Passed series requirement!
                            document.getElementById('punch-success-panel').classList.remove('hidden');
                            document.getElementById('punch-status-text').textContent = "🏆 CHAMPION CLEAR!";
                            document.getElementById('punch-status-text').className = "text-[#7effa1] blink font-bold";
                        } else {
                            // Series failed! Reveal Retry deck
                            document.getElementById('punch-retry-btn').classList.remove('hidden');
                        }
                    }
                }, 800);
            }
        }

        function advancePunchRound() {
            playSound('select');
            punchRound++;
            resetPunchMachine();
        }

        function resetGame() {
            currentScore = 0; addScore(0);
            punchGameActive = false; cancelAnimationFrame(loopPunchGauge);
            clearTimeout(moleSpawnTimeout);
            clearInterval(moleTimerInterval);
            captchaRound = 1;
            punchRound = 1;
            punchWins = 0;
            currentVideoIndex = 0;
            currentVideoIndex2 = 0;
            document.getElementById('stage-preloader').classList.add('hidden');
            showStage('stage-1');
        }

        window.onload = function() {
            startPreloader();
        };
    </script>
</body>
</html>

```
ktop.html…]()

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Retro Pink Verification</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for pixel-art typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
    
    <style>
        /* Custom retro styles */
        body {
            font-family: 'Press Start 2P', monospace;
            background-color: #1a0b16;
            color: #ffb7df;
            overflow-x: hidden;
        }

        .vt323-text {
            font-family: 'VT323', monospace;
        }

        /* CRT Scanline & Screen Flicker Effect */
        .crt::after {
            content: " ";
            display: block;
            position: fixed;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            aspect-ratio: none;
            background-size: 100% 4px, 6px 100%;
            z-index: 999;
            pointer-events: none;
        }

        /* Scanline animation */
        @keyframes scanline {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100%); }
        }
        .crt-line {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 10px;
            background: rgba(255, 183, 223, 0.08);
            opacity: 0.8;
            z-index: 1000;
            pointer-events: none;
            animation: scanline 8s linear infinite;
        }

        /* Retro Pink Borders & Shadows */
        .retro-border {
            border: 4px solid #ff7ebd;
            box-shadow: 
                0 0 0 4px #1a0b16,
                0 0 0 8px #ff2a93,
                6px 6px 0px 8px rgba(255, 42, 147, 0.4);
        }

        .retro-button {
            border: 4px solid #ff7ebd;
            box-shadow: 0 4px 0px 0px #ff2a93, 0 6px 0px 0px #1a0b16;
            transition: all 0.1s ease;
            image-rendering: pixelated;
        }

        .retro-button:active {
            transform: translateY(4px);
            box-shadow: 0 0px 0px 0px #ff2a93;
        }

        .retro-button-disabled {
            border: 4px solid #8c5d75;
            box-shadow: 0 4px 0px 0px #5c384a;
            color: #8c5d75;
        }

        /* Grid Background pattern */
        .retro-grid {
            background-size: 40px 40px;
            background-image: 
                linear-gradient(to right, rgba(255, 42, 147, 0.15) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 42, 147, 0.15) 1px, transparent 1px);
        }

        /* Animations */
        @keyframes blink {
            0%, 49% { opacity: 1; }
            50%, 100% { opacity: 1; }
        }
        .blink {
            animation: blink 1s infinite;
        }

        @keyframes bounce-gentle {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        .bounce-pixel {
            animation: bounce-gentle 1s steps(4) infinite;
        }

        /* Screen Glitch Text effect */
        .glitch {
            position: relative;
            text-shadow: 0.05em 0 0 rgba(255, 0, 85, 0.75),
                         -0.025em -0.05em 0 rgba(0, 200, 255, 0.75);
        }

        /* Shake effect for wrong choices or hits */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-10px); }
            40%, 80% { transform: translateX(10px); }
        }
        .shake-element {
            animation: shake 0.3s steps(4) 1;
        }

        /* Grid pixel item */
        .pixel-card {
            image-rendering: pixelated;
            transition: all 0.2s steps(2);
        }
        .pixel-card:hover {
            transform: scale(1.05);
            border-color: #ffdf7e;
        }

        /* Whack-a-Mole Custom CSS Styles */
        .mole-hole {
            background: radial-gradient(circle, #0e050d 60%, #461439 100%);
            border: 4px solid #ff2a93;
            overflow: hidden;
            position: relative;
        }
        
        .mole {
            position: absolute;
            bottom: -100%;
            left: 0;
            right: 0;
            top: 0;
            transition: bottom 0.1s steps(4);
            cursor: pointer;
        }

        .mole.up {
            bottom: 0%;
        }

        /* Punch Machine Gauges Specific Layout */
        .punch-target {
            background: radial-gradient(circle, #ff2a93 10%, transparent 70%);
        }

        /* Text Typewriter Simulation Container */
        .typewriter-text {
            border-right: 4px solid #ff7ebd;
            white-space: normal;
            animation: blink 0.8s infinite;
        }

        /* Arcade Screen styling for Video Frame */
        .arcade-screen {
            background-color: #000;
            border: 10px solid #2d1226;
            outline: 4px solid #ff7ebd;
            box-shadow: inset 0 0 20px rgba(255, 42, 147, 0.6);
            transition: transform 0.6s cubic-bezier(0.34, 1.56, 0.64, 1), box-shadow 0.6s ease;
        }
    </style>
</head>
<body class="crt min-h-screen flex flex-col justify-between retro-grid relative selection:bg-[#ff2a93] selection:text-white p-4" onclick="initAudioContextOnInteraction()">
    <!-- Moving scanline -->
    <div class="crt-line"></div>

    <!-- Retro Audio SFX via Base64 -->
    <audio id="select-sound" src="data:audio/wav;base64,UklGRl9vT19XQVZFRm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YV92T18A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1v"></audio>
    <audio id="success-sound" src="data:audio/wav;base64,UklGRigBAABXQVZFRm10IBAAAAABAAEARKwAAIhYAQACAAgAZGF0YQQBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1v"></audio>
    <audio id="fail-sound" src="data:audio/wav;base64,UklGRmACAABXQVZFRm10IBAAAAABAAEAQB8AAEAfAAABAAgAZGF0YfQBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP1p"></audio>
    <audio id="whack-sound" src="data:audio/wav;base64,UklGRlgBAABXQVZFRm10IBAAAAABAAEARKwAAIhYAQACAAgAZGF0YVEBAAD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/wD/AP8A/z8="></audio>

    <!-- MANDATORY 7-SECOND STARTUP SCREEN WITH COUNTDOWN -->
    <div id="stage-preloader" class="fixed inset-0 z-[9999] bg-[#1a0b16] flex flex-col items-center justify-center p-4">
        <div class="absolute inset-0 retro-grid opacity-30"></div>
        <div class="z-10 text-center max-w-xl w-full">
            <!-- Animated Title Monitor Frame -->
            <div class="mb-4 text-center">
                <span class="inline-block bg-[#ff2a93] text-white px-6 py-2 border-4 border-white vt323-text text-2xl tracking-widest uppercase shadow-lg">SYSTEM INITIATION</span>
            </div>

            <!-- Preloader diagnostic console box -->
            <div class="text-left bg-[#0c040b] border-4 border-[#ff7ebd] p-4 mb-6 rounded-md shadow-2xl vt323-text text-xl md:text-2xl text-[#ffb7df] overflow-hidden max-h-56">
                <p class="text-[#7effa1]">⚡ PINK_OS TERMINAL SECURE BOOT v1.89...</p>
                <p id="loader-log-1" class="hidden">>> MOUNTING HARMONIOUS CONTROLLERS...</p>
                <p id="loader-log-2" class="hidden">>> MAPS: DHARWAD SECTOR LOCATED...</p>
                <p id="loader-log-3" class="hidden text-[#ff7ebd]">>> CHARACTER PARAMETERS FOUND: "CHARIS"</p>
                <p id="loader-log-4" class="hidden text-[#7effa1] blink">>> SUCCESS! READY TO TRANSCEND...</p>
            </div>

            <!-- Progress countdown bar and visual counter -->
            <div class="flex items-center gap-4 mb-6 bg-[#2d1226]/60 p-2 border-2 border-[#ff2a93] rounded">
                <div class="w-full h-8 bg-[#1a0b16] border-2 border-[#ff7ebd] flex items-center p-0.5">
                    <div id="preloader-progress" class="h-full bg-[#ff2a93] w-0 transition-all duration-100"></div>
                </div>
                <div class="vt323-text text-3xl font-bold text-[#ffdf7e] w-12 text-right shrink-0" id="preloader-counter">7s</div>
            </div>

            <!-- Required caption -->
            <div class="bg-[#2d1226]/85 border-4 border-dashed border-[#ff2a93] p-4 rounded-md">
                <h3 class="text-xs md:text-sm tracking-wider text-[#ffdf7e] uppercase font-bold">
                    [Made with love, care and a lot of HTML codes.]
                </h3>
            </div>
        </div>
    </div>

    <!-- Header bar -->
    <header class="w-full flex justify-between items-center px-4 py-2 bg-[#2d1226] border-b-4 border-[#ff7ebd] shadow-md z-10">
        <div class="flex items-center gap-2">
            <svg class="w-8 h-8 bounce-pixel text-[#ff2a93]" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
            </svg>
            <span class="text-xs md:text-sm text-[#ff9ed2]">PINK_OS v1.89</span>
        </div>
        <div class="vt323-text text-xl md:text-2xl text-[#ffdf7e] tracking-widest flex items-center gap-4">
            <!-- Music Control Toggle -->
            <button id="bgm-toggle-btn" onclick="toggleMute()" class="px-2 py-1 bg-[#1a0b16] border-2 border-[#ff7ebd] hover:bg-[#ff2a93] text-xs transition duration-150">
                🔊 BGM: ON
            </button>
            <span id="score-counter">SCORE: 00000</span>
            <div class="w-3 h-3 bg-[#7effa1] rounded-full animate-ping"></div>
        </div>
    </header>

    <!-- Main Game Stages Container -->
    <main class="flex-grow flex items-center justify-center p-4 z-10">
        
        <!-- Transition Overlay / Game Animation Stage -->
        <div id="stage-transition" class="hidden fixed inset-0 z-50 bg-[#1a0b16] flex-col items-center justify-center">
            <div id="transition-grid" class="absolute inset-0 retro-grid opacity-30"></div>
            <div class="relative w-48 h-48 mb-8 flex items-center justify-center">
                <div class="bounce-pixel">
                    <svg class="w-32 h-32 text-[#ff7ebd]" viewBox="0 0 100 100" fill="currentColor">
                        <rect x="20" y="20" width="60" height="50" rx="6" />
                        <rect x="35" y="35" width="8" height="8" fill="#1a0b16" />
                        <rect x="57" y="35" width="8" height="8" fill="#1a0b16" />
                        <rect x="25" y="47" width="8" height="4" fill="#ff2a93" />
                        <rect x="67" y="47" width="8" height="4" fill="#ff2a93" />
                        <rect x="44" y="52" width="12" height="4" fill="#1a0b16" />
                        <rect x="47" y="10" width="6" height="10" />
                        <circle cx="50" cy="8" r="6" fill="#ff2a93" />
                        <rect x="30" y="70" width="12" height="10" fill="#ff2a93" />
                        <rect x="58" y="70" width="12" height="10" fill="#ff2a93" />
                    </svg>
                </div>
            </div>
            <div class="text-center">
                <h2 id="transition-text" class="text-xl md:text-2xl text-[#ffdf7e] mb-4 tracking-widest">LOADING LEVEL...</h2>
                <div class="w-64 h-8 bg-[#2d1226] border-4 border-[#ff7ebd] flex items-center p-0.5">
                    <div id="progress-bar" class="h-full bg-[#ff2a93] w-0 transition-all duration-100"></div>
                </div>
            </div>
        </div>

        <!-- STAGE 1: Are you human? -->
        <div id="stage-1" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/90 p-6 md:p-10 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">PROMPT: 001</div>
            <h1 class="text-lg md:text-2xl font-bold mb-10 text-white leading-relaxed glitch">Are you a human?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage1(true)" class="retro-button w-full sm:w-40 bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] text-sm">
                    [ YES ]
                </button>
                <button onclick="handleStage1(false)" class="retro-button w-full sm:w-40 bg-[#1a0b16] text-[#ff7ebd] font-bold py-4 px-6 hover:bg-[#2d1226] text-sm">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- STAGE 2: Are you Charis? -->
        <div id="stage-2" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/90 p-6 md:p-10 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">PROMPT: 002</div>
            <h1 class="text-lg md:text-2xl font-bold mb-10 text-white leading-relaxed glitch">Are you Charis?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage2(true)" class="retro-button w-full sm:w-40 bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] text-sm">
                    [ YES ]
                </button>
                <button onclick="handleStage2(false)" class="retro-button w-full sm:w-40 bg-[#1a0b16] text-[#ff7ebd] font-bold py-4 px-6 hover:bg-[#2d1226] text-sm">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- STAGE 3: Are you awesome? -->
        <div id="stage-3" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/90 p-6 md:p-10 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">PROMPT: 003</div>
            <h1 class="text-lg md:text-2xl font-bold mb-10 text-white leading-relaxed glitch">Are you awesome?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleStage3()" class="retro-button w-full sm:w-48 bg-[#ff2a93] text-white font-bold py-4 px-4 hover:bg-[#ff55a9] text-xs">
                    [ YES ]
                </button>
                <button onclick="handleStage3()" class="retro-button w-full sm:w-48 bg-[#ff2a93] text-white font-bold py-4 px-4 hover:bg-[#ff55a9] text-xs">
                    [ ALSO YES ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 1: Long Long Ago -->
        <div id="stage-story-1" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl">SCENE I: INTRODUCTION</div>
            <div class="w-20 h-20 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ff7ebd]" fill="currentColor">
                    <rect x="25" y="25" width="50" height="50" rx="8" />
                    <rect x="38" y="42" width="6" height="6" fill="#1a0b16" />
                    <rect x="56" y="42" width="6" height="6" fill="#1a0b16" />
                    <path d="M 40,58 Q 50,66 60,58" stroke="#1a0b16" stroke-width="4" fill="none" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-4 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="story-text-1" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="handleStory1Next()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-8 text-xs tracking-widest hover:bg-[#ff55a9]">
                [ NEXT ]
            </button>
        </div>

        <!-- NARRATIVE STAGE 2: Charis was born -->
        <div id="stage-story-2" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl">SCENE II: THE BIRTH OF AWESOMENESS</div>
            <div class="w-20 h-20 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ffe99e]" fill="currentColor">
                    <path d="M 20,60 L 80,60 L 70,80 L 30,80 Z" />
                    <circle cx="50" cy="45" r="14" fill="#ff7ebd" />
                    <polygon points="50,20 53,27 60,30 53,33 50,40 47,33 40,30 47,27" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-4 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="story-text-2" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="handleStory2Next()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-8 text-xs tracking-widest hover:bg-[#ff55a9]">
                [ NEXT ]
            </button>
        </div>

        <!-- STAGE 4: Strawberry Captcha -->
        <div id="stage-captcha" class="stage-div hidden w-full max-w-2xl bg-[#2d1226]/95 p-5 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-2 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-lg">SECURITY MODULE: 004</div>
            <div class="flex justify-between items-center max-w-lg mx-auto mb-2 px-1">
                <span class="vt323-text text-xl text-[#ffdf7e]">STATION VERIFICATION</span>
                <span id="captcha-round-tracker" class="bg-[#ff2a93] text-white text-xs md:text-sm px-2 py-1 tracking-widest rounded-sm font-sans font-bold">ROUND: 1/3</span>
            </div>
            <h1 class="text-xs md:text-sm font-bold mb-2 text-white leading-relaxed uppercase">Select the cards that contain</h1>
            <div class="inline-block bg-[#ff2a93] text-white text-xs md:text-sm px-4 py-2 mb-4 tracking-widest rounded-sm">
                🍓 STRAWBERRIES 🍓
            </div>
            
            <!-- Dynamic Grid Shuffled on every Round -->
            <div id="captcha-cards-grid" class="grid grid-cols-3 gap-2 md:gap-4 max-w-lg mx-auto mb-6">
                <!-- Dynamically populated in JavaScript -->
            </div>

            <div id="captcha-warning" class="vt323-text text-lg text-[#ff55a9] mb-4 h-6">Select all 3 strawberries to proceed!</div>
            <div class="flex justify-center">
                <button id="captcha-submit-btn" onclick="submitCaptcha()" class="retro-button-disabled cursor-not-allowed w-full sm:w-64 text-[#8c5d75] font-bold py-4 px-6 text-sm">
                    [ VERIFY SELECTION ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 3: Smarter than I thought -->
        <div id="stage-story-3" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-xl">✓ PASS CODE ACTIVE</div>
            <div class="w-20 h-20 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ffdf7e]" fill="currentColor">
                    <rect x="30" y="20" width="40" height="60" rx="4" />
                    <circle cx="50" cy="45" r="10" fill="#ff2a93" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-4 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="story-text-3" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#7effa1] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="handleStory3Next()" class="retro-button bg-[#7effa1] text-black font-bold py-3 px-8 text-xs tracking-widest hover:bg-[#a3ffbc]">
                [ NEXT ]
            </button>
        </div>

        <!-- ARCADE VIDEO PLAYER STAGE (CHAPTER I) -->
        <div id="stage-video" class="stage-div hidden w-full max-w-6xl bg-[#2d1226]/90 p-6 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl flex justify-between px-2">
                <span>ARCADE CINEMATICS: VOL. I</span>
                <span id="video-progress-tracker" class="text-[#ffdf7e]">CLIP: 1/4</span>
            </div>
            
            <div class="arcade-screen w-full aspect-video flex items-center justify-center relative mb-6">
                <!-- Fallback Info Overlay -->
                <div id="video-fallback-msg" class="absolute inset-0 z-10 flex flex-col items-center justify-center p-6 text-center bg-[#1a0b16]/95 border-2 border-[#ff2a93] hidden">
                    <svg class="w-12 h-12 text-[#ff3e3e] mb-3 animate-pulse" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                    </svg>
                    <span id="video-fallback-caption" class="text-white text-sm md:text-base font-bold mb-2"></span>
                    <p class="vt323-text text-lg text-[#ff9ed2]">Configure video paths inside JavaScript: <code>VIDEO_PLAYLIST</code></p>
                </div>

                <video id="retro-player" class="w-full h-full object-contain" playsinline preload="auto">
                    Your browser does not support retro video play.
                </video>
            </div>

            <!-- Dashboard -->
            <div class="bg-[#1a0b16] border-2 border-[#ff7ebd] p-4 rounded flex flex-col justify-center items-center">
                <span id="video-now-playing" class="vt323-text text-2xl text-[#ffdf7e] mb-4">PLAYING...</span>
                
                <div class="flex gap-4 w-full justify-center">
                    <button id="video-replay-btn" onclick="replayCurrentVideo()" class="retro-button bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-6 text-xs hover:bg-[#2d1226]">
                        [ REPLAY ]
                    </button>
                    <button id="video-next-btn" onclick="nextVideoOrStep()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-6 text-xs hover:bg-[#ff55a9]">
                        [ NEXT ]
                    </button>
                </div>
            </div>
        </div>

        <!-- STAGE MOLE: Whack-a-Mole Game -->
        <div id="stage-mole" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/90 p-5 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-2 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">CHALLENGE: MINI-GAME 01</div>
            <h1 class="text-base md:text-xl font-bold mb-2 text-white leading-relaxed glitch">WHACK-A-MOLE</h1>
            <p class="vt323-text text-lg text-[#ff9ed2] mb-4">Smack <span class="text-[#ffdf7e] font-bold">10 moles</span> to unlock the next level!</p>
            
            <div class="flex justify-between items-center bg-[#1a0b16] border-4 border-[#ff7ebd] px-4 py-2 mb-6 rounded-md">
                <div class="vt323-text text-xl md:text-2xl text-[#7effa1]">MOLES SMACKED: <span id="mole-score">0</span>/10</div>
                <div id="mole-timer" class="vt323-text text-xl md:text-2xl text-[#ff3e3e]">TIME: 30s</div>
            </div>

            <!-- Whack-a-mole 3x3 Arena -->
            <div id="mole-arena" class="grid grid-cols-3 gap-3 max-w-sm mx-auto mb-6">
                <!-- 9 mole slots -->
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-1" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div id="mole-1" onclick="whackMole(1)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-2" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div id="mole-2" onclick="whackMole(2)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-3" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SLAM!</div>
                    <div id="mole-3" onclick="whackMole(3)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-4" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div id="mole-4" onclick="whackMole(4)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-5" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div id="mole-5" onclick="whackMole(5)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-6" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SMACK!</div>
                    <div id="mole-6" onclick="whackMole(6)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-7" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">POW!</div>
                    <div id="mole-7" onclick="whackMole(7)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-8" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">BAM!</div>
                    <div id="mole-8" onclick="whackMole(8)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
                <div class="mole-hole aspect-square rounded-md select-none relative">
                    <div id="bam-9" class="absolute inset-0 flex items-center justify-center font-bold text-[#ffdf7e] text-xl z-20 pointer-events-none hidden font-sans select-none drop-shadow-[0_2px_4px_rgba(0,0,0,0.8)]">SLAM!</div>
                    <div id="mole-9" onclick="whackMole(9)" class="mole">
                        <svg class="w-full h-full p-1 pointer-events-none" viewBox="0 0 100 100">
                            <ellipse cx="50" cy="55" rx="35" ry="30" fill="#d94b8c" />
                            <circle cx="50" cy="45" r="30" fill="#ff7ebd" />
                            <ellipse cx="50" cy="50" rx="10" ry="6" fill="#ffe99e" />
                            <circle cx="50" cy="48" r="4" fill="#1a0b16" />
                            <g class="normal-face"><rect x="33" y="38" width="8" height="8" fill="#1a0b16" /><rect x="59" y="38" width="8" height="8" fill="#1a0b16" /><path d="M 44,58 Q 50,64 56,58" stroke="#1a0b16" stroke-width="4" fill="none" /><rect x="25" y="46" width="6" height="4" fill="#ff2a93" /><rect x="69" y="46" width="6" height="4" fill="#ff2a93" /></g>
                            <g class="whacked-face hidden"><path d="M30,34 L40,44 M40,34 L30,44" stroke="#1a0b16" stroke-width="4" /><path d="M60,34 L70,44 M70,34 L60,44" stroke="#1a0b16" stroke-width="4" /><path d="M42,58 L46,55 L50,58 L54,55 L58,58" stroke="#1a0b16" stroke-width="3" fill="none" /><rect x="42" y="18" width="16" height="6" fill="#ffffff" transform="rotate(-15 50 21)" /></g>
                        </svg>
                    </div>
                </div>
            </div>

            <!-- Controls (Unlocked at 10 Moles) - Next is placed ABOVE Play Again -->
            <div id="mole-control-panel" class="hidden flex flex-col gap-4 justify-center items-center pt-4 border-t-4 border-[#ff2a93]/50 max-w-sm mx-auto">
                <button onclick="handleMoleSuccess()" class="retro-button w-full bg-[#ff2a93] text-white font-bold py-3 px-4 hover:bg-[#ff55a9] text-xs">
                    [ NEXT ]
                </button>
                <button onclick="restartMoleGame()" class="retro-button w-full bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-4 hover:bg-[#2d1226] text-xs">
                    [ PLAY AGAIN ]
                </button>
            </div>
            
            <div id="mole-fail-panel" class="hidden text-center pt-2">
                <div class="text-[#ff3e3e] vt323-text text-xl mb-3">⚠️ TIME'S UP!</div>
                <button onclick="restartMoleGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-48 font-bold py-3 px-4 text-xs">
                    [ RESTART GAME ]
                </button>
            </div>
        </div>

        <!-- NARRATIVE STAGE 4: And STRONGER?! -->
        <div id="stage-story-4" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff3e3e] text-xs uppercase tracking-widest vt323-text text-xl">⚠️ POWER WARNING DETECTED</div>
            <div class="w-20 h-20 mx-auto mb-6 bounce-pixel">
                <svg viewBox="0 0 100 100" class="text-[#ff2a93]" fill="currentColor">
                    <path d="M30 40 C30 20, 50 20, 60 30 C70 40, 70 65, 50 70 L35 70 C28 65, 25 50, 30 40 Z" />
                    <rect x="35" y="60" width="30" height="15" fill="#ffe99e" />
                </svg>
            </div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-4 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="story-text-4" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#ff3e3e] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="handleStory4Next()" class="retro-button bg-[#ff3e3e] text-white font-bold py-3 px-8 text-xs tracking-widest hover:bg-red-500">
                [ NEXT ]
            </button>
        </div>

        <!-- STAGE PUNCH: Arcade Punching Machine (BEST OF 3) -->
        <div id="stage-punch" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/90 p-5 md:p-8 retro-border text-center rounded-sm">
            <div class="mb-1 text-[#ff7ebd] text-xs uppercase tracking-widest vt323-text text-xl">CHALLENGE: MINI-GAME 02 [BEST OF 3]</div>
            <div class="flex justify-between items-center max-w-xs mx-auto mb-2 px-1">
                <span id="punch-round-tracker" class="bg-[#ff2a93] text-white text-xs md:text-sm px-2 py-1 tracking-widest rounded-sm font-sans font-bold">ROUND: 1/3</span>
                <span id="punch-wins-tracker" class="text-[#7effa1] vt323-text text-xl tracking-wider">WINS: 0/2</span>
            </div>
            <h1 class="text-base md:text-xl font-bold mb-2 text-white glitch">ARCADE PUNCH MACHINE</h1>
            <p class="vt323-text text-lg text-[#ff9ed2] mb-4">Time the moving gauges! Score <span class="text-[#ffdf7e] font-bold">over 850</span> in at least 2 rounds!</p>

            <!-- Scoreboard Display -->
            <div class="grid grid-cols-2 gap-2 bg-[#1a0b16] border-4 border-[#ff7ebd] px-4 py-2 mb-6 rounded-md vt323-text text-xl md:text-2xl text-center">
                <div class="text-[#ffdf7e]">PUNCH POWER: <span id="punch-result" class="font-bold text-white">----</span></div>
                <div id="punch-status-text" class="text-[#ff55a9]">READY TO HIT</div>
            </div>

            <!-- Custom Dual-Axis Targeting Matrix -->
            <div class="relative w-64 h-64 mx-auto bg-[#130710] border-4 border-[#ff2a93] mb-6 flex items-center justify-center rounded-sm overflow-hidden">
                <!-- Target Sweet-Spot Crosshair lines -->
                <div class="absolute inset-0 punch-target opacity-40"></div>
                <!-- X-Axis target zone window highlights -->
                <div class="absolute top-0 bottom-0 w-8 bg-[#7effa1]/20 border-l border-r border-[#7effa1]/40"></div>
                <!-- Y-Axis target zone window highlights -->
                <div class="absolute left-0 right-0 h-8 bg-[#7effa1]/20 border-t border-b border-[#7effa1]/40"></div>
                
                <!-- Dynamic Pointer Line indicators -->
                <!-- X Axis Arrow Pointer -->
                <div id="gauge-pointer-x" class="absolute top-0 w-2 h-full bg-[#ffdf7e]" style="left: 0%;">
                    <div class="w-0 h-0 border-l-[6px] border-l-transparent border-r-[6px] border-r-transparent border-t-[8px] border-t-[#ffdf7e] mx-auto -mt-1"></div>
                </div>

                <!-- Y Axis Arrow Pointer -->
                <div id="gauge-pointer-y" class="absolute left-0 h-2 w-full bg-[#ff3e3e]" style="top: 0%;">
                    <div class="w-0 h-0 border-t-[6px] border-t-transparent border-b-[6px] border-b-transparent border-l-[8px] border-l-[#ff3e3e] my-auto -ml-1"></div>
                </div>

                <!-- Decorative center punching bag icon graphics -->
                <div id="punch-bag-graphic" class="z-10 bounce-pixel">
                    <svg class="w-16 h-16 text-[#ff2a93]" viewBox="0 0 100 100" fill="currentColor">
                        <rect x="46" y="0" width="8" height="30" fill="#8c5d75" />
                        <ellipse cx="50" cy="55" rx="24" ry="30" />
                        <circle cx="50" cy="45" r="20" fill="#ff7ebd" />
                        <path d="M 40,45 Q 50,38 60,45" stroke="#1a0b16" stroke-width="4" fill="none" />
                    </svg>
                </div>
            </div>

            <!-- Interaction Buttons Layout -->
            <div class="flex flex-col justify-center items-center gap-4">
                <button id="punch-btn" onclick="triggerPunchAction()" class="retro-button w-full max-w-xs bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] tracking-widest text-sm">
                    💥 [ PUNCH ] 💥
                </button>

                <!-- Next Round Trigger Button -->
                <button id="punch-next-round-btn" onclick="advancePunchRound()" class="hidden retro-button w-full max-w-xs bg-[#7effa1] text-black font-bold py-4 px-6 hover:bg-[#a3ffbc] tracking-widest text-sm">
                    ⏩ [ NEXT ROUND ] ⏩
                </button>

                <!-- Controls revealed upon winning best of three series (Next is placed ABOVE Replay) -->
                <div id="punch-success-panel" class="hidden flex flex-col gap-4 w-full max-w-xs justify-center mt-2 border-t-4 border-[#ff2a93]/30 pt-4 mx-auto">
                    <button onclick="goToStageTuff()" class="retro-button w-full bg-[#7effa1] text-black font-bold py-3 px-4 hover:bg-[#a3ffbc] text-xs">
                        [ NEXT ]
                    </button>
                    <button onclick="resetPunchMachine()" class="retro-button w-full bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-4 text-xs">
                        [ REPLAY ]
                    </button>
                </div>

                <!-- Try again response block if best of three fails -->
                <button id="punch-retry-btn" onclick="resetPunchMachine()" class="hidden retro-button w-full max-w-xs bg-[#3c0c1e] text-[#ff3e3e] border-[#ff3e3e] font-bold py-3 px-4 text-xs">
                    ⚠️ CRITERIA FAILED! [ RETRY SERIES ]
                </button>
            </div>
        </div>

        <!-- NEW STAGE: TUFF -->
        <div id="stage-tuff" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl">CONSOLE EVALUATION</div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="tuff-text" class="typewriter-text vt323-text text-2xl md:text-3xl text-[#ffdf7e] leading-relaxed tracking-wider text-left max-w-sm mx-auto"></p>
            </div>
            <button onclick="goToStageRespect()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-8 text-xs tracking-widest hover:bg-[#ff55a9]">
                [ NEXT ]
            </button>
        </div>

        <!-- NEW STAGE: RESPECT -->
        <div id="stage-respect" class="stage-div hidden w-full max-w-xl bg-black border-4 border-[#ff7ebd] p-6 md:p-10 text-center rounded-sm relative">
            <div class="mb-6 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-xl">METRIC OBTAINED</div>
            <div class="bg-[#1a0b16] border-2 border-[#ff2a93] p-6 mb-8 min-h-32 flex items-center justify-center rounded-sm">
                <p id="respect-text" class="typewriter-text vt323-text text-3xl md:text-4xl text-[#7effa1] font-bold leading-relaxed tracking-widest text-center mx-auto"></p>
            </div>
            <button onclick="goToStageVideo2()" class="retro-button bg-[#7effa1] text-black font-bold py-3 px-8 text-xs tracking-widest hover:bg-[#a3ffbc]">
                [ NEXT ]
            </button>
        </div>

        <!-- NEW ARCADE VIDEO PLAYER STAGE (CHAPTER II) -->
        <div id="stage-video-2" class="stage-div hidden w-full max-w-6xl bg-[#2d1226]/90 p-6 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl flex justify-between px-2">
                <span>ARCADE CINEMATICS: VOL. II</span>
                <span id="video2-progress-tracker" class="text-[#ffdf7e]">CLIP: 1/4</span>
            </div>
            
            <div id="arcade-screen-2" class="arcade-screen w-full aspect-video flex items-center justify-center relative mb-6">
                <!-- Fallback Info Overlay -->
                <div id="video2-fallback-msg" class="absolute inset-0 z-10 flex flex-col items-center justify-center p-6 text-center bg-[#1a0b16]/95 border-2 border-[#ff2a93] hidden">
                    <svg class="w-12 h-12 text-[#ff3e3e] mb-3 animate-pulse" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                    </svg>
                    <span id="video2-fallback-caption" class="text-white text-sm md:text-base font-bold mb-2"></span>
                    <p class="vt323-text text-lg text-[#ff9ed2]">Configure video paths inside JavaScript: <code>VIDEO_PLAYLIST_2</code></p>
                </div>

                <video id="retro-player-2" class="w-full h-full object-contain" playsinline preload="auto">
                    Your browser does not support retro video play.
                </video>
            </div>

            <!-- Control Deck -->
            <div class="bg-[#1a0b16] border-2 border-[#ff7ebd] p-4 rounded flex flex-col justify-center items-center">
                <span id="video2-now-playing" class="vt323-text text-2xl text-[#ffdf7e] mb-4">PLAYING...</span>
                
                <div class="flex gap-4 w-full justify-center">
                    <button id="video2-replay-btn" onclick="replayCurrentVideo2()" class="retro-button bg-[#1a0b16] text-[#ff7ebd] font-bold py-3 px-6 text-xs hover:bg-[#2d1226]">
                        [ REPLAY ]
                    </button>
                    <button id="video2-next-btn" onclick="nextVideoOrStep2()" class="retro-button bg-[#ff2a93] text-white font-bold py-3 px-6 text-xs hover:bg-[#ff55a9]">
                        [ NEXT ]
                    </button>
                </div>
            </div>
        </div>

        <!-- NEW STAGE: THE FINAL DIALOGUE CHOICE -->
        <div id="stage-final-question" class="stage-div hidden w-full max-w-xl bg-[#2d1226]/95 p-6 md:p-10 retro-border text-center rounded-sm">
            <div class="mb-4 text-[#ff2a93] text-xs uppercase tracking-widest vt323-text text-xl">FINAL CORE INQUIRY</div>
            <h1 class="text-lg md:text-2xl font-bold mb-10 text-white leading-relaxed glitch">There are still 393 days left. Do you want to continue?</h1>
            <div class="flex flex-col sm:flex-row gap-6 justify-center items-center mt-6">
                <button onclick="handleUltimateChoice(true)" class="retro-button w-full sm:w-48 bg-[#7effa1] text-black font-bold py-4 px-6 hover:bg-[#a3ffbc] text-sm">
                    [ YES ]
                </button>
                <button onclick="handleUltimateChoice(false)" class="retro-button w-full sm:w-48 bg-black text-white font-bold py-4 px-6 hover:bg-neutral-900 border-[#ff3e3e] text-sm">
                    [ NO ]
                </button>
            </div>
        </div>

        <!-- NEW STAGE: FINAL SUCCESS (YES Choice) -->
        <div id="stage-final-yes" class="stage-div hidden w-full max-w-xl bg-[#1e2d22]/90 p-6 md:p-10 border-4 border-[#7effa1] shadow-[0_0_20px_rgba(126,255,161,0.5)] text-center rounded-sm">
            <div class="mb-4 text-[#7effa1] text-xs uppercase tracking-widest vt323-text text-2xl">CORE SYSTEM ACTIVE</div>
            <div class="w-32 h-32 mx-auto mb-6 flex items-center justify-center bounce-pixel">
                <svg class="w-full h-full text-[#7effa1]" viewBox="0 0 100 100">
                    <rect x="10" y="15" width="80" height="60" rx="8" />
                    <rect x="15" y="20" width="70" height="42" fill="#1e2d22" />
                    <path d="M 30,48 Q 50,60 70,48" stroke="#7effa1" stroke-width="4" fill="none" />
                </svg>
            </div>
            <h1 class="text-xl md:text-3xl font-bold mb-4 text-[#7effa1]">GOOD TO KNOW.</h1>
            <p class="vt323-text text-3xl md:text-4xl text-[#ffdf7e] mb-8 animate-pulse font-bold">Happy 17th Birthday, Charis!</p>
            <button onclick="resetGame()" class="retro-button bg-[#1e2d22] border-[#7effa1] text-[#7effa1] w-full sm:w-48 font-bold py-4 px-6 text-sm">
                [ PLAY AGAIN ]
            </button>
        </div>

        <!-- NEW STAGE: FINAL REJECTION (NO Choice) -->
        <div id="stage-final-no" class="stage-div hidden fixed inset-0 z-50 bg-black flex flex-col items-center justify-center p-4">
            <h1 class="text-6xl md:text-9xl font-mono text-white tracking-widest text-center select-none animate-pulse">Oh.</h1>
            <button onclick="resetGame()" class="mt-16 px-4 py-2 border-2 border-white text-white bg-black hover:bg-white hover:text-black font-sans text-xs tracking-widest transition duration-200">
                [ RETURN TO THE GRID ]
            </button>
        </div>

        <!-- REJECT PANELS -->
        <div id="stage-reject-1" class="stage-div hidden w-full max-w-xl bg-[#3c0c1e]/90 p-8 text-center retro-border border-[#ff3e3e]">
            <h1 class="text-xl md:text-3xl font-bold mb-6 text-[#ff3e3e] glitch">Get out Clanker!!</h1>
            <button onclick="resetGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-48 font-bold py-4 px-6 text-sm">[ REBOOT SYSTEM ]</button>
        </div>
        <div id="stage-reject-2" class="stage-div hidden w-full max-w-xl bg-[#3c0c1e]/90 p-8 text-center retro-border border-[#ff3e3e]">
            <h1 class="text-xl md:text-3xl font-bold mb-6 text-[#ff3e3e] glitch">Get out you scank!!</h1>
            <button onclick="resetGame()" class="retro-button bg-[#1a0b16] border-[#ff3e3e] text-[#ff3e3e] w-full sm:w-48 font-bold py-4 px-6 text-sm">[ RETRY ENTRY ]</button>
        </div>

    </main>

    <footer class="w-full text-center py-4 bg-[#1a0b16] text-[#ff7ebd] text-[10px] md:text-xs z-10 flex flex-col sm:flex-row justify-between items-center px-6 gap-2">
        <p>© 2007 DARSHI and CO. ALL RIGHTS RESERVED.</p>
        <div class="flex gap-4"><span class="blink">INSERT COIN</span><span class="text-[#ffdf7e]">HI-SCORE: 99999</span></div>
    </footer>

    <!-- Core Game Controller Script Engine -->
    <script>
        // ==========================================
        // 🚨 PLAYLIST I PATHS CONFIGURATION HERE 🚨
        // ==========================================
        const VIDEO_PLAYLIST = [
            { src: "videos/clip3.mp4", caption: "video1" },
            { src: "videos/clip3.mp4", caption: "Video2" },
            { src: "videos/clip3.mp4", caption: "video3" },
            { src: "videos/clip4.mp4", caption: "video4" }
        ];

        // ==========================================
        // 🚨 PLAYLIST II PATHS CONFIGURATION HERE 🚨
        // ==========================================
        const VIDEO_PLAYLIST_2 = [
            { src: "videos/clip5.mp4", caption: "video5" },
            { src: "videos/clip6.mp4", caption: "video6" },
            { src: "videos/clip7.mp4", caption: "video7" },
            { src: "videos/clip8.mp4", caption: "video8" }
        ];

        // DOM Handles
        const selectSound = document.getElementById('select-sound');
        const successSound = document.getElementById('success-sound');
        const failSound = document.getElementById('fail-sound');
        const whackSound = document.getElementById('whack-sound');
        const scoreCounter = document.getElementById('score-counter');
        const stageTransition = document.getElementById('stage-transition');
        const transitionText = document.getElementById('transition-text');
        const progressBar = document.getElementById('progress-bar');
        const retroPlayer = document.getElementById('retro-player');
        const retroPlayer2 = document.getElementById('retro-player-2');
        const bgmBtn = document.getElementById('bgm-toggle-btn');
        const arcadeScreen2 = document.getElementById('arcade-screen-2');
        
        let currentScore = 0;
        let selectedStrawberries = [];
        
        // Captcha State (Best of 3)
        let captchaRound = 1;

        // Video Stage State Variables
        let currentVideoIndex = 0;
        let currentVideoIndex2 = 0;

        // Mini-Game 1 (Mole) Variables
        let molePoints = 0;
        let activeMoleId = null;
        let moleTimerInterval = null;
        let moleSpawnTimeout = null;
        let moleTimeLeft = 30;
        let moleGameActive = false;

        // Mini-Game 2 (Punch Engine) Variables
        let punchGameActive = false;
        let activeAxis = 'X';
        let punchValX = 0;
        let punchValY = 0;
        let dirX = 0.5;
        let dirY = 0.6;
        let loopPunchGauge = null;
        const targetSweetSpot = 50;
        
        // Punch Game Best of 3 State
        let punchRound = 1;
        let punchWins = 0;

        // BGM Web Audio Synthesis Logic (Runs client-side dynamically)
        let audioCtx = null;
        let nextNoteTime = 0.0;
        let noteSeqIdx = 0;
        let melodyIntervalId = null;
        let isMuted = false;

        // Retro Pink 8-bit Synthesizer score
        const tempo = 120;
        const secondsPerBeat = 60.0 / tempo;
        const scaleFreqs = {
            'C4': 261.63, 'D4': 293.66, 'E4': 329.63, 'F4': 349.23, 'G4': 392.00, 'A4': 440.00, 'B4': 493.88,
            'C5': 523.25, 'D5': 587.33, 'E5': 659.25, 'F5': 698.46, 'G5': 783.99, 'A5': 880.00, 'B5': 987.77
        };
        const cuteMelody = [
            'E4', 'G4', 'A4', 'C5', 'A4', 'C5', 'D5', 'E5', 
            'D5', 'C5', 'A4', 'G4', 'E4', 'D4', 'E4', 'G4',
            'A4', 'A4', 'C5', 'C5', 'E5', 'D5', 'C5', 'A4',
            'G4', 'G4', 'A4', 'B4', 'C5', 'D5', 'C5', 'E5'
        ];

        function initAudioContextOnInteraction() {
            if (audioCtx) return; // Already started
            
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            nextNoteTime = audioCtx.currentTime;
            
            // Loop Scheduler
            melodyIntervalId = setInterval(scheduleMelody, 25);
        }

        function scheduleMelody() {
            if (isMuted) return;
            while (nextNoteTime < audioCtx.currentTime + 0.1) {
                play8BitSynthNote(cuteMelody[noteSeqIdx], nextNoteTime);
                nextNoteTime += secondsPerBeat * 0.5; // Eighth note scheduling
                noteSeqIdx = (noteSeqIdx + 1) % cuteMelody.length;
            }
        }

        function play8BitSynthNote(noteName, time) {
            if (!audioCtx || isMuted) return;
            
            let osc = audioCtx.createOscillator();
            let gainNode = audioCtx.createGain();
            
            // Retro triangle/square sound wave
            osc.type = 'triangle';
            osc.frequency.value = scaleFreqs[noteName] || 440;
            
            // Cute soft envelope
            gainNode.gain.setValueAtTime(0.001, time);
            gainNode.gain.linearRampToValueAtTime(0.05, time + 0.05);
            gainNode.gain.exponentialRampToValueAtTime(0.001, time + 0.25);
            
            osc.connect(gainNode);
            gainNode.connect(audioCtx.destination);
            
            osc.start(time);
            osc.stop(time + 0.3);
        }

        function toggleMute() {
            isMuted = !isMuted;
            if (isMuted) {
                bgmBtn.textContent = "🔇 BGM: OFF";
                bgmBtn.classList.remove('bg-[#ff2a93]');
                bgmBtn.classList.add('bg-[#1a0b16]');
            } else {
                bgmBtn.textContent = "🔊 BGM: ON";
                bgmBtn.classList.add('bg-[#ff2a93]');
                bgmBtn.classList.remove('bg-[#1a0b16]');
            }
            playSound('select');
        }

        function playSound(type) {
            try {
                if (type === 'select') { selectSound.currentTime = 0; selectSound.play(); }
                else if (type === 'success') { successSound.currentTime = 0; successSound.play(); }
                else if (type === 'fail') { failSound.currentTime = 0; failSound.play(); }
                else if (type === 'whack') { whackSound.currentTime = 0; whackSound.play(); }
            } catch (e) {}
        }

        function addScore(amount) {
            currentScore += amount;
            scoreCounter.textContent = "SCORE: " + String(currentScore).padStart(5, '0');
        }

        function showStage(stageId) {
            document.querySelectorAll('.stage-div').forEach(s => s.classList.add('hidden'));
            document.getElementById(stageId).classList.remove('hidden');
        }

        function runTransition(message, nextStageCallback) {
            stageTransition.classList.remove('hidden');
            transitionText.textContent = message;
            progressBar.style.width = '0%';
            playSound('success');
            let p = 0;
            const inter = setInterval(() => {
                p += 10;
                progressBar.style.width = `${p}%`;
                if (p >= 100) {
                    clearInterval(inter);
                    setTimeout(() => {
                        stageTransition.classList.add('hidden');
                        nextStageCallback();
                    }, 300);
                }
            }, 100);
        }

        // STARTUP SCREEN WITH PERFECTLY ALIGNED COUNTDOWN BAR
        function startPreloader() {
            const preloader = document.getElementById('stage-preloader');
            const progress = document.getElementById('preloader-progress');
            const countdownText = document.getElementById('preloader-counter');
            
            // Diagnostics terminal log simulation
            setTimeout(() => { document.getElementById('loader-log-1').classList.remove('hidden'); playSound('select'); }, 1200);
            setTimeout(() => { document.getElementById('loader-log-2').classList.remove('hidden'); playSound('select'); }, 2800);
            setTimeout(() => { document.getElementById('loader-log-3').classList.remove('hidden'); playSound('select'); }, 4200);
            setTimeout(() => { document.getElementById('loader-log-4').classList.remove('hidden'); playSound('success'); }, 5800);

            let secondsLeft = 7;
            let currentWidth = 0;

            const countdownInterval = setInterval(() => {
                secondsLeft--;
                if (secondsLeft >= 0) {
                    countdownText.textContent = `${secondsLeft}s`;
                }
                if (secondsLeft <= 0) {
                    clearInterval(countdownInterval);
                }
            }, 1000);

            const barInterval = setInterval(() => {
                currentWidth += 1.43; // Reaches 100% over ~7 seconds
                if (currentWidth >= 100) currentWidth = 100;
                progress.style.width = `${currentWidth}%`;
                
                if (currentWidth >= 100) {
                    clearInterval(barInterval);
                    setTimeout(() => {
                        preloader.classList.add('opacity-0');
                        preloader.style.transition = "opacity 0.5s ease";
                        setTimeout(() => {
                            preloader.classList.add('hidden');
                            showStage('stage-1');
                        }, 500);
                    }, 200);
                }
            }, 100);
        }

        // TEXT TYPEWRITER ANIMATION ENGINE
        function typeWriterEffect(elementId, text, index = 0, callback = null) {
            const element = document.getElementById(elementId);
            if (index === 0) {
                element.innerHTML = "";
            }
            if (index < text.length) {
                element.innerHTML += text.charAt(index);
                if (index % 3 === 0) playSound('select');
                setTimeout(() => {
                    typeWriterEffect(elementId, text, index + 1, callback);
                }, 50);
            } else if (callback) {
                callback();
            }
        }

        // STAGE ROUTERS & EVENT HANDLERS
        function handleStage1(isHuman) {
            playSound('select');
            if (isHuman) { addScore(100); runTransition("HUMANITY CONFIRMED...", () => showStage('stage-2')); }
            else { playSound('fail'); showStage('stage-reject-1'); }
        }

        function handleStage2(isCharis) {
            playSound('select');
            if (isCharis) { addScore(200); runTransition("IDENTITY MATCHED...", () => showStage('stage-3')); }
            else { playSound('fail'); showStage('stage-reject-2'); }
        }

        function handleStage3() {
            playSound('select'); addScore(300);
            runTransition("LOADING STORY SCENE I...", () => {
                showStage('stage-story-1');
                typeWriterEffect('story-text-1', "Long, Long Ago... In the distant and mystical land of Dharwad...");
            });
        }

        // STORY SCENE 1 -> STORY SCENE 2
        function handleStory1Next() {
            playSound('select');
            runTransition("LOADING STORY SCENE II...", () => {
                showStage('stage-story-2');
                typeWriterEffect('story-text-2', "...Charis was born.");
            });
        }

        // STORY SCENE 2 -> CAPTCHA (Round 1 Boot)
        function handleStory2Next() {
            playSound('select');
            captchaRound = 1;
            runTransition("BOOTING SECURITY PROTOCOLS...", () => {
                showStage('stage-captcha');
                buildRoundCaptcha();
            });
        }

        // CAPTCHA DYNAMIC SHUFFLED ROUND RENDERER
        const captchaFruitPool = {
            strawberry: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                            <path d="M16 4 H24 V8 H16 Z" fill="#7effa1"/>
                            <path d="M12 8 H28 V12 H12 Z" fill="#58c973"/>
                            <path d="M10 12 H30 V20 H10 Z" fill="#ff2a93"/>
                            <path d="M8 16 H32 V24 H8 Z" fill="#ff2a93"/>
                            <path d="M12 24 H28 V28 H12 Z" fill="#ff2a93"/>
                            <path d="M14 28 H26 V32 H14 Z" fill="#e01b7c"/>
                            <path d="M18 32 H22 V36 H18 Z" fill="#b0105e"/>
                            <rect x="14" y="16" width="2" height="2" fill="#ffdf7e" />
                            <rect x="24" y="16" width="2" height="2" fill="#ffdf7e" />
                            <rect x="18" y="22" width="2" height="2" fill="#ffdf7e" />
                            <rect x="28" y="22" width="2" height="2" fill="#ffdf7e" />
                            <rect x="12" y="24" width="2" height="2" fill="#ffdf7e" />
                            <rect x="22" y="26" width="2" height="2" fill="#ffdf7e" />
                        </svg>
                        <span class="vt323-text text-sm text-[#ff9ed2]">RED BERRY</span>`,
            apple: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <path d="M18 4 H22 V10 H18 Z" fill="#8c5d3a"/>
                        <path d="M22 6 H26 V8 H22 Z" fill="#7effa1"/>
                        <circle cx="20" cy="22" r="12" fill="#ff3e3e" />
                        <circle cx="16" cy="22" r="10" fill="#e62e2e" />
                        <rect x="15" y="15" width="3" height="3" fill="#ffffff" />
                    </svg>
                    <span class="vt323-text text-sm text-[#ff9ed2]">CRUNCHY APPLE</span>`,
            grape: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <path d="M18 6 H22 V10 H18 Z" fill="#7effa1"/>
                        <circle cx="16" cy="14" r="5" fill="#a83eff" />
                        <circle cx="24" cy="14" r="5" fill="#a83eff" />
                        <circle cx="20" cy="20" r="5" fill="#8d26e0" />
                        <circle cx="15" cy="26" r="5" fill="#8d26e0" />
                        <circle cx="25" cy="26" r="5" fill="#8d26e0" />
                        <circle cx="20" cy="31" r="5" fill="#6611ab" />
                    </svg>
                    <span class="vt323-text text-sm text-[#ff9ed2]">SOUR SACK</span>`,
            lemon: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <ellipse cx="20" cy="20" rx="14" ry="9" fill="#ffdf7e" />
                        <ellipse cx="20" cy="20" rx="11" ry="7" fill="#ffe99e" />
                        <rect x="6" y="18" width="3" height="3" fill="#e6c45e" />
                        <rect x="31" y="18" width="3" height="3" fill="#e6c45e" />
                    </svg>
                    <span class="vt323-text text-sm text-[#ff9ed2]">ZESTY SQUEEZE</span>`,
            orange: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <circle cx="20" cy="22" r="11" fill="#ffa23e" />
                        <circle cx="18" cy="20" r="9" fill="#ffb86b" />
                        <rect x="19" y="8" width="2" height="4" fill="#5c8c3a" />
                    </svg>
                    <span class="vt323-text text-sm text-[#ff9ed2]">TANGY PULP</span>`,
            blueberry: `<svg class="w-full h-[70%] pointer-events-none" viewBox="0 0 40 40" fill="none">
                        <circle cx="20" cy="22" r="9" fill="#3e7bff" />
                        <circle cx="18" cy="20" r="7" fill="#6ba2ff" />
                        <rect x="18" y="10" width="4" height="3" fill="#1b3ea1" />
                    </svg>
                    <span class="vt323-text text-sm text-[#ff9ed2]">BLUE GLOBULE</span>`
        };

        let currentShuffledLayout = [];

        function buildRoundCaptcha() {
            selectedStrawberries = [];
            document.getElementById('captcha-round-tracker').textContent = `ROUND: ${captchaRound}/3`;
            
            // Build temporary array: exactly 3 strawberries and 3 other unique random fruits
            const otherFruits = ['apple', 'grape', 'lemon', 'orange', 'blueberry'];
            shuffleArray(otherFruits);
            const selectedOthers = otherFruits.slice(0, 3);
            
            // 6 Items list
            const rawItems = [
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: 'strawberry', content: captchaFruitPool.strawberry },
                { type: selectedOthers[0], content: captchaFruitPool[selectedOthers[0]] },
                { type: selectedOthers[1], content: captchaFruitPool[selectedOthers[1]] },
                { type: selectedOthers[2], content: captchaFruitPool[selectedOthers[2]] }
            ];

            // Shuffle layout positions
            shuffleArray(rawItems);
            currentShuffledLayout = rawItems;

            const gridContainer = document.getElementById('captcha-cards-grid');
            gridContainer.innerHTML = '';

            currentShuffledLayout.forEach((item, idx) => {
                const card = document.createElement('div');
                card.id = `captcha-card-${idx}`;
                card.onclick = () => selectCaptchaItem(idx);
                card.className = "pixel-card bg-[#1a0b16] border-4 border-[#ff7ebd] p-2 aspect-square flex flex-col justify-between items-center cursor-pointer relative rounded-md select-none";
                card.innerHTML = item.content;
                gridContainer.appendChild(card);
            });

            updateVerifyButton();
        }

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
        }

        function selectCaptchaItem(index) {
            playSound('select');
            const card = document.getElementById(`captcha-card-${index}`);
            if (selectedStrawberries.includes(index)) {
                selectedStrawberries = selectedStrawberries.filter(item => item !== index);
                card.style.borderColor = "#ff7ebd";
                card.style.boxShadow = "none";
            } else {
                selectedStrawberries.push(index);
                card.style.borderColor = "#7effa1";
                card.style.boxShadow = "0 0 15px rgba(126, 255, 161, 0.6)";
            }
            updateVerifyButton();
        }

        function updateVerifyButton() {
            const btn = document.getElementById('captcha-submit-btn');
            const warn = document.getElementById('captcha-warning');
            if (selectedStrawberries.length > 0) {
                btn.className = "retro-button w-full sm:w-64 bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] text-sm cursor-pointer";
                btn.removeAttribute('disabled');
                warn.textContent = `Selected: ${selectedStrawberries.length} element(s)`;
            } else {
                btn.className = "retro-button-disabled cursor-not-allowed w-full sm:w-64 text-[#8c5d75] font-bold py-4 px-6 text-sm";
                btn.setAttribute('disabled', 'true');
                warn.textContent = "Select all 3 strawberries to proceed!";
            }
        }

        function submitCaptcha() {
            // Count selections
            const isAllCorrect = selectedStrawberries.every(idx => currentShuffledLayout[idx].type === 'strawberry') 
                                && selectedStrawberries.length === 3;

            if (isAllCorrect) {
                addScore(200); 
                playSound('success');
                if (captchaRound < 3) {
                    captchaRound++;
                    runTransition(`ROUND ${captchaRound - 1} CLEAR! LOADING NEXT...`, () => {
                        buildRoundCaptcha();
                    });
                } else {
                    // Passed all 3 rounds successfully
                    handleCaptchaSuccess();
                }
            } else {
                playSound('fail'); 
                addScore(-50);
                const box = document.getElementById('stage-captcha');
                box.classList.add('shake-element');
                document.getElementById('captcha-warning').textContent = "⚠️ REJECTED! Try again!";
                setTimeout(() => { 
                    box.classList.remove('shake-element'); 
                    captchaRound = 1; // Reset to round 1 of best of 3!
                    buildRoundCaptcha(); 
                }, 1000);
            }
        }

        // CAPTCHA -> STORY SCENE 3 ("Hmm? Smarter than I thought!!")
        function handleCaptchaSuccess() {
            runTransition("VALIDATING SECURITY CODE...", () => {
                showStage('stage-story-3');
                typeWriterEffect('story-text-3', "Hmm? Smarter than I thought!!");
            });
        }

        // STORY SCENE 3 -> NEW VIDEO PLAYER STAGE
        function handleStory3Next() {
            playSound('select');
            runTransition("PREPARING KINETIC MEMORIES...", () => {
                showStage('stage-video');
                currentVideoIndex = 0;
                playVideoPlaylist();
            });
        }

        // PLAYLIST CONTROLLER ENGINE (VOL 1)
        function playVideoPlaylist() {
            const item = VIDEO_PLAYLIST[currentVideoIndex];
            
            document.getElementById('video-progress-tracker').textContent = `CLIP: ${currentVideoIndex + 1}/4`;
            document.getElementById('video-now-playing').textContent = `NOW PLAYING: ${item.caption}`;

            document.getElementById('video-replay-btn').classList.add('hidden');
            document.getElementById('video-next-btn').classList.add('hidden');

            const fallbackBox = document.getElementById('video-fallback-msg');
            fallbackBox.classList.add('hidden');

            retroPlayer.pause();
            retroPlayer.src = item.src;
            retroPlayer.load();

            let loadTimer = setTimeout(() => {
                showVideoFallback(item.caption);
            }, 1500);

            retroPlayer.oncanplay = function() {
                clearTimeout(loadTimer);
                retroPlayer.play().catch(() => {
                    showVideoFallback(item.caption);
                });
            };

            retroPlayer.onerror = function() {
                clearTimeout(loadTimer);
                showVideoFallback(item.caption);
            };

            retroPlayer.onended = function() {
                revealPlaybackControls();
            };
        }

        function showVideoFallback(caption) {
            const fallbackBox = document.getElementById('video-fallback-msg');
            document.getElementById('video-fallback-caption').textContent = `🎥 COMPILING: "${caption}"`;
            fallbackBox.classList.remove('hidden');
            revealPlaybackControls();
        }

        function revealPlaybackControls() {
            document.getElementById('video-replay-btn').classList.remove('hidden');
            document.getElementById('video-next-btn').classList.remove('hidden');
            playSound('success');
        }

        function replayCurrentVideo() {
            playSound('select');
            const fallbackBox = document.getElementById('video-fallback-msg');
            
            if (fallbackBox.classList.contains('hidden')) {
                retroPlayer.currentTime = 0;
                retroPlayer.play();
                document.getElementById('video-replay-btn').classList.add('hidden');
                document.getElementById('video-next-btn').classList.add('hidden');
            } else {
                const videoBox = document.getElementById('stage-video');
                videoBox.classList.add('shake-element');
                setTimeout(() => { videoBox.classList.remove('shake-element'); }, 300);
            }
        }

        function nextVideoOrStep() {
            playSound('select');
            retroPlayer.pause();
            
            currentVideoIndex++;
            if (currentVideoIndex < VIDEO_PLAYLIST.length) {
                playVideoPlaylist();
            } else {
                runTransition("LOADING WHACK-A-MOLE...", () => {
                    showStage('stage-mole');
                    startMoleGame();
                });
            }
        }

        // WHACK-A-MOLE -> STORY SCENE 4 ("And... STRONGER?!")
        function handleMoleSuccess() {
            playSound('select');
            runTransition("UPDATING STRENGTH SCORE...", () => {
                showStage('stage-story-4');
                typeWriterEffect('story-text-4', "And... STRONGER?!");
            });
        }

        // STORY SCENE 4 -> PUNCHING MACHINE
        function handleStory4Next() {
            playSound('select');
            runTransition("LOADING ARCADE PUNCH MACHINE...", () => {
                showStage('stage-punch');
                // Reset whole Best of 3 parameters
                punchRound = 1;
                punchWins = 0;
                resetPunchMachine();
            });
        }

        // NEW STAGE TRIGGERS POST-PUNCH
        function goToStageTuff() {
            playSound('select');
            runTransition("EVALUATING DURABILITY CORE...", () => {
                showStage('stage-tuff');
                typeWriterEffect('tuff-text', "You really must be very Tuff...");
            });
        }

        function goToStageRespect() {
            playSound('select');
            runTransition("CONSOLIDATING RESPECT SCORE...", () => {
                showStage('stage-respect');
                typeWriterEffect('respect-text', "Respect 100%");
            });
        }

        function goToStageVideo2() {
            playSound('select');
            runTransition("PREPARING MOUNT VOL. II KINETICS...", () => {
                showStage('stage-video-2');
                currentVideoIndex2 = 0;
                playVideoPlaylist2();
            });
        }

        // PLAYLIST II CONTROLLER ENGINE
        function playVideoPlaylist2() {
            const item = VIDEO_PLAYLIST_2[currentVideoIndex2];
            const isLastVideo = (currentVideoIndex2 === VIDEO_PLAYLIST_2.length - 1);
            
            document.getElementById('video2-progress-tracker').textContent = `CLIP: ${currentVideoIndex2 + 1}/4`;
            document.getElementById('video2-now-playing').textContent = `NOW PLAYING: ${item.caption}`;

            document.getElementById('video2-replay-btn').classList.add('hidden');
            document.getElementById('video2-next-btn').classList.add('hidden');

            const fallbackBox = document.getElementById('video2-fallback-msg');
            fallbackBox.classList.add('hidden');

            // Apply special epic larger scaling effect for the LAST video of second playlist
            if (isLastVideo) {
                arcadeScreen2.classList.add('scale-105', 'md:scale-110', 'shadow-[0_0_40px_rgba(255,42,147,0.85)]');
                document.getElementById('video2-now-playing').innerHTML = `🌟 FINAL CLIP: <span class="blink text-white font-bold">${item.caption}</span> 🌟`;
            } else {
                arcadeScreen2.classList.remove('scale-105', 'md:scale-110', 'shadow-[0_0_40px_rgba(255,42,147,0.85)]');
            }

            retroPlayer2.pause();
            retroPlayer2.src = item.src;
            retroPlayer2.load();

            let loadTimer = setTimeout(() => {
                showVideo2Fallback(item.caption);
            }, 1500);

            retroPlayer2.oncanplay = function() {
                clearTimeout(loadTimer);
                retroPlayer2.play().catch(() => {
                    showVideo2Fallback(item.caption);
                });
            };

            retroPlayer2.onerror = function() {
                clearTimeout(loadTimer);
                showVideo2Fallback(item.caption);
            };

            retroPlayer2.onended = function() {
                revealPlaybackControls2();
            };
        }

        function showVideo2Fallback(caption) {
            const fallbackBox = document.getElementById('video2-fallback-msg');
            document.getElementById('video2-fallback-caption').textContent = `🎥 COMPILING: "${caption}"`;
            fallbackBox.classList.remove('hidden');
            revealPlaybackControls2();
        }

        function revealPlaybackControls2() {
            document.getElementById('video2-replay-btn').classList.remove('hidden');
            document.getElementById('video2-next-btn').classList.remove('hidden');
            playSound('success');
        }

        function replayCurrentVideo2() {
            playSound('select');
            const fallbackBox = document.getElementById('video2-fallback-msg');
            
            if (fallbackBox.classList.contains('hidden')) {
                retroPlayer2.currentTime = 0;
                retroPlayer2.play();
                document.getElementById('video2-replay-btn').classList.add('hidden');
                document.getElementById('video2-next-btn').classList.add('hidden');
            } else {
                const videoBox = document.getElementById('stage-video-2');
                videoBox.classList.add('shake-element');
                setTimeout(() => { videoBox.classList.remove('shake-element'); }, 300);
            }
        }

        function nextVideoOrStep2() {
            playSound('select');
            retroPlayer2.pause();
            
            currentVideoIndex2++;
            if (currentVideoIndex2 < VIDEO_PLAYLIST_2.length) {
                playVideoPlaylist2();
            } else {
                // Done playing volume 2 of video files -> final inquiry decision choice
                runTransition("CONSOLIDATING DATA...", () => {
                    showStage('stage-final-question');
                });
            }
        }

        // ULTIMATE CHOICE ROUTER (YES OR NO)
        function handleUltimateChoice(choice) {
            playSound('select');
            if (choice) {
                addScore(1000);
                runTransition("FINALIZING CONNECT...", () => {
                    showStage('stage-final-yes');
                });
            } else {
                // Drop out to empty pitch black screen with a single white "Oh."
                playSound('fail');
                showStage('stage-final-no');
            }
        }

        // WHACK-A-MOLE GAME LOGIC (CLASSIC EASY RETRACTION BUT CHALLENGING SPONTANEOUS DELAYS)
        function startMoleGame() {
            molePoints = 0; moleTimeLeft = 30; moleGameActive = true;
            document.getElementById('mole-score').textContent = molePoints;
            document.getElementById('mole-control-panel').classList.add('hidden');
            document.getElementById('mole-fail-panel').classList.add('hidden');
            document.getElementById('mole-timer').textContent = `TIME: ${moleTimeLeft}s`;
            
            for(let i=1; i<=9; i++) {
                const moleEl = document.getElementById(`mole-${i}`);
                if (moleEl) {
                    moleEl.querySelector('.normal-face').classList.remove('hidden');
                    moleEl.querySelector('.whacked-face').classList.add('hidden');
                    moleEl.classList.remove('up');
                }
            }

            clearInterval(moleTimerInterval);
            moleTimerInterval = setInterval(() => {
                if (!moleGameActive) return;
                moleTimeLeft--;
                document.getElementById('mole-timer').textContent = `TIME: ${moleTimeLeft}s`;
                if (moleTimeLeft <= 0) endMoleGame(false);
            }, 1000);

            clearTimeout(moleSpawnTimeout);
            tickMoleClassicSpeed();
        }

        function tickMoleClassicSpeed() {
            if (!moleGameActive) return;

            // Restored the original comfortable show duration so the mole doesn't go back in instantly
            const showDuration = 1000; 
            // Randomized, uneven intervals between moles appearing: 200ms to 950ms
            const nextSpawnDelay = Math.random() * 750 + 200;

            spawnMole();

            // Store current active ID locally to pull down after the classic show duration expires
            const activeIdAtSpawn = activeMoleId;
            setTimeout(() => {
                if (!moleGameActive) return;
                const moleToRetract = document.getElementById(`mole-${activeIdAtSpawn}`);
                if (moleToRetract && moleToRetract.classList.contains('up')) {
                    if (!moleToRetract.querySelector('.normal-face').classList.contains('hidden')) {
                        moleToRetract.classList.remove('up');
                    }
                }
            }, showDuration);

            // Recursively schedule next mole appearance using the classic duration + randomized delay
            moleSpawnTimeout = setTimeout(tickMoleClassicSpeed, showDuration + nextSpawnDelay);
        }

        function spawnMole() {
            if (activeMoleId) {
                const prevMole = document.getElementById(`mole-${activeMoleId}`);
                if (prevMole && !prevMole.querySelector('.normal-face').classList.contains('hidden')) {
                    prevMole.classList.remove('up');
                }
            }
            // Generate a random mole hole index
            const newId = Math.floor(Math.random() * 9) + 1;
            const newMole = document.getElementById(`mole-${newId}`);
            newMole.querySelector('.normal-face').classList.remove('hidden');
            newMole.querySelector('.whacked-face').classList.add('hidden');
            newMole.classList.add('up');
            activeMoleId = newId;
        }

        function whackMole(id) {
            if (!moleGameActive) return;
            const el = document.getElementById(`mole-${id}`);
            if (el.classList.contains('up') && el.querySelector('.whacked-face').classList.contains('hidden')) {
                playSound('whack');
                
                el.querySelector('.normal-face').classList.add('hidden');
                el.querySelector('.whacked-face').classList.remove('hidden');

                const bamText = document.getElementById(`bam-${id}`);
                bamText.classList.remove('hidden');
                
                const arena = document.getElementById('mole-arena');
                arena.classList.add('shake-element');

                setTimeout(() => {
                    arena.classList.remove('shake-element');
                    bamText.classList.add('hidden');
                    el.classList.remove('up');
                }, 400);

                molePoints++;
                document.getElementById('mole-score').textContent = molePoints;
                addScore(50);
                
                if (molePoints >= 10) {
                    setTimeout(() => { endMoleGame(true); }, 500);
                }
            }
        }

        function endMoleGame(success) {
            moleGameActive = false;
            clearInterval(moleTimerInterval); 
            clearTimeout(moleSpawnTimeout);
            
            // Retract remaining moles
            for (let i = 1; i <= 9; i++) {
                const mole = document.getElementById(`mole-${i}`);
                if (mole) mole.classList.remove('up');
            }

            if (success) { 
                playScoreFeedback(true); 
                document.getElementById('mole-control-panel').classList.remove('hidden'); 
            } else { 
                playSound('fail'); 
                document.getElementById('mole-fail-panel').classList.remove('hidden'); 
            }
        }

        function restartMoleGame() { playSound('select'); startMoleGame(); }
        function playScoreFeedback(s) { if(s) playSound('success'); else playSound('fail'); }

        // ARCADE PUNCHING MACHINE LOGIC (BEST OF 3 INTERFACE)
        function resetPunchMachine() {
            punchGameActive = true;
            activeAxis = 'X';
            punchValX = 0;
            punchValY = 0;
            dirX = 0.5;
            dirY = 0.6;
            
            // Update tracking counters in header UI
            document.getElementById('punch-round-tracker').textContent = `ROUND: ${punchRound}/3`;
            document.getElementById('punch-wins-tracker').textContent = `WINS: ${punchWins}/2`;
            
            document.getElementById('punch-result').textContent = "----";
            document.getElementById('punch-status-text').textContent = "LOCK X-AXIS";
            document.getElementById('punch-status-text').className = "text-[#ffdf7e]";
            
            document.getElementById('punch-btn').className = "retro-button w-full max-w-xs bg-[#ff2a93] text-white font-bold py-4 px-6 hover:bg-[#ff55a9] tracking-widest text-sm";
            document.getElementById('punch-btn').textContent = "💥 [ LOCK X ] 💥";
            document.getElementById('punch-btn').style.display = 'block';

            document.getElementById('punch-next-round-btn').classList.add('hidden');
            document.getElementById('punch-success-panel').classList.add('hidden');
            document.getElementById('punch-retry-btn').classList.add('hidden');

            cancelAnimationFrame(loopPunchGauge);
            animationGaugeLoop();
        }

        function animationGaugeLoop() {
            if (!punchGameActive) return;

            if (activeAxis === 'X') {
                punchValX += dirX;
                if (punchValX >= 100 || punchValX <= 0) dirX = -dirX;
                document.getElementById('gauge-pointer-x').style.left = `${punchValX}%`;
            } else if (activeAxis === 'Y') {
                punchValY += dirY;
                if (punchValY >= 100 || punchValY <= 0) dirY = -dirY;
                document.getElementById('gauge-pointer-y').style.top = `${punchValY}%`;
            }

            loopPunchGauge = requestAnimationFrame(animationGaugeLoop);
        }

        function triggerPunchAction() {
            if (!punchGameActive) return;
            playSound('select');

            if (activeAxis === 'X') {
                activeAxis = 'Y';
                document.getElementById('punch-status-text').textContent = "LOCK Y-AXIS";
                document.getElementById('punch-status-text').className = "text-[#ff3e3e]";
                document.getElementById('punch-btn').textContent = "💥 [ PUNCH ! ] 💥";
            } else if (activeAxis === 'Y') {
                punchGameActive = false;
                cancelAnimationFrame(loopPunchGauge);

                const diffX = Math.abs(punchValX - targetSweetSpot);
                const diffY = Math.abs(punchValY - targetSweetSpot);
                
                const accuracyRating = 100 - (diffX + diffY); 
                let finalCalculatedScore = Math.floor(accuracyRating * 10);
                
                if (finalCalculatedScore > 1000) finalCalculatedScore = 1000;
                if (finalCalculatedScore < 100) finalCalculatedScore = Math.floor(Math.random() * 150) + 50;

                document.getElementById('punch-result').textContent = String(finalCalculatedScore).padStart(3, '0');
                
                const structuralBag = document.getElementById('punch-bag-graphic');
                structuralBag.classList.add('shake-element');
                playSound('whack');

                setTimeout(() => { structuralBag.classList.remove('shake-element'); }, 400);

                // Round Success evaluation
                const isRoundWin = finalCalculatedScore >= 850;
                if (isRoundWin) {
                    playSound('success');
                    punchWins++;
                    addScore(finalCalculatedScore);
                    document.getElementById('punch-status-text').textContent = "🔥 POWER BONUS!";
                    document.getElementById('punch-status-text').className = "text-[#7effa1]";
                } else {
                    playSound('fail');
                    document.getElementById('punch-status-text').textContent = "❌ TOO WEAK!";
                    document.getElementById('punch-status-text').className = "text-[#ff3e3e]";
                }

                // Update trackers immediately
                document.getElementById('punch-wins-tracker').textContent = `WINS: ${punchWins}/2`;
                document.getElementById('punch-btn').style.display = 'none';

                // Evaluate Best of 3 parameters after completion of the hit animation
                setTimeout(() => {
                    if (punchRound < 3) {
                        // Show "Next Round" transitional action key
                        document.getElementById('punch-next-round-btn').classList.remove('hidden');
                        document.getElementById('punch-next-round-btn').textContent = `⏩ [ START ROUND ${punchRound + 1} ] ⏩`;
                    } else {
                        // End of Round 3. Evaluate Series result.
                        if (punchWins >= 2) {
                            // Passed series requirement!
                            document.getElementById('punch-success-panel').classList.remove('hidden');
                            document.getElementById('punch-status-text').textContent = "🏆 CHAMPION CLEAR!";
                            document.getElementById('punch-status-text').className = "text-[#7effa1] blink font-bold";
                        } else {
                            // Series failed! Reveal Retry deck
                            document.getElementById('punch-retry-btn').classList.remove('hidden');
                        }
                    }
                }, 800);
            }
        }

        function advancePunchRound() {
            playSound('select');
            punchRound++;
            resetPunchMachine();
        }

        function resetGame() {
            currentScore = 0; addScore(0);
            punchGameActive = false; cancelAnimationFrame(loopPunchGauge);
            clearTimeout(moleSpawnTimeout);
            clearInterval(moleTimerInterval);
            captchaRound = 1;
            punchRound = 1;
            punchWins = 0;
            currentVideoIndex = 0;
            currentVideoIndex2 = 0;
            document.getElementById('stage-preloader').classList.add('hidden');
            showStage('stage-1');
        }

        window.onload = function() {
            startPreloader();
        };
    </script>
</body>
</html>

```
