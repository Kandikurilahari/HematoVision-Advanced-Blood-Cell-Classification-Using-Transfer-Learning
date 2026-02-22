The project is in file format.
from flask import Flask, render_template, request
import numpy as np
from tensorflow.keras.models import load_model
from tensorflow.keras.preprocessing import image
import os

app = Flask(__name__)

# Load trained model
model = load_model("blood_cell_model.h5")

# Class labels (change according to your training order)
classes = ['Eosinophil', 'Lymphocyte', 'Monocyte', 'Neutrophil']

@app.route('/')
def home():
    return render_template('index.html')

@app.route('/predict', methods=['POST'])
def predict():
    file = request.files['file']
    
    if file:
        filepath = os.path.join("static", file.filename)
        file.save(filepath)

        # Preprocess image
        img = image.load_img(filepath, target_size=(224, 224))
        img_array = image.img_to_array(img)
        img_array = np.expand_dims(img_array, axis=0)
        img_array = img_array / 255.0

        prediction = model.predict(img_array)
        predicted_class = classes[np.argmax(prediction)]

        return render_template('index.html', prediction=predicted_class)

    return render_template('index.html', prediction="No file selected")

if __name__ == "__main__":
    app.run(debug=True)


    <!DOCTYPE html>
<html>
<head>
    <title>HematoVision - Blood Cell Classification</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #ff9966, #ff5e62);
            text-align: center;
        }

        .container {
            width: 50%;
            margin: 80px auto;
            background: white;
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0px 10px 20px rgba(0,0,0,0.2);
        }

        h1 {
            color: #e74c3c;
        }

        p {
            color: #555;
            font-size: 18px;
        }

        input[type="file"] {
            margin-top: 20px;
            padding: 10px;
        }

        .btn {
            margin-top: 20px;
            padding: 10px 25px;
            background-color: #e74c3c;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }

        .btn:hover {
            background-color: #c0392b;
        }

        .result {
            margin-top: 30px;
            font-size: 20px;
            font-weight: bold;
            color: green;
        }

        footer {
            margin-top: 40px;
            color: white;
            font-size: 14px;
        }
    </style>
</head>

<body>

    <div class="container">
        <h1>HematoVision</h1>
        <p>Blood Cell Classification System</p>

        <input type="file" id="imageUpload"><br>

        <button class="btn" onclick="showResult()">Predict</button>

        <div class="result" id="resultText"></div>
    </div>

    <footer>
        © 2026 HematoVision Project
    </footer>

    <script>
        function showResult() {
            let result = document.getElementById("resultText");
            result.innerHTML = "Prediction Result: Neutrophil (Sample Output)";
        }
    </script>

</body>
</html>
