<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Diyanah FP</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

    <style>
        :root {
            --blue-main: #4facfe;
            --pink-main: #f093fb;
            --text-dark: #2d3436;
            --white: #ffffff;
        }

        body {
            font-family: 'Sarabun', sans-serif;
            margin: 0;
            background-color: #f0faff; /* พื้นหลังฟ้าอ่อนมากๆ */
            color: var(--text-dark);
        }

        /* Header Gradient ฟ้า-ชมพู */
        header {
            background: linear-gradient(135deg, #4facfe 0%, #f093fb 100%);
            color: white;
            padding: 4rem 1rem;
            text-align: center;
            border-bottom: 8px solid rgba(255,255,255,0.3);
        }

        .profile-img img {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 6px solid white;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            margin-bottom: 1.5rem;
            object-fit: cover;
        }

        .contact-chips {
            margin-top: 1.5rem;
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }

        .contact-chips span {
            background: rgba(255,255,255,0.2);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            backdrop-filter: blur(5px);
        }

        /* Portfolio Section */
        main {
            max-width: 1100px;
            margin: -30px auto 50px;
            background: white;
            border-radius: 30px;
            padding: 2rem;
            box-shadow: 0 15px 35px rgba(0,0,0,0.05);
        }

        .portfolio-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            border-bottom: 2px solid #f1f1f1;
            padding-bottom: 1rem;
        }

        .btn-add {
            background: linear-gradient(to right, #ff758c, #ff7eb3);
            color: white;
            border: none;
            padding: 12px 25px;
            border-radius: 30px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.3s;
        }

        .btn-add:hover { 
            transform: scale(1.05); 
            box-shadow: 0 5px 15px rgba(255, 117, 140, 0.4); 
        }

        /* Card Grid */
        .portfolio-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
        }

        .card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid #eee;
            transition: 0.3s;
            cursor: pointer;
            display: flex;
            flex-direction: column;
        }

        .card:hover { 
            transform: translateY(-10px); 
            border-color: var(--pink-main); 
        }

        .card-img { 
            width: 100%; 
            height: 200px; 
            object-fit: cover; 
        }
        
        .card-content { 
            padding: 1.5rem; 
            flex-grow: 1;
        }

        /* Modal Styles */
        .modal { 
            display: none; 
            position: fixed; 
            z-index: 999; 
            left: 0; 
            top: 0; 
            width: 100%; 
            height: 100%; 
            background: rgba(0,0,0,0.7); 
            backdrop-filter: blur(8px); 
            overflow-y: auto;
        }
        
        .modal-content { 
            background: white; 
            margin: 5% auto; 
            padding: 2.5rem; 
            width: 90%; 
            max-width: 550px; 
            border-radius: 25px; 
            position: relative;
        }

        input, textarea { 
            width: 100%; 
            padding: 12px; 
            margin: 8px 0; 
            border: 1px solid #ddd; 
            border-radius: 10px; 
            box-sizing: border-box; 
            font-family: 'Sarabun', sans-serif;
        }

        .btn-save { background: var(--blue-main); color: white; border: none; padding: 12px 30px; border-radius: 10px; cursor: pointer; }
        .btn-cancel { background: #f1f1f1; border: none; padding: 12px 30px; border-radius: 10px; cursor: pointer; margin-left: 10px; }

        .link-group { display: flex; gap: 10px; margin-top: 1.5rem; }
        .btn-doc { background: #ff4757; color: white; padding: 10px 20px; border-radius: 10px; text-decoration: none; flex: 1; text-align: center; }
        .btn-web { background: #2f3542; color: white; padding: 10px 20px; border-radius: 10px; text-decoration: none; flex: 1; text-align: center; }

        .close { 
            position: absolute;
            right: 20px;
            top: 10px;
            font-size: 2rem; 
            cursor: pointer; 
            color: #aaa;
        }
        
        #viewImg {
            width: 100%;
            border-radius: 15px;
            margin-bottom: 15px;
        }
    </style>
</head>
<body>

    <header>
        <div class="profile-container">
            <div class="profile-img">
                <img src="https://i.postimg.cc/jjJ5B79T/Screenshot-2026-02-27-134215.png" alt="Profile" id="profilePic">
            </div>
            <h1 contenteditable="true">นางสาวดิยานะฮ์ เฟื่องปัญญา</h1>
            <p contenteditable="true">ชั้นมัธยมศึกษาปีที่ 4/3 | โรงเรียนมัธยมนาคนาวาอุปถัมภ์</p>
            <p contenteditable="true" style="font-size: 0.9rem; opacity: 0.9;">วิชา คอมออกแบบ</p>
            
            <div class="contact-chips">
                <span contenteditable="true"><i class="fas fa-envelope"></i> diyanah@edu.bangkok.go.th</span>
                <span contenteditable="true"><i class="fas fa-phone"></i> 089-484-1952</span>
            </div>
        </div>
    </header>

    <main>
        <section class="portfolio-header">
            <h2>คลังเก็บผลงาน</h2>
            <button id="openAddModal" class="btn-add"><i class="fas fa-plus"></i> เพิ่มผลงานใหม่</button>
        </section>

        <div class="portfolio-grid" id="portfolioGrid">
            </div>
    </main>

    <div id="addModal" class="modal">
        <div class="modal-content">
            <h3><i class="fas fa-folder-plus"></i> เพิ่มผลงานใหม่</h3>
            <input type="text" id="workTitle" placeholder="ชื่อผลงาน (เช่น ออกแบบโปสเตอร์)">
            <input type="text" id="workImg" placeholder="URL รูปภาพหน้าปก (https://...)">
            <input type="text" id="workDoc" placeholder="URL ไฟล์เอกสาร/PDF (Google Drive/Canva)">
            <input type="text" id="workLink" placeholder="URL ลิงก์เว็บไซต์อื่นๆ (ถ้ามี)">
            <textarea id="workDesc" placeholder="รายละเอียดหรือแนวคิดในการออกแบบ"></textarea>
            
            <div class="modal-btns">
                <button onclick="addWork()" class="btn-save">บันทึกข้อมูล</button>
                <button onclick="closeModal('addModal')" class="btn-cancel">ยกเลิก</button>
            </div>
        </div>
    </div>

    <div id="viewModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="closeModal('viewModal')">&times;</span>
            <img id="viewImg" src="" alt="Work Image">
            <div class="view-body">
                <h2 id="viewTitle"></h2>
                <p id="viewDesc"></p>
                <div class="link-group">
                    <a id="viewDoc" href="#" target="_blank" class="btn-doc"><i class="fas fa-file-pdf"></i> ดูไฟล์เอกสาร</a>
                    <a id="viewLink" href="#" target="_blank" class="btn-web"><i class="fas fa-external-link-alt"></i> ดูเว็บไซต์</a>
                </div>
            </div>
        </div>
    </div>

    <script>
        // ข้อมูลผลงานเริ่มต้น
        let works = [
            {
                id: 1,
                title: "งานออกแบบสื่อสร้างสรรค์",
                img: "https://images.unsplash.com/photo-1558655146-d09347e92766?w=500",
                desc: "ผลงานชิ้นนี้เน้นการใช้คู่สีที่ตัดกันเพื่อดึงดูดสายตาและสร้างความน่าสนใจให้กับตัวงาน",
                doc: "#", 
                link: "#"
            }
        ];

        const grid = document.getElementById('portfolioGrid');

        // ฟังก์ชันแสดงผลงานทั้งหมด
        function renderWorks() {
            grid.innerHTML = '';
            works.forEach(work => {
                const card = document.createElement('div');
                card.className = 'card';
                card.innerHTML = `
                    <img src="${work.img}" class="card-img" onclick="viewDetails(${work.id})">
                    <div class="card-content" onclick="viewDetails(${work.id})">
                        <h3 style="margin:0 0 10px 0; color:#333;">${work.title}</h3>
                        <p style="font-size:0.85rem; color:#666;">${work.desc.substring(0, 80)}...</p>
                        <div style="margin-top:10px;">
                            ${work.doc !== '#' ? '<span style="font-size:11px; background:#ffeef0; color:#ff4757; padding:4px 8px; border-radius:5px; margin-right:5px;"><i class="fas fa-file-pdf"></i> มีเอกสาร</span>' : ''}
                            ${work.link !== '#' ? '<span style="font-size:11px; background:#e0f2fe; color:#0369a1; padding:4px 8px; border-radius:5px;"><i class="fas fa-link"></i> มีลิงก์เว็บ</span>' : ''}
                        </div>
                    </div>
                    <button onclick="deleteWork(${work.id}, event)" style="background:none; border:none; color:#ddd; cursor:pointer; padding:10px; width:100%; text-align:right; font-size: 12px;"><i class="fas fa-trash"></i> ลบงาน</button>
                `;
                grid.appendChild(card);
            });
        }

        // ฟังก์ชันเปิด/ปิด Modal
        document.getElementById('openAddModal').onclick = () => {
            document.getElementById('addModal').style.display = 'block';
        };

        function closeModal(id) { 
            document.getElementById(id).style.display = 'none'; 
        }

        // ปิด Modal เมื่อคลิกข้างนอกกล่อง
        window.onclick = function(event) {
            if (event.target.className === 'modal') {
                event.target.style.display = "none";
            }
        }

        // ฟังก์ชันเพิ่มงาน
        function addWork() {
            const title = document.getElementById('workTitle').value;
            const img = document.getElementById('workImg').value || 'https://via.placeholder.com/500x300/f093fb/ffffff?text=Portfolio';
            const doc = document.getElementById('workDoc').value || '#';
            const link = document.getElementById('workLink').value || '#';
            const desc = document.getElementById('workDesc').value;

            if (title && desc) {
                works.push({ id: Date.now(), title, img, doc, link, desc });
                renderWorks();
                closeModal('addModal');
                // ล้างค่าในฟอร์ม
                document.querySelectorAll('#addModal input, #addModal textarea').forEach(input => input.value = '');
            } else {
                alert('กรุณากรอกชื่อผลงานและรายละเอียดด้วยนะคะ');
            }
        }

        // ฟังก์ชันดูรายละเอียด
        function viewDetails(id) {
            const work = works.find(w => w.id === id);
            document.getElementById('viewImg').src = work.img;
            document.getElementById('viewTitle').innerText = work.title;
            document.getElementById('viewDesc').innerText = work.desc;
            
            // จัดการปุ่มลิงก์เอกสาร
            const docBtn = document.getElementById('viewDoc');
            if(work.doc === '#') docBtn.style.display = 'none';
            else { docBtn.style.display = 'block'; docBtn.href = work.doc; }
            
            // จัดการปุ่มลิงก์เว็บ
            const linkBtn = document.getElementById('viewLink');
            if(work.link === '#') linkBtn.style.display = 'none';
            else { linkBtn.style.display = 'block'; linkBtn.href = work.link; }

            document.getElementById('viewModal').style.display = 'block';
        }

        // ฟังก์ชันลบงาน
        function deleteWork(id, event) {
            event.stopPropagation(); // กันไม่ให้ไปเปิดหน้า View Details
            if(confirm('ต้องการลบผลงานนี้ใช่ไหมคะ?')) {
                works = works.filter(w => w.id !== id);
                renderWorks();
            }
        }

        // โหลดข้อมูลครั้งแรก
        renderWorks();
    </script>
</body>
</html>
