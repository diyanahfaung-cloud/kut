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
            background-color: #f0faff;
            color: var(--text-dark);
        }

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

        .link-group { display: flex; gap: 10px; margin-top: 1.5rem; flex-wrap: wrap; }
        .btn-doc { background: #ff4757; color: white; padding: 10px 20px; border-radius: 10px; text-decoration: none; flex: 1; text-align: center; min-width: 140px; }
        .btn-web { background: #2f3542; color: white; padding: 10px 20px; border-radius: 10px; text-decoration: none; flex: 1; text-align: center; min-width: 140px; }

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
            <p contenteditable="true" style="font-size: 0.9rem; opacity: 0.9;">วิชา คอมพิวเตอร์เพื่อการออกแบบ</p>
            
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
            <input type="text" id="workLink" placeholder="URL ลิงก์เว็บไซต์อื่นๆ (ถ้ามีหลายลิงก์คั่นด้วยลูกน้ำ , )">
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
                <div class="link-group" id="viewLinkGroup">
                    </div>
            </div>
        </div>
    </div>

    <script>
        // ข้อมูลผลงานเริ่มต้น
        let works = [
            {
                id: 1,
                title: "ผลงานที่ 1 ",
                img: "https://i.postimg.cc/BtH3MTbR/image.png",
                desc: "คอมพิวเตอร์เพื่อการออกแบบ มี2 งาน 1งานเอสาร 2มายแมพ",
                doc: "https://docs.google.com/document/d/1xffvOlmbgaNfpF2xxneXiyR30RFU8im5/edit?usp=sharing&ouid=101604807719918854225&rtpof=true&sd=true",
                link: ["https://drive.google.com/file/d/1BSvO04XxlJrlyOQwX7jyqk_LQLUkdyJ-/view?usp=classroom_web&authuser=0"]
            },
            {
                id: 2,
                title: "ผลงานที่ 2 ใบปลิวแนะนำตัว ",
                img: "https://i.postimg.cc/dDHfRDmf/image.png", 
                desc: "ใบปลิวแนะนำตัว เรซูเม่ ",
                doc: "#", 
                link: ["https://drive.google.com/file/d/1_AOl-bZhuLGEhk5uavG_2kwpt-rdxcQH/view?usp=classroom_web&authuser=0"]
            },
            {
                id: 3,
                title: "ผลงานที่ 3 ใบปลิว ",
                img: "https://i.postimg.cc/Ty00RHtZ/image.png",
                desc: "ใบปลิวคืนสู่เหย้า รร มัธยมนาคนาวาอุปถัมภ์ ",
                doc: "#",
                link: ["https://drive.google.com/file/d/1ZaLh5iULAxmUxJpKUw_ZQST7MMxYR1YI/view?usp=classroom_web&authuser=0"]
            },
            {
                id: 4,
                title: "ผลงานที่ 4 Christmas Card ",
                img: "https://i.postimg.cc/HkB3f1QB/Screenshot-2026-03-04-084539.png",
                desc: "การ์ดคริสมาสนี้มี3ผลงาน 1Paint 2โปรแกรมหรือแอพลิเคชันใดก็ได้ 3AI",
                doc: "#",
                link: [
                    "https://drive.google.com/file/d/1arqptw3p9CJyYPUCIDo3GL1EzKyKc_Wc/view?usp=classroom_web&authuser=0",
                    "https://drive.google.com/file/d/1DogGo0c1yxsR5DSvjvzur1n2Jd3wwy_y/view?usp=classroom_web&authuser=0",
                    "https://drive.google.com/file/d/1jcu8-l_q7gDaa7_495dYgNJMW3U4rfUF/view?usp=classroom_web&authuser=0"
                ]
            },
            {
                id: 5,
                title: "ผลงานที่ 5 Happy New Year Card ",
                img: "https://i.postimg.cc/vcvC1X2G/image.png",
                desc: "การ์ดปีใหม่นี้มี2ปลงาน 1โปรแกรมหรือ แอพลิเคชันใดก็ได้งดTemplateหรือแบบสำเร็จรูป 2AI ข้อ AI Generate  ใช้ prompt เดียวกัน ใช้อย่างน้อย4เว็บไซต์ และระบุเว็บไซต์ที่ใช้ในการ Gen ภาพ AI ใส่ในไฟล์ Google Docs ",
                doc: "https://docs.google.com/document/d/1faKcAbnc1TkrxOMM46OqrZpaPamsTNN6HJkolErwB4A/edit?usp=sharing",
                link: ["https://drive.google.com/file/d/1XkZxQiG-W-G7QN1Idcc_49O_9Qi7ZT_Z/view?usp=classroom_web&authuser=0"]
            },
            {
                id: 6,
                title: "ผลงานที่ 6 นิตยสาร/Magazine ",
                img: "https://i.postimg.cc/jwQBzXd0/image.png", 
                desc: "ออกแบบปกนิตยสาร หรือ Magazine ",
                doc: "#", 
                link: ["https://drive.google.com/file/d/1ETbVEOsG66IT-uANZ3ofBAh8_VmTqkZm/view?usp=classroom_web&authuser=0"]
            },
            {
                id: 7,
                title: "ผลงานที่ 7 ออกแบบหน้าเว็บ",
                img: "https://i.postimg.cc/Yqh9Wv95/skr-nch-xt-2026-03-05-131414.png", // รูปภาพตัวอย่าง
                desc: "รายละเอียดของผลงานชิ้นที่ 7 เว็บไซต์นี้นี่แหละค่ะงานที่7",
                doc: "#", 
                link: ["#"]
            },
            {
                id: 8,
                title: "ผลงานที่ 8 valentine card ",
                img: "https://i.postimg.cc/kBbgCznq/image.png", // หน้าปกงานที่ 8
                desc: "ออกแบบการ์วาเลนไทน์มี2งาน 1ออกแบบเอง 2ใช้เอไอในการสร้างชิ้นงาน ",
                doc: "#", // งานนี้ยังไม่มีลิงก์เอกสาร
                link: [
                    "https://drive.google.com/file/d/17zM-zEHAAkMEJJprsm9SSz4NiLgdFpT6/view?usp=classroom_web&authuser=0", // รูปเพิ่มเติมที่ 1
                    "https://drive.google.com/file/d/1US82OuAHRgRF8PAp-cqWuSMK1qlt88Ea/view?usp=classroom_web&authuser=0" // รูปเพิ่มเติมที่ 2 (เพิ่มใหม่)
                ] 
            }
        ];

        const grid = document.getElementById('portfolioGrid');

        // ฟังก์ชันแสดงผลงานทั้งหมด
        function renderWorks() {
            grid.innerHTML = '';
            works.forEach(work => {
                // ตรวจสอบว่ามีลิงก์เพิ่มเติมหรือไม่
                let hasLink = false;
                if (Array.isArray(work.link)) {
                    hasLink = work.link.length > 0 && work.link[0] !== '#';
                } else {
                    hasLink = work.link && work.link !== '#';
                }

                const card = document.createElement('div');
                card.className = 'card';
                card.innerHTML = `
                    <img src="${work.img}" class="card-img" onclick="viewDetails(${work.id})">
                    <div class="card-content" onclick="viewDetails(${work.id})">
                        <h3 style="margin:0 0 10px 0; color:#333;">${work.title}</h3>
                        <p style="font-size:0.85rem; color:#666;">${work.desc.substring(0, 80)}...</p>
                        <div style="margin-top:10px;">
                            ${work.doc !== '#' ? '<span style="font-size:11px; background:#ffeef0; color:#ff4757; padding:4px 8px; border-radius:5px; margin-right:5px;"><i class="fas fa-file-pdf"></i> มีเอกสาร</span>' : ''}
                            ${hasLink ? '<span style="font-size:11px; background:#e0f2fe; color:#0369a1; padding:4px 8px; border-radius:5px;"><i class="fas fa-image"></i> มีรูปเพิ่มเติม</span>' : ''}
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
            const linkRaw = document.getElementById('workLink').value || '#';
            const desc = document.getElementById('workDesc').value;

            // แปลงลิงก์ที่กรอกให้เป็น Array
            let linkArray = linkRaw !== '#' ? linkRaw.split(',').map(item => item.trim()) : ['#'];

            if (title && desc) {
                works.push({ id: Date.now(), title, img, doc, link: linkArray, desc });
                renderWorks();
                closeModal('addModal');
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
            
            const linkGroup = document.getElementById('viewLinkGroup');
            linkGroup.innerHTML = ''; // ล้างปุ่มเก่าออกก่อน

            // 1. สร้างปุ่มลิงก์เอกสาร (ถ้ามี)
            if(work.doc !== '#') {
                linkGroup.innerHTML += `<a href="${work.doc}" target="_blank" class="btn-doc"><i class="fas fa-file-pdf"></i> ดูไฟล์เอกสาร</a>`;
            }
            
            // 2. สร้างปุ่มลิงก์รูปภาพเพิ่มเติม (รองรับหลายปุ่ม)
            let links = Array.isArray(work.link) ? work.link : [work.link];
            let linkCount = 1;
            
            links.forEach(lk => {
                if(lk && lk !== '#') {
                    let btnText = links.length > 1 ? `ดูรูปเพิ่มเติม ${linkCount}` : 'ดูรูปเพิ่มเติม';
                    linkGroup.innerHTML += `<a href="${lk}" target="_blank" class="btn-web"><i class="fas fa-image"></i> ${btnText}</a>`;
                    linkCount++;
                }
            });

            document.getElementById('viewModal').style.display = 'block';
        }

        // ฟังก์ชันลบงาน
        function deleteWork(id, event) {
            event.stopPropagation();
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
