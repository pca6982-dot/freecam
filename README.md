<!DOCTYPE html>
<html>
<head>
    <style>
        /* ضع هنا تصميم CSS الخاص بك */
        body { margin: 0; overflow: hidden; background: transparent; }
        .menu-container {
            position: absolute; bottom: 4vw; left: 50%; transform: translateX(-50%);
            color: white; font-family: sans-serif; text-align: center;
        }
        .crosshair {
            position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
            width: 1.5vw;
        }
    </style>
</head>
<body>
    <div id="ui-wrapper" style="display: none;">
        <div class="menu-container">
            <div id="options-list"></div>
        </div>
        <img class="crosshair" src="https://files.catbox.moe/cm9g47.png">
    </div>

    <script>
        // استقبال الأوامر من ملف الـ Lua
        window.addEventListener('message', function(event) {
            if (event.data.action === "displayFreecam") {
                document.getElementById('ui-wrapper').style.display = event.data.visible ? 'block' : 'none';
            }
        });
    </script>
</body>
</html>
