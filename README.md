<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Controle ESP32</title>
    <style>
        button {
            padding: 20px;
            font-size: 20px;
            cursor: pointer;
            margin: 10px;
            border: none;
            border-radius: 15px;
            transition: background-color 0.3s;
        }

        #ledOn {
            background-color: blue;
        }

        #ledOff {
            background-color: red;
        }
    </style>
</head>

<body>
    <button id="ledOn" onclick="toggleLED('on')">Ligar LED</button>
    <button id="ledOff" onclick="toggleLED('off')">Desligar LED</button>

    <script>
        function toggleLED(state) {
            let xhr = new XMLHttpRequest();
            let ip = '192.168.1.244';
            let url = 'http://' + ip + '/led?state=' + state;
            xhr.open('GET', url, true);
            xhr.send();
        }
    </script>
</body>

</html>

