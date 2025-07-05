<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Blog Theme Preview</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #6366f1;
            --secondary-color: #8b5cf6;
            --accent-color: #06b6d4;
            --text-primary: #1f2937;
            --text-secondary: #6b7280;
            --text-light: #9ca3af;
            --bg-primary: #ffffff;
            --bg-secondary: #f9fafb;
            --bg-accent: #f3f4f6;
            --border-color: #e5e7eb;
            --gradient-1: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
            --gradient-2: linear-gradient(135deg, #06b6d4 0%, #3b82f6 100%);
            --gradient-3: linear-gradient(135deg, #f59e0b 0%, #ef4444 100%);
            --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            background: var(--bg-primary);
            overflow-x: hidden;
        }

        /* Header */
        .header {
            background: var(--bg-primary);
            box-shadow: var(--shadow-sm);
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.95);
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            background: var(--gradient-1);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gradient-1);
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::after {
            width: 100%;
        }

        .search-box {
            position: relative;
        }

        .search-box input {
            padding: 10px 15px 10px 40px;
            border: 2px solid var(--border-color);
            border-radius: 25px;
            outline: none;
            width: 250px;
            transition: all 0.3s ease;
        }

        .search-box input:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(99, 102, 241, 0.1);
        }

        .search-box i {
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-light);
        }

        /* Hero Section */
        .hero {
            margin-top: 70px;
            background: var(--gradient-1);
            padding: 80px 0;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="white" opacity="0.1"><polygon points="0,0 1000,100 1000,0"/></svg>');
            background-size: cover;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 20px;
            position: relative;
            z-index: 1;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero p {
            font-size: 1.25rem;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 30px;
            background: white;
            color: var(--primary-color);
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: var(--shadow-lg);
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-xl);
        }

        /* Main Content */
        .main-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 60px 20px;
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 40px;
        }

        .content-area {
            background: var(--bg-primary);
        }

        /* Featured Post */
        .featured-post {
            background: var(--bg-primary);
            border-radius: 20px;
            box-shadow: var(--shadow-lg);
            overflow: hidden;
            margin-bottom: 40px;
            transition: all 0.3s ease;
        }

        .featured-post:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-xl);
        }

        .featured-image {
            height: 300px;
            background: var(--gradient-2);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .featured-content {
            padding: 30px;
        }

        .featured-badge {
            display: inline-block;
            background: var(--gradient-1);
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .featured-title {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 15px;
            line-height: 1.3;
        }

        .featured-excerpt {
            color: var(--text-secondary);
            margin-bottom: 20px;
            font-size: 1.1rem;
        }

        .post-meta {
            display: flex;
            align-items: center;
            gap: 20px;
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .post-meta i {
            color: var(--primary-color);
        }

        /* Blog Posts Grid */
        .posts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .post-card {
            background: var(--bg-primary);
            border-radius: 15px;
            box-shadow: var(--shadow-md);
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .post-card:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .post-image {
            height: 200px;
            background: var(--gradient-3);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
        }

        .post-content {
            padding: 25px;
        }

        .post-category {
            display: inline-block;
            background: var(--bg-accent);
            color: var(--primary-color);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .post-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 10px;
            line-height: 1.4;
        }

        .post-excerpt {
            color: var(--text-secondary);
            margin-bottom: 15px;
            font-size: 0.95rem;
        }

        .read-more {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 5px;
            transition: all 0.3s ease;
        }

        .read-more:hover {
            gap: 10px;
        }

        /* Sidebar */
        .sidebar {
            background: var(--bg-primary);
        }

        .sidebar-widget {
            background: var(--bg-primary);
            border-radius: 15px;
            box-shadow: var(--shadow-md);
            padding: 25px;
            margin-bottom: 30px;
        }

        .widget-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: var(--text-primary);
        }

        .about-widget {
            text-align: center;
        }

        .author-avatar {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: var(--gradient-1);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2rem;
        }

        .popular-posts {
            list-style: none;
        }

        .popular-posts li {
            padding: 15px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .popular-posts li:last-child {
            border-bottom: none;
        }

        .popular-posts a {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .popular-posts a:hover {
            color: var(--primary-color);
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag {
            background: var(--bg-accent);
            color: var(--text-primary);
            padding: 8px 15px;
            border-radius: 20px;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .tag:hover {
            background: var(--primary-color);
            color: white;
        }

        /* AdSense Placeholders */
        .adsense-banner {
            background: linear-gradient(45deg, #f3f4f6, #e5e7eb);
            border: 2px dashed var(--border-color);
            border-radius: 10px;
            padding: 40px;
            text-align: center;
            color: var(--text-light);
            font-weight: 500;
            margin: 30px 0;
        }

        .adsense-sidebar {
            background: linear-gradient(45deg, #f3f4f6, #e5e7eb);
            border: 2px dashed var(--border-color);
            border-radius: 10px;
            padding: 30px;
            text-align: center;
            color: var(--text-light);
            font-weight: 500;
            margin-bottom: 30px;
        }

        /* Footer */
        .footer {
            background: var(--text-primary);
            color: white;
            padding: 60px 0 30px;
            margin-top: 80px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .footer-section h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            margin-bottom: 20px;
        }

        .footer-section p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 15px;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section ul li a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section ul li a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: var(--gradient-1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 40px;
            padding-top: 30px;
            text-align: center;
            color: rgba(255, 255, 255, 0.6);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                height: auto;
                padding: 15px 20px;
            }

            .nav-menu {
                flex-direction: column;
                gap: 1rem;
                margin: 15px 0;
            }

            .search-box input {
                width: 100%;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .main-content {
                grid-template-columns: 1fr;
                gap: 20px;
                padding: 40px 20px;
            }

            .posts-grid {
                grid-template-columns: 1fr;
            }

            .footer-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
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

        .post-card {
            animation: fadeInUp 0.6s ease-out;
        }

        .post-card:nth-child(2) {
            animation-delay: 0.1s;
        }

        .post-card:nth-child(3) {
            animation-delay: 0.2s;
        }

        .post-card:nth-child(4) {
            animation-delay: 0.3s;
        }

        /* Dark mode support */
        @media (prefers-color-scheme: dark) {
            :root {
                --text-primary: #f9fafb;
                --text-secondary: #d1d5db;
                --text-light: #9ca3af;
                --bg-primary: #1f2937;
                --bg-secondary: #111827;
                --bg-accent: #374151;
                --border-color: #4b5563;
            }

            .header {
                background: rgba(31, 41, 55, 0.95);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="header-content">
            <a href="#" class="logo">BlogKu</a>
            <nav>
                <ul class="nav-menu">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#blog">Blog</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <div class="search-box">
                <i class="fas fa-search"></i>
                <input type="text" placeholder="Search articles...">
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Welcome to My Blog</h1>
            <p>Discover amazing stories, tutorials, and insights about web development, design, and technology</p>
            <a href="#blog" class="cta-button">Start Reading</a>
        </div>
    </section>

    <!-- Main Content -->
    <main class="main-content">
        <div class="content-area">
            <!-- Featured Post -->
            <article class="featured-post">
                <div class="featured-image">
                    <i class="fas fa-star"></i>
                </div>
                <div class="featured-content">
                    <span class="featured-badge">Featured</span>
                    <h2 class="featured-title">How to Build a Modern Blog with Jekyll and GitHub Pages</h2>
                    <p class="featured-excerpt">Learn how to create a beautiful, fast, and SEO-optimized blog using Jekyll and GitHub Pages. This comprehensive guide covers everything from setup to monetization with Google AdSense.</p>
                    <div class="post-meta">
                        <span><i class="fas fa-calendar"></i> January 15, 2025</span>
                        <span><i class="fas fa-user"></i> Admin</span>
                        <span><i class="fas fa-eye"></i> 1,234 views</span>
                        <span><i class="fas fa-clock"></i> 8 min read</span>
                    </div>
                </div>
            </article>

            <!-- AdSense Banner -->
            <div class="adsense-banner">
                <i class="fas fa-ad"></i>
                <p>Google AdSense Banner (728x90)</p>
            </div>

            <!-- Blog Posts Grid -->
            <div class="posts-grid">
                <article class="post-card">
                    <div class="post-image">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="post-content">
                        <span class="post-category">Tutorial</span>
                        <h3 class="post-title">CSS Grid vs Flexbox: When to Use Each</h3>
                        <p class="post-excerpt">Understanding the differences between CSS Grid and Flexbox will help you choose the right layout method for your projects.</p>
                        <a href="#" class="read-more">Read More <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>

                <article class="post-card">
                    <div class="post-image">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="post-content">
                        <span class="post-category">Design</span>
                        <h3 class="post-title">Mobile-First Design Principles</h3>
                        <p class="post-excerpt">Learn how to design websites that work perfectly on mobile devices and scale up beautifully to desktop.</p>
                        <a href="#" class="read-more">Read More <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>

                <article class="post-card">
                    <div class="post-image">
                        <i class="fas fa-rocket"></i>
                    </div>
                    <div class="post-content">
                        <span class="post-category">Performance</span>
                        <h3 class="post-title">10 Ways to Speed Up Your Website</h3>
                        <p class="post-excerpt">Discover proven techniques to improve your website's loading speed and user experience.</p>
                        <a href="#" class="read-more">Read More <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>

                <article class="post-card">
                    <div class="post-image">
                        <i class="fas fa-search"></i>
                    </div>
                    <div class="post-content">
                        <span class="post-category">SEO</span>
                        <h3 class="post-title">SEO Best Practices for 2025</h3>
                        <p class="post-excerpt">Stay ahead of the competition with these essential SEO strategies that actually work in 2025.</p>
                        <a href="#" class="read-more">Read More <i class="fas fa-arrow-right"></i></a>
                    </div>
                </article>
            </div>
        </div>

        <!-- Sidebar -->
        <aside class="sidebar">
            <!-- AdSense Sidebar -->
            <div class="adsense-sidebar">
                <i class="fas fa-ad"></i>
                <p>Google AdSense<br>Sidebar Ad (300x250)</p>
            </div>

            <!-- About Widget -->
            <div class="sidebar-widget about-widget">
                <h3 class="widget-title">About Me</h3>
                <div class="author-avatar">
                    <i class="fas fa-user"></i>
                </div>
                <p>Hi, I'm a passionate web developer sharing my knowledge about modern web technologies, design trends, and best practices.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                </div>
            </div>

            <!-- Popular Posts Widget -->
            <div class="sidebar-widget">
                <h3 class="widget-title">Popular Posts</h3>
                <ul class="popular-posts">
                    <li><a href="#">How to Build a Modern Blog with Jekyll</a></li>
                    <li><a href="#">CSS Grid vs Flexbox: Complete Guide</a></li>
                    <li><a href="#">Mobile-First Design Principles</a></li>
                    <li><a href="#">10 Ways to Speed Up Your Website</a></li>
                    <li><a href="#">SEO Best Practices for 2025</a></li>
                </ul>
            </div>

            <!-- Tags Widget -->
            <div class="sidebar-widget">
                <h3 class="widget-title">Tags</h3>
                <div class="tags">
                    <a href="#" class="tag">Jekyll</a>
                    <a href="#" class="tag">CSS</a>
                    <a href="#" class="tag">JavaScript</a>
                    <a href="#" class="tag">SEO</a>
                    <a href="#" class="tag">Design</a>
                    <a href="#" class="tag">Tutorial</a>
                    <a href="#" class="tag">Web Dev</a>
                    <a href="#" class="tag">Performance</a>
                </div>
            </div>
        </aside>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-section">
                <h3>BlogKu</h3>
                <p>A modern blog about web development, design, and technology. Follow along for tutorials, tips, and insights.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                    <a href="#"><i class="fab fa-github"></i></a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                    <li><a href="#">Privacy Policy</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Categories</h3>
                <ul>
                    <li><a href="#">Web Development</a></li>
                    <li><a href="#">Design</a></li>
                    <li><a href="#">SEO</a></li>
                    <li><a href="#">Performance</a></li>
                    <li><a href="#">Tutorials</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h3>Contact</h3>
                <p><i class="fas fa-envelope"></i> hello@blogku.com</p>
                <p><i class="fas fa-phone"></i> +62 123 4567 890</p>
                <p><i class="fas fa-map-marker-alt"></i> Jakarta, Indonesia</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2025 BlogKu. All rights reserved. Made with ❤️ using Jekyll & GitHub Pages</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Search functionality
        const searchInput = document.querySelector('.search-box input');
        searchInput.addEventListener('input', function(e) {
            const searchTerm = e.target.value.toLowerCase();
            const postCards = document.querySelectorAll('.post-card');
            
            postCards.forEach(card => {
                const title = card.querySelector('.post-title').textContent.toLowerCase();
                const excerpt = card.querySelector('.post-excerpt').textContent.toLowerCase();
                
                if (title.includes(searchTerm) || excerpt.includes(searchTerm)) {
                    card.style.display = 'block';
                } else {
                    card.style.display = searchTerm ? 'none' : 'block';
                }
            });
        });

        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.querySelector('.header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(255, 255, 255, 0.98)';
                header.style.boxShadow = '0 4px 20px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.background = 'rgba(255, 255, 255, 0.95)';
                header.style.boxShadow = '0 1px 2px rgba(0, 0, 0, 0.05)';
            }
        });

        // Animate elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe all post cards and sidebar widgets
        document.querySelectorAll('.post-card, .sidebar-widget').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'all 0.6s ease-out';
            observer.observe(el);
        });

        // Mobile menu toggle
        const mobileMenuBtn = document.createElement('button');
        mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
        mobileMenuBtn.className = 'mobile-menu-btn';
        mobileMenuBtn.style.cssText = `
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-primary);
            cursor: pointer;
        `;

        // Add mobile menu styles
        const mobileMenuStyles = `
            @media (max-width: 768px) {
                .mobile-menu-btn {
                    display: block !important;
                }
                .nav-menu {
                    display: none;
                    position: absolute;
                    top: 100%;
                    left: 0;
                    right: 0;
                    background: white;
                    flex-direction: column;
                    padding: 20px;
                    box-shadow: var(--shadow-lg);
                }
                .nav-menu.active {
                    display: flex !important;
                }
            }
        `;

        const style = document.createElement('style');
        style.textContent = mobileMenuStyles;
        document.head.appendChild(style);

        const headerContent = document.querySelector('.header-content');
        headerContent.appendChild(mobileMenuBtn);

        mobileMenuBtn.addEventListener('click', function() {
            const navMenu = document.querySelector('.nav-menu');
            navMenu.classList.toggle('active');
        });

        // Reading progress indicator
        const progressBar = document.createElement('div');
        progressBar.style.cssText = `
            position: fixed;
            top: 70px;
            left: 0;
            height: 3px;
            background: var(--gradient-1);
            z-index: 1000;
            transition: width 0.3s ease;
        `;
        document.body.appendChild(progressBar);

        window.addEventListener('scroll', function() {
            const scrolled = (window.scrollY / (document.body.scrollHeight - window.innerHeight)) * 100;
            progressBar.style.width = scrolled + '%';
        });

        // Auto-hide header on scroll down, show on scroll up
        let lastScrollY = window.scrollY;
        window.addEventListener('scroll', function() {
            const header = document.querySelector('.header');
            if (window.scrollY > lastScrollY && window.scrollY > 100) {
                header.style.transform = 'translateY(-100%)';
            } else {
                header.style.transform = 'translateY(0)';
            }
            lastScrollY = window.scrollY;
        });

        // Add loading animation
        window.addEventListener('load', function() {
            document.body.style.opacity = '0';
            document.body.style.transition = 'opacity 0.5s ease';
            setTimeout(() => {
                document.body.style.opacity = '1';
            }, 100);
        });

        // Newsletter signup (example)
        const newsletterForm = document.createElement('div');
        newsletterForm.innerHTML = `
            <div class="newsletter-signup" style="
                background: var(--gradient-1);
                color: white;
                padding: 40px;
                border-radius: 15px;
                margin: 30px 0;
                text-align: center;
            ">
                <h3 style="margin-bottom: 15px;">Subscribe to Newsletter</h3>
                <p style="margin-bottom: 20px; opacity: 0.9;">Get the latest posts delivered right to your inbox</p>
                <form style="display: flex; gap: 10px; max-width: 400px; margin: 0 auto;">
                    <input type="email" placeholder="Your email..." style="
                        flex: 1;
                        padding: 12px;
                        border: none;
                        border-radius: 25px;
                        outline: none;
                    ">
                    <button type="submit" style="
                        padding: 12px 24px;
                        background: white;
                        color: var(--primary-color);
                        border: none;
                        border-radius: 25px;
                        font-weight: 600;
                        cursor: pointer;
                        transition: all 0.3s ease;
                    ">Subscribe</button>
                </form>
            </div>
        `;

        // Add newsletter signup to sidebar
        const sidebar = document.querySelector('.sidebar');
        sidebar.appendChild(newsletterForm);

        // Back to top button
        const backToTopBtn = document.createElement('button');
        backToTopBtn.innerHTML = '<i class="fas fa-arrow-up"></i>';
        backToTopBtn.style.cssText = `
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gradient-1);
            color: white;
            border: none;
            font-size: 18px;
            cursor: pointer;
            opacity: 0;
            transform: translateY(100px);
            transition: all 0.3s ease;
            z-index: 1000;
            box-shadow: var(--shadow-lg);
        `;

        document.body.appendChild(backToTopBtn);

        window.addEventListener('scroll', function() {
            if (window.scrollY > 500) {
                backToTopBtn.style.opacity = '1';
                backToTopBtn.style.transform = 'translateY(0)';
            } else {
                backToTopBtn.style.opacity = '0';
                backToTopBtn.style.transform = 'translateY(100px)';
            }
        });

        backToTopBtn.addEventListener('click', function() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        });

        // Copy to clipboard functionality for code blocks
        document.querySelectorAll('pre').forEach(pre => {
            const button = document.createElement('button');
            button.innerHTML = '<i class="fas fa-copy"></i>';
            button.style.cssText = `
                position: absolute;
                top: 10px;
                right: 10px;
                background: rgba(255, 255, 255, 0.2);
                border: none;
                color: white;
                padding: 8px;
                border-radius: 5px;
                cursor: pointer;
                transition: all 0.3s ease;
            `;
            pre.style.position = 'relative';
            pre.appendChild(button);

            button.addEventListener('click', function() {
                navigator.clipboard.writeText(pre.textContent).then(() => {
                    button.innerHTML = '<i class="fas fa-check"></i>';
                    setTimeout(() => {
                        button.innerHTML = '<i class="fas fa-copy"></i>';
                    }, 2000);
                });
            });
        });

        console.log('Modern Blog Theme loaded successfully! 🚀');
    </script>
