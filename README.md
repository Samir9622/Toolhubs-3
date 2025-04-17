<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToolHub Pro - Multi-Tool Suite</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css" rel="stylesheet">
    <style>
        :root {
            --primary-color: #4f46e5;
            --secondary-color: #f43f5e;
            --text-primary: #1f2937;
            --text-secondary: #6b7280;
            --bg-primary: #ffffff;
            --bg-secondary: #f3f4f6;
            --bg-tertiary: #e5e7eb;
            --shadow-color: rgba(0, 0, 0, 0.1);
            --highlight-color: #f0fdf4;
        }
        
        [data-theme="dark"] {
            --primary-color: #6366f1;
            --secondary-color: #f87171;
            --text-primary: #f9fafb;
            --text-secondary: #d1d5db;
            --bg-primary: #111827;
            --bg-secondary: #1f2937;
            --bg-tertiary: #374151;
            --shadow-color: rgba(0, 0, 0, 0.3);
            --highlight-color: #064e3b;
        }
        
        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
            color: var(--text-primary);
            background-color: var(--bg-secondary);
            transition: background-color 0.3s, color 0.3s;
            min-height: 100vh;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: var(--bg-secondary);
        }
        
        ::-webkit-scrollbar-thumb {
            background: var(--text-secondary);
            border-radius: 4px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-color);
        }

        /* Calculator Specific Styles */
        .calculator {
            background-color: var(--bg-primary);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 20px var(--shadow-color);
            max-width: 360px;
            margin: 0 auto;
        }
        
        .calculator-display {
            background-color: var(--bg-tertiary);
            color: var(--text-primary);
            text-align: right;
            font-size: 2.2rem;
            padding: 1rem;
            font-family: 'Courier New', monospace;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
            min-height: 5rem;
            position: relative;
        }
        
        .calculator-history {
            font-size: 0.9rem;
            color: var(--text-secondary);
            position: absolute;
            top: 0.5rem;
            right: 1rem;
            max-width: 90%;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        
        .calculator-keys {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 2px;
            padding: 2px;
        }
        
        .calculator-key {
            border: none;
            font-size: 1.25rem;
            padding: 1rem 0;
            background-color: var(--bg-secondary);
            color: var(--text-primary);
            cursor: pointer;
            transition: all 0.2s;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .calculator-key:hover {
            background-color: var(--primary-color);
            color: white;
        }
        
        .calculator-key:active,
        .calculator-key.active {
            transform: scale(0.95);
            background-color: var(--secondary-color);
        }
        
        .key-operator {
            background-color: var(--primary-color);
            color: white;
        }
        
        .key-equal {
            background-color: var(--secondary-color);
            color: white;
            grid-column: span 2;
        }
        
        .key-memory {
            background-color: var(--bg-tertiary);
            font-size: 1.1rem;
        }

        /* Tool Section Styling */
        .tool-section {
            background-color: var(--bg-primary);
            border-radius: 12px;
            box-shadow: 0 4px 12px var(--shadow-color);
            margin-bottom: 2rem;
            transition: transform 0.3s, box-shadow 0.3s;
            overflow: hidden;
        }
        
        .tool-section:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 24px var(--shadow-color);
        }
        
        .sidebar {
            background-color: var(--bg-primary);
            border-right: 1px solid var(--bg-tertiary);
            height: 100vh;
            position: fixed;
            top: 0;
            left: 0;
            width: 260px;
            overflow-y: auto;
            transition: transform 0.3s;
            z-index: 50;
        }
        
        .logo-icon {
            color: var(--primary-color);
            font-size: 1.5rem;
            margin-right: 0.5rem;
        }
        
        .pro-badge {
            background-color: var(--secondary-color);
            color: white;
            padding: 0.1rem 0.4rem;
            border-radius: 0.25rem;
            font-size: 0.75rem;
            margin-left: 0.25rem;
            vertical-align: middle;
        }
        
        .nav-link {
            display: flex;
            align-items: center;
            padding: 0.75rem 1rem;
            color: var(--text-primary);
            border-left: 3px solid transparent;
            transition: all 0.2s;
        }
        
        .nav-link:hover {
            background-color: var(--bg-secondary);
            border-left-color: var(--primary-color);
        }
        
        .nav-link.active {
            background-color: var(--bg-tertiary);
            border-left-color: var(--primary-color);
            color: var(--primary-color);
        }
        
        .nav-link i {
            width: 1.5rem;
            text-align: center;
            margin-right: 0.75rem;
            font-size: 1.1rem;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .sidebar {
                transform: translateX(-100%);
            }
            
            .sidebar.open {
                transform: translateX(0);
            }
            
            .content {
                margin-left: 0;
                padding: 1rem;
            }
            
            .mobile-menu-toggle {
                display: block !important;
            }
        }

        /* Animation Effects */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .fade-in {
            animation: fadeIn 0.3s ease forwards;
        }
        
        /* Input and Button Styling */
        input[type="text"],
        input[type="number"],
        textarea,
        select {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid var(--bg-tertiary);
            background-color: var(--bg-primary);
            color: var(--text-primary);
            border-radius: 0.5rem;
            transition: border-color 0.3s;
            outline: none;
        }
        
        input[type="text"]:focus,
        input[type="number"]:focus,
        textarea:focus,
        select:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.2);
        }
        
        .btn {
            padding: 0.75rem 1.5rem;
            border-radius: 0.5rem;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border: none;
        }
        
        .btn-primary {
            background-color: var(--primary-color);
            color: white;
        }
        
        .btn-primary:hover {
            background-color: #4338ca;
        }
        
        .btn-secondary {
            background-color: var(--bg-tertiary);
            color: var(--text-primary);
        }
        
        .btn-secondary:hover {
            background-color: #d1d5db;
        }
        
        .btn i {
            margin-right: 0.5rem;
        }
        
        /* For sticky headers */
        .tool-header {
            background-color: var(--bg-primary);
            border-bottom: 1px solid var(--bg-tertiary);
            position: sticky;
            top: 0;
            z-index: 10;
        }
    </style>
