<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Built-in Functions - Complete Guide</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Outfit:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-dark: #0d1117;
            --bg-darker: #010409;
            --bg-code: #161b22;
            --text-primary: #e6edf3;
            --text-secondary: #8b949e;
            --accent-blue: #58a6ff;
            --accent-purple: #bc8cff;
            --accent-green: #3fb950;
            --accent-yellow: #d29922;
            --accent-red: #f85149;
            --accent-orange: #ff9b5f;
            --border: #30363d;
            --shadow: rgba(0, 0, 0, 0.3);
        }

        body {
            background: linear-gradient(135deg, var(--bg-darker) 0%, var(--bg-dark) 100%);
            color: var(--text-primary);
            font-family: 'Outfit', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.7;
            padding: 0;
            min-height: 100vh;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 60px 40px;
        }

        /* Header */
        header {
            text-align: center;
            margin-bottom: 80px;
            position: relative;
        }

        h1 {
            font-size: 4rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--accent-blue) 0%, var(--accent-purple) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            letter-spacing: -2px;
        }

        .subtitle {
            font-size: 1.3rem;
            color: var(--text-secondary);
            font-weight: 400;
        }

        /* Navigation */
        nav {
            background: var(--bg-code);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 30px;
            margin-bottom: 60px;
            box-shadow: 0 8px 32px var(--shadow);
        }

        nav h2 {
            color: var(--accent-blue);
            margin-bottom: 20px;
            font-size: 1.5rem;
        }

        nav ul {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 12px;
        }

        nav a {
            color: var(--text-secondary);
            text-decoration: none;
            padding: 8px 12px;
            border-radius: 6px;
            display: block;
            transition: all 0.2s;
            font-weight: 500;
        }

        nav a:hover {
            background: rgba(88, 166, 255, 0.1);
            color: var(--accent-blue);
            transform: translateX(5px);
        }

        /* Section */
        .section {
            margin-bottom: 80px;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 40px;
            color: var(--accent-purple);
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        h2::before {
            content: '';
            width: 6px;
            height: 40px;
            background: linear-gradient(to bottom, var(--accent-purple), var(--accent-blue));
            border-radius: 3px;
        }

        /* Method Card */
        .method-card {
            background: var(--bg-code);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 40px;
            margin-bottom: 40px;
            box-shadow: 0 4px 24px var(--shadow);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .method-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 40px var(--shadow);
            border-color: var(--accent-blue);
        }

        .method-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 25px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--border);
        }

        .method-name {
            font-size: 2rem;
            font-weight: 700;
            color: var(--accent-blue);
            font-family: 'JetBrains Mono', monospace;
        }

        .badge {
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .badge-immutable {
            background: rgba(63, 185, 80, 0.2);
            color: var(--accent-green);
            border: 1px solid var(--accent-green);
        }

        .badge-mutable {
            background: rgba(248, 81, 73, 0.2);
            color: var(--accent-red);
            border: 1px solid var(--accent-red);
        }

        .description {
            font-size: 1.15rem;
            color: var(--text-primary);
            margin-bottom: 25px;
            line-height: 1.8;
        }

        .key-points {
            background: rgba(88, 166, 255, 0.05);
            border-left: 4px solid var(--accent-blue);
            padding: 20px 25px;
            margin: 25px 0;
            border-radius: 8px;
        }

        .key-points h4 {
            color: var(--accent-blue);
            margin-bottom: 15px;
            font-size: 1.1rem;
        }

        .key-points ul {
            list-style: none;
            padding-left: 0;
        }

        .key-points li {
            padding-left: 25px;
            position: relative;
            margin-bottom: 8px;
            color: var(--text-secondary);
        }

        .key-points li::before {
            content: '▹';
            position: absolute;
            left: 0;
            color: var(--accent-blue);
            font-weight: bold;
        }

        /* Code Block - VS Code Style */
        .code-container {
            margin: 25px 0;
            position: relative;
        }

        .code-header {
            background: #1f2428;
            padding: 12px 20px;
            border-radius: 12px 12px 0 0;
            display: flex;
            align-items: center;
            gap: 10px;
            border: 1px solid var(--border);
            border-bottom: none;
        }

        .code-dots {
            display: flex;
            gap: 8px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }

        .dot-red { background: #ff5f56; }
        .dot-yellow { background: #ffbd2e; }
        .dot-green { background: #27c93f; }

        .code-title {
            color: var(--text-secondary);
            font-size: 0.85rem;
            font-family: 'JetBrains Mono', monospace;
            margin-left: auto;
        }

        pre {
            margin: 0;
            padding: 30px;
            background: #0d1117;
            border: 1px solid var(--border);
            border-radius: 0 0 12px 12px;
            overflow-x: auto;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.95rem;
            line-height: 1.8;
        }

        code {
            font-family: 'JetBrains Mono', monospace;
        }

        /* Syntax Highlighting */
        .keyword { color: #ff7b72; font-weight: 500; }
        .function { color: #d2a8ff; }
        .string { color: #a5d6ff; }
        .number { color: #79c0ff; }
        .comment { color: #8b949e; font-style: italic; }
        .operator { color: #ff7b72; }
        .variable { color: #ffa657; }
        .property { color: #79c0ff; }
        .result { color: #7ee787; }

        /* Use Cases */
        .use-cases {
            margin-top: 30px;
        }

        .use-cases h4 {
            color: var(--accent-green);
            margin-bottom: 20px;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .use-case {
            margin-bottom: 30px;
        }

        .use-case-title {
            font-weight: 600;
            color: var(--accent-yellow);
            margin-bottom: 12px;
            font-size: 1.05rem;
        }

        /* Interview Section */
        .interview-card {
            background: linear-gradient(135deg, rgba(188, 140, 255, 0.1) 0%, rgba(88, 166, 255, 0.1) 100%);
            border: 2px solid var(--accent-purple);
            border-radius: 16px;
            padding: 35px;
            margin-bottom: 35px;
        }

        .interview-question {
            font-size: 1.4rem;
            color: var(--accent-purple);
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: flex-start;
            gap: 12px;
        }

        .interview-question::before {
            content: 'Q:';
            color: var(--accent-blue);
            font-weight: 800;
            flex-shrink: 0;
        }

        .interview-answer {
            color: var(--text-primary);
            line-height: 1.9;
            font-size: 1.05rem;
        }

        /* Summary Table */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 30px 0;
            background: var(--bg-code);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 24px var(--shadow);
        }

        thead {
            background: linear-gradient(135deg, var(--accent-blue) 0%, var(--accent-purple) 100%);
        }

        th {
            padding: 18px;
            text-align: left;
            font-weight: 700;
            font-size: 1.05rem;
            color: white;
        }

        td {
            padding: 16px 18px;
            border-top: 1px solid var(--border);
            color: var(--text-secondary);
        }

        tr:hover {
            background: rgba(88, 166, 255, 0.05);
        }

        td:first-child {
            font-family: 'JetBrains Mono', monospace;
            color: var(--accent-blue);
            font-weight: 600;
        }

        /* Tips Section */
        .tips-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .tip-card {
            background: var(--bg-code);
            border: 1px solid var(--border);
            border-left: 4px solid var(--accent-green);
            padding: 25px;
            border-radius: 12px;
        }

        .tip-card h4 {
            color: var(--accent-green);
            margin-bottom: 12px;
            font-size: 1.1rem;
        }

        .tip-card p {
            color: var(--text-secondary);
            line-height: 1.7;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 12px;
            height: 12px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-darker);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 6px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-blue);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .method-card {
            animation: fadeInUp 0.6s ease-out;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .container {
                padding: 30px 20px;
            }

            h1 {
                font-size: 2.5rem;
            }

            h2 {
                font-size: 2rem;
            }

            .method-card {
                padding: 25px;
            }

            pre {
                font-size: 0.85rem;
                padding: 20px;
            }

            nav ul {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>JavaScript Built-in Functions</h1>
            <p class="subtitle">Complete Interview Guide with Visual Code Examples</p>
        </header>

        <nav>
            <h2>📚 Quick Navigation</h2>
            <ul>
                <li><a href="#array-methods">Array Methods</a></li>
                <li><a href="#string-methods">String Methods</a></li>
                <li><a href="#interview-questions">Interview Questions</a></li>
                <li><a href="#summary">Summary Table</a></li>
            </ul>
        </nav>

        <!-- MAP METHOD -->
        <section id="array-methods" class="section">
            <h2>Array Methods</h2>

            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">map()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Creates a <strong>NEW array</strong> by transforming each element using a callback function.
                </p>

                <div class="key-points">
                    <h4>🎯 Key Points</h4>
                    <ul>
                        <li>Returns a new array (doesn't modify original)</li>
                        <li>Always returns an array of the same length</li>
                        <li>Use when you need to transform data</li>
                    </ul>
                </div>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">syntax.js</span>
                    </div>
                    <pre><code><span class="keyword">const</span> newArray = array.<span class="function">map</span>((<span class="variable">element</span>, <span class="variable">index</span>, <span class="variable">array</span>) => {
  <span class="keyword">return</span> newValue;
});</code></pre>
                </div>

                <div class="use-cases">
                    <h4>💡 Real-World Use Cases</h4>

                    <div class="use-case">
                        <div class="use-case-title">1. Extract specific properties from objects</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">example1.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">users</span> = [
  { <span class="property">id</span>: <span class="number">1</span>, <span class="property">name</span>: <span class="string">'Alice'</span>, <span class="property">age</span>: <span class="number">25</span> },
  { <span class="property">id</span>: <span class="number">2</span>, <span class="property">name</span>: <span class="string">'Bob'</span>, <span class="property">age</span>: <span class="number">30</span> }
];

<span class="keyword">const</span> <span class="variable">names</span> = users.<span class="function">map</span>(<span class="variable">user</span> => user.name);
<span class="comment">// Result: ['Alice', 'Bob']</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">2. Format data for display</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">example2.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">prices</span> = [<span class="number">10</span>, <span class="number">20</span>, <span class="number">30</span>];

<span class="keyword">const</span> <span class="variable">formatted</span> = prices.<span class="function">map</span>(<span class="variable">price</span> => <span class="string">`$${price}.00`</span>);
<span class="comment">// Result: ['$10.00', '$20.00', '$30.00']</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">3. Convert temperature units</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">example3.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">celsius</span> = [<span class="number">0</span>, <span class="number">10</span>, <span class="number">20</span>, <span class="number">30</span>];

<span class="keyword">const</span> <span class="variable">fahrenheit</span> = celsius.<span class="function">map</span>(<span class="variable">temp</span> => (temp * <span class="number">9</span>/<span class="number">5</span>) + <span class="number">32</span>);
<span class="comment">// Result: [32, 50, 68, 86]</span></code></pre>
                        </div>
                    </div>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Map transforms each element in an array and returns a new array with the same length. It's immutable, meaning it doesn't change the original array. I use it when I need to convert data from one format to another, like extracting user names from user objects or formatting prices for display."
                    </p>
                </div>
            </div>

            <!-- FOREACH METHOD -->
            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">forEach()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Executes a function for each array element. Returns <code style="color: var(--accent-red);">undefined</code>.
                </p>

                <div class="key-points">
                    <h4>🎯 Key Points</h4>
                    <ul>
                        <li>Does NOT return a new array</li>
                        <li>Cannot break or return early</li>
                        <li>Use for side effects (logging, updating DOM, etc.)</li>
                    </ul>
                </div>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">syntax.js</span>
                    </div>
                    <pre><code>array.<span class="function">forEach</span>((<span class="variable">element</span>, <span class="variable">index</span>, <span class="variable">array</span>) => {
  <span class="comment">// Perform action, no return value</span>
});</code></pre>
                </div>

                <div class="use-cases">
                    <h4>💡 Real-World Use Cases</h4>

                    <div class="use-case">
                        <div class="use-case-title">1. Update DOM elements</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">dom-update.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">buttons</span> = [<span class="string">'Submit'</span>, <span class="string">'Cancel'</span>, <span class="string">'Reset'</span>];

buttons.<span class="function">forEach</span>(<span class="variable">text</span> => {
  <span class="keyword">const</span> <span class="variable">button</span> = document.<span class="function">createElement</span>(<span class="string">'button'</span>);
  button.textContent = text;
  document.body.<span class="function">appendChild</span>(button);
});</code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">2. Log for debugging</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">debug.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">errors</span> = [<span class="string">'Error 1'</span>, <span class="string">'Error 2'</span>, <span class="string">'Error 3'</span>];

errors.<span class="function">forEach</span>((<span class="variable">error</span>, <span class="variable">index</span>) => {
  console.<span class="function">log</span>(<span class="string">`${index + 1}. ${error}`</span>);
});
<span class="comment">// Output: 1. Error 1</span>
<span class="comment">//         2. Error 2</span>
<span class="comment">//         3. Error 3</span></code></pre>
                        </div>
                    </div>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "ForEach is used when you want to perform an action for each element but don't need to create a new array. It's perfect for side effects like updating the DOM, logging, or calling APIs. The key difference from map is: use forEach for actions, use map for transformations."
                    </p>
                </div>
            </div>

            <!-- FILTER METHOD -->
            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">filter()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Creates a <strong>NEW array</strong> with elements that pass a test condition.
                </p>

                <div class="key-points">
                    <h4>🎯 Key Points</h4>
                    <ul>
                        <li>Returns a new array (can be shorter, same length, or empty)</li>
                        <li>Keeps only elements where callback returns truthy value</li>
                        <li>Doesn't modify original array</li>
                    </ul>
                </div>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">syntax.js</span>
                    </div>
                    <pre><code><span class="keyword">const</span> filtered = array.<span class="function">filter</span>((<span class="variable">element</span>, <span class="variable">index</span>, <span class="variable">array</span>) => {
  <span class="keyword">return</span> booleanCondition;
});</code></pre>
                </div>

                <div class="use-cases">
                    <h4>💡 Real-World Use Cases</h4>

                    <div class="use-case">
                        <div class="use-case-title">1. Filter by condition</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">filter-products.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">products</span> = [
  { <span class="property">name</span>: <span class="string">'Laptop'</span>, <span class="property">price</span>: <span class="number">1000</span>, <span class="property">inStock</span>: <span class="keyword">true</span> },
  { <span class="property">name</span>: <span class="string">'Phone'</span>, <span class="property">price</span>: <span class="number">500</span>, <span class="property">inStock</span>: <span class="keyword">false</span> },
  { <span class="property">name</span>: <span class="string">'Tablet'</span>, <span class="property">price</span>: <span class="number">300</span>, <span class="property">inStock</span>: <span class="keyword">true</span> }
];

<span class="keyword">const</span> <span class="variable">available</span> = products.<span class="function">filter</span>(<span class="variable">product</span> => product.inStock);
<span class="comment">// Result: Laptop and Tablet objects</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">2. Remove falsy values</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">remove-falsy.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">mixed</span> = [<span class="number">0</span>, <span class="number">1</span>, <span class="keyword">false</span>, <span class="number">2</span>, <span class="string">''</span>, <span class="number">3</span>, <span class="keyword">null</span>, <span class="keyword">undefined</span>, <span class="string">'hello'</span>];

<span class="keyword">const</span> <span class="variable">truthy</span> = mixed.<span class="function">filter</span>(Boolean);
<span class="comment">// Result: [1, 2, 3, 'hello']</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">3. Search functionality</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">search.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">users</span> = [<span class="string">'Alice'</span>, <span class="string">'Bob'</span>, <span class="string">'Charlie'</span>, <span class="string">'David'</span>];
<span class="keyword">const</span> <span class="variable">searchTerm</span> = <span class="string">'a'</span>;

<span class="keyword">const</span> <span class="variable">results</span> = users.<span class="function">filter</span>(<span class="variable">user</span> => 
  user.<span class="function">toLowerCase</span>().<span class="function">includes</span>(searchTerm.<span class="function">toLowerCase</span>())
);
<span class="comment">// Result: ['Alice', 'Charlie', 'David']</span></code></pre>
                        </div>
                    </div>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Filter creates a new array containing only elements that pass a test. The callback should return true to keep the element or false to exclude it. It's commonly used for search functionality, removing unwanted items, or finding items that meet certain criteria."
                    </p>
                </div>
            </div>

            <!-- REDUCE METHOD -->
            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">reduce()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Reduces an array to a <strong>SINGLE value</strong> by executing a reducer function.
                </p>

                <div class="key-points">
                    <h4>🎯 Key Points</h4>
                    <ul>
                        <li>Returns a single value (number, string, object, array)</li>
                        <li>Accumulator stores the intermediate result</li>
                        <li>Initial value is optional but recommended</li>
                    </ul>
                </div>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">syntax.js</span>
                    </div>
                    <pre><code><span class="keyword">const</span> result = array.<span class="function">reduce</span>((<span class="variable">accumulator</span>, <span class="variable">currentValue</span>, <span class="variable">index</span>, <span class="variable">array</span>) => {
  <span class="keyword">return</span> newAccumulator;
}, initialValue);</code></pre>
                </div>

                <div class="use-cases">
                    <h4>💡 Real-World Use Cases</h4>

                    <div class="use-case">
                        <div class="use-case-title">1. Sum of numbers</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">sum.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">numbers</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">3</span>, <span class="number">4</span>, <span class="number">5</span>];

<span class="keyword">const</span> <span class="variable">sum</span> = numbers.<span class="function">reduce</span>((<span class="variable">acc</span>, <span class="variable">num</span>) => acc + num, <span class="number">0</span>);
<span class="comment">// Result: 15</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">2. Count occurrences</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">count.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">fruits</span> = [<span class="string">'apple'</span>, <span class="string">'banana'</span>, <span class="string">'apple'</span>, <span class="string">'orange'</span>, <span class="string">'banana'</span>, <span class="string">'apple'</span>];

<span class="keyword">const</span> <span class="variable">count</span> = fruits.<span class="function">reduce</span>((<span class="variable">acc</span>, <span class="variable">fruit</span>) => {
  acc[fruit] = (acc[fruit] || <span class="number">0</span>) + <span class="number">1</span>;
  <span class="keyword">return</span> acc;
}, {});

<span class="comment">// Result: { apple: 3, banana: 2, orange: 1 }</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">3. Group by property</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">group-by.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">people</span> = [
  { <span class="property">name</span>: <span class="string">'Alice'</span>, <span class="property">age</span>: <span class="number">25</span> },
  { <span class="property">name</span>: <span class="string">'Bob'</span>, <span class="property">age</span>: <span class="number">30</span> },
  { <span class="property">name</span>: <span class="string">'Charlie'</span>, <span class="property">age</span>: <span class="number">25</span> }
];

<span class="keyword">const</span> <span class="variable">groupedByAge</span> = people.<span class="function">reduce</span>((<span class="variable">acc</span>, <span class="variable">person</span>) => {
  <span class="keyword">const</span> <span class="variable">age</span> = person.age;
  <span class="keyword">if</span> (!acc[age]) acc[age] = [];
  acc[age].<span class="function">push</span>(person);
  <span class="keyword">return</span> acc;
}, {});

<span class="comment">// Result: { 25: [Alice, Charlie], 30: [Bob] }</span></code></pre>
                        </div>
                    </div>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Reduce is the most powerful array method. It processes each element and accumulates a result, returning a single value. The accumulator carries the result from one iteration to the next. I use it for summing values, counting occurrences, grouping data, or transforming arrays into objects."
                    </p>
                </div>
            </div>

            <!-- FIND METHOD -->
            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">find()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Returns the <strong>FIRST element</strong> that passes a test. Returns <code style="color: var(--accent-red);">undefined</code> if none found.
                </p>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">find-user.js</span>
                    </div>
                    <pre><code><span class="keyword">const</span> <span class="variable">users</span> = [
  { <span class="property">id</span>: <span class="number">1</span>, <span class="property">name</span>: <span class="string">'Alice'</span> },
  { <span class="property">id</span>: <span class="number">2</span>, <span class="property">name</span>: <span class="string">'Bob'</span> },
  { <span class="property">id</span>: <span class="number">3</span>, <span class="property">name</span>: <span class="string">'Charlie'</span> }
];

<span class="keyword">const</span> <span class="variable">user</span> = users.<span class="function">find</span>(<span class="variable">u</span> => u.id === <span class="number">2</span>);
<span class="comment">// Result: { id: 2, name: 'Bob' }</span></code></pre>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Find returns the first element that satisfies a condition, or undefined if nothing matches. It's more efficient than filter when you only need one item because it stops searching after finding the first match."
                    </p>
                </div>
            </div>

            <!-- SPLICE METHOD -->
            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">splice()</span>
                    <span class="badge badge-mutable">⚠️ Mutates</span>
                </div>

                <p class="description">
                    <strong>MODIFIES</strong> the original array by removing, replacing, or adding elements.
                </p>

                <div class="key-points">
                    <h4>🎯 Key Points</h4>
                    <ul>
                        <li>MUTATES the original array</li>
                        <li>Returns array of deleted elements</li>
                        <li>Can delete, insert, and replace in one operation</li>
                    </ul>
                </div>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">syntax.js</span>
                    </div>
                    <pre><code>array.<span class="function">splice</span>(start, deleteCount, item1, item2, ...);</code></pre>
                </div>

                <div class="use-cases">
                    <h4>💡 Real-World Use Cases</h4>

                    <div class="use-case">
                        <div class="use-case-title">1. Remove elements</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">remove.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">arr</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">3</span>, <span class="number">4</span>, <span class="number">5</span>];
arr.<span class="function">splice</span>(<span class="number">2</span>, <span class="number">2</span>); <span class="comment">// Remove 2 elements at index 2</span>
<span class="comment">// arr is now: [1, 2, 5]</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">2. Insert elements</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">insert.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">fruits</span> = [<span class="string">'apple'</span>, <span class="string">'banana'</span>];
fruits.<span class="function">splice</span>(<span class="number">1</span>, <span class="number">0</span>, <span class="string">'orange'</span>, <span class="string">'mango'</span>);
<span class="comment">// fruits is now: ['apple', 'orange', 'mango', 'banana']</span></code></pre>
                        </div>
                    </div>

                    <div class="use-case">
                        <div class="use-case-title">3. Replace elements</div>
                        <div class="code-container">
                            <div class="code-header">
                                <div class="code-dots">
                                    <span class="dot dot-red"></span>
                                    <span class="dot dot-yellow"></span>
                                    <span class="dot dot-green"></span>
                                </div>
                                <span class="code-title">replace.js</span>
                            </div>
                            <pre><code><span class="keyword">const</span> <span class="variable">colors</span> = [<span class="string">'red'</span>, <span class="string">'blue'</span>, <span class="string">'green'</span>];
colors.<span class="function">splice</span>(<span class="number">1</span>, <span class="number">1</span>, <span class="string">'yellow'</span>); <span class="comment">// Replace 'blue' with 'yellow'</span>
<span class="comment">// colors is now: ['red', 'yellow', 'green']</span></code></pre>
                        </div>
                    </div>
                </div>

                <div class="key-points" style="background: rgba(248, 81, 73, 0.1); border-left-color: var(--accent-red);">
                    <h4 style="color: var(--accent-red);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Splice is the Swiss Army knife of array modification. Unlike slice, it mutates the original array. It can remove items, add items, or both. The second parameter is how many items to delete. I use it when I need to modify an array in place."
                    </p>
                </div>
            </div>
        </section>

        <!-- STRING METHODS SECTION -->
        <section id="string-methods" class="section">
            <h2>String Methods</h2>

            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">split()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Splits a string into an <strong>ARRAY</strong> based on a separator.
                </p>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">split-examples.js</span>
                    </div>
                    <pre><code><span class="comment">// Split by space</span>
<span class="keyword">const</span> <span class="variable">sentence</span> = <span class="string">'Hello World from JavaScript'</span>;
<span class="keyword">const</span> <span class="variable">words</span> = sentence.<span class="function">split</span>(<span class="string">' '</span>);
<span class="comment">// Result: ['Hello', 'World', 'from', 'JavaScript']</span>

<span class="comment">// Split into characters</span>
<span class="keyword">const</span> <span class="variable">word</span> = <span class="string">'Hello'</span>;
<span class="keyword">const</span> <span class="variable">chars</span> = word.<span class="function">split</span>(<span class="string">''</span>);
<span class="comment">// Result: ['H', 'e', 'l', 'l', 'o']</span>

<span class="comment">// Parse CSV</span>
<span class="keyword">const</span> <span class="variable">csv</span> = <span class="string">'name,age,city'</span>;
<span class="keyword">const</span> <span class="variable">columns</span> = csv.<span class="function">split</span>(<span class="string">','</span>);
<span class="comment">// Result: ['name', 'age', 'city']</span></code></pre>
                </div>

                <div class="key-points" style="background: rgba(188, 140, 255, 0.05); border-left-color: var(--accent-purple);">
                    <h4 style="color: var(--accent-purple);">🎤 Interview Explanation</h4>
                    <p style="color: var(--text-primary);">
                        "Split converts a string into an array by breaking it at a separator. It's the opposite of join(). I use it constantly for parsing CSV, splitting sentences into words, or converting strings to character arrays."
                    </p>
                </div>
            </div>

            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">replace()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Replaces substring(s) with another string.
                </p>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">replace-examples.js</span>
                    </div>
                    <pre><code><span class="comment">// Replace first occurrence</span>
<span class="keyword">const</span> <span class="variable">str</span> = <span class="string">'Hello World World'</span>;
<span class="keyword">const</span> <span class="variable">result</span> = str.<span class="function">replace</span>(<span class="string">'World'</span>, <span class="string">'Earth'</span>);
<span class="comment">// Result: 'Hello Earth World'</span>

<span class="comment">// Replace all (use replaceAll or regex)</span>
<span class="keyword">const</span> <span class="variable">str2</span> = <span class="string">'Hello World World'</span>;
<span class="keyword">const</span> <span class="variable">result2</span> = str2.<span class="function">replaceAll</span>(<span class="string">'World'</span>, <span class="string">'Earth'</span>);
<span class="comment">// Result: 'Hello Earth Earth'</span>

<span class="comment">// Format phone number</span>
<span class="keyword">const</span> <span class="variable">phone</span> = <span class="string">'1234567890'</span>;
<span class="keyword">const</span> <span class="variable">formatted</span> = phone.<span class="function">replace</span>(<span class="operator">/</span>(\d{3})(\d{3})(\d{4})<span class="operator">/</span>, <span class="string">'($1) $2-$3'</span>);
<span class="comment">// Result: '(123) 456-7890'</span></code></pre>
                </div>
            </div>

            <div class="method-card">
                <div class="method-header">
                    <span class="method-name">includes()</span>
                    <span class="badge badge-immutable">Immutable</span>
                </div>

                <p class="description">
                    Checks if a string contains a substring. Returns boolean.
                </p>

                <div class="code-container">
                    <div class="code-header">
                        <div class="code-dots">
                            <span class="dot dot-red"></span>
                            <span class="dot dot-yellow"></span>
                            <span class="dot dot-green"></span>
                        </div>
                        <span class="code-title">includes-examples.js</span>
                    </div>
                    <pre><code><span class="comment">// Email validation</span>
<span class="keyword">const</span> <span class="variable">email</span> = <span class="string">'user@example.com'</span>;
<span class="keyword">const</span> <span class="variable">isValid</span> = email.<span class="function">includes</span>(<span class="string">'@'</span>) && email.<span class="function">includes</span>(<span class="string">'.'</span>);
<span class="comment">// Result: true</span>

<span class="comment">// Case-insensitive search</span>
<span class="keyword">const</span> <span class="variable">text</span> = <span class="string">'Hello World'</span>;
<span class="keyword">const</span> <span class="variable">hasHello</span> = text.<span class="function">toLowerCase</span>().<span class="function">includes</span>(<span class="string">'hello'</span>);
<span class="comment">// Result: true</span></code></pre>
                </div>
            </div>
        </section>

        <!-- INTERVIEW QUESTIONS -->
        <section id="interview-questions" class="section">
            <h2>Top Interview Questions</h2>

            <div class="interview-card">
                <div class="interview-question">
                    What's the difference between map() and forEach()?
                </div>
                <div class="interview-answer">
                    <p style="margin-bottom: 15px;">
                        The key difference is that <strong>map returns a new array</strong> while <strong>forEach returns undefined</strong>. Map should be used when you want to transform data, while forEach should be used for side effects.
                    </p>
                    <div class="code-container">
                        <div class="code-header">
                            <div class="code-dots">
                                <span class="dot dot-red"></span>
                                <span class="dot dot-yellow"></span>
                                <span class="dot dot-green"></span>
                            </div>
                            <span class="code-title">comparison.js</span>
                        </div>
                        <pre><code><span class="comment">// map - transformation</span>
<span class="keyword">const</span> <span class="variable">numbers</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">3</span>];
<span class="keyword">const</span> <span class="variable">doubled</span> = numbers.<span class="function">map</span>(<span class="variable">n</span> => n * <span class="number">2</span>); <span class="comment">// [2, 4, 6]</span>

<span class="comment">// forEach - side effects</span>
numbers.<span class="function">forEach</span>(<span class="variable">n</span> => console.<span class="function">log</span>(n)); <span class="comment">// Just logs, returns undefined</span></code></pre>
                    </div>
                    <p style="margin-top: 15px;">
                        Another difference: you can chain methods after map, but not forEach since it returns undefined.
                    </p>
                </div>
            </div>

            <div class="interview-card">
                <div class="interview-question">
                    What's the difference between filter() and find()?
                </div>
                <div class="interview-answer">
                    <p style="margin-bottom: 15px;">
                        <strong>Filter returns an array</strong> of ALL elements that pass the test, while <strong>find returns only the FIRST element</strong> that passes the test.
                    </p>
                    <div class="code-container">
                        <div class="code-header">
                            <div class="code-dots">
                                <span class="dot dot-red"></span>
                                <span class="dot dot-yellow"></span>
                                <span class="dot dot-green"></span>
                            </div>
                            <span class="code-title">filter-vs-find.js</span>
                        </div>
                        <pre><code><span class="keyword">const</span> <span class="variable">numbers</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">3</span>, <span class="number">4</span>, <span class="number">5</span>];

<span class="comment">// filter returns array</span>
<span class="keyword">const</span> <span class="variable">evens</span> = numbers.<span class="function">filter</span>(<span class="variable">n</span> => n % <span class="number">2</span> === <span class="number">0</span>);
<span class="comment">// Result: [2, 4]</span>

<span class="comment">// find returns single element</span>
<span class="keyword">const</span> <span class="variable">firstEven</span> = numbers.<span class="function">find</span>(<span class="variable">n</span> => n % <span class="number">2</span> === <span class="number">0</span>);
<span class="comment">// Result: 2</span></code></pre>
                    </div>
                    <p style="margin-top: 15px;">
                        Find is more efficient when you only need one item because it stops searching after the first match.
                    </p>
                </div>
            </div>

            <div class="interview-card">
                <div class="interview-question">
                    What's the difference between slice() and splice()?
                </div>
                <div class="interview-answer">
                    <p style="margin-bottom: 15px;">
                        <strong>Slice extracts a portion and returns a NEW array</strong> without modifying the original. <strong>Splice MODIFIES the original array</strong> and can add, remove, or replace elements.
                    </p>
                    <div class="code-container">
                        <div class="code-header">
                            <div class="code-dots">
                                <span class="dot dot-red"></span>
                                <span class="dot dot-yellow"></span>
                                <span class="dot dot-green"></span>
                            </div>
                            <span class="code-title">slice-vs-splice.js</span>
                        </div>
                        <pre><code><span class="keyword">const</span> <span class="variable">arr</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">3</span>, <span class="number">4</span>, <span class="number">5</span>];

<span class="comment">// slice - doesn't modify original</span>
<span class="keyword">const</span> <span class="variable">sliced</span> = arr.<span class="function">slice</span>(<span class="number">1</span>, <span class="number">3</span>);
<span class="comment">// sliced: [2, 3]</span>
<span class="comment">// arr still: [1, 2, 3, 4, 5]</span>

<span class="comment">// splice - modifies original</span>
<span class="keyword">const</span> <span class="variable">removed</span> = arr.<span class="function">splice</span>(<span class="number">1</span>, <span class="number">2</span>, <span class="string">'a'</span>, <span class="string">'b'</span>);
<span class="comment">// removed: [2, 3]</span>
<span class="comment">// arr now: [1, 'a', 'b', 4, 5]</span></code></pre>
                    </div>
                    <p style="margin-top: 15px;">
                        Remember: <strong>slice is safe and immutable</strong>, <strong>splice is destructive and mutates</strong>.
                    </p>
                </div>
            </div>

            <div class="interview-card">
                <div class="interview-question">
                    How would you remove duplicates from an array?
                </div>
                <div class="interview-answer">
                    <div class="code-container">
                        <div class="code-header">
                            <div class="code-dots">
                                <span class="dot dot-red"></span>
                                <span class="dot dot-yellow"></span>
                                <span class="dot dot-green"></span>
                            </div>
                            <span class="code-title">remove-duplicates.js</span>
                        </div>
                        <pre><code><span class="keyword">const</span> <span class="variable">arr</span> = [<span class="number">1</span>, <span class="number">2</span>, <span class="number">2</span>, <span class="number">3</span>, <span class="number">4</span>, <span class="number">4</span>, <span class="number">5</span>];

<span class="comment">// Method 1: Using Set (most common, modern)</span>
<span class="keyword">const</span> <span class="variable">unique1</span> = [...<span class="keyword">new</span> <span class="function">Set</span>(arr)];

<span class="comment">// Method 2: Using filter + indexOf</span>
<span class="keyword">const</span> <span class="variable">unique2</span> = arr.<span class="function">filter</span>((<span class="variable">item</span>, <span class="variable">index</span>) => arr.<span class="function">indexOf</span>(item) === index);

<span class="comment">// Method 3: Using reduce</span>
<span class="keyword">const</span> <span class="variable">unique3</span> = arr.<span class="function">reduce</span>((<span class="variable">acc</span>, <span class="variable">item</span>) => {
  <span class="keyword">if</span> (!acc.<span class="function">includes</span>(item)) acc.<span class="function">push</span>(item);
  <span class="keyword">return</span> acc;
}, []);

<span class="comment">// All result in: [1, 2, 3, 4, 5]</span></code></pre>
                    </div>
                    <p style="margin-top: 15px;">
                        I prefer the <strong>Set method</strong> because it's the most concise and performant for large arrays.
                    </p>
                </div>
            </div>
        </section>

        <!-- SUMMARY TABLE -->
        <section id="summary" class="section">
            <h2>Quick Reference Table</h2>

            <table>
                <thead>
                    <tr>
                        <th>Method</th>
                        <th>Mutates?</th>
                        <th>Returns</th>
                        <th>Use Case</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>map()</td>
                        <td>No</td>
                        <td>New array</td>
                        <td>Transform data</td>
                    </tr>
                    <tr>
                        <td>forEach()</td>
                        <td>No</td>
                        <td>undefined</td>
                        <td>Side effects</td>
                    </tr>
                    <tr>
                        <td>filter()</td>
                        <td>No</td>
                        <td>New array</td>
                        <td>Select items</td>
                    </tr>
                    <tr>
                        <td>reduce()</td>
                        <td>No</td>
                        <td>Single value</td>
                        <td>Aggregate data</td>
                    </tr>
                    <tr>
                        <td>find()</td>
                        <td>No</td>
                        <td>Element/undefined</td>
                        <td>Find one item</td>
                    </tr>
                    <tr>
                        <td>some()</td>
                        <td>No</td>
                        <td>Boolean</td>
                        <td>Check if any match</td>
                    </tr>
                    <tr>
                        <td>every()</td>
                        <td>No</td>
                        <td>Boolean</td>
                        <td>Check if all match</td>
                    </tr>
                    <tr>
                        <td>slice()</td>
                        <td>No</td>
                        <td>New array</td>
                        <td>Extract portion</td>
                    </tr>
                    <tr>
                        <td>splice()</td>
                        <td><strong style="color: var(--accent-red);">Yes</strong></td>
                        <td>Removed items</td>
                        <td>Modify array</td>
                    </tr>
                    <tr>
                        <td>sort()</td>
                        <td><strong style="color: var(--accent-red);">Yes</strong></td>
                        <td>Same array</td>
                        <td>Order items</td>
                    </tr>
                    <tr>
                        <td>reverse()</td>
                        <td><strong style="color: var(--accent-red);">Yes</strong></td>
                        <td>Same array</td>
                        <td>Flip order</td>
                    </tr>
                    <tr>
                        <td>includes()</td>
                        <td>No</td>
                        <td>Boolean</td>
                        <td>Check existence</td>
                    </tr>
                    <tr>
                        <td>join()</td>
                        <td>No</td>
                        <td>String</td>
                        <td>Array to string</td>
                    </tr>
                    <tr>
                        <td>split()</td>
                        <td>No</td>
                        <td>Array</td>
                        <td>String to array</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- TIPS SECTION -->
        <section class="section">
            <h2>Interview Tips</h2>

            <div class="tips-grid">
                <div class="tip-card">
                    <h4>💡 Mention Immutability</h4>
                    <p>Always state whether a method mutates the original array or creates a new one.</p>
                </div>

                <div class="tip-card">
                    <h4>🎯 Give Real Examples</h4>
                    <p>Don't just explain syntax, show practical use cases from real-world applications.</p>
                </div>

                <div class="tip-card">
                    <h4>⚡ Discuss Performance</h4>
                    <p>Talk about time complexity when relevant (O(1) for push/pop, O(n) for shift/unshift).</p>
                </div>

                <div class="tip-card">
                    <h4>🔄 Know Return Values</h4>
                    <p>Every method returns something specific - know what each method returns.</p>
                </div>

                <div class="tip-card">
                    <h4>📊 Compare Methods</h4>
                    <p>Show you understand differences: map vs forEach, filter vs find, slice vs splice.</p>
                </div>

                <div class="tip-card">
                    <h4>🚀 Modern Alternatives</h4>
                    <p>Mention ES6+ features like spread operator, destructuring, and Set when relevant.</p>
                </div>
            </div>
        </section>
    </div>
</body>
</html>
