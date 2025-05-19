<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Repo GX Manager | ريبو جي إكس مانجر</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6C63FF;
            --primary-light: #8B85FF;
            --secondary: #4D44DB;
            --accent: #FF6584;
            --dark: #2A2D3E;
            --dark-light: #3A3D4E;
            --light: #F8F9FF;
            --gray: #E5E7EB;
            --success: #4ADE80;
            --warning: #F59E0B;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            transition: all 0.3s ease;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 3rem 0 5rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .logo {
            width: 120px;
            height: 120px;
            margin: 0 auto 1.5rem;
            background-color: white;
            border-radius: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            transition: all 0.3s ease;
        }
        
        .logo:hover {
            transform: rotate(10deg) scale(1.05);
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 0.5rem;
            font-weight: 800;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }
        
        .tagline {
            font-size: 1.3rem;
            opacity: 0.9;
            margin-bottom: 2rem;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
        }
        
        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2rem;
        }
        
        .btn {
            padding: 0.8rem 1.8rem;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            text-decoration: none;
        }
        
        .btn-primary {
            background-color: white;
            color: var(--primary);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }
        
        .btn-secondary {
            background-color: transparent;
            color: white;
            border: 2px solid rgba(255,255,255,0.3);
        }
        
        .btn-secondary:hover {
            background-color: rgba(255,255,255,0.1);
            border-color: rgba(255,255,255,0.5);
        }
        
        /* Feature Sections */
        .section-title {
            text-align: center;
            margin: 3rem 0 2rem;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--dark);
            display: inline-block;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            padding: 0 1rem;
        }
        
        .section-title h2:before, .section-title h2:after {
            content: "";
            position: absolute;
            height: 3px;
            width: 100px;
            top: 50%;
            background: linear-gradient(90deg, var(--primary), transparent);
        }
        
        .section-title h2:before {
            right: 100%;
        }
        
        .section-title h2:after {
            left: 100%;
            background: linear-gradient(90deg, transparent, var(--accent));
        }
        
        /* Feature Cards */
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }
        
        .feature-card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            box-shadow: 0 5px 25px rgba(0,0,0,0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(0,0,0,0.05);
            position: relative;
            overflow: hidden;
        }
        
        .feature-card:before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: linear-gradient(to bottom, var(--primary), var(--accent));
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            width: 60px;
            height: 60px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, rgba(108, 99, 255, 0.1) 0%, rgba(255, 101, 132, 0.1) 100%);
        }
        
        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        
        .feature-title:after {
            content: "";
            flex: 1;
            height: 1px;
            background: linear-gradient(90deg, var(--gray), transparent);
            margin-left: 1rem;
        }
        
        .feature-content {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }
        
        .feature-item {
            display: flex;
            gap: 0.7rem;
        }
        
        .feature-item i {
            color: var(--primary);
            margin-top: 0.2rem;
        }
        
        .feature-text {
            flex: 1;
        }
        
        .feature-text strong {
            display: block;
            margin-bottom: 0.3rem;
            color: var(--dark-light);
        }
        
        .feature-text p {
            color: var(--dark-light);
            line-height: 1.6;
            font-size: 0.95rem;
        }
        
        .special-badge {
            background-color: var(--accent);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-size: 0.8rem;
            font-weight: 600;
            display: inline-block;
            margin-top: 0.5rem;
        }
        
        /* How It Works Section */
        .workflow {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin: 4rem 0;
            flex-wrap: wrap;
        }
        
        .workflow-card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            box-shadow: 0 5px 25px rgba(0,0,0,0.05);
            width: 100%;
            max-width: 500px;
            position: relative;
        }
        
        .workflow-title {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: var(--dark);
            font-weight: 700;
            text-align: center;
            position: relative;
            padding-bottom: 1rem;
        }
        
        .workflow-title:after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            border-radius: 3px;
        }
        
        .step {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
            position: relative;
            padding-left: 2rem;
        }
        
        .step:last-child {
            margin-bottom: 0;
        }
        
        .step-number {
            position: absolute;
            left: 0;
            top: 0;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.9rem;
        }
        
        .step-content {
            flex: 1;
        }
        
        .step-title {
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }
        
        .step-desc {
            color: var(--dark-light);
            line-height: 1.6;
            font-size: 0.95rem;
        }
        
        /* Language Toggle */
        .lang-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        
        .toggle-btn {
            background: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 50px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .toggle-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 7px 20px rgba(0,0,0,0.15);
        }
        
        /* Background Elements */
        .bg-elements {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }
        
        .bg-circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(255,255,255,0.1);
        }
        
        .circle-1 {
            width: 300px;
            height: 300px;
            top: -100px;
            right: -100px;
        }
        
        .circle-2 {
            width: 200px;
            height: 200px;
            bottom: -50px;
            left: -50px;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .workflow {
                flex-direction: column;
                align-items: center;
            }
        }
        
        @media (max-width: 768px) {
            .features {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            .tagline {
                font-size: 1.1rem;
            }
            
            .section-title h2 {
                font-size: 1.8rem;
            }
            
            .section-title h2:before, 
            .section-title h2:after {
                width: 50px;
            }
        }
        
        @media (max-width: 576px) {
            .container {
                padding: 1.5rem;
            }
            
            .feature-card {
                padding: 1.5rem;
            }
            
            .section-title h2:before, 
            .section-title h2:after {
                width: 30px;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }
            
            .btn {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="lang-toggle">
        <button class="toggle-btn" id="langSwitch">
            <span>EN</span>
            <i class="fas fa-globe"></i>
        </button>
    </div>

    <header>
        <div class="bg-elements">
            <div class="bg-circle circle-1"></div>
            <div class="bg-circle circle-2"></div>
        </div>
        <div class="header-content">
            <div class="logo">
                <img src="https://c.top4top.io/p_3426kvzpb0.png" alt="Repo GX Logo" width="70">
            </div>
            <h1>Repo GX Manager</h1>
            <p class="tagline">The Ultimate GitHub Repository Management Tool | أداة إدارة مستودعات GitHub المتكاملة</p>
            
            <div class="cta-buttons">
                <a href="#download" class="btn btn-primary">
                    <i class="fas fa-download"></i>
                    Download | تحميل
                </a>
                <a href="#demo" class="btn btn-secondary">
                    <i class="fas fa-play"></i>
                    Live Demo | تجربة مباشرة
                </a>
            </div>
        </div>
    </header>

    <div class="container">
        <!-- Authentication System -->
        <div class="section-title">
            <h2>Authentication System | نظام المصادقة</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-lock"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-shield-alt"></i>
                    Secure Authentication
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Secure GitHub token authentication with encrypted storage</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>مصادقة آمنة باستخدام توكن GitHub مع تخزين مشفر</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Remember login credentials for quick access</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>تذكر بيانات الدخول للوصول السريع</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Supports both personal & organization accounts</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>يدعم الحسابات الشخصية والمنظمات</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- DEB Package Management -->
        <div class="section-title">
            <h2>DEB Package Management | إدارة حزم DEB</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-box-open"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-cogs"></i>
                    DEB Package Manager
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>One-click DEB package uploads with progress tracking</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>رفع حزم DEB بنقرة واحدة مع متابعة التقدم</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Automatic metadata extraction from DEB files</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>استخراج تلقائي للبيانات الوصفية من ملفات DEB</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Smart architecture detection (arm64/arm64e/arm)</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>كشف ذكي للبنية (arm64/arm64e/arm)</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Full metadata editor with validation</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>محرر بيانات وصفية كامل مع تحقق</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-star"></i>
                        <div class="feature-text">
                            <strong>Special Feature:</strong>
                            <p>Merge new packages with existing Packages file</p>
                            <span class="special-badge">مميز خاص</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Media Management -->
        <div class="section-title">
            <h2>Media Management | إدارة الوسائط</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-images"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-photo-video"></i>
                    Media Handling
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Upload package icons (PNG/JPG) with drag & drop</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>رفع أيقونات للحزم (PNG/JPG) بالسحب والإفلات</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Add custom header images for your repo</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>إضافة صور رأس مخصصة للمستودع</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Image preview before upload with cropping tools</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>معاينة الصور قبل الرفع مع أدوات القص</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Automatic resizing and optimization</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>تغيير حجم تلقائي وتحسين</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Packages File System -->
        <div class="section-title">
            <h2>Packages File System | نظام ملف Packages</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-file-code"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-file-alt"></i>
                    Packages File
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Auto-generate Packages file with all metadata</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>إنشاء تلقائي لملف Packages مع جميع البيانات</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Manual Packages file upload option</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>خيار رفع ملف Packages يدوياً</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Smart merging with existing packages</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>دمج ذكي مع الحزم الموجودة</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Edit Packages content directly in built-in editor</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>تعديل محتوى الملف مباشرة في المحرر المدمج</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- File Manager -->
        <div class="section-title">
            <h2>File Manager | مدير الملفات</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-folder-open"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-file-archive"></i>
                    File Explorer
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Browse repository contents with tree view</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>تصفح محتويات المستودع مع عرض شجري</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Create/rename/delete folders easily</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>إنشاء/إعادة تسمية/حذف مجلدات بسهولة</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Edit text files in-app with syntax highlighting</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>تعديل الملفات النصية داخل التطبيق مع تلوين الصيغة</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>View file details (size, last modified, permissions)</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>عرض تفاصيل الملفات (الحجم، آخر تعديل، صلاحيات)</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Customization -->
        <div class="section-title">
            <h2>Customization | التخصيص</h2>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-paint-brush"></i>
                </div>
                <h3 class="feature-title">
                    <i class="fas fa-sliders-h"></i>
                    Personalization
                </h3>
                <div class="feature-content">
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Dark/Light mode with automatic system detection</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>وضع ليلي/نهاري مع كشف تلقائي للنظام</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>8 professionally designed color themes</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>8 ألوان للوحة التحكم مصممة باحترافية</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>English/Arabic language support with RTL</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>دعم اللغتين الإنجليزية والعربية مع RTL</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>English:</strong>
                            <p>Auto-update options with notification system</p>
                        </div>
                    </div>
                    <div class="feature-item">
                        <i class="fas fa-check-circle"></i>
                        <div class="feature-text">
                            <strong>العربية:</strong>
                            <p>خيارات التحديث التلقائي مع نظام إشعارات</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- How It Works -->
        <div class="section-title">
            <h2>How It Works | طريقة العمل</h2>
        </div>
        
        <div class="workflow">
            <!-- New Repositories -->
            <div class="workflow-card">
                <h3 class="workflow-title">For New Repositories | للمستودعات الجديدة</h3>
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-content">
                        <h4 class="step-title">Upload DEB packages | رفع حزم DEB</h4>
                        <p class="step-desc">
                            <strong>English:</strong> Simply drag and drop your DEB files or select them from your device
                            <br><br>
                            <strong>العربية:</strong> اسحب وأفلت ملفات DEB أو اخترها من جهازك
                        </p>
                    </div>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-content">
                        <h4 class="step-title">Metadata auto-filled | تعبئة البيانات تلقائياً</h4>
                        <p class="step-desc">
                            <strong>English:</strong> The app automatically extracts all package information
                            <br><br>
                            <strong>العربية:</strong> التطبيق يستخرج تلقائياً جميع معلومات الحزمة
                        </p>
                    </div>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-content">
                        <h4 class="step-title">Packages file generated | إنشاء ملف Packages</h4>
                        <p class="step-desc">
                            <strong>English:</strong> The Packages file is created automatically with all entries
                            <br><br>
                            <strong>العربية:</strong> يتم إنشاء ملف Packages أوتوماتيكياً مع جميع المدخلات
                        </p>
                    </div>
                </div>
            </div>
            
            <!-- Existing Repositories -->
            <div class="workflow-card">
                <h3 class="workflow-title">For Existing Repositories | للمستودعات الموجودة</h3>
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-content">
                        <h4 class="step-title">Upload Packages file | رفع ملف Packages</h4>
                        <p class="step-desc">
                            <strong>English:</strong> Start by uploading your existing Packages file
                            <br><br>
                            <strong>العربية:</strong> ابدأ برفع ملف Packages القديم الخاص بك
                        </p>
                    </div>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <div class="step-content">
                        <h4 class="step-title">Add new DEB packages | إضافة حزم جديدة</h4>
                        <p class="step-desc">
                            <strong>English:</strong> Upload new DEB packages as you normally would
                            <br><br>
                            <strong>العربية:</strong> ارفع حزم DEB جديدة كما تفعل عادةً
                        </p>
                    </div>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-content">
                        <h4 class="step-title">Automatic merging | دمج تلقائي</h4>
                        <p class="step-desc">
                            <strong>English:</strong> The app intelligently merges new entries with your existing Packages
                            <br><br>
                            <strong>العربية:</strong> يدمج التطبيق المدخلات الجديدة مع ملف Packages القديم بذكاء
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Language toggle functionality
        document.getElementById('langSwitch').addEventListener('click', function() {
            const html = document.documentElement;
            const isRTL = html.getAttribute('dir') === 'rtl';
            const isArabic = html.getAttribute('lang') === 'ar';
            
            // Toggle direction and language
            html.setAttribute('dir', isRTL ? 'ltr' : 'rtl');
            html.setAttribute('lang', isArabic ? 'en' : 'ar');
            
            // Update button text
            const span = this.querySelector('span');
            span.textContent = isArabic ? 'EN' : 'AR';
        });
        
        // Add animation to feature cards
        const featureCards = document.querySelectorAll('.feature-card');
        featureCards.forEach((card, index) => {
            card.style.transitionDelay = `${index * 0.1}s`;
        });
        
        // Animate elements when they come into view
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate');
                }
            });
        }, { threshold: 0.1 });
        
        document.querySelectorAll('.feature-card, .workflow-card').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>