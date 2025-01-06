<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ChatGPT Prompt Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            text-align: center;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        input, select, button {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ddd;
        }
        button {
            background-color: #28a745;
            color: #fff;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
        #output {
            margin-top: 20px;
            padding: 15px;
            background-color: #f1f1f1;
            border: 1px solid #ddd;
            border-radius: 5px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>ChatGPT Prompt Generator</h1>
        <p>Generate powerful prompts for ChatGPT effortlessly!</p>
        
        <form id="promptForm">
            <label for="category">Select a Category:</label>
            <select id="category" required>
                <option value="">--Choose a Category--</option>
                <option value="writing">Writing</option>
                <option value="coding">Coding</option>
                <option value="brainstorming">Brainstorming</option>
                <option value="language">Learning Languages</option>
            </select>

            <label for="idea">Enter Your Idea or Question:</label>
            <input type="text" id="idea" placeholder="E.g., Write a story about..." required>
            
            <button type="button" onclick="generatePrompt()">Generate Prompt</button>
        </form>

        <div id="output">
            <h3>Your ChatGPT Prompt:</h3>
            <p id="promptText"></p>
        </div>
    </div>

    <script>
        function generatePrompt() {
            const category = document.getElementById('category').value;
            const idea = document.getElementById('idea').value;

            if (!category || !idea) {
                alert("Please select a category and enter an idea.");
                return;
            }

            let prompt = "";

            switch (category) {
                case "writing":
                    prompt = `Write a creative story about: ${idea}`;
                    break;
                case "coding":
                    prompt = `Explain how to solve this coding problem: ${idea}`;
                    break;
                case "brainstorming":
                    prompt = `Generate ideas or solutions for: ${idea}`;
                    break;
                case "language":
                    prompt = `Help me learn about: ${idea}`;
                    break;
                default:
                    prompt = "Invalid category selected.";
            }

            document.getElementById('promptText').innerText = prompt;
            document.getElementById('output').style.display = 'block';
        }
        
    </script>
</body>
</html>
