# External-exam

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    <title>Employee Database Management System</title>
</head>

<body>
   
    <div id="app">
        <header class="header">
            <h1>Employee Database Management</h1>
           
        </header>
        <div class="container">
            <label for="uname"><b>Username</b></label>
            <input type="text" placeholder="Enter Username" name="uname" required>
      
            <label for="psw"><b>Password</b></label>
            <input type="password" placeholder="Enter Password" name="psw" required>
      
            <form action="process_login.php" method="post">
                <button type="submit">Login</button>
           
              </form>
            
            <label>
              <input type="checkbox" checked="checked" name="remember"> Remember me
            </label>
            
          </div>
          <div class="employees__names">
            <span class="employees__names--title">
                <button class="createEmployee">
                  Register
              </span>
            <div class="employees__names--list"></div>
        </div>
      

        <div class="employees">
            
        </div>
        <div class="addEmployee">
            <form class="addEmployee_create">
                Create Employee
             
                <input type="text" name="imageUrl" 
                       placeholder="Image URL (Optional)" />
                       <input type="text" name="firstName" 
                       placeholder="Types of Employee" required />
           
            </div>
            </form>
        </div>
    </div>
    <div class="employees__names">
        <span class="employees__names--title">
            <button class="createEmployee">
              Employee List
          </span>
        <div class="employees__names--list"></div>
    </div>
    <div class="employees__single">
        <div class="employees__single--title">
            <button class="createEmployee">
                Delete/Edit Employee
        </div>
        <div class="employees__single--info"></div>
    </div>
    <div class="employees__names">
        <span class="employees__names--title">
            <button class="createEmployee">
             
              <div class="popup" onclick="myFunction()"> Display Employee
                <span class="popuptext" id="myPopup"></span>
              </div>
          </span>
        <div class="employees__names--list"></div>
    </div>
    <div class="employees__single">
        <div class="employees__single--title">
                Search Employee
        </div>
        <div class="employees__single--info"></div>
        <div>
            <input type="text" name="firstName" 
                   placeholder="First Name" required />
            <input type="text" name="lastName" 
                   placeholder="Last Name" required />
                   <input type="submit" 
                   class="addEmployee_create--submit" 
                   value="Submit" />
        </div>
    </div>
    

    <script src="script.js"></script>
</body>

</html>

/* Filename - App.css */
/* It containds the Form and Page Styling*/

body {
    background: #f3f3f3;
    text-align: center;
}
.App {
    background-color: #fff;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
    padding: 10px 20px;
    transition: transform 0.2s;
    width: 500px;
    text-align: center;
    margin: auto;
    margin-top: 20px;
}

h1 {
    font-size: x-large;
    text-align: center;
    color: #327c35;
}

fieldset {
    border: none;
}

input {
    display: block;
    width: 100%;
    /* margin-bottom: 15px; */
    padding: 8px;
    box-sizing: border-box;
    border: 1px solid #ddd;
    border-radius: 3px;
    font-size: 12px;
}
input[type="radio"],
input[type="checkbox"] {
    display: inline;
    width: 10%;
}
select {
    display: block;
    width: 100%;
    margin-bottom: 15px;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #ddd;
    border-radius: 5px;
}

label {
    font-size: 15px;
    display: block;
    width: 100%;
    margin-top: 8px;
    margin-bottom: 5px;
    text-align: left;
    color: #555;
    font-weight: bold;
}

button {
    padding: 15px;
    border-radius: 10px;
    margin: 15px;
    border: none;
    color: white;
    cursor: pointer;
    background-color: #4caf50;
    width: 40%;
    font-size: 16px;
}
textarea {
    resize: none;
    width: 98%;
    min-height: 100px;
    max-height: 150px;
}


// Filename - App.js
// It contains the Form, its Structure
// and Basic Form Functionalities

import "./App.css";
import { React, useState } from "react";

