File 1: positioning.html
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 6.4 — Positioning Practice</title>
    <!-- Link to External Stylesheet -->
    <link rel="stylesheet" href="position-style.css">
</head>
<body>

    <!-- 2. Sticky Navigation Bar -->
    <nav class="sticky-nav">
        <div class="nav-content">
            <span class="logo">Positioning Lab</span>
            <ul>
                <li><a href="#section1">Introduction</a></li>
                <li><a href="#section2">Card Showcase</a></li>
                <li><a href="#section3">Conclusion</a></li>
            </ul>
        </div>
    </nav>

    <!-- 3. Fixed Floating Action Button (FAB) -->
    <a href="#section1" class="floating-btn" title="Back to Top">↑ Top</a>

    <!-- Header -->
    <header class="page-header">
        <h1>CSS Positioning Practice</h1>
        <p>Scroll down to observe the sticky navbar, fixed action button, and absolute badges.</p>
    </header>

    <main class="container">
        
        <!-- Section 1 -->
        <section id="section1" class="content-section">
            <h2>Section 1: Sticky Navigation</h2>
            <p>Notice how the navigation bar sticks securely to the very top of the browser viewport as you scroll down the page. This is achieved using <code>position: sticky</code>.</p>
        </section>

        <!-- Section 2: Absolute Badge & Relative Parent -->
        <section id="section2" class="content-section">
            <h2>Section 2: Absolute Badge inside Relative Card</h2>
            <p>The card below uses <code>position: relative</code> so that the notification badge can be precisely positioned using <code>position: absolute</code> in the top-right corner.</p>
            
            <!-- 4 & 5. Relative Parent Card with Absolute Badge -->
            <div class="relative-card">
                <span class="absolute-badge">New!</span>
                <h3>Special Feature Card</h3>
                <p>This container acts as the positioned ancestor. The badge is locked to its top-right corner regardless of inner content sizing.</p>
            </div>
        </section>

        <!-- Section 3 -->
        <section id="section3" class="content-section">
            <h2>Section 3: Fixed Floating Action Button</h2>
            <p>Look at the bottom-right corner of your screen. The "↑ Top" button uses <code>position: fixed</code> combined with a high <code>z-index</code>, floating above all other page content even when scrolling through long sections.</p>
        </section>

    </main>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Student Positioning Lab. All rights reserved.</p>
    </footer>

</body>
</html>
File 2: position-style.css
CSS
/* --- Global Reset & Typography --- */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    scroll-behavior: smooth;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f8fafc;
    color: #334155;
    line-height: 1.6;
}

/* --- 2. Sticky Navigation Bar --- */
.sticky-nav {
    position: sticky;           /* Sticks to top of viewport */
    top: 0;
    background-color: #1e293b;
    color: #ffffff;
    padding: 1rem 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
    z-index: 1000;              /* Ensures navbar stays above all content */
}

.nav-content {
    max-width: 900px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-weight: 700;
    font-size: 1.1rem;
    color: #38bdf8;
}

.sticky-nav ul {
    list-style: none;
    display: flex;
    gap: 1.5rem;
}

.sticky-nav a {
    color: #cbd5e1;
    text-decoration: none;
    font-size: 0.95rem;
    transition: color 0.2s ease;
}

.sticky-nav a:hover {
    color: #ffffff;
}

/* --- 3. Fixed Floating Action Button (FAB) --- */
.floating-btn {
    position: fixed;            /* Fixed relative to browser viewport */
    bottom: 2rem;
    right: 2rem;
    background-color: #2563eb;
    color: #ffffff;
    padding: 0.75rem 1.2rem;
    border-radius: 50px;
    text-decoration: none;
    font-weight: 600;
    font-size: 0.95rem;
    box-shadow: 0 10px 15px -3px rgba(37, 99, 235, 0.3);
    z-index: 999;               /* Layered above content */
    transition: background-color 0.2s ease, transform 0.2s ease;
}

.floating-btn:hover {
    background-color: #1d4ed8;
    transform: translateY(-2px);
}

/* --- Header Styling --- */
.page-header {
    background: linear-gradient(135deg, #0f172a, #1e293b);
    color: #ffffff;
    text-align: center;
    padding: 4rem 1.5rem;
}

.page-header h1 {
    font-size: 2.5rem;
    margin-bottom: 0.5rem;
}

.page-header p {
    color: #94a3b8;
    font-size: 1.1rem;
}

/* --- Main Container & Sections --- */
.container {
    max-width: 800px;
    margin: 3rem auto;
    padding: 0 1.5rem;
}

.content-section {
    background-color: #ffffff;
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    padding: 2.5rem;
    margin-bottom: 2.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.02);
}

.content-section h2 {
    color: #1e3a8a;
    font-size: 1.4rem;
    margin-bottom: 1rem;
}

.content-section p {
    color: #475569;
}

/* --- 4 & 5. Relative Parent Card & Absolute Badge --- */
.relative-card {
    position: relative;         /* Establishes positioning context for child elements */
    background-color: #eff6ff;
    border: 1px solid #bfdbfe;
    border-radius: 8px;
    padding: 2rem;
    margin-top: 1.5rem;
}

.absolute-badge {
    position: absolute;         /* Positioned relative to .relative-card */
    top: -12px;                 /* Pulls badge slightly above the card edge */
    right: 20px;
    background-color: #ef4444;  /* Red accent */
    color: #ffffff;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 0.3rem 0.8rem;
    border-radius: 50px;
    text-transform: uppercase;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.relative-card h3 {
    color: #1e40af;
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
}

.relative-card p {
    color: #3b82f6;
    font-size: 0.95rem;
}

/* --- Footer --- */
footer {
    text-align: center;
    padding: 2rem;
    background-color: #0f172a;
    color: #94a3b8;
    font-size: 0.9rem;
}