<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>Book Form</title>  
</head>  
<body>  
    <form method="POST" action="lab1.php">  
        <table>  
            <tr>  
                <td>Book ID</td>  
                <td><input type="text" name="bookID" /></td></tr>  
            <tr>  
                <td>Book Title</td>  
                <td><input type="text" name="bookTitle" /></td></tr>  
            <tr>  
                <td>Book Price</td>  
                <td><input type="text" name="bookPrice" /></td></tr>  
            <tr>  
                <td>No. of Copies </td>  
                <td><input type="text" name="bookCopies" /></td></tr>  
            <tr>  
                    <td align="center"><input type="submit" name="submit" value="Submit" /> </td>  
                    <td align="center"><input type="reset" name="reset" value="Reset" /></td>  
                </tr>  
        </table>  
    </form>  
</body>  
</html>  
 
    
 
<?php 
if ($_SERVER["REQUEST_METHOD"] === "POST") { 
 
    $bname   = $_POST["bookID"]      ?? ""; 
    $btitle  = $_POST["bookTitle"]   ?? ""; 
    $bprice  = $_POST["bookPrice"]   ?? ""; 
    $bcopies = $_POST["bookCopies"]  ?? ""; 
 
    if (empty($bname) || empty($btitle) || empty($bprice) || empty($bcopies)) {         echo "Fields cannot be empty"; 
    } 
    elseif (!ctype_digit($bprice)) {         echo "Price must contain digits only"; 
    } 
    elseif ($bprice <= 0 || $bcopies <= 0) {         echo "Price and Copies must be greater than 0"; 
    } 
    else { 
        echo "Form data is validated"; 
    } 
 
} else { 
    echo "Please submit the form."; 
} 
?> 
 
   222222 
 
<?php  
 
session_start();  
 
$sessionTimeout = 30 * 60; // 30 minutes 
 
if (isset($_SESSION['LAST_ACTIVITY'])) { 
 
    $lastActivity = $_SESSION['LAST_ACTIVITY'];  
    $currentTime = time();  
    $timeSinceLastActivity = $currentTime - $lastActivity; 
 
    if ($timeSinceLastActivity > $sessionTimeout) { 
 
        session_unset();                  session_destroy();                  echo "Session expired. Please log in again."; 
 
    } else { 
 
        $_SESSION['LAST_ACTIVITY'] = $currentTime;                  echo "Session active."; 
    } 
 
} else { 
 
    $_SESSION['LAST_ACTIVITY'] = time();          echo "Session started."; 
} 
 
?> 
 
3333333 
 
 
<!DOCTYPE html> 
<html> 
<head> 
    <title>Student Form</title> 
</head> 
<body> 
    <form action="3cookie.php" method="post"> 
        Student Name: <input type="text" name="name" required><br><br> 
        Phone Number: <input type="text" name="phone" required><br><br> 
        <input type="submit" value="Submit"> 
    </form> 
</body> 
</html> 
    
 
 
<!DOCTYPE html>  
<?php  
if ($_SERVER["REQUEST_METHOD"] == "POST") { 
    $cookie_name = $_POST['name'];     $cookie_value = $_POST['phone']; 
setcookie($cookie_name, $cookie_value, time() + 1800, "/"); // 3600 is 60 minutes  
  
if(!isset($_COOKIE[$cookie_name])) {  
    echo "Cookie named '" . $cookie_name . "' is not set!";  
} else {  
    echo "Cookie '" . $cookie_name . "' is set!<br>";      echo "Value is: " . $_COOKIE[$cookie_name];  
}  
 } 
?> 
444  
 
 
<!DOCTYPE html> 
<html> 
<head> 
    <title>Login Page</title> 
</head> 
 
<body> 
    <h2>Login Form</h2> 
 
    <form method="post" action="4pro.php"> 
        <label>Enter Username</label><br> 
      <input type="text" name="username" required><br><br> 
 
        <label>Enter Password</label><br> 
        <input type="password" name="password" required><br><br> 
 
        <input type="submit" name="submit" value="Submit"> 
        <input type="reset" value="Reset"> 
    </form> 
 
</body> 
</html> 
 
 
<?php 
 
$servername = "localhost"; 
$username   = "root"; 
$password   = ""; // If you set a MySQL password, enter it here 
$dbname     = "your_database_name"; 
 
$conn = new mysqli($servername, $username, $password, $dbname); 
 
// Check connection if ($conn->connect_error) { 
    die("Connection failed: " . $conn->connect_error); 
} 
 
if (isset($_POST['submit'])) { 
   
    $username = $_POST['username']; 
    $password = $_POST['password']; 
 
    $sql = "SELECT * FROM student WHERE username='$username' AND password='$password'";     $result = $conn->query($sql); 
 
    if ($result->num_rows > 0) {         echo "Login Successful!"; 
    } else { 
        echo "Invalid username or password."; 
    } 
} 
 
$conn->close(); 
 
?> 
 
 
 
555 
<!DOCTYPE html>  
<html>  
<body>  
  
<div id="demo">  
<h1>The XMLHttpRequest Object</h1>  
<button type="button" onclick="loadDoc()">Change Content</button> </div>  
<script> function loadDoc() {   var xhttp = new XMLHttpRequest();   xhttp.onreadystatechange = function() { if (this.readyState == 4 && this.status == 200) 
{       document.getElementById("demo").innerHTML = this.responseText;  
    }  
  };  
  xhttp.open("GET", "ajaxinfo.txt", true);   xhttp.send();  
}  
</script>  
  
