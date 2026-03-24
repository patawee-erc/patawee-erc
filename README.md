<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Milk.Sabo</title>
    <!-- นำเข้าฟอนต์จาก Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
    <!-- นำเข้าไอคอน (Font Awesome) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

    <style>
        /* CSS Reset & Basic Setup */
        * {
            box-sizing: border-box;
        }
        body {
            background-color: #fee440;
            margin: 0;
            overflow: hidden;
            font-family: 'Poppins', sans-serif;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* พื้นหลัง SVG */
        svg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            z-index: -1; /* ส่งไปอยู่เลเยอร์หลังสุด */
        }

        /* การ์ดตรงกลาง (Glassmorphism Effect) */
        .card {
            background: rgba(255, 255, 255, 0.25); /* สีขาวโปร่งแสง */
            backdrop-filter: blur(10px); /* เอฟเฟกต์เบลอ */
            -webkit-backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            width: 90%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.18);
            animation: fadeIn 1.5s ease;
        }

        /* รูปโปรไฟล์ */
        .avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background-color: #fff;
            margin: 0 auto 20px;
            border: 4px solid rgba(255,255,255,0.5);
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 3em;
            color: #ccc;
        }
        .avatar img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* ข้อความ */
        h1 {
            margin: 0;
            color: #333;
            font-size: 28px;
            font-weight: 700;
            letter-spacing: 1px;
        }
        p.bio {
            color: #555;
            margin-top: 10px;
            margin-bottom: 30px;
            font-size: 16px;
        }

        /* ปุ่มลิงก์ต่างๆ */
        .btn-link {
            display: block;
            background: rgba(255, 255, 255, 0.6);
            color: #333;
            padding: 12px 20px;
            margin: 10px 0;
            border-radius: 50px;
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 500;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
        }

        .btn-link:hover {
            background: white;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            color: #9b5de5; /* เปลี่ยนสีตัวอักษรเมื่อ Hover */
        }

        /* Footer เล็กๆ */
        .footer {
            margin-top: 20px;
            font-size: 12px;
            color: #666;
            opacity: 0.8;
        }

        /* Animation ตอนโหลดหน้า */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* SVG Animation เดิม */
        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .out-top { animation: rotate 20s linear infinite; transform-origin: 13px 25px; }
        .in-top { animation: rotate 10s linear infinite; transform-origin: 13px 25px; }
        .out-bottom { animation: rotate 25s linear infinite; transform-origin: 84px 93px; }
        .in-bottom { animation: rotate 15s linear infinite; transform-origin: 84px 93px; }
    </style>
</head>
<body>

    <!-- พื้นหลัง Animation SVG -->
    <svg preserveAspectRatio="xMidYMid slice" viewBox="10 10 80 80">
        <defs>
            <!-- Styles อยู่ใน head แล้ว แต่เก็บ defs ไว้เพื่อความสมบูรณ์ -->
        </defs>
        <path fill="#9b5de5" class="out-top" d="M37-5C25.1-14.7,5.7-19.1-9.2-10-28.5,1.8-32.7,31.1-19.8,49c15.5,21.5,52.6,22,67.2,2.3C59.4,35,53.7,8.5,37-5Z"/>
        <path fill="#f15bb5" class="in-top" d="M20.6,4.1C11.6,1.5-1.9,2.5-8,11.2-16.3,23.1-8.2,45.6,7.4,50S42.1,38.9,41,24.5C40.2,14.1,29.4,6.6,20.6,4.1Z"/>
        <path fill="#00bbf9" class="out-bottom" d="M105.9,48.6c-12.4-8.2-29.3-4.8-39.4.8-23.4,12.8-37.7,51.9-19.1,74.1s63.9,15.3,76-5.6c7.6-13.3,1.8-31.1-2.3-43.8C117.6,63.3,114.7,54.3,105.9,48.6Z"/>
        <path fill="#00f5d4" class="in-bottom" d="M102,67.1c-9.6-6.1-22-3.1-29.5,2-15.4,10.7-19.6,37.5-7.6,47.8s35.9,3.9,44.5-12.5C115.5,92.6,113.9,74.6,102,67.1Z"/>
    </svg>

    <!-- ส่วนเนื้อหาหลัก -->
    <div class="card">
        <!-- ใส่รูปโปรไฟล์ตรง src (ถ้ายังไม่มีจะเป็นไอคอนยิ้ม) -->
        <div class="avatar">
           <img src="https://milksabo.github.io/img/pf.jpg" alt="Profile">
            
        </div>
        
        <h1>Milk.sabo</h1>
        <p class="bio">Web Developer | IT Technician <br>Digital Creator | Art & Lifestyle 🎨</p>

        <!-- ลิงก์ต่างๆ -->
        <a href="https://www.instagram.com/milkoomilk" target="_blank" class="btn-link">
            <i class="fa-brands fa-instagram"></i> Instagram
        </a>
        <a href="https://facebook.com/milk.sabour" target="_blank" class="btn-link">
            <i class="fa-brands fa-facebook"></i> Facebook
        </a>
        
        <div class="footer">
            © 2024 Milk.sabo - All rights reserved
        </div>
    </div>

</body>
</html>
