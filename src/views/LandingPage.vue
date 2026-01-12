<template>
  <div class="landing-page">
    <!-- Navigation -->
    <nav class="navbar" ref="navbar">
      <div class="nav-container">
        <a href="#" class="logo" ref="logo">
          <img src="/src/images/SGC-LOGO-NEW.jpeg" alt="SGC Logo" class="logo-image">
          <span class="logo-text">
            <span class="logo-s">S</span><span class="logo-g">G</span><span class="logo-c">C</span>
          </span>
        </a>
        <ul class="nav-links" ref="navLinks">
          <li><a href="#tech" class="nav-link">Tech Insights</a></li>
          <li><a href="#products" class="nav-link">Products</a></li>
          <li><a href="#team" class="nav-link">Team</a></li>
          <li><a href="#about" class="nav-link">About</a></li>
          <li><a href="#contact" class="nav-cta">Get Started</a></li>
        </ul>
        <button class="mobile-menu-btn" @click="toggleMobileMenu" ref="menuBtn">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </nav>

    <!-- Mobile Menu -->
    <div class="mobile-menu" :class="{ active: mobileMenuOpen }">
      <div class="mobile-menu-content">
        <ul>
          <li><a href="#tech" @click="closeMobileMenu">Tech Insights</a></li>
          <li><a href="#products" @click="closeMobileMenu">Products</a></li>
          <li><a href="#team" @click="closeMobileMenu">Team</a></li>
          <li><a href="#about" @click="closeMobileMenu">About</a></li>
          <li><a href="#contact" @click="closeMobileMenu">Contact</a></li>
        </ul>
      </div>
    </div>

    <!-- Hero Section -->
    <section class="hero" ref="heroSection">
      <div class="hero-background">
        <div class="gradient-orb orb-1" ref="orb1"></div>
        <div class="gradient-orb orb-2" ref="orb2"></div>
        <div class="gradient-orb orb-3" ref="orb3"></div>
        <div class="grid-pattern"></div>
        <div class="floating-icons">
          <div class="float-icon" style="top: 15%; left: 10%; animation-delay: 0s;">🌾</div>
          <div class="float-icon" style="top: 25%; right: 15%; animation-delay: 1s;">🚜</div>
          <div class="float-icon" style="top: 65%; left: 8%; animation-delay: 2s;">🌿</div>
          <div class="float-icon" style="bottom: 20%; right: 10%; animation-delay: 1.5s;">🌻</div>
          <div class="float-icon" style="top: 45%; left: 85%; animation-delay: 0.5s;">🌾</div>
        </div>
      </div>
      
      <div class="hero-container">
        <div class="hero-content">
          <div class="hero-badge" ref="heroBadge">
            <span class="badge-dot"></span>
            <span>Revolutionizing Agriculture</span>
          </div>
          
          <h1 class="hero-title" ref="heroTitle">
            <span class="title-line" ref="titleLine1">Cultivating the</span>
            <span class="title-line gradient-text" ref="titleLine2">Future of Agriculture</span>
          </h1>
          
          <p class="hero-description" ref="heroDesc">
            SGC delivers innovative AgriTech solutions to empower farmers, boost yields, 
            and promote sustainable practices for a growing world.
          </p>
          
          <div class="hero-actions" ref="heroActions">
            <a href="#products" class="btn btn-primary">
              <span>Explore Products</span>
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M5 12h14M12 5l7 7-7 7"/>
              </svg>
            </a>
            <a href="#contact" class="btn btn-outline">
              <span>Contact Us</span>
            </a>
          </div>
          
          <div class="hero-stats" ref="heroStats">
            <div class="stat-item">
              <div class="stat-number">50%</div>
              <div class="stat-label">Water Savings</div>
            </div>
            <div class="stat-divider"></div>
            <div class="stat-item">
              <div class="stat-number">24/7</div>
              <div class="stat-label">Monitoring</div>
            </div>
            <div class="stat-divider"></div>
            <div class="stat-item">
              <div class="stat-number">100+</div>
              <div class="stat-label">Happy Farmers</div>
            </div>
          </div>
        </div>
        
        <div class="hero-visual" ref="heroVisual">
          <div class="visual-card" ref="visualCard">
            <img src="https://images.unsplash.com/photo-1530836369250-ef72a3f5cda8?q=80&w=2070&auto=format&fit=crop" alt="Smart Farm Technology" />
            <div class="card-glow"></div>
          </div>
          <div class="floating-badge badge-1" ref="floatingBadge1">
            <div class="badge-icon">🌱</div>
            <div class="badge-text">
              <div class="badge-title">Smart Growth</div>
              <div class="badge-subtitle">AI-Powered</div>
            </div>
          </div>
          <div class="floating-badge badge-2" ref="floatingBadge2">
            <div class="badge-icon">💧</div>
            <div class="badge-text">
              <div class="badge-title">Water Optimized</div>
              <div class="badge-subtitle">50% Less Usage</div>
            </div>
          </div>
        </div>
      </div>
      
      <div class="scroll-indicator" ref="scrollIndicator">
        <div class="scroll-text">Scroll to discover</div>
        <div class="scroll-line"></div>
      </div>
    </section>

    <!-- Tech Section -->
    <section class="tech-section" id="tech" ref="techSection">
      <div class="container">
        <div class="section-header" ref="techHeader">
          <span class="section-tag">
            <span class="tag-dot"></span>
            Innovation
          </span>
          <h2 class="section-title">The Future is <span class="gradient-text">Growing</span></h2>
          <p class="section-description">
            Discover how technology is transforming agriculture, enabling smarter, 
            more efficient, and sustainable farming practices.
          </p>
        </div>
        
        <div class="tech-grid">
          <div class="tech-card" v-for="(tech, index) in techFeatures" :key="index" :ref="el => { if (el) techCards[index] = el }">
            <div class="tech-card-inner">
              <div class="tech-icon-wrapper">
                <div class="icon-bg"></div>
                <div class="tech-icon" v-html="tech.icon"></div>
              </div>
              <h3 class="tech-title">{{ tech.title }}</h3>
              <p class="tech-description">{{ tech.description }}</p>
              <div class="tech-link">
                Learn more
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M5 12h14M12 5l7 7-7 7"/>
                </svg>
              </div>
            </div>
            <div class="card-shine"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Newsletter Section -->
    <section class="newsletter-section" ref="newsletterSection">
      <div class="container">
        <div class="newsletter-card">
          <div class="newsletter-glow"></div>
          <div class="newsletter-content">
            <div class="newsletter-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"/>
              </svg>
            </div>
            <h3 class="newsletter-title">Stay Ahead of the Curve</h3>
            <p class="newsletter-desc">Subscribe to our newsletter for the latest AgriTech news, product updates, and farming tips delivered straight to your inbox.</p>
            <form class="newsletter-form" @submit.prevent="subscribeNewsletter">
              <div class="form-input-wrapper">
                <svg class="input-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                  <polyline points="22,6 12,13 2,6"/>
                </svg>
                <input type="email" placeholder="Enter your email address" v-model="email" required />
              </div>
              <button type="submit" class="btn btn-primary">
                <span>Subscribe</span>
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M22 2L11 13M22 2l-7 20-4-9-9-4 20-7z"/>
                </svg>
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Products Section -->
    <section class="products-section" id="products" ref="productsSection">
      <div class="container">
        <div class="section-header" ref="productsHeader">
          <span class="section-tag">
            <span class="tag-dot"></span>
            Our Flagship Product
          </span>
          <h2 class="section-title">Smart Greenhouse <span class="gradient-text">Container</span></h2>
          <p class="section-description">
            A fully-integrated, climate-controlled farming environment built within a 
            standard shipping container. It combines IoT sensors, automated irrigation, 
            and intelligent lighting to create the perfect growing conditions.
          </p>
        </div>
        
        <div class="product-showcase">
          <div class="product-media" ref="productMedia">
            <div class="product-image-wrapper">
              <img src="https://images.unsplash.com/photo-1625246333195-78d9c38ad449?q=80&w=2070&auto=format&fit=crop" alt="Smart Greenhouse Container" />
              <div class="image-overlay"></div>
              <div class="image-glow"></div>
            </div>
            <div class="product-badge">
              <svg viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
              </svg>
              <span>Featured</span>
            </div>
          </div>
          
          <div class="product-info" ref="productInfo">
            <div class="product-tag">Premium Solution</div>
            <h3 class="product-heading">Maximize Yield, Minimize Footprint</h3>
            <p class="product-text">
              The SGC is engineered for efficiency and scalability. Grow a wide variety of 
              crops anywhere in the world, regardless of external climate conditions. Our system 
              helps you conserve water, reduce waste, and achieve predictable, high-quality 
              harvests year-round.
            </p>
            
            <div class="product-features">
              <div class="feature-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
                <span>Climate-controlled environment</span>
              </div>
              <div class="feature-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
                <span>IoT sensors & automation</span>
              </div>
              <div class="feature-item">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <polyline points="20 6 9 17 4 12"/>
                </svg>
                <span>Year-round harvesting</span>
              </div>
            </div>
            
            <div class="product-pricing">
              <div class="price-content">
                <div class="price-label">Starting at</div>
                <div class="price-amount">
                  <span class="currency">Ksh.</span>
                  <span class="amount">20,000</span>
                  <span class="period">/unit</span>
                </div>
              </div>
              <a href="#contact" class="btn btn-primary btn-large">
                <span>Request a Quote</span>
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M5 12h14M12 5l7 7-7 7"/>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="team-section" id="team" ref="teamSection">
      <div class="container">
        <div class="section-header" ref="teamHeader">
          <span class="section-tag">
            <span class="tag-dot"></span>
            The Innovators
          </span>
          <h2 class="section-title">Meet Our <span class="gradient-text">Team</span></h2>
          <p class="section-description">
            We are a cocktail of different specialists, united by a passion for 
            revolutionizing agriculture through technology.
          </p>
        </div>
        
        <div class="team-grid">
          <div class="team-card" v-for="(member, index) in teamMembers" :key="index" :ref="el => { if (el) teamCards[index] = el }">
            <div class="team-card-inner">
              <div class="member-avatar">
                <div class="avatar-ring"></div>
                <img :src="member.image" :alt="member.name" />
                <div class="avatar-glow"></div>
              </div>
              <div class="member-details">
                <h4 class="member-name">{{ member.name }}</h4>
                <p class="member-role">{{ member.role }}</p>
                <p class="member-bio">{{ member.bio }}</p>
              </div>
              <div class="member-social">
                <a href="#" class="social-icon" aria-label="LinkedIn">
                  <svg viewBox="0 0 24 24" fill="currentColor">
                    <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/>
                  </svg>
                </a>
                <a href="#" class="social-icon" aria-label="GitHub">
                  <svg viewBox="0 0 24 24" fill="currentColor">
                    <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section class="about-section" id="about" ref="aboutSection">
      <div class="container">
        <div class="section-header" ref="aboutHeader">
          <span class="section-tag">
            <span class="tag-dot"></span>
            Our Purpose
          </span>
          <h2 class="section-title">Driving Agricultural <span class="gradient-text">Innovation</span></h2>
          <p class="section-description">
            We are driven by a singular focus: to empower agricultural communities 
            through accessible and powerful technology.
          </p>
        </div>
        
        <div class="about-grid">
          <div class="about-card" ref="visionCard">
            <div class="about-card-bg"></div>
            <div class="about-icon-wrapper">
              <div class="icon-circle"></div>
              <svg class="about-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="12" cy="12" r="10"/>
                <path d="M12 6v6l4 2"/>
              </svg>
            </div>
            <h3 class="about-title">Our Vision</h3>
            <p class="about-text">
              A future where technology bridges the gap, enabling every farmer to achieve 
              optimal yields and contribute to global food security.
            </p>
            <div class="about-glow"></div>
          </div>
          
          <div class="about-card" ref="missionCard">
            <div class="about-card-bg"></div>
            <div class="about-icon-wrapper">
              <div class="icon-circle"></div>
              <svg class="about-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
              </svg>
            </div>
            <h3 class="about-title">Our Mission</h3>
            <p class="about-text">
              To design and deploy practical, data-driven solutions that solve real-world 
              agricultural challenges and improve livelihoods.
            </p>
            <div class="about-glow"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- Reviews Section -->
    <section class="reviews-section" ref="reviewsSection">
      <div class="container">
        <div class="section-header" ref="reviewsHeader">
          <span class="section-tag">
            <span class="tag-dot"></span>
            Testimonials
          </span>
          <h2 class="section-title">What Farmers <span class="gradient-text">Say</span></h2>
          <p class="section-description">
            Real stories from farmers who have transformed their yields with SGC technology
          </p>
        </div>
        
        <div class="reviews-grid">
          <div class="review-card" v-for="(review, index) in reviews" :key="index" :ref="el => { if (el) reviewCards[index] = el }">
            <div class="review-header">
              <img :src="review.image" :alt="review.name" class="reviewer-avatar" />
              <div class="reviewer-info">
                <h4 class="reviewer-name">{{ review.name }}</h4>
                <p class="reviewer-location">{{ review.location }}</p>
              </div>
            </div>
            <div class="review-rating">
              <svg v-for="n in 5" :key="n" class="leaf-icon" :class="{ filled: n <= review.rating }" viewBox="0 0 24 24" fill="currentColor">
                <path d="M17,8C8,10 5.9,16.17 3.82,21.34L5.71,22L6.66,19.7C7.14,19.87 7.64,20 8,20C19,20 22,3 22,3C21,5 14,5.25 9,6.25C4,7.25 2,11.5 2,13.5C2,15.5 3.75,17.25 3.75,17.25C7,8 17,8 17,8Z"/>
              </svg>
            </div>
            <p class="review-text">"{{ review.text }}"</p>
            <div class="review-stats">
              <div class="stat-badge">
                <span class="stat-icon">📈</span>
                <span>{{ review.yieldIncrease }}</span>
              </div>
              <div class="stat-badge">
                <span class="stat-icon">💧</span>
                <span>{{ review.waterSaved }}</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- App Download CTA Section -->
    <section class="app-cta-section" ref="appCtaSection">
      <div class="container">
        <div class="app-cta-wrapper">
          <div class="app-cta-content" ref="appCtaContent">
            <div class="cta-badge">
              <span class="badge-dot"></span>
              Download Now
            </div>
            <h2 class="app-cta-title">
              <span class="gradient-text">Smart Farming</span><br>
              In Your Pocket
            </h2>
            <p class="app-cta-desc">
              Monitor your greenhouse, control irrigation, and get AI-powered insights—all from your smartphone. Join thousands of farmers using SGC mobile app.
            </p>
            <div class="app-features">
              <div class="app-feature" v-for="(feature, index) in appFeatures" :key="index">
                <div class="feature-check">
                  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3">
                    <polyline points="20 6 9 17 4 12"/>
                  </svg>
                </div>
                <span>{{ feature }}</span>
              </div>
            </div>
            <a :href="playStoreLink" target="_blank" class="play-store-btn" ref="playStoreBtn">
              <svg viewBox="0 0 24 24" class="play-icon">
                <path fill="currentColor" d="M3,20.5V3.5C3,2.91 3.34,2.39 3.84,2.15L13.69,12L3.84,21.85C3.34,21.6 3,21.09 3,20.5M16.81,15.12L6.05,21.34L14.54,12.85L16.81,15.12M20.16,10.81C20.5,11.08 20.75,11.5 20.75,12C20.75,12.5 20.53,12.9 20.18,13.18L17.89,14.5L15.39,12L17.89,9.5L20.16,10.81M6.05,2.66L16.81,8.88L14.54,11.15L6.05,2.66Z"/>
              </svg>
              <div class="btn-content">
                <span class="btn-subtitle">GET IT ON</span>
                <span class="btn-title">Google Play</span>
              </div>
            </a>
          </div>
          <div class="app-cta-visual" ref="appCtaVisual">
            <div class="phone-mockup">
              <div class="phone-frame">
                <div class="phone-notch"></div>
                <div class="phone-screen">
                  <img src="/src/images/screenshot-SGC-app.jpeg" alt="SGC Mobile App" class="app-screenshot">
                </div>
              </div>
              <div class="floating-stat stat-1">
                <span class="stat-emoji">🌡️</span>
                <span class="stat-text">24°C</span>
              </div>
              <div class="floating-stat stat-2">
                <span class="stat-emoji">💧</span>
                <span class="stat-text">78%</span>
              </div>
              <div class="floating-stat stat-3">
                <span class="stat-emoji">🌱</span>
                <span class="stat-text">+125%</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact" ref="contactSection">
      <div class="container">
        <div class="contact-wrapper">
          <div class="contact-left" ref="contactLeft">
            <div class="contact-header">
              <span class="section-tag">
                <span class="tag-dot"></span>
                Get In Touch
              </span>
              <h2 class="contact-title">Let's <span class="gradient-text">Grow</span> Together</h2>
              <p class="contact-desc">Ready to transform your farming? Let's talk about how SGC can help you achieve optimal yields.</p>
            </div>
            
            <div class="contact-info">
              <div class="contact-item">
                <div class="contact-icon-wrapper">
                  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/>
                    <circle cx="12" cy="10" r="3"/>
                  </svg>
                </div>
                <div class="contact-text">
                  <div class="contact-label">Address</div>
                  <div class="contact-value">123 AgriTech Avenue, Nairobi, Kenya</div>
                </div>
              </div>
              
              <div class="contact-item">
                <div class="contact-icon-wrapper">
                  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
                  </svg>
                </div>
                <div class="contact-text">
                  <div class="contact-label">Phone</div>
                  <div class="contact-value"><a href="tel:+254712345678">+254 712 345 678</a></div>
                </div>
              </div>
              
              <div class="contact-item">
                <div class="contact-icon-wrapper">
                  <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
                    <polyline points="22,6 12,13 2,6"/>
                  </svg>
                </div>
                <div class="contact-text">
                  <div class="contact-label">Email</div>
                  <div class="contact-value"><a href="mailto:info@farmershelp.co.ke">info@farmershelp.co.ke</a></div>
                </div>
              </div>
            </div>
            
            <div class="social-section">
              <div class="social-title">Follow Us</div>
              <div class="social-links">
                <a href="#" class="social-link">
                  <svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
                </a>
                <a href="#" class="social-link">
                  <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
                </a>
              </div>
            </div>
          </div>
          
          <div class="contact-right" ref="contactRight">
            <form class="contact-form" @submit.prevent="submitContact">
              <div class="form-grid">
                <div class="form-group">
                  <label>Full Name</label>
                  <input type="text" placeholder="John Doe" v-model="contactForm.name" required />
                </div>
                <div class="form-group">
                  <label>Email Address</label>
                  <input type="email" placeholder="john@example.com" v-model="contactForm.email" required />
                </div>
              </div>
              <div class="form-group">
                <label>Your Message</label>
                <textarea placeholder="Tell us about your project..." v-model="contactForm.message" rows="6" required></textarea>
              </div>
              <button type="submit" class="btn btn-primary btn-large btn-block">
                <span>Send Message</span>
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M22 2L11 13M22 2l-7 20-4-9-9-4 20-7z"/>
                </svg>
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer" ref="footer">
      <div class="container">
        <div class="footer-main">
          <div class="footer-brand">
            <div class="footer-logo">
              <div class="logo-icon">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                  <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
                  <path d="M12 8v5m0 0l-3-3m3 3l3-3"/>
                </svg>
              </div>
              <span class="logo-text">SGC</span>
            </div>
            <p class="footer-tagline">Grow better with our technology driven solutions.</p>
            <div class="footer-social">
              <a href="#" class="footer-social-link">
                <svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
              </a>
              <a href="#" class="footer-social-link">
                <svg viewBox="0 0 24 24" fill="currentColor"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
              </a>
            </div>
          </div>
          
          <div class="footer-links-section">
            <h4 class="footer-heading">Quick Links</h4>
            <ul class="footer-links">
              <li><a href="#tech">Tech Insights</a></li>
              <li><a href="#products">Products</a></li>
              <li><a href="#team">Our Team</a></li>
              <li><a href="#about">About Us</a></li>
            </ul>
          </div>
          
          <div class="footer-contact-section">
            <h4 class="footer-heading">Contact</h4>
            <ul class="footer-contact-list">
              <li>123 AgriTech Avenue</li>
              <li>Nairobi, Kenya</li>
              <li><a href="tel:+254712345678">+254 712 345 678</a></li>
              <li><a href="mailto:info@farmershelp.co.ke">info@farmershelp.co.ke</a></li>
            </ul>
          </div>
        </div>
        
        <div class="footer-bottom">
          <p class="copyright">© 2026 SGC. All rights reserved.</p>
          <div class="footer-bottom-links">
            <a href="#">Privacy Policy</a>
            <span class="separator">•</span>
            <a href="#">Terms of Service</a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

