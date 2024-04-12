<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biryani Recipe</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 20px;
        }

        #recipe-steps {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #recipe-steps h2 {
            color: #333;
            text-align: center;
        }

        .step {
            margin-bottom: 20px;
            padding: 10px;
            background-color: #f9f9f9;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Biryani Recipe</h1>
    </header>
    <div id="recipe-steps">
        <!-- Recipe steps will be inserted here -->
    </div>

    <script>
        // Define the steps of the biryani recipe
        const recipeSteps = [
            "Wash and soak rice for 30 minutes.",
            "Heat ghee or oil in a large pot.",
            "Add whole spices and sauté until fragrant.",
            "Add sliced onions and cook until golden brown.",
            "Add ginger-garlic paste and sauté until raw smell disappears.",
            "Add chopped tomatoes and cook until soft.",
            "Add marinated chicken pieces and cook until half done.",
            "Layer soaked rice over the chicken.",
            "Add water and season with salt.",
            "Cover and cook until rice is done and chicken is tender.",
            "Garnish with fried onions, mint, and coriander leaves.",
            "Sprinkle saffron milk on top for aroma.",
            "Serve hot with raita and salad. Enjoy!"
            // Add more steps as needed
        ];

        // Function to simulate asynchronous behavior
        function simulateAsyncOperation(step, callback) {
            setTimeout(() => {
                callback(step);
            }, 1000); // Simulate 1 second delay
        }

        // Function to display each step of the recipe
        function displayStep(step) {
            const recipeStepsContainer = document.getElementById('recipe-steps');
            const stepElement = document.createElement('div');
            stepElement.classList.add('step');
            stepElement.textContent = step;
            recipeStepsContainer.appendChild(stepElement);
        }

        // Function to iterate through recipe steps asynchronously using callbacks
        function displayRecipeSteps() {
            let stepIndex = 0;

            function nextStep() {
                if (stepIndex < recipeSteps.length) {
                    const step = recipeSteps[stepIndex];
                    simulateAsyncOperation(step, (step) => {
                        displayStep(step);
                        stepIndex++;
                        nextStep(); // Move to the next step
                    });
                }
            }

            nextStep();
        }

        // Display the recipe steps when the page loads
        window.onload = function() {
            displayRecipeSteps();
        };
    </script>
</body>
</html>
