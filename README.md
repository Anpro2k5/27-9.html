
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Công cụ tính toán số học</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 30px;
            color:red
        }

        .section {
            margin-bottom: 20px;
        }

        input {
            margin: 5px;
        }

        button {
            margin: 5px;
            padding: 5px 10px;
        }
    </style>
</head>
<body>

    <h1>Công cụ tính toán số học</h1>

    <!-- Tính tổng từ 1 đến n -->
    <div class="section">
        <h2>1.Tính tổng từ 1 đến n</h2>
        <input type="number" id="n" placeholder="Nhập số n">
        <button onclick="calculateSum()">Tính tổng</button>
        <p id="resultSum"></p>
    </div>

    <!-- Tính tổng các số chẵn từ 1 đến n -->
    <div class="section">
        <h2>2.Tính tổng các số chẵn từ 1 đến n</h2>
        <button onclick="calculateEvenSum()">Tính tổng số chẵn</button>
        <p id="resultEvenSum"></p>
    </div>

    <!-- Tính tổng các số lẻ từ 1 đến n -->
    <div class="section">
        <h2>3.Tính tổng các số lẻ từ 1 đến n</h2>
        <button onclick="calculateOddSum()">Tính tổng số lẻ</button>
        <p id="resultOddSum"></p>
    </div>

    <!-- Kiểm tra n có phải số nguyên tố không -->
    <div class="section">
        <h2>4.Kiểm tra số nguyên tố</h2>
        <button onclick="checkPrime()">Kiểm tra số nguyên tố</button>
        <p id="resultPrime"></p>
    </div>

    <!-- Tìm UCLN của 2 số a và b -->
    <div class="section">
        <h2>5.Tìm UCLN của 2 số a và b</h2>
        <input type="number" id="a" placeholder="Nhập số a">
        <input type="number" id="b" placeholder="Nhập số b">
        <button onclick="calculateGCD()">Tìm UCLN</button>
        <p id="resultGCD"></p>
    </div>

    <script>
        // Tính tổng từ 1 đến n
        function calculateSum() {
            var n = parseInt(document.getElementById("n").value);
            var sum = 0;
            for (var i = 1; i <= n; i++) {
                sum += i;
            }
            document.getElementById("resultSum").innerText = "Tổng từ 1 đến " + n + " là: " + sum;
        }

        // Tính tổng các số chẵn từ 1 đến n
        function calculateEvenSum() {
            var n = parseInt(document.getElementById("n").value);
            var evenSum = 0;
            for (var i = 2; i <= n; i += 2) {
                evenSum += i;
            }
            document.getElementById("resultEvenSum").innerText = "Tổng các số chẵn từ 1 đến " + n + " là: " + evenSum;
        }

        // Tính tổng các số lẻ từ 1 đến n
        function calculateOddSum() {
            var n = parseInt(document.getElementById("n").value);
            var oddSum = 0;
            for (var i = 1; i <= n; i += 2) {
                oddSum += i;
            }
            document.getElementById("resultOddSum").innerText = "Tổng các số lẻ từ 1 đến " + n + " là: " + oddSum;
        }

        // Kiểm tra số nguyên tố
        function checkPrime() {
            var n = parseInt(document.getElementById("n").value);
            var isPrime = true;
            if (n <= 1) {
                isPrime = false;
            } else {
                for (var i = 2; i <= Math.sqrt(n); i++) {
                    if (n % i === 0) {
                        isPrime = false;
                        break;
                    }
                }
            }
            if (isPrime) {
                document.getElementById("resultPrime").innerText = n + " là số nguyên tố.";
            } else {
                document.getElementById("resultPrime").innerText = n + " không phải là số nguyên tố.";
            }
        }

        // Tìm UCLN của 2 số a và b
        function calculateGCD() {
            var a = parseInt(document.getElementById("a").value);
            var b = parseInt(document.getElementById("b").value);
            while (b != 0) {
                var temp = b;
                b = a % b;
                a = temp;
            }
            document.getElementById("resultGCD").innerText = "UCLN của hai số là: " + a;
        }
    </script>
</body>
