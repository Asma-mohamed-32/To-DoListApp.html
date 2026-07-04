<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To Do List</title>
    <style>
body{
    font-family: Arial, sans-serif;
    background:rgb(34, 105, 105);
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.container{
    background:gray;
    padding:20px;
    border-radius:10px;
    width:350px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
}

h1{
    text-align:center;
}

.input-box{
    display:flex;
    gap:10px;
}

input{
    flex:1;
    padding:10px;
}

button{
    padding:10px 15px;
    background:#4CAF50;
    color:white;
    border:none;
    cursor:pointer;
}

li{
    margin-top:10px;
    padding:10px;
    background:#eee;
    display:flex;
    justify-content:space-between;
    border-radius:5px;
}

.delete{
    background:red;
    color:white;
    border:none;
    padding:5px 10px;
}

.completed {
    text-decoration: line-through;
    color: gray;
}

.tick-btn {
    background: rgb(33, 201, 33);
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
    margin-right: 5px;
    border-radius: 5px;
}

.delete-btn {
    background: rgb(233, 40, 40);
    color: white;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
    border-radius: 5px;
}
    </style>
</head>
<body>

    <div class="container">
        <h1>My To-Do List</h1>

        <div class="input-box">
            <input type="text" id="taskInput\" placeholder="Enter a task">
            <button onclick="addTask()">Add</button>
        </div>

        <ul id="taskList"></ul>
    </div>

    <script>
       function addTask() {
    let input = document.getElementById("taskInput");
    let task = input.value.trim();

    if (task === "") return;

    let li = document.createElement("li");

    li.innerHTML = `
        <span>${task}</span>
        <div>
            <button class="tick-btn" onclick="completeTask(this)">✓</button>
            <button class="delete-btn" onclick="deleteTask(this)">🗑</button>
        </div>
    `;

    document.getElementById("taskList").appendChild(li);
    input.value = "";
}

function completeTask(button) {
    let taskText = button.parentElement.parentElement.querySelector("span");
    taskText.classList.toggle("completed");
}

function deleteTask(button) {
    button.parentElement.parentElement.remove();
}
    </script>
</body>
</html>


