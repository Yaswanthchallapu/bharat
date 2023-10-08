<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <meta name="description"
        content="
    A temperature converter helps in the conversion of the measurement units of the temperature recorded in a particular unit. Temperature expresses the degree of heat or cold of a solid, liquid, or gas. Temperature is measured using a thermometer.">

    <meta name="keywords" content="temperature converter, convert celsius to fahrenheit, convert fahrenheit to celsius">

    <!-- Favicon -->
    <link rel="shortcut icon" href="./Img/favicon.ico" type="image/x-icon">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css"
        integrity="sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l" crossorigin="anonymous">

    <!-- Style CSS -->
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Mulish:wght@300&display=swap');

*{
    font-family: 'Mulish', sans-serif;
}

body{
    width: 100%;
    height: 100vh;
    background-color:blueviolet;
    display: grid;
    justify-content: center;
    align-items: center;
    place-items: center;
}

#fa{
    font-size: 60px;
}

form{
    background-color: greenyellow;
    padding: 50px;
    display: flex;
    flex-direction: column;
    -webkit-box-shadow: 0 10px 6px -6px blue;
    -moz-box-shadow: 0 10px 6px -6px blue;
    box-shadow: 0 10px 6px -6px skyblue;
    border-radius: 10px;
}

#tempCalc label{
    font-size: 30px;
}

#resultContainer{
    font-size: 35px;
}
    </style>

    <title>Temperature Converter</title>
</head>

<body>

    <h1 class="text-center"> <span id="fa" class="fa"></span> TEMPERATURE CONVERTER</h1>

    <form class="text-center" id="tempCalc" onsubmit="calculateTemp(); return false">
        <label for="temp"><h1>TEMPERATURE<h1></label>
        <div class="row my-3">
            <div class="col">
                <input type="number" step="any" id="temp" class="form-control">
            </div>
            <div class="col">
                <select name="temp_diff" class="form-control" id="temp_diff">
                    <option value="cel"><span>&#176;</span>Celsius</option>
                    <option value="fah"><span>&#176;</span>Fahrenheit</option>
                </select>
            </div>
        </div>

        <!-- <input type="submit" class="d-flex justify-content-center mx-auto" name="temp"> -->
        <button type="CONVERT" class="btn btn-danger d-flex justify-content-center mx-auto my-2">CONVERT</button>
        <br />
        <span id="resultContainer"></span>
    </form>

    <!-- Script JS -->
    <script>console.log('Welcome to 🌡 Temperature Converter');

        const tempLoad = () => {
            let fa = document.getElementById('fa');
            fa.innerHTML = "&#xf2cb";
            fa.style.color = "green";

            setTimeout(() => {
                fa.innerHTML = "&#xf2ca;";
                fa.style.color = "#ffa41b";
            }, 1000)

            setTimeout(() => {
                fa.innerHTML = "&#xf2c9;";
            }, 2000)

            setTimeout(() => {
                fa.innerHTML = "&#xf2c8;";
            }, 3000)

            setTimeout(() => {
                fa.innerHTML = "&#xf2c7;";
                fa.style.color = "#ff5151";
            }, 4000)
        }

        setInterval(() => {
            fa.style.color = "blue";
            tempLoad();
        }, 5000);


        tempLoad();

        const calculateTemp = () => {
            const numberTemp = document.getElementById('temp').value;
            // console.log(numberTemp);

            const tempSelected = document.querySelector('#temp_diff');
            const valeTemp = temp_diff.options[tempSelected.selectedIndex].value;
            // console.log(valeTemp);


            // Convert temperature from Celcius to Fahrenheit
            const celTOfah = (cel) => {
                let fahrenheit = (cel * (9 / 5) + 32);
                return fahrenheit;
            }

            // Convert temperature from Fahrenheit to Celsius
            const fahTOcel = (fehr) => {
                let celsius = ((fehr - 32) * 5 / 9);
                return celsius;
            }

            let result;
            if (valeTemp == "cel") {
                result = celTOfah(numberTemp);
                document.getElementById('resultContainer').innerHTML = `= ${result}°Fahrenheit`;
            } else {
                result = fahTOcel(numberTemp);
                document.getElementById('resultContainer').innerHTML = `= ${result}°Celsius`;
            }

            setTimeout(() => {
                window.location.reload();
            }, 1500);
        }
        </script>

    <!-- Font Awesome -->
    <script src="https://kit.fontawesome.com/c387a6ff36.js" crossorigin="anonymous"></script>

    <!-- Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
        integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
        crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-Piv4xVNRyMGpqkS2by6br4gNJ7DXjqk09RmUpJ8jgGtD7zP9yug3goQfGII0yAns"
        crossorigin="anonymous"></script>
</body>

</html