// Refs
const navbar = ref(null)
const logo = ref(null)
const navLinks = ref(null)
const menuBtn = ref(null)
const heroSection = ref(null)
const heroBadge = ref(null)
const heroTitle = ref(null)
const titleLine1 = ref(null)
const titleLine2 = ref(null)
const heroDesc = ref(null)
const heroActions = ref(null)
const heroStats = ref(null)
const heroVisual = ref(null)
const visualCard = ref(null)
const floatingBadge1 = ref(null)
const floatingBadge2 = ref(null)
const orb1 = ref(null)
const orb2 = ref(null)
const orb3 = ref(null)
const scrollIndicator = ref(null)
const techSection = ref(null)
const techHeader = ref(null)
const techCards = ref([])
const newsletterSection = ref(null)
const productsSection = ref(null)
const productsHeader = ref(null)
const productMedia = ref(null)
const productInfo = ref(null)
const teamSection = ref(null)
const teamHeader = ref(null)
const teamCards = ref([])
const reviewsSection = ref(null)
const reviewsHeader = ref(null)
const reviewCards = ref([])
const appCtaSection = ref(null)
const appCtaContent = ref(null)
const appCtaVisual = ref(null)
const playStoreBtn = ref(null)
const aboutSection = ref(null)
const aboutHeader = ref(null)
const visionCard = ref(null)
const missionCard = ref(null)
const contactSection = ref(null)
const contactLeft = ref(null)
const contactRight = ref(null)
const footer = ref(null)

