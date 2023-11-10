<!DOCTYPE html>
<html>
<head>
    <title>Relógio Digital</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-image: url('https://sua-imagem-aqui.com');
            background-size: cover;
            color: #61dafb;
            font-family: Arial, sans-serif;
        }
        #relogio {
            font-size: 60px;
            margin-bottom: 50px; /* Aumenta o espaço abaixo do relógio */
        }
        #data {
            font-size: 30px;
        }
    </style>
</head>
<body>
    <div id="relogio"></div>
    <div id="data"></div>

    <script>
        function atualizarRelogio() {
            var agora = new Date();
            var horas = agora.getHours();
            var minutos = agora.getMinutes();
            var segundos = agora.getSeconds();

            horas = horas < 10 ? "0" + horas : horas;
            minutos = minutos < 10 ? "0" + minutos : minutos;
            segundos = segundos < 10 ? "0" + segundos : segundos;

            var tempo = horas + ":" + minutos + ":" + segundos;

            document.getElementById('relogio').textContent = tempo;

            var dia = agora.getDate();
            var mes = agora.getMonth() + 1; // Os meses começam do 0
            var ano = agora.getFullYear();

            dia = dia < 10 ? "0" + dia : dia;
            mes = mes < 10 ? "0" + mes : mes;

            var dataAtual = dia + "/" + mes + "/" + ano;

            document.getElementById('data').textContent = dataAtual;
        }

        setInterval(atualizarRelogio, 1000);
    </script>
</body>
</html>