</body>  
</html>  
 
666 
 
let colors=['red', 'blue', 'green']; let[val1,val2]=colors; console.log(val1,val2); 
 
let obj={     sid:101,     sname:'John',     sper:93 
}; 
let{sid,sname}=obj; console.log(sid,sname); 
 
function sum(...numbers){ 
    let total=0;     for(let num of numbers){         total+=num; 
    } 
    console.log("total = ",total); 
} 
 
sum(1,2,3); 
 
 
const arr1=[1,2,3]; const arr2=[4,5,6]; 
 
const merge=[...arr1,...arr2]; console.log("merged array = ",merge); 
 
const copy=[...arr1]; console.log("copied array = ",copy); 
 
 
77 
 
import { useState } from "react"; 
 
function MyForm() {   const [name, setName] = useState(""); 
 
  const handleSubmit = (event) => {     event.preventDefault(); 
    alert(`The name you entered was: ${name}`); 
  }; 
 
  return ( 
    <form onSubmit={handleSubmit}> 
      <label> 
        Enter your name: 
        <input           type="text"           value={name} 
          onChange={(e) => setName(e.target.value)} 
        /> 
      </label> 
      <input type="submit" /> 
    </form> 
  ); 
} 
 
export default MyForm; 
 
import React from 'react'; import ReactDOM from 'react-dom/client'; import MyForm from './App'; 
 
const root = ReactDOM.createRoot(document.getElementById('root')); root.render(<MyForm />); 
 
 
88 
 
import React, { useState } from 'react';  
  
const Counter = () => {   const [count, setCount] = useState(0);   const increment = () => setCount(prevCount => prevCount + 1);   const decrement = () => setCount(prevCount => prevCount - 
1);   const reset = () => setCount(0);    return (  
    <div>  
      <h2>Count: {count}</h2>  
      <button onClick={increment}>Increment</button>  
      <button onClick={decrement}>Decrement</button>  
      <button onClick={reset}>Reset</button>     
</div>  
  );  
};  
  
const App = () => {   return (  
    <div><h1>Simple Counter App</h1>  
      <Counter />  
    </div>  
  );  
};  
  
export default App;  
 
 
import React from 'react'; import ReactDOM from 'react-dom/client'; import MyForm from './App'; 
 
const root = ReactDOM.createRoot(document.getElementById('root')); root.render(<MyForm />); 
 
999 
 
Type the following code in App.js of Src folder import React, { useState } from 'react'; function App() { 
 const [color, setColor] = useState('black');  const [index, setIndex] = useState(0); 
  
 // Function to change the color randomly  const changeColor = () => { 
 const colors = ['red', 'blue', 'green', 'purple', 'orange', 'pink', 'brown'];  const newColor = colors[index];  setColor(newColor); 
 setIndex((prevIndex) => (prevIndex + 1) % colors.length); 
 }; 
 return ( 
 <div> 
 <h1>Change Paragraph Color</h1> 
 <p style={{ color: color, fontSize: '20px' }}> 
 Click the button to change my color! </p> 
 <button onClick={changeColor} > Change Color</button> 
 </div> 
 ); 
} 
export default App; 
Type the following code in index.js import React from 'react'; 
import ReactDOM from 'react-dom/client'; import './index.css'; import App from './App'; 
const root = ReactDOM.createRoot(document.getElementById('root')); root.render(<App />); 
10. WRITE A PROGRAM USING 
 
 
10000 
import React, { useState } from "react"; 
 
function TodoList() { 
  const [todos, setTodos] = useState([]);   const [inputValue, setInputValue] = useState(""); 
 
  function handleChange(e) {     setInputValue(e.target.value); 
  } 
 
  function handleSubmit(e) {     e.preventDefault();     if (inputValue.trim() === "") return; 
 
    const newTodo = {       id: Date.now(),       text: inputValue, 
    }; 
 
    setTodos([...todos, newTodo]);     setInputValue(""); 
  } 
 
  function handleDelete(id) {     setTodos(todos.filter((todo) => todo.id !== id)); 
  } 
 
  return ( 
    <div> 
      <h1>Todo List</h1> 
 
      <form onSubmit={handleSubmit}> 
        <input           type="text"           value={inputValue}           onChange={handleChange} 
        /> 
        <button type="submit">Add Todo</button> 
      </form> 
 
      <ul> 
        {todos.map((todo) => ( 
          <li key={todo.id}> 
            {todo.text} 
            <button onClick={() => handleDelete(todo.id)}> 
              Delete 
            </button> 
          </li> 
        ))} 
      </ul> 
    </div> 
  ); 
} 
 
export default TodoList; 
 
import React from "react"; import ReactDOM from "react-dom/client"; import TodoList from "./App"; 
 
const root = ReactDOM.createRoot(document.getElementById("root")); root.render(<TodoList />); 
 
import React from "react"; import ReactDOM from "react-dom/client"; import TodoList from "./App"; 
 
const root = ReactDOM.createRoot(document.getElementById("root")); root.render(<TodoList />); 
 
 