// Data
const mobileMenuOpen = ref(false)
const email = ref('')
const contactForm = ref({
  name: '',
  email: '',
  message: ''
})

const techFeatures = [
  {
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="2"/><path d="M16.24 7.76a6 6 0 0 1 0 8.49m-8.48-.01a6 6 0 0 1 0-8.49m11.31-2.82a10 10 0 0 1 0 14.14m-14.14 0a10 10 0 0 1 0-14.14"/></svg>',
    title: 'IoT-Based Smart Farming',
    description: 'Leverage the Internet of Things (IoT) to monitor your farm in real-time. Sensors collect data on soil moisture, temperature, and crop health, enabling precise and automated responses.'
  },
  {
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2.69l5.66 5.66a8 8 0 1 1-11.31 0z"/></svg>',
    title: 'Precision Irrigation',
    description: 'Optimize water usage by up to 50%. Our systems analyze soil and weather data to deliver water exactly when and where it\'s needed, preventing waste and improving crop yield.'
  },
  {
    icon: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21.21 15.89A10 10 0 1 1 8 2.83M22 12A10 10 0 0 0 12 2v10z"/></svg>',
    title: 'Data-Driven Decisions',
    description: 'Turn raw data into actionable insights. Our platform provides analytics and predictions to help you make informed decisions about planting, harvesting, and resource management.'
  }
]