function App() {
    const [firstName, setFirstName] = useState("");
    const [lastName, setLastName] = useState("");
    const [email, setEmail] = useState("");
    const [contact, setContact] = useState("");
    const [gender, setGender] = useState("male");
    const [subjects, setSubjects] = useState({
        english: true,
        maths: false,
        physics: false,
    });
    const [resume, setResume] = useState("");
    const [url, setUrl] = useState();
    const [selectedOption, setSelectedOption] =
        useState("");
    const [about, setAbout] = useState("");

    const handleSubmit = (e) => {
        e.preventDefault();
        console.log(
            firstName,
            lastName,
            email,
            contact,
            gender,
            selectedOption,
            subjects,
            resume,
            url,
            about
        );
        // Add your form submission logic here
    };

    const handleSubjectChange = (sub) => {
        setSubjects((prev) => ({
            ...prev,
            [sub]: !prev[sub],
        }));
    };
    const handleReset = () => {
        // Reset all state variables here
        setFirstName("");
        setLastName("");
        setEmail("");
        setContact("");
        setGender("male");
        setSubjects({
            english: true,
            maths: false,
            physics: false,
        });
        setResume("");
        setUrl("");
        setSelectedOption("");
        setAbout("");
    };

    return (
        <div className="App">
            <h1>Form in React</h1>
            <fieldset>
                <form action="#" method="get">
                    <label for="firstname">
                        First Name*
                    </label>
                    <input
                        type="text"
                        name="firstname"
                        id="firstname"
                        value={firstName}
                        onChange={(e) =>
                            setFirstName(e.target.value)
                        }
                        placeholder="Enter First Name"
                        required
                    />
                    <label for="lastname">Last Name*</label>
                    <input
                        type="text"
                        name="lastname"
                        id="lastname"
                        value={lastName}
                        onChange={(e) =>
                            setLastName(e.target.value)
                        }
                        placeholder="Enter Last Name"
                        required
                    />
                    <label for="email">Enter Email* </label>
                    <input
                        type="email"
                        name="email"
                        id="email"
                        value={email}
                        onChange={(e) =>
                            setEmail(e.target.value)
                        }
                        placeholder="Enter email"
                        required
                    />
                    <label for="tel">Contact*</label>
                    <input
                        type="tel"
                        name="contact"
                        id="contact"
                        value={contact}
                        onChange={(e) =>
                            setContact(e.target.value)
                        }
                        placeholder="Enter Mobile number"
                        required
                    />
                    <label for="gender">Gender*</label>
                    <input
                        type="radio"
                        name="gender"
                        value="male"
                        id="male"
                        checked={gender === "male"}
                        onChange={(e) =>
                            setGender(e.target.value)
                        }
                    />
                    Male
                    <input
                        type="radio"
                        name="gender"
                        value="female"
                        id="female"
                        checked={gender === "female"}
                        onChange={(e) =>
                            setGender(e.target.value)
                        }
                    />
                    Female
                    <input
                        type="radio"
                        name="gender"
                        value="other"
                        id="other"
                        checked={gender === "other"}
                        onChange={(e) =>
                            setGender(e.target.value)
                        }
                    />
                    Other
                    <label for="lang">
                        Your best Subject
                    </label>
                    <input
                        type="checkbox"
                        name="lang"
                        id="english"
                        checked={subjects.english === true}
                        onChange={(e) =>
                            handleSubjectChange("english")
                        }
                    />
                    English
                    <input
                        type="checkbox"
                        name="lang"
                        id="maths"
                        checked={subjects.maths === true}
                        onChange={(e) =>
                            handleSubjectChange("maths")
                        }
                    />
                    Maths
                    <input
                        type="checkbox"
                        name="lang"
                        id="physics"
                        checked={subjects.physics === true}
                        onChange={(e) =>
                            handleSubjectChange("physics")
                        }
                    />
                    Physics
                    <label for="file">Upload Resume*</label>
                    <input
                        type="file"
                        name="file"
                        id="file"
                        onChange={(e) =>
                            setResume(e.target.files[0])
                        }
                        placeholder="Enter Upload File"
                        required
                    />
                    <label for="url">Enter URL*</label>
                    <input
                        type="url"
                        name="url"
                        id="url"
                        onChange={(e) =>
                            setUrl(e.target.value)
                        }
                        placeholder="Enter url"
                        required
                    />
                    <label>Select your choice</label>
                    <select
                        name="select"
                        id="select"
                        value={selectedOption}
                        onChange={(e) =>
                            setSelectedOption(
                                e.target.value
                            )
                        }
                    >
                        <option
                            value=""
                            disabled
                            selected={selectedOption === ""}
                        >
                            Select your Ans
                        </option>
                        <optgroup label="Beginers">
                            <option value="1">HTML</option>
                            <option value="2">CSS</option>
                            <option value="3">
                                JavaScript
                            </option>
                        </optgroup>
                        <optgroup label="Advance">
                            <option value="4">React</option>
                            <option value="5">Node</option>
                            <option value="6">
                                Express
                            </option>
                            <option value="t">
                                MongoDB
                            </option>
                        </optgroup>
                    </select>
                    <label for="about">About</label>
                    <textarea
                        name="about"
                        id="about"
                        cols="30"
                        rows="10"
                        onChange={(e) =>
                            setAbout(e.target.value)
                        }
                        placeholder="About your self"
                        required
                    ></textarea>
                    <button
                        type="reset"
                        value="reset"
                        onClick={() => handleReset()}
                    >
                        Reset
                    </button>
                    <button
                        type="submit"
                        value="Submit"
                        onClick={(e) => handleSubmit(e)}
                    >
                        Submit
                    </button>
                </form>
            </fieldset>
        </div>
    );
}

export default App;
