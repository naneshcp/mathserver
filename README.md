# Ex.05 Design a Website for Server Side Processing
# Date:05/12/2024
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
 ```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lamp Filament Power Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 50px;
            
            background-color: antiquewhite;
        }
        .container {
            max-width: 500px;
            margin: auto;
        }
        input[type="number"] {
            width: 100%;
            padding: 8px;
            margin: 5px 0;
            box-sizing: border-box;
        }
        button {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Lamp Filament Power Calculator</h1><br><br>
        <label for="intensity">Intensity (I):</label>
        <input type="number" id="intensity" step="any">
        <br><br><br>
        <label for="resistance">Resistance (R):</label>
        <input type="number" id="resistance" step="any">

        <br><br><br><br>

        <button onclick="calculatePower()">Calculate Power</button>
        
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculatePower() {
            let intensity = document.getElementById('intensity').value;
            let resistance = document.getElementById('resistance').value;

            if (intensity === '' || resistance === '') {
                alert('Please enter both intensity and resistance values.');
                return;
            }

            intensity = parseFloat(intensity);
            resistance = parseFloat(resistance);

            let power = Math.pow(intensity, 2) * resistance;

            document.getElementById('result').innerHTML = `Power (P) = ${power.toFixed(2)} watts`;
        }
    </script>
</body>
</html>
```



# SERVER SIDE PROCESSING:
```from django.shortcuts import render 
def lipower(request): 
    context={} 
    context['power'] = "0" 
    context['i'] = "0" 
    context['r'] = "0" 
    if request.method == 'POST': 
        print("POST method is used")
        i = request.POST.get('intensity','0')
        r = request.POST.get('resistance','0')
        print('request=',request) 
        print('intensity=',i) 
        print('resistance=',r) 
        power = (int(i) * int(i)) * (int(r))
        context['power'] = power 
        context['i'] = i
        context['r'] = r 
        print('Power=',power) 
    return render(request,'calculator.html',context)
```

# HOMEPAGE:
![output05(web)i](https://github.com/user-attachments/assets/9561e24c-7a0a-4d9a-93d6-20e72d80295b)
![output05(web)cmd](https://github.com/user-attachments/assets/35d4ef66-6bed-46a6-bba7-673dff5abb68)
![output05(web)ii](https://github.com/user-attachments/assets/de804c0e-ac82-4c05-b6dd-200350a027c7)

# RESULT:
The program for performing server side processing is completed successfully.