const reviews = [
  {
    name: 'John Kamau',
    location: 'Kiambu County',
    image: 'https://images.unsplash.com/photo-1566492031773-4f4e44671857?q=80&w=400&auto=format&fit=crop',
    rating: 5,
    text: 'SGC transformed my 2-acre farm. The smart irrigation system cut my water usage in half while my tomato yields doubled. Best investment I\'ve ever made!',
    yieldIncrease: '+120% yield',
    waterSaved: '50% less water'
  },
  {
    name: 'Mary Wanjiku',
    location: 'Nyeri',
    image: 'https://images.unsplash.com/photo-1487412720507-e7ab37603c6f?q=80&w=400&auto=format&fit=crop',
    rating: 5,
    text: 'The IoT sensors detect problems before I even notice them. I saved an entire crop from disease thanks to the early warning system. Amazing technology!',
    yieldIncrease: '+85% yield',
    waterSaved: '45% less water'
  },
  {
    name: 'Peter Ochieng',
    location: 'Nakuru',
    image: 'https://images.unsplash.com/photo-1463453091185-61582044d556?q=80&w=400&auto=format&fit=crop',
    rating: 5,
    text: 'From struggling farmer to profitable business owner. The data insights help me plan better, and the automation gives me time to expand. Life-changing!',
    yieldIncrease: '+95% yield',
    waterSaved: '60% less water'
  },
  {
    name: 'Grace Akinyi',
    location: 'Kisumu',
    image: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?q=80&w=400&auto=format&fit=crop',
    rating: 5,
    text: 'Running my greenhouse is now so easy with SGC. I can monitor everything from my phone and the smart climate control ensures perfect conditions 24/7.',
    yieldIncrease: '+110% yield',
    waterSaved: '55% less water'
  },
  {
    name: 'David Mwangi',
    location: 'Meru',
    image: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=400&auto=format&fit=crop',
    rating: 4,
    text: 'The precision farming tools are incredible. My coffee plants have never been healthier, and the yield quality has impressed even the most demanding buyers.',
    yieldIncrease: '+75% yield',
    waterSaved: '40% less water'
  },
  {
    name: 'Sarah Njeri',
    location: 'Thika',
    image: 'https://images.unsplash.com/photo-1544005313-94ddf0286df2?q=80&w=400&auto=format&fit=crop',
    rating: 5,
    text: 'Best decision for my flower farm. The automated systems maintain perfect humidity and temperature, resulting in premium quality flowers year-round.',
    yieldIncrease: '+130% yield',
    waterSaved: '65% less water'
  }
]

