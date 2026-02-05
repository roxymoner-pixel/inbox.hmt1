# inbox.hmt1
<!DOCTYPE html>
<html lang="fa">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>لیست شبانه</title>

<style>
    body {
        margin: 0;
        font-family: sans-serif;
        background: #0e0e0e;
        color: #fff;
    }

    .screen {
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px;
    }

    .box {
        width: 100%;
        max-width: 380px;
        background: #1a1a1a;
        border-radius: 16px;
        padding: 20px;
    }

    h2 {
        text-align: center;
        margin-bottom: 16px;
    }

    h3 {
        margin-top: 24px;
        border-bottom: 1px solid #333;
        padding-bottom: 6px;
    }

    .task {
        display: flex;
        align-items: center;
        margin: 10px 0;
        gap: 10px;
    }

    input[type="checkbox"] {
        transform: scale(1.3);
    }

    input[type="password"] {
        width: 100%;
        padding: 12px;
        border-radius: 10px;
        border: none;
        margin-bottom: 12px;
    }

    button {
        width: 100%;
        padding: 14px;
        margin-top: 20px;
        border: none;
        border-radius: 12px;
        background: #444;
        color: #aaa;
        font-size: 16px;
    }

    button.active {
        background: #ff4d6d;
        color: white;
    }
</style>
</head>

<body>

<!-- صفحه رمز -->
<div class="screen" id="loginScreen">
    <div class="box">
        <h2>رمز رو وارد کن 🔒</h2>
        <input type="password" id="password" placeholder="رمز">
        <button onclick="checkPassword()">ورود</button>
    </div>
</div>

<!-- صفحه لیست‌ها -->
<div class="screen" id="mainScreen" style="display:none;">
    <div class="box">

        <h3>کار های بشار الستایش</h3>
        <div class="task"><input type="checkbox" class="taskBox">کار ۱</div>
        <div class="task"><input type="checkbox" class="taskBox">کار ۲</div>
        <div class="task"><input type="checkbox" class="taskBox">کار ۳</div>

        <h3>کار های روکسی خوشگله</h3>
        <div class="task"><input type="checkbox" class="taskBox">کار ۱</div>
        <div class="task"><input type="checkbox" class="taskBox">کار ۲</div>
        <div class="task"><input type="checkbox" class="taskBox">کار ۳</div>

        <button id="goodNightBtn" onclick="resetTasks()">شب بخیر 🌙</button>
    </div>
</div>

<script>
    const CORRECT_PASSWORD = "1234"; // ← رمز رو اینجا عوض کن

    function checkPassword() {
        const pass = document.getElementById("password").value;
        if (pass === CORRECT_PASSWORD) {
            document.getElementById("loginScreen").style.display = "none";
            document.getElementById("mainScreen").style.display = "flex";
        } else {
            alert("رمز اشتباهه");
        }
    }

    const checkboxes = document.querySelectorAll(".taskBox");
    const btn = document.getElementById("goodNightBtn");

    checkboxes.forEach(cb => {
        cb.addEventListener("change", () => {
            const allChecked = [...checkboxes].every(c => c.checked);
            if (allChecked) {
                btn.classList.add("active");
            } else {
                btn.classList.remove("active");
            }
        });
    });

    function resetTasks() {
        if (!btn.classList.contains("active")) return;
        checkboxes.forEach(c => c.checked = false);
        btn.classList.remove("active");
        alert("شب بخیر 😴\nروز جدید شروع شد");
    }
</script>

</body>
</html>
const CORRECT_PASSWORD = "1234";<div class="task"><input type="checkbox" class="taskBox">کار جدید</div>
