<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Neon Login Page</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        font-family: "Poppins", sans-serif;
        background: #05070f;
        display: flex;
        justify-content: center;
        align-items: center;
        overflow: hidden;
        color: #fff;
    }

    /* Animated Background Grid */
    .grid {
        position: absolute;
        width: 200%;
        height: 200%;
        background: 
            linear-gradient(90deg, #0ff2, #0ff2 1px, transparent 1px),
            linear-gradient(#0ff2, #0ff2 1px, transparent 1px);
        background-size: 40px 40px;
        animation: moveGrid 15s linear infinite;
        pointer-events: none;
    }
    @keyframes moveGrid {
        0% { transform: translate(0, 0); }
        100% { transform: translate(-200px, -200px); }
    }

    .card {
        width: 330px;
        padding: 40px;
        background: rgba(15, 25, 50, 0.55);
        border-radius: 20px;
        backdrop-filter: blur(12px);
        box-shadow: 0 0 20px #00eaff33, 0 0 50px #00eaff22 inset;
        border: 1px solid #00eaff55;
        position: relative;
    }

    .title {
        text-align: center;
        font-size: 26px;
        margin-bottom: 25px;
        color: #00eaff;
        text-shadow: 0 0 10px #00eaff, 0 0 20px #00eaff55;
    }

    input {
        width: 100%;
        padding: 13px 15px;
        margin: 10px 0;
        background: #0a1228;
        border: 1px solid #00eaff55;
        border-radius: 10px;
        color: #fff;
        font-size: 14px;
        outline: none;
        transition: .2s;
    }

    input:focus {
        border-color: #00eaff;
        box-shadow: 0 0 10px #00eaff66;
    }

    button {
        width: 100%;
        padding: 13px;
        margin-top: 15px;
        background: #00eaff;
        border: none;
        border-radius: 10px;
        cursor: pointer;
        font-size: 15px;
        font-weight: 600;
        color: #000;
        box-shadow: 0 0 20px #00eaffaa;
        transition: .25s;
    }

    button:hover {
        transform: translateY(-2px);
        box-shadow: 0 0 30px #00eaffcc;
    }

    .status {
        text-align: center;
        margin-top: 15px;
        font-size: 14px;
        opacity: 0.9;
    }
</style>
</head>
<body>

<div class="grid"></div>

<div class="card">
    <div class="title">Neon Login</div>

    <input id="user" type="text" placeholder="Username">
    <input id="pass" type="password" placeholder="Password">

    <button onclick="login()">Login</button>

    <div class="status" id="status"></div>
</div>

<script>
function login() {
    const user = document.getElementById("user").value.trim();
    const pass = document.getElementById("pass").value.trim();
    const status = document.getElementById("status");

    if (user === "" || pass === "") {
        status.style.color = "#ff4d4d";
        status.textContent = "Please fill in all fields.";
        return;
    }

    if (user === "admin" && pass === "1234") {
        status.style.color = "#00ffa6";
        status.textContent = "Login successful!";
    } else {
        status.style.color = "#ff4d4d";
        status.textContent = "Incorrect username or password.";
    }
}
</script>

</body>
</html>