</head>
<body data-theme="light">
    <!-- Mobile Menu Toggle -->
    <button id="mobile-menu-toggle" class="fixed top-4 left-4 z-50 bg-white p-2 rounded-md shadow-md hidden">
        <i class="fas fa-bars text-gray-700"></i>
    </button>

    <!-- Sidebar Navigation -->
    <div class="sidebar" id="sidebar">
        <div class="p-4 flex justify-between items-center border-b border-gray-200">
            <div class="flex items-center">
                <span class="logo-icon">🧰</span>
                <h1 class="text-xl font-bold">ToolHub<span class="pro-badge">Pro</span></h1>
            </div>
            <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-200 transition-colors">
                <i class="fas fa-moon"></i>
            </button>
        </div>
        
        <div class="p-3">
            <input type="text" id="tool-search" placeholder="Search tools..." class="w-full p-2 rounded bg-gray-100 text-gray-800">
        </div>
        
        <nav class="tool-nav">
            <a href="#calculator" data-tool="calculator" class="nav-link active">
                <i class="fas fa-calculator"></i> Calculator
            </a>
            <a href="#password-generator" data-tool="password-generator" class="nav-link">
                <i class="fas fa-key"></i> Password Generator
            </a>
            <a href="#text-case-converter" data-tool="text-case-converter" class="nav-link">
                <i class="fas fa-font"></i> Text Case Converter
            </a>
            <a href="#word-counter" data-tool="word-counter" class="nav-link">
                <i class="fas fa-calculator"></i> Word Counter
            </a>
            <a href="#color-picker" data-tool="color-picker" class="nav-link">
                <i class="fas fa-palette"></i> Color Picker
            </a>
            <a href="#base64-converter" data-tool="base64-converter" class="nav-link">
                <i class="fas fa-exchange-alt"></i> Base64 Converter
            </a>
            <a href="#url-encoder" data-tool="url-encoder" class="nav-link">
                <i class="fas fa-link"></i> URL Encoder/Decoder
            </a>
            <a href="#json-formatter" data-tool="json-formatter" class="nav-link">
                <i class="fas fa-code"></i> JSON Formatter
            </a>
        </nav>
    </div>

    <!-- Main Content -->
    <div class="content ml-0 md:ml-64 transition-all duration-300 p-4 md:p-8">
        <header class="mb-8">
            <h1 class="text-3xl font-bold text-center mb-2">ToolHub Pro</h1>
            <p class="text-center text-gray-600">Your Ultimate Online Toolbox</p>
        </header>

        <!-- Calculator Tool -->
        <div id="calculator" class="tool-section fade-in">
            <div class="tool-header p-4">
                <h2 class="text-xl font-bold flex items-center">
                    <i class="fas fa-calculator mr-2 text-indigo-600"></i> 
                    Calculator
                </h2>
                <p class="text-gray-600 text-sm">Perform mathematical calculations with keyboard support</p>
            </div>
            
            <div class="p-4">
                <div class="calculator">
                    <div class="calculator-display" id="calculator-display">
                        <div class="calculator-history" id="calculator-history"></div>
                        <div id="calculator-current">0</div>
                    </div>
                    <div class="calculator-keys">
                        <button class="calculator-key key-memory" data-action="memory-clear">MC</button>
                        <button class="calculator-key key-memory" data-action="memory-recall">MR</button>
                        <button class="calculator-key key-memory" data-action="memory-add">M+</button>
                        <button class="calculator-key key-memory" data-action="memory-subtract">M-</button>
                        
                        <button class="calculator-key" data-action="clear">C</button>
                        <button class="calculator-key" data-action="negate">±</button>
                        <button class="calculator-key" data-action="percentage">%</button>
                        <button class="calculator-key key-operator" data-action="divide">÷</button>
                        
                        <button class="calculator-key" data-digit="7">7</button>
                        <button class="calculator-key" data-digit="8">8</button>
                        <button class="calculator-key" data-digit="9">9</button>
                        <button class="calculator-key key-operator" data-action="multiply">×</button>
                        
                        <button class="calculator-key" data-digit="4">4</button>
                        <button class="calculator-key" data-digit="5">5</button>
                        <button class="calculator-key" data-digit="6">6</button>
                        <button class="calculator-key key-operator" data-action="subtract">−</button>
                        
                        <button class="calculator-key" data-digit="1">1</button>
                        <button class="calculator-key" data-digit="2">2</button>
                        <button class="calculator-key" data-digit="3">3</button>
                        <button class="calculator-key key-operator" data-action="add">+</button>
                        
                        <button class="calculator-key" data-digit="0">0</button>
                        <button class="calculator-key" data-digit=".">.</button>
                        <button class="calculator-key key-equal" data-action="calculate">=</button>
                    </div>
                </div>
                <div class="mt-4 text-gray-600 text-sm">
                    <p><strong>Keyboard shortcuts:</strong></p>
                    <ul class="list-disc pl-5 mt-2">
                        <li>Numbers 0-9 for digits</li>
                        <li>+, -, *, / for operations</li>
                        <li>Enter or = for equals</li>
                        <li>Escape or C for clear</li>
                        <li>Backspace to delete last character</li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Password Generator Tool -->
        <div id="password-generator" class="tool-section fade-in hidden">
            <div class="tool-header p-4">
                <h2 class="text-xl font-bold flex items-center">
                    <i class="fas fa-key mr-2 text-indigo-600"></i> 
                    Password Generator
                </h2>
                <p class="text-gray-600 text-sm">Generate secure, random passwords</p>
            </div>
            
            <div class="p-4">
                <div class="mb-4">
                    <label class="block text-gray-700 mb-2">Password Length: <span id="length-value">16</span></label>
                    <div class="flex items-center">
                        <input type="range" id="password-length" min="8" max="64" value="16" 
                               class="w-3/4 mr-4">
                        <input type="number" id="password-length-input" min="8" max="64" value="16" 
                               class="w-1/4 p-2 border rounded">
                    </div>
                </div>
                
                <div class="mb-4 grid grid-cols-2 gap-4">
                    <div class="flex items-center">
                        <input type="checkbox" id="include-uppercase" checked class="mr-2">
                        <label for="include-uppercase">Uppercase Letters</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="include-lowercase" checked class="mr-2">
                        <label for="include-lowercase">Lowercase Letters</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="include-numbers" checked class="mr-2">
                        <label for="include-numbers">Numbers</label>
                    </div>
                    <div class="flex items-center">
                        <input type="checkbox" id="include-symbols" checked class="mr-2">
                        <label for="include-symbols">Special Characters</label>
                    </div>
                </div>
                
                <div class="mb-4">
                    <label class="block text-gray-700 mb-2">Password Strength</label>
                    <div class="bg-gray-200 rounded-full h-4">
                        <div id="password-strength" class="bg-red-500 h-4 rounded-full" style="width: 0%;"></div>
                    </div>
                    <p class="text-sm mt-1 text-gray-600" id="strength-text">Generate a password</p>
                </div>
                
                <div class="mb-4">
                    <div class="flex">
                        <input type="text" id="password-output" readonly 
                               class="flex-grow p-2 border rounded-l font-mono" 
                               placeholder="Your generated password">
                        <button id="copy-password" class="bg-indigo-600 text-white px-4 rounded-r">
                            <i class="fas fa-copy"></i>
                        </button>
                    </div>
                </div>
                
                <button id="generate-password" class="btn btn-primary w-full">
                    <i class="fas fa-sync-alt"></i> Generate Password
                </button>
            </div>
        </div>

        <!-- Text Case Converter Tool -->
        <div id="text-case-converter" class="tool-section fade-in hidden">
            <div class="tool-header p-4">
                <h2 class="text-xl font-bold flex items-center">
                    <i class="fas fa-font mr-2 text-indigo-600"></i> 
                    Text Case Converter
                </h2>
                <p class="text-gray-600 text-sm">Convert text to different cases</p>
            </div>
            
            <div class="p-4">
                <div class="mb-4">
                    <label for="case-input" class="block mb-2">Input Text</label>
                    <textarea id="case-input" rows="6" class="w-full p-2 border rounded" 
                              placeholder="Enter your text here..."></textarea>
                </div>
                
                <div class="mb-4 grid grid-cols-2 md:grid-cols-3 gap-2">
                    <button class="btn btn-secondary" data-case="upper">UPPERCASE</button>
                    <button class="btn btn-secondary" data-case="lower">lowercase</button>
                    <button class="btn btn-secondary" data-case="title">Title Case</button>
                    <button class="btn btn-secondary" data-case="sentence">Sentence case</button>
                    <button class="btn btn-secondary" data-case="camel">camelCase</button>
                    <button class="btn btn-secondary" data-case="pasca
