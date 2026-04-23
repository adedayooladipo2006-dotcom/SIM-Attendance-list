<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>SIM Attendance | Admin Protected</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Segoe UI', Roboto, sans-serif; }
        body { background: linear-gradient(145deg, #e9f0f5 0%, #d9e2ec 100%); min-height: 100vh; padding: 30px 20px; }
        .dashboard { max-width: 1400px; margin: 0 auto; }
        .uni-header { background: #0a2b3e; border-radius: 32px; padding: 20px 28px; margin-bottom: 30px; color: white; display: flex; justify-content: space-between; flex-wrap: wrap; align-items: center; }
        .title-section h1 { font-size: 1.9rem; }
        .badge { background: #f4c542; color: #1e2f3a; padding: 8px 20px; border-radius: 40px; font-weight: bold; }
        .split-layout { display: flex; flex-wrap: wrap; gap: 28px; }
        .form-panel, .records-panel { background: white; border-radius: 36px; padding: 28px 26px; box-shadow: 0 20px 35px -12px rgba(0,0,0,0.2); }
        .form-panel { flex: 1.2; min-width: 280px; }
        .records-panel { flex: 2; min-width: 380px; }
        .form-group { margin-bottom: 22px; }
        label { font-weight: 600; color: #1e4663; display: block; margin-bottom: 8px; }
        input, select { width: 100%; padding: 14px 16px; border: 2px solid #e2e8f0; border-radius: 24px; font-size: 0.95rem; }
        input:focus { border-color: #f4b942; outline: none; }
        .btn-primary { background: #0f3b2c; color: white; border: none; padding: 14px 18px; width: 100%; border-radius: 40px; font-weight: bold; cursor: pointer; margin-top: 12px; }
        .btn-primary:hover { background: #1b5e44; }
        .btn-secondary { background: #2c5282; color: white; border: none; padding: 10px 18px; border-radius: 40px; font-weight: bold; cursor: pointer; }
        .btn-danger { background: #b91c1c; color: white; border: none; padding: 10px 18px; border-radius: 40px; font-weight: bold; cursor: pointer; }
        .btn-warning { background: #d97706; color: white; border: none; padding: 10px 18px; border-radius: 40px; font-weight: bold; cursor: pointer; }
        .action-bar { display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; margin-bottom: 20px; gap: 12px; }
        .admin-bar { background: #fef3c7; padding: 12px 18px; border-radius: 28px; margin-bottom: 20px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 12px; }
        .admin-badge { background: #d97706; color: white; padding: 4px 12px; border-radius: 30px; font-size: 0.75rem; font-weight: bold; }
        .login-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); display: flex; justify-content: center; align-items: center; z-index: 1000; }
        .login-card { background: white; padding: 40px; border-radius: 48px; width: 350px; text-align: center; }
        .login-card input { margin: 15px 0; }
        .table-wrapper { overflow-x: auto; max-height: 450px; overflow-y: auto; }
        .attendance-table { width: 100%; border-collapse: collapse; font-size: 0.85rem; }
        .attendance-table th { background: #f1f6fa; padding: 14px 10px; position: sticky; top: 0; }
        .attendance-table td { padding: 12px 10px; border-bottom: 1px solid #e9edf2; }
        .delete-btn { background: none; border: none; color: #b91c1c; font-size: 1.2rem; cursor: pointer; padding: 4px 12px; }
        .empty-msg { text-align: center; padding: 40px; color: #5a6e7c; }
        .footer-note { margin-top: 25px; font-size: 0.75rem; text-align: center; color: #4b6b87; border-top: 1px solid #e2edf7; padding-top: 18px; }
        .lecture-highlight { background: #fef7e0; border-left: 4px solid #f4b942; padding: 10px 14px; border-radius: 20px; margin-bottom: 20px; }
        @media (max-width: 760px) { .form-panel, .records-panel { padding: 20px; } }
    </style>
</head>
<body>

<div id="loginModal" class="login-overlay">
    <div class="login-card">
        <h2 style="color:#0a2b3e;">🔐 Admin Access</h2>
        <p style="margin: 10px 0; color: gray;">Enter credentials to manage attendance</p>
        <input type="password" id="adminPassword" placeholder="Admin Password" style="width:100%;">
        <button onclick="attemptLogin()" class="btn-primary" style="margin-top: 10px;">Login as Admin</button>
        <button onclick="enterStudentMode()" class="btn-outline" style="margin-top: 10px; background:transparent; border:2px solid #2c5282; padding:12px; width:100%; border-radius:40px; cursor:pointer;">Continue as Student (View Only)</button>
        <p style="margin-top: 20px; font-size: 12px;">Default Admin: <strong>password: ********2026</strong></p>
    </div>
</div>

<div class="dashboard" id="mainApp" style="display: none;">
    <div class="uni-header">
        <div class="title-section"><h1>📋 SIM Attendance System</h1><p>Securities & Investment Management</p></div>
        <div class="badge"><span id="roleDisplay">👤 Student Mode</span></div>
    </div>
    <div class="split-layout">
        <div class="form-panel">
            <h3>✍️ Mark Your Attendance</h3>
            <form id="attendanceForm">
                <div class="form-group"><label>📚 Lecture Topic</label><input type="text" id="lectureTopic" placeholder="e.g., Portfolio Theory" required></div>
                <div class="form-group"><label>📖 Course Code</label><input type="text" id="courseCode" placeholder="e.g., SIM401" required></div>
                <div class="form-group"><label>📅 Date</label><input type="date" id="lectureDate" required></div>
                <div class="form-group"><label>👤 Full Name</label><input type="text" id="studentName" placeholder="Full Name" required></div>
                <div class="form-group"><label>🆔 Matric Number</label><input type="text" id="matricNo" placeholder="SIM/2022/XXX" required></div>
                <button type="submit" class="btn-primary">✅ Mark Attendance</button>
            </form>
            <div class="footer-note">* All students can mark their attendance. Admin can delete/clear/export.</div>
        </div>
        <div class="records-panel">
            <div class="action-bar"><h3>📋 Attendance Register</h3><button id="printPDFBtn" class="btn-secondary">🖨️ PDF Report</button></div>
            <div id="adminControls" style="display: none;" class="admin-bar">
                <span class="admin-badge">👑 Admin Mode</span>
                <button id="exportDataBtn" class="btn-secondary">📤 Export JSON</button>
                <label style="background:#4a6fa5; padding:10px 18px; border-radius:40px; color:white; cursor:pointer;">📥 Import JSON<input type="file" id="importFileInput" accept=".json" style="display:none;"></label>
                <button id="clearAllBtn" class="btn-danger">🗑️ Clear All</button>
                <button id="logoutBtn" class="btn-warning">🚪 Logout</button>
            </div>
            <div id="liveLectureInfo" class="lecture-highlight">💡 Loading records...</div>
            <div class="table-wrapper"><table class="attendance-table"><thead><tr><th>Student Name</th><th>Matric No</th><th>Course Code</th><th>Lecture Topic</th><th>Date</th><th id="actionColHeader">Action</th></tr></thead><tbody id="attendanceTableBody"></tbody></table></div>
            <div class="footer-note">💡 <strong>Note:</strong> Students can view & add attendance. Admin can delete entries, clear all, import/export.</div>
        </div>
    </div>
</div>

<script>
    let attendanceRecords = [];
    let isAdmin = false;

    // Load from localStorage
    function loadRecords() {
        const stored = localStorage.getItem("sim_attendance_records");
        if(stored) {
            try { attendanceRecords = JSON.parse(stored); } catch(e) { attendanceRecords = []; }
        } else { attendanceRecords = []; }
        renderTable();
        updateSummary();
    }
    function persist() { localStorage.setItem("sim_attendance_records", JSON.stringify(attendanceRecords)); }
    function formatDate(d) { if(!d) return '—'; return new Date(d).toLocaleDateString('en-GB', { year:'numeric', month:'short', day:'numeric' }); }
    function escapeHtml(str) { if(!str) return ''; return str.replace(/[&<>]/g, function(m) { return m === '&' ? '&amp;' : m === '<' ? '&lt;' : '&gt;'; }); }
    
    function updateSummary() {
        const div = document.getElementById('liveLectureInfo');
        if(!attendanceRecords.length) { div.innerHTML = '📌 No records yet. Students can mark attendance above.'; return; }
        const courses = [...new Set(attendanceRecords.map(r=>r.courseCode))];
        div.innerHTML = `🎓 <strong>Courses:</strong> ${courses.join(', ')} &nbsp;|&nbsp; 👥 <strong>Total entries:</strong> ${attendanceRecords.length} &nbsp;|&nbsp; 🧑‍🎓 <strong>Unique students:</strong> ${new Set(attendanceRecords.map(r=>r.matricNo)).size}`;
    }
    
    function renderTable() {
        const tbody = document.getElementById('attendanceTableBody');
        const actionHeader = document.getElementById('actionColHeader');
        if(!attendanceRecords.length) { tbody.innerHTML = '<tr><td colspan="6" class="empty-msg">📭 No attendance records yet.</td></tr>'; return; }
        let html = '';
        attendanceRecords.forEach((rec, idx) => {
            html += `<tr>
                        <td>${escapeHtml(rec.studentName)}</td>
                        <td>${escapeHtml(rec.matricNo)}</td>
                        <td>${escapeHtml(rec.courseCode)}</td>
                        <td>${escapeHtml(rec.lectureTopic)}</td>
                        <td>${formatDate(rec.lectureDate)}</td>
                        <td>${isAdmin ? `<button class="delete-btn" data-idx="${idx}">✖️</button>` : '—'}</td>
                     </tr>`;
        });
        tbody.innerHTML = html;
        if(isAdmin) {
            document.querySelectorAll('.delete-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    const idx = parseInt(btn.getAttribute('data-idx'));
                    if(!isNaN(idx)) { attendanceRecords.splice(idx,1); persist(); renderTable(); updateSummary(); }
                });
            });
        }
        if(actionHeader) actionHeader.innerText = isAdmin ? 'Action (Admin)' : 'Action';
    }
    
    function addRecord(topic, code, date, name, matric) {
        if(!topic.trim() || !code.trim() || !date || !name.trim() || !matric.trim()) { alert("Please fill all fields"); return false; }
        attendanceRecords.unshift({ id: Date.now(), lectureTopic: topic.trim(), courseCode: code.trim().toUpperCase(), lectureDate: date, studentName: name.trim(), matricNo: matric.trim().toUpperCase(), createdAt: new Date().toISOString() });
        persist(); renderTable(); updateSummary(); return true;
    }
    
    function exportJSON() {
        if(!attendanceRecords.length) { alert("No data to export"); return; }
        const blob = new Blob([JSON.stringify(attendanceRecords,null,2)], {type:"application/json"});
        const a = document.createElement('a'); a.href = URL.createObjectURL(blob); a.download = `SIM_attendance_${new Date().toISOString().slice(0,10)}.json`; a.click(); URL.revokeObjectURL(a.href);
    }
    
    function importJSON(file) {
        const reader = new FileReader();
        reader.onload = function(e) {
            try {
                const imported = JSON.parse(e.target.result);
                if(!Array.isArray(imported)) throw new Error();
                const valid = imported.filter(r => r.studentName && r.matricNo && r.lectureTopic && r.courseCode && r.lectureDate);
                if(confirm(`Merge ${valid.length} records with existing ${attendanceRecords.length}?`)) {
                    attendanceRecords = [...attendanceRecords, ...valid];
                    persist(); renderTable(); updateSummary(); alert("Import successful!");
                }
            } catch(err) { alert("Invalid JSON file"); }
        }; reader.readAsText(file);
    }
    
    function clearAll() { if(confirm("⚠️ DELETE ALL RECORDS? This cannot be undone.")) { attendanceRecords = []; persist(); renderTable(); updateSummary(); } }
    
    function generatePDF() {
        if(!attendanceRecords.length) { alert("No records"); return; }
        const container = document.createElement('div'); container.style.padding = '28px'; container.style.background = 'white';
        container.innerHTML = `<div style="text-align:center"><h1>SECURITIES & INVESTMENT MANAGEMENT</h1><h3>Attendance Report</h3><p>Generated: ${new Date().toLocaleDateString()} | Total: ${attendanceRecords.length}</p></div>
        <table style="width:100%; border-collapse:collapse;"><thead><tr style="background:#eef2f7;"><th>#</th><th>Student</th><th>Matric</th><th>Course</th><th>Lecture</th><th>Date</th></tr></thead><tbody>`;
        attendanceRecords.forEach((r,i)=> { container.innerHTML += `<tr><td>${i+1}</td><td>${escapeHtml(r.studentName)}</td><td>${escapeHtml(r.matricNo)}</td><td>${escapeHtml(r.courseCode)}</td><td>${escapeHtml(r.lectureTopic)}</td><td>${formatDate(r.lectureDate)}</td></tr>`; });
        container.innerHTML += `</tbody></table><div style="margin-top:40px; display:flex; justify-content:space-between;"><div>Lecturer Signature: ______________</div><div>Date: ${new Date().toLocaleDateString()}</div></div>`;
        html2pdf().set({ margin:0.5, filename:`SIM_Attendance_${new Date().toISOString().slice(0,10)}.pdf`, jsPDF:{unit:'in', format:'a4', orientation:'landscape'} }).from(container).save();
    }
    
    // LOGIN SYSTEM
    function attemptLogin() {
        const pwd = document.getElementById('adminPassword').value;
        if(pwd === "simadmin2026") {
            isAdmin = true;
            document.getElementById('loginModal').style.display = 'none';
            document.getElementById('mainApp').style.display = 'block';
            document.getElementById('roleDisplay').innerHTML = '👑 Admin Mode (Full Control)';
            document.getElementById('adminControls').style.display = 'flex';
            loadRecords();
        } else { alert("Wrong password! Access denied. Use 'simadmin2026' or continue as student."); }
    }
    
    function enterStudentMode() {
        isAdmin = false;
        document.getElementById('loginModal').style.display = 'none';
        document.getElementById('mainApp').style.display = 'block';
        document.getElementById('roleDisplay').innerHTML = '👤 Student Mode (View & Add Only)';
        document.getElementById('adminControls').style.display = 'none';
        loadRecords();
    }
    
    function logout() {
        isAdmin = false;
        document.getElementById('mainApp').style.display = 'none';
        document.getElementById('loginModal').style.display = 'flex';
        document.getElementById('adminPassword').value = '';
    }
    
    // Event listeners
    document.getElementById('attendanceForm').addEventListener('submit', (e) => {
        e.preventDefault();
        const topic = document.getElementById('lectureTopic').value, code = document.getElementById('courseCode').value, date = document.getElementById('lectureDate').value, name = document.getElementById('studentName').value, matric = document.getElementById('matricNo').value;
        if(addRecord(topic,code,date,name,matric)) {
            document.getElementById('lectureTopic').value = ''; document.getElementById('courseCode').value = ''; document.getElementById('studentName').value = ''; document.getElementById('matricNo').value = '';
            document.getElementById('lectureDate').value = new Date().toISOString().split('T')[0];
        }
    });
    document.getElementById('printPDFBtn').addEventListener('click', generatePDF);
    document.getElementById('exportDataBtn')?.addEventListener('click', exportJSON);
    document.getElementById('importFileInput')?.addEventListener('change', (e) => { if(e.target.files[0]) importJSON(e.target.files[0]); e.target.value = ''; });
    document.getElementById('clearAllBtn')?.addEventListener('click', clearAll);
    document.getElementById('logoutBtn')?.addEventListener('click', logout);
    
    // set default date
    const dateInput = document.getElementById('lectureDate');
    if(dateInput && !dateInput.value) dateInput.value = new Date().toISOString().split('T')[0];
</script>
</body>
</html>