const appFeatures = [
  'Real-time greenhouse monitoring',
  'Remote irrigation control',
  'AI-powered crop recommendations',
  'Weather alerts & forecasts'
]

const playStoreLink = 'https://play.google.com/store/apps'

const teamMembers = [
  {
    name: 'Denis Muli',
    role: 'Team Lead & IoT Developer',
    bio: 'Denis leads the team with a passion for AgriTech and builds the smart hardware that powers our solutions.',
    image: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?q=80&w=400&auto=format&fit=crop'
  },
  {
    name: 'Arnold Njeru',
    role: 'Analyst & Graphics Designer',
    bio: 'Arnold translates complex data into beautiful, intuitive designs, ensuring our platform is both powerful and user-friendly.',
    image: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?q=80&w=400&auto=format&fit=crop'
  },
  {
    name: 'Brian Mutune',
    role: 'Software Developer',
    bio: 'Brian is a core developer, crafting the robust backend and seamless user interfaces of our applications.',
    image: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?q=80&w=400&auto=format&fit=crop'
  },
  {
    name: 'Marco',
    role: 'Software Developer',
    bio: 'Marco specializes in mobile development, bringing SGC\'s capabilities to the field in the palm of your hand.',
    image: 'https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?q=80&w=400&auto=format&fit=crop'
  },
  {
    name: 'Nyaga Robinson',
    role: 'Software Developer',
    bio: 'Nyaga focuses on data pipelines and machine learning, turning farm data into predictive, actionable insights.',
    image: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?q=80&w=400&auto=format&fit=crop'
  }
]

