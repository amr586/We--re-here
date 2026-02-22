<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>شركة البرمجة - حلول برمجية متكاملة</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cairo', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 1.5rem;
            font-weight: bold;
            color: #2563eb;
            cursor: pointer;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 0.5rem;
        }

        .nav-links a {
            color: #4b5563;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            transition: all 0.3s;
        }

        .nav-links a:hover {
            background: #dbeafe;
            color: #2563eb;
        }

        .menu-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            margin-top: 64px;
            height: 600px;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), 
                        url('https://images.unsplash.com/photo-1759884247387-a5d791ffb2bc?w=1200') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            padding: 2rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            font-weight: 900;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
        }

        .btn {
            background: #2563eb;
            color: white;
            padding: 1rem 2rem;
            border: none;
            border-radius: 0.5rem;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            display: inline-block;
        }

        .btn:hover {
            background: #1d4ed8;
            transform: translateY(-2px);
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 900;
        }

        .section-title p {
            font-size: 1.2rem;
            color: #6b7280;
        }

        /* Grid */
        .grid {
            display: grid;
            gap: 2rem;
        }

        .grid-2 {
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .grid-3 {
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        }

        .grid-4 {
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        }

        /* Cards */
        .card {
            background: white;
            border-radius: 1rem;
            padding: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: all 0.3s;
            text-align: center;
        }

        .card:hover {
            box-shadow: 0 10px 20px rgba(0,0,0,0.15);
            transform: translateY(-5px);
        }

        .icon-box {
            width: 4rem;
            height: 4rem;
            border-radius: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            font-size: 2rem;
        }

        .icon-box.blue { background: #dbeafe; color: #2563eb; }
        .icon-box.green { background: #d1fae5; color: #059669; }
        .icon-box.purple { background: #e9d5ff; color: #9333ea; }
        .icon-box.orange { background: #fed7aa; color: #ea580c; }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .card p {
            color: #6b7280;
            line-height: 1.8;
        }

        /* Pricing Cards */
        .pricing-card {
            background: white;
            border-radius: 1rem;
            padding: 2rem;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: all 0.3s;
            position: relative;
        }

        .pricing-card.featured {
            border: 3px solid;
            transform: scale(1.05);
        }

        .pricing-card.featured.blue { border-color: #2563eb; }
        .pricing-card.featured.green { border-color: #059669; }
        .pricing-card.featured.purple { border-color: #9333ea; }
        .pricing-card.featured.orange { border-color: #ea580c; }

        .badge {
            background: #2563eb;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            margin-bottom: 1rem;
            display: inline-block;
        }

        .badge.green { background: #059669; }
        .badge.purple { background: #9333ea; }
        .badge.orange { background: #ea580c; }

        .price {
            font-size: 3rem;
            font-weight: 900;
            margin: 1rem 0;
        }

        .price.blue { color: #2563eb; }
        .price.green { color: #059669; }
        .price.purple { color: #9333ea; }
        .price.orange { color: #ea580c; }

        .features-list {
            list-style: none;
            margin: 2rem 0;
            text-align: right;
        }

        .features-list li {
            padding: 0.5rem 0;
            display: flex;
            align-items: start;
            gap: 0.5rem;
        }

        .features-list li::before {
            content: "✓";
            color: #10b981;
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Backgrounds */
        .bg-gray { background: #f9fafb; }
        .bg-blue { background: linear-gradient(to bottom right, #dbeafe, white); }
        .bg-green { background: linear-gradient(to bottom right, #d1fae5, white); }
        .bg-purple { background: linear-gradient(to bottom right, #e9d5ff, white); }
        .bg-orange { background: linear-gradient(to bottom right, #fed7aa, white); }
        .bg-dark { background: #111827; color: white; }

        /* Features Grid */
        .feature-item {
            display: flex;
            align-items: start;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .checkmark {
            color: #10b981;
            font-size: 1.5rem;
            flex-shrink: 0;
        }

        /* Image Section */
        .image-section {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .image-box {
            height: 400px;
            border-radius: 1rem;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .image-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background: #1f2937;
            padding: 2rem;
            border-radius: 1rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #4b5563;
            border-radius: 0.5rem;
            background: #374151;
            color: white;
            font-family: 'Cairo', sans-serif;
        }

        .form-group textarea {
            resize: vertical;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        /* Contact Info */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .contact-item {
            text-align: center;
        }

        .contact-icon {
            width: 4rem;
            height: 4rem;
            background: #2563eb;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            font-size: 1.5rem;
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-links a {
            width: 3rem;
            height: 3rem;
            background: #1f2937;
            border-radius: 0.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s;
            font-size: 1.5rem;
        }

        .social-links a:hover {
            background: #2563eb;
            transform: translateY(-3px);
        }

        /* Footer */
        footer {
            background: #000;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        /* Scroll to Top Button */
        .scroll-top {
            position: fixed;
            bottom: 2rem;
            left: 2rem;
            width: 3rem;
            height: 3rem;
            background: #2563eb;
            color: white;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: none;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            transition: all 0.3s;
            z-index: 999;
        }

        .scroll-top:hover {
            background: #1d4ed8;
            transform: translateY(-3px);
        }

        .scroll-top.show {
            display: flex;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                position: absolute;
                top: 100%;
                right: 0;
                left: 0;
                background: white;
                flex-direction: column;
                padding: 1rem;
                box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            }

            .nav-links.active {
                display: flex;
            }

            .menu-toggle {
                display: block;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .image-section {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }

            .pricing-card.featured {
                transform: scale(1);
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo" onclick="scrollToSection('home')">
                <span>💻</span>
                <span>شركة البرمجة</span>
            </div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home" onclick="scrollToSection('home')">الرئيسية</a></li>
                <li><a href="#services" onclick="scrollToSection('services')">الخدمات</a></li>
                <li><a href="#websites" onclick="scrollToSection('websites')">المواقع</a></li>
                <li><a href="#ecommerce" onclick="scrollToSection('ecommerce')">المتاجر</a></li>
                <li><a href="#mobile" onclick="scrollToSection('mobile')">التطبيقات</a></li>
                <li><a href="#erp" onclick="scrollToSection('erp')">ERP</a></li>
                <li><a href="#contact" onclick="scrollToSection('contact')">تواصل معنا</a></li>
            </ul>
            <button class="menu-toggle" onclick="toggleMenu()">☰</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div>
            <h1>حلول برمجية متكاملة لنجاح أعمالك</h1>
            <p>نصمم ونطور مواقع، متاجر، تطبيقات، وأنظمة ERP احترافية</p>
            <a href="#services" class="btn" onclick="scrollToSection('services')">اكتشف خدماتنا</a>
        </div>
    </section>

    <!-- Services Overview -->
    <section id="services" class="bg-gray">
        <div class="container">
            <div class="section-title">
                <h2>خدماتنا</h2>
                <p>نقدم مجموعة متكاملة من الحلول البرمجية</p>
            </div>

            <div class="grid grid-4">
                <div class="card" onclick="scrollToSection('websites')">
                    <div class="icon-box blue">🌐</div>
                    <h3>المواقع الإلكترونية</h3>
                    <p>تصميم وتطوير مواقع إلكترونية احترافية ومتجاوبة مع جميع الأجهزة</p>
                </div>

                <div class="card" onclick="scrollToSection('ecommerce')">
                    <div class="icon-box green">🛒</div>
                    <h3>المتاجر الإلكترونية</h3>
                    <p>إنشاء متاجر إلكترونية متكاملة مع أنظمة الدفع وإدارة المخزون</p>
                </div>

                <div class="card" onclick="scrollToSection('mobile')">
                    <div class="icon-box purple">📱</div>
                    <h3>تطبيقات الموبايل</h3>
                    <p>تطوير تطبيقات موبايل احترافية لأنظمة iOS و Android</p>
                </div>

                <div class="card" onclick="scrollToSection('erp')">
                    <div class="icon-box orange">💾</div>
                    <h3>أنظمة ERP</h3>
                    <p>حلول متكاملة لإدارة موارد الشركات والمؤسسات</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Why Choose Us -->
    <section class="container">
        <div class="image-section">
            <div>
                <h2 style="font-size: 2.5rem; margin-bottom: 1.5rem; font-weight: 900;">لماذا تختارنا؟</h2>
                <p style="font-size: 1.1rem; color: #6b7280; margin-bottom: 2rem;">
                    نحن نقدم أفضل الحلول البرمجية بأعلى معايير الجودة والاحترافية
                </p>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;">
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>فريق متخصص من المطورين والمصممين</span>
                    </div>
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>تقنيات حديثة ومتطورة</span>
                    </div>
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>دعم فني على مدار الساعة</span>
                    </div>
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>أسعار تنافسية ومناسبة</span>
                    </div>
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>التسليم في الوقت المحدد</span>
                    </div>
                    <div class="feature-item">
                        <span class="checkmark">✓</span>
                        <span>ضمان الجودة والأداء</span>
                    </div>
                </div>
            </div>
            <div class="image-box">
                <img src="https://images.unsplash.com/photo-1616386261012-8a328c89d5b6?w=800" alt="Technology Workspace">
            </div>
        </div>
    </section>

    <!-- Websites Section -->
    <section id="websites" class="bg-blue">
        <div class="container">
            <div class="section-title">
                <div class="icon-box blue" style="margin: 0 auto 1rem;">🌐</div>
                <h2>تطوير المواقع الإلكترونية</h2>
                <p>نصمم مواقع إلكترونية احترافية تعكس هوية علامتك التجارية</p>
            </div>

            <div class="grid grid-4" style="margin-bottom: 3rem;">
                <div class="card">
                    <div class="icon-box blue">💻</div>
                    <h3>تطوير احترافي</h3>
                    <p>باستخدام أحدث التقنيات والأطر البرمجية</p>
                </div>
                <div class="card">
                    <div class="icon-box blue">🎨</div>
                    <h3>تصميم مبتكر</h3>
                    <p>واجهات جذابة وسهلة الاستخدام</p>
                </div>
                <div class="card">
                    <div class="icon-box blue">⚡</div>
                    <h3>أداء سريع</h3>
                    <p>تحسين الأداء وسرعة التحميل</p>
                </div>
                <div class="card">
                    <div class="icon-box blue">🛡️</div>
                    <h3>أمان عالي</h3>
                    <p>حماية كاملة للبيانات والمعلومات</p>
                </div>
            </div>

            <div class="grid grid-3">
                <div class="pricing-card">
                    <h3>الباقة الأساسية</h3>
                    <div class="price blue">5,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>موقع من 5 صفحات</li>
                        <li>تصميم متجاوب</li>
                        <li>استضافة لمدة سنة</li>
                        <li>دومين مجاني</li>
                        <li>دعم فني لمدة 3 أشهر</li>
                    </ul>
                    <button class="btn">اطلب الآن</button>
                </div>

                <div class="pricing-card featured blue">
                    <div class="badge">الأكثر طلباً</div>
                    <h3>الباقة المتقدمة</h3>
                    <div class="price blue">10,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>موقع من 10 صفحات</li>
                        <li>تصميم متجاوب</li>
                        <li>استضافة لمدة سنة</li>
                        <li>دومين مجاني</li>
                        <li>لوحة تحكم إدارية</li>
                        <li>تحسين محركات البحث SEO</li>
                        <li>دعم فني لمدة 6 أشهر</li>
                    </ul>
                    <button class="btn">اطلب الآن</button>
                </div>

                <div class="pricing-card">
                    <h3>الباقة الشاملة</h3>
                    <div class="price blue">20,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>موقع غير محدود الصفحات</li>
                        <li>تصميم متجاوب ومخصص</li>
                        <li>استضافة لمدة سنتين</li>
                        <li>دومين مجاني</li>
                        <li>لوحة تحكم متقدمة</li>
                        <li>تحسين محركات البحث SEO</li>
                        <li>تكامل مع أنظمة خارجية</li>
                        <li>دعم فني لمدة سنة</li>
                    </ul>
                    <button class="btn">اطلب الآن</button>
                </div>
            </div>
        </div>
    </section>

    <!-- E-commerce Section -->
    <section id="ecommerce" class="bg-green">
        <div class="container">
            <div class="section-title">
                <div class="icon-box green" style="margin: 0 auto 1rem;">🛒</div>
                <h2>المتاجر الإلكترونية</h2>
                <p>أطلق متجرك الإلكتروني وابدأ البيع أونلاين بكل سهولة</p>
            </div>

            <div class="grid grid-4" style="margin-bottom: 3rem;">
                <div class="card">
                    <div class="icon-box green">🛍️</div>
                    <h3>إدارة المنتجات</h3>
                    <p>نظام شامل لإدارة المنتجات والفئات</p>
                </div>
                <div class="card">
                    <div class="icon-box green">💳</div>
                    <h3>بوابات الدفع</h3>
                    <p>تكامل مع جميع بوابات الدفع الإلكتروني</p>
                </div>
                <div class="card">
                    <div class="icon-box green">📊</div>
                    <h3>تقارير مفصلة</h3>
                    <p>لوحة تحكم بتقارير المبيعات والإحصائيات</p>
                </div>
                <div class="card">
                    <div class="icon-box green">🚚</div>
                    <h3>إدارة الشحن</h3>
                    <p>تكامل مع شركات الشحن المحلية والدولية</p>
                </div>
            </div>

            <div class="grid grid-3">
                <div class="pricing-card">
                    <h3>متجر صغير</h3>
                    <div class="price green">15,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>حتى 100 منتج</li>
                        <li>تصميم متجاوب</li>
                        <li>لوحة تحكم إدارية</li>
                        <li>بوابة دفع واحدة</li>
                        <li>استضافة لمدة سنة</li>
                        <li>دعم فني لمدة 3 أشهر</li>
                    </ul>
                    <button class="btn" style="background: #059669;">اطلب الآن</button>
                </div>

                <div class="pricing-card featured green">
                    <div class="badge green">الأكثر طلباً</div>
                    <h3>متجر متوسط</h3>
                    <div class="price green">30,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>حتى 500 منتج</li>
                        <li>تصميم متجاوب ومخصص</li>
                        <li>لوحة تحكم متقدمة</li>
                        <li>عدة بوابات دفع</li>
                        <li>نظام إدارة المخزون</li>
                        <li>تكامل مع شركات الشحن</li>
                        <li>استضافة لمدة سنة</li>
                        <li>دعم فني لمدة 6 أشهر</li>
                    </ul>
                    <button class="btn" style="background: #059669;">اطلب الآن</button>
                </div>

                <div class="pricing-card">
                    <h3>متجر شامل</h3>
                    <div class="price green">50,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>منتجات غير محدودة</li>
                        <li>تصميم مخصص بالكامل</li>
                        <li>لوحة تحكم احترافية</li>
                        <li>جميع بوابات الدفع</li>
                        <li>نظام إدارة متقدم</li>
                        <li>تكامل كامل مع الشحن</li>
                        <li>نظام ولاء العملاء</li>
                        <li>تطبيق موبايل مجاني</li>
                        <li>استضافة لمدة سنتين</li>
                        <li>دعم فني لمدة سنة</li>
                    </ul>
                    <button class="btn" style="background: #059669;">اطلب الآن</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Mobile Apps Section -->
    <section id="mobile" class="bg-purple">
        <div class="container">
            <div class="section-title">
                <div class="icon-box purple" style="margin: 0 auto 1rem;">📱</div>
                <h2>تطبيقات الموبايل</h2>
                <p>نطور تطبيقات موبايل احترافية لأنظمة iOS و Android</p>
            </div>

            <div class="grid grid-4" style="margin-bottom: 3rem;">
                <div class="card">
                    <div class="icon-box purple">📱</div>
                    <h3>iOS & Android</h3>
                    <p>تطوير تطبيقات لكل من iOS و Android</p>
                </div>
                <div class="card">
                    <div class="icon-box purple">🖥️</div>
                    <h3>واجهات مميزة</h3>
                    <p>تصميم واجهات مستخدم جذابة وسهلة</p>
                </div>
                <div class="card">
                    <div class="icon-box purple">⚡</div>
                    <h3>أداء عالي</h3>
                    <p>تطبيقات سريعة وفعالة</p>
                </div>
                <div class="card">
                    <div class="icon-box purple">☁️</div>
                    <h3>تكامل سحابي</h3>
                    <p>ربط مع الخدمات السحابية</p>
                </div>
            </div>

            <div class="grid grid-3">
                <div class="pricing-card">
                    <h3>تطبيق بسيط</h3>
                    <div class="price purple">25,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>تطبيق لمنصة واحدة (iOS أو Android)</li>
                        <li>تصميم 5-7 شاشات</li>
                        <li>لوحة تحكم بسيطة</li>
                        <li>تكامل مع API واحد</li>
                        <li>نشر على المتجر</li>
                        <li>دعم فني لمدة 3 أشهر</li>
                    </ul>
                    <button class="btn" style="background: #9333ea;">اطلب الآن</button>
                </div>

                <div class="pricing-card featured purple">
                    <div class="badge purple">الأكثر طلباً</div>
                    <h3>تطبيق متقدم</h3>
                    <div class="price purple">50,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>تطبيق لمنصتين (iOS & Android)</li>
                        <li>تصميم 10-15 شاشة</li>
                        <li>لوحة تحكم متقدمة</li>
                        <li>تكامل مع عدة APIs</li>
                        <li>إشعارات فورية</li>
                        <li>نظام دفع إلكتروني</li>
                        <li>نشر على المتاجر</li>
                        <li>دعم فني لمدة 6 أشهر</li>
                    </ul>
                    <button class="btn" style="background: #9333ea;">اطلب الآن</button>
                </div>

                <div class="pricing-card">
                    <h3>تطبيق شامل</h3>
                    <div class="price purple">100,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>تطبيق لمنصتين (iOS & Android)</li>
                        <li>عدد شاشات غير محدود</li>
                        <li>لوحة تحكم احترافية</li>
                        <li>تكامل كامل مع الأنظمة</li>
                        <li>إشعارات فورية متقدمة</li>
                        <li>أنظمة دفع متعددة</li>
                        <li>خرائط وموقع جغرافي</li>
                        <li>دردشة فورية</li>
                        <li>نشر على المتاجر</li>
                        <li>دعم فني لمدة سنة</li>
                    </ul>
                    <button class="btn" style="background: #9333ea;">اطلب الآن</button>
                </div>
            </div>
        </div>
    </section>

    <!-- ERP Section -->
    <section id="erp" class="bg-orange">
        <div class="container">
            <div class="section-title">
                <div class="icon-box orange" style="margin: 0 auto 1rem;">💾</div>
                <h2>أنظمة ERP</h2>
                <p>حلول متكاملة لإدارة موارد المؤسسات والشركات</p>
            </div>

            <div class="grid grid-4" style="margin-bottom: 3rem;">
                <div class="card">
                    <div class="icon-box orange">👥</div>
                    <h3>إدارة الموارد البشرية</h3>
                    <p>نظام شامل لإدارة الموظفين والرواتب والحضور</p>
                </div>
                <div class="card">
                    <div class="icon-box orange">📄</div>
                    <h3>المحاسبة والمالية</h3>
                    <p>إدارة الحسابات والفواتير والتقارير المالية</p>
                </div>
                <div class="card">
                    <div class="icon-box orange">💰</div>
                    <h3>المبيعات والمشتريات</h3>
                    <p>متابعة المبيعات والمشتريات وإدارة العلاقات</p>
                </div>
                <div class="card">
                    <div class="icon-box orange">📈</div>
                    <h3>التقارير والتحليلات</h3>
                    <p>تقارير تفصيلية ولوحات تحكم تحليلية</p>
                </div>
            </div>

            <div class="grid grid-3">
                <div class="pricing-card">
                    <h3>نظام أساسي</h3>
                    <div class="price orange">50,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>3 وحدات أساسية</li>
                        <li>حتى 20 مستخدم</li>
                        <li>لوحة تحكم إدارية</li>
                        <li>تقارير أساسية</li>
                        <li>دعم فني لمدة 6 أشهر</li>
                        <li>تدريب الفريق</li>
                    </ul>
                    <button class="btn" style="background: #ea580c;">اطلب الآن</button>
                </div>

                <div class="pricing-card featured orange">
                    <div class="badge orange">الأكثر طلباً</div>
                    <h3>نظام متقدم</h3>
                    <div class="price orange">120,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>6 وحدات كاملة</li>
                        <li>حتى 50 مستخدم</li>
                        <li>لوحة تحكم متقدمة</li>
                        <li>تقارير تفصيلية</li>
                        <li>تكامل مع أنظمة خارجية</li>
                        <li>تطبيق موبايل</li>
                        <li>دعم فني لمدة سنة</li>
                        <li>تدريب وورش عمل</li>
                    </ul>
                    <button class="btn" style="background: #ea580c;">اطلب الآن</button>
                </div>

                <div class="pricing-card">
                    <h3>نظام شامل</h3>
                    <div class="price orange">250,000 <small style="font-size: 1rem;">ر.س</small></div>
                    <ul class="features-list">
                        <li>جميع الوحدات</li>
                        <li>عدد مستخدمين غير محدود</li>
                        <li>لوحة تحكم مخصصة</li>
                        <li>تقارير وتحليلات متقدمة</li>
                        <li>تكامل كامل</li>
                        <li>تطبيقات موبايل</li>
                        <li>ذكاء اصطناعي وتحليلات</li>
                        <li>نظام أمان متقدم</li>
                        <li>دعم فني مدى الحياة</li>
                        <li>تدريب شامل</li>
                    </ul>
                    <button class="btn" style="background: #ea580c;">اطلب الآن</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="bg-dark">
        <div class="container">
            <div class="section-title">
                <h2>تواصل معنا</h2>
                <p style="color: #9ca3af;">نحن هنا للإجابة على جميع استفساراتك</p>
            </div>

            <div class="contact-info">
                <div class="contact-item">
                    <div class="contact-icon">📞</div>
                    <h3>الهاتف</h3>
                    <p style="color: #9ca3af;">+966 50 123 4567</p>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">✉️</div>
                    <h3>البريد الإلكتروني</h3>
                    <p style="color: #9ca3af;">info@software.com</p>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">📍</div>
                    <h3>العنوان</h3>
                    <p style="color: #9ca3af;">الرياض، المملكة العربية السعودية</p>
                </div>
                <div class="contact-item">
                    <div class="contact-icon">🕐</div>
                    <h3>ساعات العمل</h3>
                    <p style="color: #9ca3af;">الأحد - الخميس: 9 صباحاً - 6 مساءً</p>
                </div>
            </div>

            <div class="contact-form">
                <form onsubmit="return handleSubmit(event)">
                    <div class="form-row">
                        <div class="form-group">
                            <label>الاسم</label>
                            <input type="text" placeholder="اسمك الكامل" required>
                        </div>
                        <div class="form-group">
                            <label>البريد الإلكتروني</label>
                            <input type="email" placeholder="example@email.com" required>
                        </div>
                    </div>
                    <div class="form-group">
                        <label>الخدمة المطلوبة</label>
                        <select required>
                            <option value="">اختر الخدمة</option>
                            <option>تطوير موقع إلكتروني</option>
                            <option>إنشاء متجر إلكتروني</option>
                            <option>تطوير تطبيق موبايل</option>
                            <option>نظام ERP</option>
                            <option>استشارة تقنية</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>الرسالة</label>
                        <textarea rows="5" placeholder="اكتب رسالتك هنا..." required></textarea>
                    </div>
                    <button type="submit" class="btn" style="width: 100%;">إرسال الرسالة</button>
                </form>
            </div>

            <div class="social-links">
                <a href="#" title="Facebook">📘</a>
                <a href="#" title="Twitter">🐦</a>
                <a href="#" title="LinkedIn">💼</a>
                <a href="#" title="Instagram">📷</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p style="color: #6b7280;">© 2026 شركة البرمجة. جميع الحقوق محفوظة.</p>
    </footer>

    <!-- Scroll to Top Button -->
    <button class="scroll-top" id="scrollTop" onclick="scrollToTop()">↑</button>

    <script>
        // Toggle Mobile Menu
        function toggleMenu() {
            const navLinks = document.getElementById('navLinks');
            navLinks.classList.toggle('active');
        }

        // Smooth Scroll to Section
        function scrollToSection(id) {
            const element = document.getElementById(id);
            if (element) {
                const offset = 80;
                const elementPosition = element.getBoundingClientRect().top;
                const offsetPosition = elementPosition + window.pageYOffset - offset;
                
                window.scrollTo({
                    top: offsetPosition,
                    behavior: 'smooth'
                });

                // Close mobile menu if open
                const navLinks = document.getElementById('navLinks');
                navLinks.classList.remove('active');
            }
            return false;
        }

        // Scroll to Top
        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        // Show/Hide Scroll to Top Button
        window.addEventListener('scroll', function() {
            const scrollTop = document.getElementById('scrollTop');
            if (window.pageYOffset > 400) {
                scrollTop.classList.add('show');
            } else {
                scrollTop.classList.remove('show');
            }
        });

        // Handle Form Submit
        function handleSubmit(event) {
            event.preventDefault();
            alert('تم إرسال رسالتك بنجاح! سنتواصل معك قريباً.');
            event.target.reset();
            return false;
        }

        // Close mobile menu when clicking outside
        document.addEventListener('click', function(event) {
            const nav = document.querySelector('nav');
            const menuToggle = document.querySelector('.menu-toggle');
            const navLinks = document.getElementById('navLinks');
            
            if (!nav.contains(event.target)) {
                navLinks.classList.remove('active');
            }
        });
    </script>
</body>
</html>
