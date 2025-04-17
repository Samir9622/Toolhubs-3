<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToolHub Pro - All-in-One Online Tools</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.2/css/all.min.css">
    <style>
        :root {
            --primary-color: #4f46e5;
            --primary-hover: #4338ca;
            --secondary-color: #f59e0b;
            --light-bg: #f3f4f6;
            --dark-bg: #1f2937;
            --light-text: #f9fafb;
            --dark-text: #111827;
            --light-card: #ffffff;
            --dark-card: #374151;
            --border-light: #e5e7eb;
            --border-dark: #4b5563;
        }

        body {
            transition: background-color 0.3s, color 0.3s;
            min-height: 100vh;
        }

        body[data-theme="light"] {
            background-color: var(--light-bg);
            color: var(--dark-text);
        }

        body[data-theme="dark"] {
            background-color: var(--dark-bg);
            color: var(--light-text);
        }

        /* Card styles */
        .tool-card {
            border-radius: 0.75rem;
            overflow: hidden;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        body[data-theme="light"] .tool-card {
            background-color: var(--light-card);
            border: 1px solid var(--border-light);
        }

        body[data-theme="dark"] .tool-card {
            background-color: var(--dark-card);
            border: 1px solid var(--border-dark);
        }

        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }

        /* Tool section */
        .tool-section {
            display: none;
        }

        .tool-section.active {
            display: block;
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Custom switch */
        .switch {
            position: relative;
            display: inline-block;
            width: 48px;
            height: 24px;
        }

        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }

        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }

        .slider:before {
            position: absolute;
            content: "";
            height: 18px;
            width: 18px;
            left: 3px;
            bottom: 3px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }

        input:checked + .slider {
            background-color: var(--primary-color);
        }

        input:focus + .slider {
            box-shadow: 0 0 1px var(--primary-color);
        }

        input:checked + .slider:before {
            transform: translateX(24px);
        }

        /* Custom inputs */
        .tool-input, .tool-button {
            transition: all 0.3s;
        }

        body[data-theme="light"] .tool-input {
            background-color: #f9fafb;
            border: 1px solid var(--border-light);
            color: var(--dark-text);
        }

        body[data-theme="dark"] .tool-input {
            background-color: #1f2937;
            border: 1px solid var(--border-dark);
            color: var(--light-text);
        }

        .tool-input:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.2);
        }

        .result-container {
            border-radius: 0.5rem;
            margin-top: 1rem;
            padding: 1rem;
            overflow-wrap: break-word;
        }

        body[data-theme="light"] .result-container {
            background-color: #f3f4f6;
            border: 1px solid var(--border-light);
        }

        body[data-theme="dark"] .result-container {
            background-color: #374151;
            border: 1px solid var(--border-dark);
        }

        /* Password strength */
        .strength-meter {
            height: 4px;
            border-radius: 2px;
            margin-top: 0.5rem;
            background-color: #e5e7eb;
            overflow: hidden;
        }

        .strength-fill {
            height: 100%;
            width: 0;
            transition: width 0.3s, background-color 0.3s;
        }
        
        .nav-link {
            transition: all 0.3s;
            border-radius: 0.5rem;
        }
        
        .nav-link:hover {
            background-color: rgba(79, 70, 229, 0.1);
        }
        
        .nav-link.active {
            background-color: var(--primary-color);
            color: white;
        }

        .color-preview {
            width: 100px;
            height: 100px;
            border-radius: 0.5rem;
            margin: 1rem auto;
            border: 1px solid var(--border-light);
        }

        #qrcode img {
            margin: 0 auto;
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body data-theme="light">
    <div class="flex flex-col lg:flex-row min-h-screen">
        <!-- Sidebar -->
        <div class="lg:w-64 bg-gray-800 text-white p-4">
            <div class="flex items-center justify-between mb-8">
                <div class="flex items-center">
                    <i class="fas fa-toolbox text-2xl mr-2 text-yellow-400"></i>
                    <h1 class="text-xl font-bold">ToolHub Pro</h1>
                </div>
                <button id="theme-toggle" class="p-2 rounded-full bg-gray-700 hover:bg-gray-600 focus:outline-none">
                    <i class="fas fa-moon"></i>
                </button>
            </div>
            
            <div class="mb-4">
                <div class="relative">
                    <input type="text" id="tool-search" placeholder="Search tools..." class="w-full bg-gray-700 text-white px-4 py-2 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500">
                    <i class="fas fa-search absolute right-3 top-2.5 text-gray-400"></i>
                </div>
            </div>
            
            <nav class="space-y-1">
                <a href="#password-generator" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-key mr-3"></i>
                    <span>Password Generator</span>
                </a>
                <a href="#case-converter" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-font mr-3"></i>
                    <span>Text Case Converter</span>
                </a>
                <a href="#word-counter" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-calculator mr-3"></i>
                    <span>Word Counter</span>
                </a>
                <a href="#color-picker" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-palette mr-3"></i>
                    <span>Color Picker</span>
                </a>
                <a href="#base64-tool" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-exchange-alt mr-3"></i>
                    <span>Base64 Encoder/Decoder</span>
                </a>
                <a href="#url-encoder" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-link mr-3"></i>
                    <span>URL Encoder/Decoder</span>
                </a>
                <a href="#json-formatter" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-code mr-3"></i>
                    <span>JSON Formatter</span>
                </a>
                <a href="#qr-generator" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-qrcode mr-3"></i>
                    <span>QR Code Generator</span>
                </a>
                <a href="#lorem-ipsum" class="nav-link flex items-center px-4 py-2 text-sm font-medium">
                    <i class="fas fa-align-left mr-3"></i>
                    <span>Lorem Ipsum Generator</span>
                </a>
            </nav>
        </div>
        
        <!-- Main Content -->
        <div class="flex-1 p-4 lg:p-8">
            <h1 class="text-3xl font-bold mb-6 text-center lg:text-left">Your Ultimate Online Toolbox</h1>
            
            <!-- Password Generator -->
            <div id="password-generator" class="tool-section active">
                <div class="tool-card p-6">
                    <h2 class="text-xl font-bold mb-2 flex items-center">
                        <i class="fas fa-key mr-2 text-indigo-500"></i>
                        Password Generator
                    </h2>
                    <p class="text-gray-500 dark:text-gray-400 mb-4">Create strong, secure passwords instantly</p>
                    
                    <div class="space-y-4">
                        <div>
                            <label class="block mb-2 text-sm font-medium">Password Length: <span id="length-value">12</span></label>
                            <input type="range" id="pass-length" min="8" max="32" value="12" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer">
                        </div>
                        
                        <div class="grid grid-cols-2 gap-4">
                            <div class="flex items-center">
                                <label class="switch mr-3">
                                    <input type="checkbox" id="uppercase" checked>
                                    <span class="slider"></span>
                                </label>
                                <span>Uppercase Letters</span>
                            </div>
                            
                            <div class="flex items-center">
                                <label class="switch mr-3">
                                    <input type="checkbox" id="lowercase" checked>
                                    <span class="slider"></span>
                                </label>
                                <span>Lowercase Letters</span>
                            </div>
                            
                            <div class="flex items-center">
                                <label class="switch mr-3">
                                    <input type="checkbox" id="numbers" checked>
                                    <span class="slider"></span>
                                </label>
                                <span>Numbers</span>
                            </div>
                            
                            <div class="flex items-center">
                                <label class="switch mr-3">
                                    <input type="checkbox" id="symbols" checked>
                                    <span class="slider"></span>
                                </label>
                                <span>Special Characters</span>
                            </div>
                        </div>
                        
                        <div>
                            <label class="block mb-2 text-sm font-medium">Password Strength:</label>
                            <div class="strength-meter">
                                <div class="strength-fill" id="strength-fill"></div>
                            </div>
                            <p id="strength-text" class="text-sm mt-1">Medium</p>
                        </div>
                        
                        <div class="flex space-x-4">
                            <button id="generate-btn" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                Generate Password
                            </button>
                            <button id="copy-password" class="px-4 py-2 bg-gray-200 text-gray-800 dark:bg-gray-700 dark:text-white rounded-md hover:bg-gray-300 dark:hover:bg-gray-600 focus:outline-none focus:ring-2 focus:ring-gray-500 focus:ring-offset-2">
                                <i class="far fa-copy mr-2"></i>Copy
                            </button>
                        </div>
                        
                        <div class="result-container">
                            <div id="password-result" class="font-mono text-lg"></div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Text Case Converter -->
            <div id="case-converter" class="tool-section">
                <div class="tool-card p-6">
                    <h2 class="text-xl font-bold mb-2 flex items-center">
                        <i class="fas fa-font mr-2 text-indigo-500"></i>
                        Text Case Converter
                    </h2>
                    <p class="text-gray-500 dark:text-gray-400 mb-4">Convert text between different letter cases</p>
                    
                    <div class="space-y-4">
                        <div>
                            <label class="block mb-2 text-sm font-medium">Enter your text:</label>
                            <textarea id="case-input" rows="5" class="tool-input w-full px-3 py-2 text-gray-700 border rounded-lg focus:outline-none" placeholder="Type or paste your text here..."></textarea>
                        </div>
                        
                        <div class="flex flex-wrap gap-2">
                            <button onclick="convertCase('upper')" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                UPPERCASE
                            </button>
                            <button onclick="convertCase('lower')" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                lowercase
                            </button>
                            <button onclick="convertCase('title')" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                Title Case
                            </button>
                            <button onclick="convertCase('sentence')" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                Sentence case
                            </button>
                            <button onclick="convertCase('alternating')" class="px-4 py-2 bg-indigo-600 text-white rounded-md hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">
                                aLtErNaTiNg CaSe
                            </button>
                            <button id="copy-case" class="px-4 py-2 bg-gray-200 text-gray-800 dark:bg-gray-700 dark:text-white rounded-md hover:bg-gray-300 dark:hover:bg-gray-600 focus:outline-none focus:ring-2 focus:ring-gray-500 focus:ring-offset-2">
                                <i class="far fa-copy mr-2"></i>Copy
                            </button>
                        </div>
                        
                        <div class="result-container">
                            <div id="case-output" class="whitespace-pre-wrap"></div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Word Counter -->
            <div id="word-counter" class="tool-section">
                <div class="tool-card p-6">
                    <h2 class="text-xl font-bold mb-2 flex items-center">
                        <i class="fas fa-calculator mr-2 text-indigo-500"></i>
                        Word Counter
                    </h2>
                    <p class="text-gray-500 dark:text-gray-400 mb-4">Count words, characters, and more in your text</p>
                    
                    <div class="space-y-4">
                        <div>
                            <label class="block mb-2 text-sm font-medium">Enter your text:</label>
                            <textarea id="word-input" rows="8" class="tool-input w-full px-3 py-2 text-gray-700 border rounded-lg focus:outline-none" placeholder="Type or paste your text here..."></textarea>
                        </div>
                        
                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                            <div class="bg-indigo-100 dark:bg-indigo-900 p-3 rounded-lg text-center">
                                <h3 class="text-lg font-semibold text-indigo-800 dark:text-indigo-200">Words</h3>
                                <p id="word-count" class="text-2xl font-bold text-indigo-600 dark:text-indigo-300">0</p>
                            </div>
                            
                            <div class="bg-indigo-100 dark:bg-indigo-900 p-3 rounded-lg text-center">
                                <h3 class="text-lg font-semibold text-indigo-800 dark:text-indigo-200">Characters</h3>
                                <p id="char-count" class="text-2xl font-bold text-indigo-600 dark:text-indigo-300">0</p>
                            </div>
                            
                            <div class="bg-indigo-100 dark:bg-indigo-900 p-3 rounded-lg text-center">
                                <h3 class="text-lg font-semibold text-indigo-800 dark:text-indigo-200">Sentences</h3>
                                <p id="sentence-count" class="text-2xl font-bold text-indigo-600 dark:text-indigo-300">0</p>
                            </div>
                            
                            <div class="bg-indigo-100 dark:bg-indigo-900 p-3 rounded-lg text-center">
                                <h3 class="text-lg font-semibold text-indigo-800 dark:text-indigo-200">Paragraphs</h3>
                                <p id="paragraph-count" class="text-2xl font-bold text-indigo-600 dark:text-indigo-300">0</p>
                            </div>
                        </div>
                        
                        <div class="bg-gray-100 dark:bg-gray-800 p-4 rounded-lg">
                            <h3 class="text-lg font-semibold mb-2">Reading Time</h3>
                            <div class="flex items-center">
                                <i class="far fa-clock text-indigo-500 text-2xl mr-3"></i>
                                <div>
                                    <p id="reading-time" class="text-xl font-medium">About 0 minutes</p>
                                    <p class="text-sm text-gray-500 dark:text-gray-400">Based on average reading speed (200 words per minute)</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Color Picker -->
            <div id="color-picker" class="tool-section">
                <div class="tool-card p-6">
             
