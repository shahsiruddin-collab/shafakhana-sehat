<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>شفاخانه صحت</title>

<style>
*{box-sizing:border-box}
body{
    margin:0;
    font-family:Tahoma,Arial,sans-serif;
    background:#f4f8fb;
    color:#17324d;
}
header{
    background:linear-gradient(135deg,#087f8c,#075985);
    color:white;
    padding:25px 15px;
    text-align:center;
}
header h1{margin:0;font-size:32px}
header p{margin:8px 0 0}

nav{
    background:white;
    position:sticky;
    top:0;
    z-index:10;
    display:flex;
    justify-content:center;
    flex-wrap:wrap;
    box-shadow:0 2px 8px #0002;
}
nav a{
    text-decoration:none;
    color:#075985;
    padding:15px 12px;
    font-weight:bold;
}

.container{
    max-width:1000px;
    margin:auto;
    padding:20px;
}
.hero{
    background:white;
    margin-top:20px;
    padding:35px 20px;
    border-radius:18px;
    text-align:center;
    box-shadow:0 4px 15px #0001;
}
.hero h2{font-size:28px;color:#087f8c}
.btn{
    display:inline-block;
    border:0;
    background:#087f8c;
    color:white;
    padding:12px 22px;
    border-radius:10px;
    cursor:pointer;
    margin:5px;
    font-size:16px;
}
.btn:hover{background:#075985}

section{
    scroll-margin-top:100px;
    margin-top:25px;
}
.card{
    background:white;
    padding:20px;
    margin:12px 0;
    border-radius:15px;
    box-shadow:0 3px 12px #0001;
}
.grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:15px;
}
input,select{
    width:100%;
    padding:12px;
    margin:7px 0 15px;
    border:1px solid #ccd6df;
    border-radius:9px;
    font-size:15px;
}
h2{color:#075985}
h3{color:#087f8c}

table{
    width:100%;
    border-collapse:collapse;
    margin-top:15px;
}
th,td{
    border:1px solid #ddd;
    padding:9px;
    text-align:center;
}
th{
    background:#087f8c;
    color:white;
}

.message{
    display:none;
    padding:12px;
    background:#dff7e8;
    color:#126b38;
    border-radius:8px;
    margin:10px 0;
}

footer{
    margin-top:40px;
    padding:30px;
    background:#073b4c;
    color:white;
    text-align:center;
}

.admin-panel{display:none}

@media(max-width:600px){
    header h1{font-size:25px}
    nav a{font-size:13px;padding:12px 7px}
    .container{padding:12px}
    table{font-size:12px}
    th,td{padding:6px}
}
</style>
</head>

<body>

<header>
    <h1>🏥 شفاخانه صحت</h1>
    <p>ارائه خدمات صحی با کیفیت برای همه</p>
</header>

<nav>
    <a href="#home">خانه</a>
    <a href="#services">خدمات</a>
    <a href="#doctors">داکتران</a>
    <a href="#register">ثبت مریض</a>
    <a href="#appointment">نوبت</a>
    <a href="#admin" onclick="openAdmin()">🔐 مدیریت</a>
</nav>

<div class="container">

<section id="home">
<div class="hero">
    <h2>به شفاخانه صحت خوش آمدید</h2>
    <p>
        در این وب‌سایت می‌توانید خدمات شفاخانه، داکتران،
        ثبت مریض و نوبت‌دهی را مشاهده کنید.
    </p>
    <a href="#appointment" class="btn">گرفتن نوبت</a>
</div>
</section>

<section id="services">
<h2>🩺 خدمات ما</h2>
<div class="grid">
    <div class="card">
        <h3>طب عمومی</h3>
        <p>معاینه و مشاوره صحی عمومی.</p>
    </div>
    <div class="card">
        <h3>قلب و عروق</h3>
        <p>خدمات مربوط به بیماری‌های قلبی.</p>
    </div>
    <div class="card">
        <h3>اطفال</h3>
        <p>مراقبت و معاینه کودکان.</p>
    </div>
    <div class="card">
        <h3>لابراتوار</h3>
        <p>انجام آزمایش‌های طبی.</p>
    </div>
</div>
</section>

<section id="doctors">
<h2>👨‍⚕️ داکتران</h2>

<div class="card">
<input id="doctorSearch" type="text"
placeholder="نام داکتر را جستجو کنید..."
onkeyup="searchDoctors()">
</div>

<div id="doctorList" class="grid">

<div class="card doctor">
<h3>دکتر احمد محمدی</h3>
<p>متخصص طب عمومی</p>
<p>ساعات کاری: ۸ صبح تا ۱۲ ظهر</p>
</div>

<div class="card doctor">
<h3>دکتر فاطمه حسینی</h3>
<p>متخصص اطفال</p>
<p>ساعات کاری: ۹ صبح تا ۲ بعد از ظهر</p>
</div>

<div class="card doctor">
<h3>دکتر محمود رحیمی</h3>
<p>متخصص قلب و عروق</p>
<p>ساعات کاری: ۱۰ صبح تا ۳ بعد از ظهر</p>
</div>

</div>
</section>

<section id="register">
<h2>📝 ثبت مریض</h2>

<div class="card">
<div id="patientMessage" class="message"></div>

<label>نام مریض</label>
<input id="patientName" type="text" placeholder="نام کامل">

<label>سن</label>
<input id="patientAge" type="number" placeholder="سن">

<label>شماره تماس</label>
<input id="patientPhone" type="text" placeholder="07xxxxxxxx">

<label>جنسیت</label>
<select id="patientGender">
<option value="">انتخاب کنید</option>
<option>مرد</option>
<option>زن</option>
</select>

<button class="btn" onclick="savePatient()">ثبت مریض</button>
</div>
</section>

<section id="appointment">
<h2>📅 گرفتن نوبت</h2>

<div class="card">
<div id="appointmentMessage" class="message"></div>

<label>نام</label>
<input id="appName" type="text" placeholder="نام کامل">

<label>شماره تماس</label>
<input id="appPhone" type="text" placeholder="07xxxxxxxx">

<label>بخش</label>
<select id="appDepartment">
<option>طب عمومی</option>
<option>قلب و عروق</option>
<option>اطفال</option>
<option>لابراتوار</option>
</select>

<label>تاریخ</label>
<input id="appDate" type="date">

<label>ساعت</label>
<input id="appTime" type="time">

<button class="btn" onclick="saveAppointment()">ثبت نوبت</button>
</div>
</section>

<section id="admin">
<h2>🔐 مدیریت شفاخانه</h2>

<div class="card" id="adminLogin">
<h3>ورود مدیر</h3>

<label>نام کاربری</label>
<input id="adminUser" type="text" placeholder="نام کاربری">

<label>رمز عبور</label>
<input id="adminPass" type="password" placeholder="رمز عبور">

<button class="btn" onclick="loginAdmin()">ورود</button>

<p>نام کاربری: <b>admin</b></p>
<p>رمز عبور: <b>1234</b></p>
</div>

<div class="admin-panel" id="adminPanel">

<div class="card">
<h3>📊 معلومات سیستم</h3>
<p>تعداد مریضان: <b id="patientCount">0</b></p>
<p>تعداد نوبت‌ها: <b id="appointmentCount">0</b></p>
<button class="btn" onclick="logoutAdmin()">خروج</button>
</div>

<div class="card">
<h3>👥 لیست مریضان</h3>
<div style="overflow-x:auto">
<table>
<thead>
<tr>
<th>نام</th>
<th>سن</th>
<th>شماره</th>
<th>جنسیت</th>
<th>عملیات</th>
</tr>
</thead>
<tbody id="patientTable"></tbody>
</table>
</div>
</div>

<div class="card">
<h3>📅 لیست نوبت‌ها</h3>
<div style="overflow-x:auto">
<table>
<thead>
<tr>
<th>نام</th>
<th>شماره</th>
<th>بخش</th>
<th>تاریخ</th>
<th>ساعت</th>
</tr>
</thead>
<tbody id="appointmentTable"></tbody>
</table>
</div>
</div>

</div>
</section>

</div>

<footer>
<p>🏥 شفاخانه صحت</p>
<p>این وب‌سایت یک پروژه دانشجویی است.</p>
<p>© 2026 تمام حقوق محفوظ است.</p>
</footer>

<script>

let patients =
JSON.parse(localStorage.getItem("patients")) || [];

let appointments =
JSON.parse(localStorage.getItem("appointments")) || [];


/* ثبت مریض */
function savePatient(){

    let name = document.getElementById("patientName").value.trim();
    let age = document.getElementById("patientAge").value;
    let phone = document.getElementById("patientPhone").value.trim();
    let gender = document.getElementById("patientGender").value;

    if(!name || !age || !phone || !gender){
        alert("لطفاً تمام معلومات را وارد کنید.");
        return;
    }

    patients.push({
        id: Date.now(),
        name:name,
        age:age,
        phone:phone,
        gender:gender
    });

    localStorage.setItem("patients",JSON.stringify(patients));

    document.getElementById("patientName").value="";
    document.getElementById("patientAge").value="";
    document.getElementById("patientPhone").value="";
    document.getElementById("patientGender").value="";

    showMessage("patientMessage","مریض با موفقیت ثبت شد.");

    updateStats();
    displayAdminPatients();
}


/* ثبت نوبت */
function saveAppointment(){

    let name=document.getElementById("appName").value.trim();
    let phone=document.getElementById("appPhone").value.trim();
    let department=document.getElementById("appDepartment").value;
    let date=document.getElementById("appDate").value;
    let time=document.getElementById("appTime").value;

    if(!name || !phone || !date || !time){
        alert("لطفاً تمام معلومات را وارد کنید.");
        return;
    }

    appointments.push({
        name:name,
        phone:phone,
        department:department,
        date:date,
        time:time
    });

    localStorage.setItem(
        "appointments",
        JSON.stringify(appointments)
    );

    document.getElementById("appName").value="";
    document.getElementById("appPhone").value="";
    document.getElementById("appDate").value="";
    document.getElementById("appTime").value="";

    showMessage(
        "appointmentMessage",
        "نوبت با موفقیت ثبت شد."
    );

    updateStats();
    displayAppointments();
}


/* پیام */
function showMessage(id,text){

    let box=document.getElementById(id);

    box.innerText=text;
    box.style.display="block";

    setTimeout(function(){
        box.style.display="none";
    },3000);
}


/* جستجوی داکتر */
function searchDoctors(){

    let search =
    document.getElementById("doctorSearch")
    .value.toLowerCase();

    let doctors =
    document.querySelectorAll(".doctor");

    doctors.forEach(function(doctor){

        let text =
        doctor.innerText.toLowerCase();

        if(text.includes(search)){
            doctor.style.display="block";
        }else{
            doctor.style.display="none";
        }

    });
}


/* ورود مدیریت */
function openAdmin(){

    setTimeout(function(){

        document
        .getElementById("adminUser")
        .focus();

    },500);
}


function loginAdmin(){

    let user =
    document.getElementById("adminUser").value;

    let pass =
    document.getElementById("adminPass").value;

    if(user==="admin" && pass==="1234"){

        document.getElementById("adminLogin")
        .style.display="none";

        document.getElementById("adminPanel")
        .style.display="block";

        displayAdminPatients();
        displayAppointments();
        updateStats();

    }else{

        alert("نام کاربری یا رمز عبور اشتباه است.");

    }
}


/* خروج مدیر */
function logoutAdmin(){

    document.getElementById("adminLogin")
    .style.display="block";

    document.getElementById("adminPanel")
    .style.display="none";

    document.getElementById("adminUser").value="";
    document.getElementById("adminPass").value="";
}


/* نمایش مریضان */
function displayAdminPatients(){

    let table =
    document.getElementById("patientTable");

    table.innerHTML="";

    patients.forEach(function(patient){

        let row=document.createElement("tr");

        row.innerHTML=`
        <td>${patient.name}</td>
        <td>${patient.age}</td>
        <td>${patient.phone}</td>
        <td>${patient.gender}</td>
        <td>
        <button class="btn"
        onclick="editPatient(${patient.id})">
        ویرایش
        </button>

        <button class="btn"
        onclick="deletePatient(${patient.id})">
        حذف
        </button>
        </td>
        `;

        table.appendChild(row);

    });
}


/* حذف مریض */
function deletePatient(id){

    if(!confirm("آیا مطمئن هستید که می‌خواهید حذف کنید؟")){
        return;
    }

    patients =
    patients.filter(function(patient){
        return patient.id !== id;
    });

    localStorage.setItem(
        "patients",
        JSON.stringify(patients)
    );

    displayAdminPatients();
    updateStats();
}


/* ویرایش مریض */
function editPatient(id){

    let patient =
    patients.find(function(p){
        return p.id === id;
    });

    if(!patient)return;

    let name=prompt("نام مریض:",patient.name);
    if(name===null)return;

    let age=prompt("سن:",patient.age);
    if(age===null)return;

    let phone=prompt("شماره تماس:",patient.phone);
    if(phone===null)return;

    patient.name=name;
    patient.age=age;
    patient.phone=phone;

    localStorage.setItem(
        "patients",
        JSON.stringify(patients)
    );

    displayAdminPatients();
}


/* نمایش نوبت‌ها */
function displayAppointments(){

    let table =
    document.getElementById("appointmentTable");

    table.innerHTML="";

    appointments.forEach(function(app){

        let row=document.createElement("tr");

        row.innerHTML=`
        <td>${app.name}</td>
        <td>${app.phone}</td>
        <td>${app.department}</td>
        <td>${app.date}</td>
        <td>${app.time}</td>
        `;

        table.appendChild(row);

    });
}


/* آمار */
function updateStats(){

    document.getElementById("patientCount")
    .innerText=patients.length;

    document.getElementById("appointmentCount")
    .innerText=appointments.length;
}


/* اجرای اولیه */
updateStats();
displayAdminPatients();
displayAppointments();

</script>

</body>
</html>
