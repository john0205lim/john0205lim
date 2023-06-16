- 👋 Hi, I’m @john0205lim
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
john0205lim/john0205lim is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html>
<head>
    <title>이차곡선 그리기</title>
</head>
<body>
    <canvas id="myCanvas" width="800" height="600"></canvas>
    <script>
        var canvas = document.getElementById("myCanvas");
        var ctx = canvas.getContext("2d");

        function drawQuadraticCurve(curveType) {
            var a, b, c;
            if (curveType === "포물선") {
                a = Number(prompt("포물선의 a 값을 입력하세요:"));
                b = Number(prompt("포물선의 b 값을 입력하세요:"));
                c = Number(prompt("포물선의 c 값을 입력하세요:"));
            } else if (curveType === "타원") {
                a = Number(prompt("타원의 가로 반지름을 입력하세요:"));
                b = Number(prompt("타원의 세로 반지름을 입력하세요:"));
                c = 0;  // 타원의 경우 c 값은 0
            } else if (curveType === "쌍곡선") {
                a = Number(prompt("쌍곡선의 a 값을 입력하세요:"));
                b = Number(prompt("쌍곡선의 b 값을 입력하세요:"));
                c = Number(prompt("쌍곡선의 c 값을 입력하세요:"));
            } else {
                alert("잘못된 선택입니다.");
                return;
            }

            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // 이차곡선 그리기
            ctx.beginPath();
            ctx.moveTo(0, canvas.height);
            for (var x = 0; x <= canvas.width; x++) {
                var y = a * Math.pow(x, 2) + b * x + c;
                ctx.lineTo(x, canvas.height - y);
            }
            ctx.strokeStyle = "red";
            ctx.lineWidth = 2;
            ctx.stroke();
            ctx.closePath();
        }

        var curveType = prompt("그리고자 하는 이차곡선을 선택하세요 (포물선, 타원, 쌍곡선):");
        drawQuadraticCurve(curveType);
    </script>
</body>
</html>
