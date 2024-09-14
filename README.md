<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>To-Do Checklist</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>My To-Do List</h1>
        
        <div class="input-container">
            <input type="text" id="new-task" placeholder="Add a new task...">
            <button id="add-task">Add Task</button>
        </div>

        <ul id="task-list"></ul>
    </div>

    <script>
        // Adding a task
        document.getElementById('add-task').addEventListener('click', function() {
            const taskText = document.getElementById('new-task').value;
            if (taskText === '') {
                alert("Please enter a task.");
                return;
            }

            const li = document.createElement('li');
            li.textContent = taskText;
            li.addEventListener('click', function() {
                li.classList.toggle('completed');
            });

            const deleteButton = document.createElement('button');
            deleteButton.textContent = 'Delete';
            deleteButton.classList.add('delete');
            deleteButton.addEventListener('click', function() {
                li.remove();
            });

            li.appendChild(deleteButton);
            document.getElementById('task-list').appendChild(li);
            document.getElementById('new-task').value = ''; // Clear the input field
        });
    </script>
</body>
</html>

{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    background-color: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    text-align: center;
}

h1 {
    margin-bottom: 20px;
    font-size: 24px;
    color: #333;
}

.input-container {
    margin-bottom: 20px;
    display: flex;
    gap: 10px;
}

input[type="text"] {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    width: 70%;
}

button {
    padding: 10px;
    background-color: #28a745;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #218838;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    padding: 10px;
    background-color: #f8f8f8;
    margin-bottom: 10px;
    border-radius: 4px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

li.completed {
    text-decoration: line-through;
    color: #999;
}

button.delete {
    background-color: #dc3545;
    padding: 5px 10px;
    border-radius: 4px;
}

button.delete:hover {
    background-color: #c82333;
}
