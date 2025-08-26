# Assignment: Mastering JavaScript Fundamentals

 index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Travel Planner Demo</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Travel Planner Demo</h1>
  <h2>Part 1: Destination Check</h2>
  <input id="country" type="text" placeholder="Enter country">
  <button onclick="checkDestination()">Check</button>
  <p id="destMsg"></p>
  <h2>Part 2: Functions</h2>
  <button onclick="convertCurrency(100)">Convert $100</button>
  <p id="currencyMsg"></p>

  <button onclick="greetTraveler('Jessica')">Greet Traveler</button>
  <p id="greetMsg"></p>
  <h2>Part 3: Loops</h2>
  <button onclick="listDays()">Trip Days</button>
  <p id="daysMsg"></p>

  <button onclick="showPackingList()">Packing List</button>
  <ul id="packList"></ul>
  <h2>Part 4: DOM Fun</h2>
  <button id="themeBtn">Toggle Dark Mode</button>
  <button id="addNoteBtn">Add Travel Note</button>

  <script src="script.js"></script>
</body>
</html>


style.css

body {
  font-family: Georgia, serif;
  margin: 20px;
  transition: background 0.3s, color 0.3s;
}

.dark-mode {
  background: #222;
  color: #f0f0f0;
}

h2 {
  color: teal;
}




 script.js

Part 1: If/Else

function checkDestination() {
  let country = document.getElementById("country").value.toLowerCase();
  let msg;

  if (country === "kenya") {
    msg = "Safari time! Don’t forget your camera.";
  } else if (country === "japan") {
    msg = "Get ready for cherry blossoms and sushi.";
  } else {
    msg = "Sounds exciting! Safe travels to " + country + " ✈️";
  }

  document.getElementById("destMsg").innerText = msg;
}

 Part 2: Functions

function convertCurrency(usd) {
  let rate = 130; // sample rate
  let result = usd * rate;
  document.getElementById("currencyMsg").innerText =
    "$" + usd + " = " + result + " KES (approx)";
}

function greetTraveler(name) {
  document.getElementById("greetMsg").innerText =
    "Hello " + name + "! Ready for your trip?";
}

Part 3: Loops

function listDays() {
  let text = "";
  for (let i = 1; i <= 5; i++) {
    text += "Day " + i + " itinerary planned. ";
  }
  document.getElementById("daysMsg").innerText = text;
}

function showPackingList() {
  let items = ["Passport", "Tickets", "Backpack", "Sunglasses"];
  let ul = document.getElementById("packList");
  ul.innerHTML = "";

  items.forEach(item => {
    let li = document.createElement("li");
    li.textContent = item;
    ul.appendChild(li);
  });
}

 Part 4: DOM

document.getElementById("themeBtn").onclick = function() {
  document.body.classList.toggle("dark-mode");
};

document.getElementById("addNoteBtn").onclick = function() {
  let note = document.createElement("p");
  note.textContent = "New travel note added!";
  document.body.appendChild(note);
};