// Methods
const toggleMobileMenu = () => {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

const closeMobileMenu = () => {
  mobileMenuOpen.value = false
}

const subscribeNewsletter = () => {
  alert(`Thank you for subscribing with ${email.value}!`)
  email.value = ''
}

const submitContact = () => {
  alert(`Thank you ${contactForm.value.name}! We'll get back to you soon.`)
  contactForm.value = { name: '', email: '', message: '' }
}

// GSAP Animations
let ctx

onMounted(() => {
  ctx = gsap.context(() => {
    // Navbar entrance animation
    gsap.from(navbar.value, {
      y: -100,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })
    
    gsap.from('.nav-link', {
      y: -20,
      opacity: 0,
      duration: 0.6,
      stagger: 0.1,
      delay: 0.5,
      ease: 'power2.out'
    })

    // Gradient orbs floating animation
    gsap.to(orb1.value, {
      x: 30,
      y: -40,
      scale: 1.1,
      duration: 6,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })
    
    gsap.to(orb2.value, {
      x: -40,
      y: 30,
      scale: 0.9,
      duration: 7,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })
    
    gsap.to(orb3.value, {
      x: 20,
      y: 50,
      scale: 1.05,
      duration: 8,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })

    // Hero section animations
    const heroTl = gsap.timeline({ delay: 0.3 })
    
    heroTl
      .from(heroBadge.value, {
        y: 30,
        opacity: 0,
        duration: 0.6,
        ease: 'power2.out'
      })
      .from(titleLine1.value, {
        y: 100,
        opacity: 0,
        duration: 0.8,
        ease: 'power3.out'
      }, '-=0.2')
      .from(titleLine2.value, {
        y: 100,
        opacity: 0,
        duration: 0.8,
        ease: 'power3.out'
      }, '-=0.6')
      .from(heroDesc.value, {
        y: 30,
        opacity: 0,
        duration: 0.6,
        ease: 'power2.out'
      }, '-=0.3')
      .from(heroActions.value.children, {
        y: 20,
        opacity: 0,
        duration: 0.5,
        stagger: 0.1,
        ease: 'power2.out'
      }, '-=0.2')
      .from(heroStats.value, {
        y: 30,
        opacity: 0,
        duration: 0.6,
        ease: 'power2.out'
      }, '-=0.3')
      .from(visualCard.value, {
        x: 100,
        opacity: 0,
        scale: 0.9,
        duration: 1,
        ease: 'power3.out'
      }, '-=1')
      .from(floatingBadge1.value, {
        scale: 0,
        opacity: 0,
        duration: 0.5,
        ease: 'back.out(1.7)'
      }, '-=0.3')
      .from(floatingBadge2.value, {
        scale: 0,
        opacity: 0,
        duration: 0.5,
        ease: 'back.out(1.7)'
      }, '-=0.2')

    // Floating badges continuous animation
    gsap.to(floatingBadge1.value, {
      y: -15,
      duration: 2.5,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })
    
    gsap.to(floatingBadge2.value, {
      y: 15,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })

    // Scroll indicator animation
    gsap.from(scrollIndicator.value, {
      opacity: 0,
      y: -20,
      duration: 0.8,
      delay: 2,
      ease: 'power2.out'
    })
    
    gsap.to('.scroll-line', {
      scaleY: 1.5,
      duration: 1,
      repeat: -1,
      yoyo: true,
      ease: 'power1.inOut'
    })

    // Tech Section animations
    gsap.from(techHeader.value, {
      scrollTrigger: {
        trigger: techSection.value,
        start: 'top 75%'
      },
      y: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    techCards.value.forEach((card, index) => {
      gsap.from(card, {
        scrollTrigger: {
          trigger: card,
          start: 'top 85%'
        },
        y: 80,
        opacity: 0,
        scale: 0.9,
        duration: 0.8,
        delay: index * 0.15,
        ease: 'power3.out'
      })
      
      // Card hover effect
      card.addEventListener('mouseenter', () => {
        gsap.to(card, {
          y: -10,
          duration: 0.3,
          ease: 'power2.out'
        })
      })
      
      card.addEventListener('mouseleave', () => {
        gsap.to(card, {
          y: 0,
          duration: 0.3,
          ease: 'power2.out'
        })
      })
    })

    // Newsletter section
    gsap.from('.newsletter-card', {
      scrollTrigger: {
        trigger: newsletterSection.value,
        start: 'top 75%'
      },
      scale: 0.95,
      opacity: 0,
      y: 40,
      duration: 0.8,
      ease: 'power3.out'
    })

    // Products section
    gsap.from(productsHeader.value, {
      scrollTrigger: {
        trigger: productsSection.value,
        start: 'top 75%'
      },
      y: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    gsap.from(productMedia.value, {
      scrollTrigger: {
        trigger: '.product-showcase',
        start: 'top 70%'
      },
      x: -80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })

    gsap.from(productInfo.value, {
      scrollTrigger: {
        trigger: '.product-showcase',
        start: 'top 70%'
      },
      x: 80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })
    
    gsap.from('.feature-item', {
      scrollTrigger: {
        trigger: '.product-features',
        start: 'top 80%'
      },
      x: -30,
      opacity: 0,
      duration: 0.6,
      stagger: 0.1,
      ease: 'power2.out'
    })

    // Team section
    gsap.from(teamHeader.value, {
      scrollTrigger: {
        trigger: teamSection.value,
        start: 'top 75%'
      },
      y: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    teamCards.value.forEach((card, index) => {
      if (card) {
        gsap.from(card, {
          scrollTrigger: {
            trigger: card,
            start: 'top 85%'
          },
          y: 60,
          opacity: 0,
          rotationY: 15,
          duration: 0.8,
          delay: index * 0.1,
          ease: 'power3.out'
        })
        
        // Card hover animation
        card.addEventListener('mouseenter', () => {
          gsap.to(card.querySelector('.member-avatar'), {
            scale: 1.1,
            duration: 0.3,
            ease: 'power2.out'
          })
        })
        
        card.addEventListener('mouseleave', () => {
          gsap.to(card.querySelector('.member-avatar'), {
            scale: 1,
            duration: 0.3,
            ease: 'power2.out'
          })
        })
      }
    })

    // About section
    gsap.from(aboutHeader.value, {
      scrollTrigger: {
        trigger: aboutSection.value,
        start: 'top 75%'
      },
      y: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    gsap.from(visionCard.value, {
      scrollTrigger: {
        trigger: '.about-grid',
        start: 'top 80%'
      },
      x: -60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    gsap.from(missionCard.value, {
      scrollTrigger: {
        trigger: '.about-grid',
        start: 'top 80%'
      },
      x: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    // Reviews section
    gsap.from(reviewsHeader.value, {
      scrollTrigger: {
        trigger: reviewsSection.value,
        start: 'top 75%'
      },
      y: 60,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    })

    reviewCards.value.forEach((card, index) => {
      if (card) {
        gsap.from(card, {
          scrollTrigger: {
            trigger: card,
            start: 'top 85%'
          },
          y: 60,
          opacity: 0,
          rotationY: 10,
          duration: 0.8,
          delay: index * 0.15,
          ease: 'power3.out'
        })
      }
    })

    // App CTA section
    gsap.from(appCtaContent.value, {
      scrollTrigger: {
        trigger: appCtaSection.value,
        start: 'top 70%'
      },
      x: -80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })

    gsap.from(appCtaVisual.value, {
      scrollTrigger: {
        trigger: appCtaSection.value,
        start: 'top 70%'
      },
      x: 80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })

    // Floating stats animation
    gsap.to('.floating-stat.stat-1', {
      y: -15,
      duration: 2.5,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut'
    })

    gsap.to('.floating-stat.stat-2', {
      y: -20,
      duration: 3,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut',
      delay: 0.5
    })

    gsap.to('.floating-stat.stat-3', {
      y: -18,
      duration: 2.8,
      repeat: -1,
      yoyo: true,
      ease: 'sine.inOut',
      delay: 1
    })

    // Contact section
    gsap.from(contactLeft.value, {
      scrollTrigger: {
        trigger: contactSection.value,
        start: 'top 70%'
      },
      x: -80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })

    gsap.from(contactRight.value, {
      scrollTrigger: {
        trigger: contactSection.value,
        start: 'top 70%'
      },
      x: 80,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })
    
    gsap.from('.contact-item', {
      scrollTrigger: {
        trigger: '.contact-info',
        start: 'top 80%'
      },
      y: 20,
      opacity: 0,
      duration: 0.6,
      stagger: 0.1,
      ease: 'power2.out'
    })

    // Footer
    gsap.from('.footer-main > div', {
      scrollTrigger: {
        trigger: footer.value,
        start: 'top 85%'
      },
      y: 40,
      opacity: 0,
      duration: 0.6,
      stagger: 0.15,
      ease: 'power3.out'
    })

    // Navbar scroll effect
    ScrollTrigger.create({
      start: 'top -80',
      onUpdate: (self) => {
        if (self.direction === 1 && self.scroll() > 80) {
          navbar.value.classList.add('scrolled')
        }
        if (self.scroll() < 80) {
          navbar.value.classList.remove('scrolled')
        }
      }
    })
  })
})

onUnmounted(() => {
  if (ctx) {
    ctx.revert()
  }
})
</script>

<style scoped>
@import './LandingPage-styles.css';
</style>
