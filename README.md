<html>
<head>
    <title> Digital Clock </title>
    <style>
body {
     background:#8ddaeb;
     }
.clock {
         position:absolute;
         width:auto;
		 height:auto;
         border:50px ridge;
		 border-color:#0a0f42;
         top:50%;
         left:50%;
         transform: translateX(-50%) translateY(-50%);
         color:#131f99;
         font-size:50px;
         font-family:Algerian;
         letter-spacing:15px;
        }
</style>
</head>
<body>
<div id="MyClockDisplay" class="clock"></div>

<script>
function ShowTime() {
    var date = new Date();
    var h = date.getHours();
    var m = date.getMinutes();
    var s = date.getSeconds();;
    var session = "AM";

    if (h == 0) {
       h = 12;
    }
    if (h > 12) {
       h = h - 12;
       session = "PM";
    }
    h = (h < 10) ? "0" + h : h;
    m = (m < 10) ? "0" + m : m;
    s = (s < 10) ? "0" + s : s;

    var time = h + ":" + m + ":" + s + " " + session;
    document.getElementById("MyClockDisplay").innerText = time;
    document.getElementById("MyClockDisplay").textContent = time;

    setTimeout(ShowTime, 1000);
}

window.onload = function() {
    ShowTime();
}
</script>
</body>
</html>

