```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily and Monthly Checklist</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #fef5f4;
            color: #d57c70;
            margin: 20px;
        }
        h1 {
            text-align: center;
            font-size: 24px;
            margin-bottom: 20px;
        }
        .container {
            display: grid;
            grid-template-columns: 1fr;
            grid-template-rows: auto auto;
            gap: 20px;
        }
        .calendar, .monthly {
            border: 2px solid #f7cdc2;
            padding: 10px;
            border-radius: 10px;
            background-color: #fff;
        }
        .calendar h2, .monthly h2 {
            font-size: 18px;
            margin-bottom: 10px;
        }
        .calendar-table {
            width: 100%;
            border-collapse: collapse;
        }
        .calendar-table th, .calendar-table td {
            border: 1px solid #f7cdc2;
            text-align: center;
            padding: 10px;
            width: 14.28%;
            height: 80px;
            vertical-align: top;
            cursor: pointer;
        }
        .calendar-table th {
            background-color: #fbeae7;
            font-weight: bold;
        }
        .monthly table {
            width: 100%;
            border-collapse: collapse;
            font-size: 14px;
        }
        .monthly table, .monthly th, .monthly td {
            border: 1px solid #f7cdc2;
        }
        .monthly th, .monthly td {
            text-align: center;
            padding: 8px;
        }
        .monthly th {
            background-color: #fbeae7;
        }
        .popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border: 2px solid #f7cdc2;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            z-index: 1000;
        }
        .popup h3 {
            margin-top: 0;
        }
        .popup textarea {
            width: 100%;
            height: 100px;
            margin-bottom: 10px;
        }
        .popup button {
            padding: 5px 10px;
            border: none;
            background-color: #d57c70;
            color: #fff;
            cursor: pointer;
            border-radius: 5px;
        }
        .popup button:hover {
            background-color: #f7cdc2;
        }
        .overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 999;
        }
    </style>
</head>
<body>
    <h1>일별 및 월별 체크리스트</h1>
    <div class="container">
        <div class="calendar">
            <h2>일별 일정 (달력 형식)</h2>
            <table class="calendar-table">
                <thead>
                    <tr>
                        <th>일</th>
                        <th>월</th>
                        <th>화</th>
                        <th>수</th>
                        <th>목</th>
                        <th>금</th>
                        <th>토</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td></td><td></td><td></td><td onclick="openPopup(1)">1</td><td onclick="openPopup(2)">2</td><td onclick="openPopup(3)">3</td><td onclick="openPopup(4)">4</td>
                    </tr>
                    <tr>
                        <td onclick="openPopup(5)">5</td><td onclick="openPopup(6)">6</td><td onclick="openPopup(7)">7</td><td onclick="openPopup(8)">8</td><td onclick="openPopup(9)">9</td><td onclick="openPopup(10)">10</td><td onclick="openPopup(11)">11</td>
                    </tr>
                    <tr>
                        <td onclick="openPopup(12)">12</td><td onclick="openPopup(13)">13</td><td onclick="openPopup(14)">14</td><td onclick="openPopup(15)">15</td><td onclick="openPopup(16)">16</td><td onclick="openPopup(17)">17</td><td onclick="openPopup(18)">18</td>
                    </tr>
                    <tr>
                        <td onclick="openPopup(19)">19</td><td onclick="openPopup(20)">20</td><td onclick="openPopup(21)">21</td><td onclick="openPopup(22)">22</td><td onclick="openPopup(23)">23</td><td onclick="openPopup(24)">24</td><td onclick="openPopup(25)">25</td>
                    </tr>
                    <tr>
                        <td onclick="openPopup(26)">26</td><td onclick="openPopup(27)">27</td><td onclick="openPopup(28)">28</td><td onclick="openPopup(29)">29</td><td onclick="openPopup(30)">30</td><td onclick="openPopup(31)">31</td><td></td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="monthly">
            <h2>월별 일정</h2>
            <table>
                <thead>
                    <tr>
                        <th>날짜</th>
                        <th>일정</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>1일</td>
                        <td>일정 입력</td>
                    </tr>
                    <tr>
                        <td>2일</td>
                        <td>일정 입력</td>
                    </tr>
                    <tr>
                        <td>3일</td>
                        <td>일정 입력</td>
                    </tr>
                    <!-- Add more rows as needed -->
                </tbody>
            </table>
        </div>
    </div>
    <div class="popup" id="popup">
        <h3>일정 입력</h3>
        <textarea id="taskDetails" placeholder="일정을 입력하세요..."></textarea>
        <button onclick="closePopup()">저장</button>
    </div>
    <div class="overlay" id="overlay"></div>
    <script>
        function openPopup(day) {
            document.getElementById('popup').style.display = 'block';
            document.getElementById('overlay').style.display = 'block';
            document.getElementById('taskDetails').value = `날짜: ${day}일
`;
        }

        function closePopup() {
            document.getElementById('popup').style.display = 'none';
            document.getElementById('overlay').style.display = 'none';
        }
    </script>
</body>
</html>

```