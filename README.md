# BusBee🎯


## Basic Details
### Team Name:THink Tankers


### Team Members
- Member 1: Arundhathy R Nair - MACE
- Member 2: Ashmin Shaji- MACE
- Member 3: Sandra M Kartha - Mace

### Hosted Project Link
[[mention your project hosted project link here]](https://drive.google.com/file/d/1e-jEsAFnNzJae7t7-qLw7hq7K9fKtk3i/view?usp=drivesdk)

### Project Description
BusBee is a smart and efficient platform that helps you track local bus timings in real time. With accurate location updates, estimated arrival times, and easy-to-access schedules, BusBee ensures a hassle-free commuting experience. Simply enter your location or bus route to see when the next bus will arrive, making your daily travel more convenient and reliable.
Say goodbye to long waits and missed buses! Plan your journey efficiently with BusTrack.

### The Problem statement
No way to track private buses in local routes

### The Solution
BusBee is a smart and efficient platform that helps you track local bus timings in real time. With accurate location updates, estimated arrival times, and easy-to-access schedules, BusBee ensures a hassle-free commuting experience. Simply enter your location or bus route to see when the next bus will arrive, making your daily travel more convenient and reliable.

## Technical Details
### Technologies/Components Used
For Software:
- Html, JavaScript
- Firebase SDK
- [Libraries used]
-Figma, Canva, VS Code



### Implementation
For Software:
# Installation
import { initializeApp } from "https://www.gstatic.com/firebasejs/9.15.0/firebase-app.js";
import { getFirestore, doc, getDoc } from "https://www.gstatic.com/firebasejs/9.15.0/firebase-firestore.js";

// Firebase config (already set)
const firebaseConfig = {
    apiKey: "AIzaSyDxpWQ3FhcxqZVryOJ5Fq73heDPi66bQBU",
    authDomain: "busbee-4142e.firebaseapp.com",
    databaseURL: "https://busbee-4142e-default-rtdb.firebaseio.com",
    projectId: "busbee-4142e",
    storageBucket: "busbee-4142e.firebasestorage.app",
    messagingSenderId: "1022818305047",
    appId: "1:1022818305047:web:e58a9844dba477cfcf0852"
  };

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);


// Fetch schedule for a specific bus route
async function getBusSchedule(routeId) {
    try {
      const routeRef = doc(db, "Bus Routes", routeId);
      const routeSnap = await getDoc(routeRef);
  
      if (routeSnap.exists()) {
        const schedule = routeSnap.data().schedule;
        displaySchedule(schedule);
      } else {
        displayError("Route not found");
      }
    } catch (error) {
      displayError(`Error fetching bus schedule: ${error.message}`);
    }
  }
  


// Helper function to display the schedule on the webpage
function displaySchedule(schedule) {
    const scheduleElement = document.getElementById("schedule");
    scheduleElement.innerText = schedule;
  }
  
  // Helper function to display an error message on the webpage
  function displayError(errorMessage) {
    const errorElement = document.getElementById("error");
    errorElement.innerText = errorMessage;
  }
  getBusSchedule("Route"); 
 
  
const db = firebase.firestore();

async function getBusSchedules() {
    const snapshot = await db.collection("bus_routes").get();
    snapshot.forEach(doc => {
        console.log(doc.id, "=>", doc.data());
    });
}

getBusSchedules();

<!DOCTYPE html> 
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bus Tracker</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Local Bus Tracker</h1>

    <label for="location">Enter Your Location:</label>
    <input type="text" id="location" placeholder="Enter your location">

    <label for="routeSelect">Select a Bus Route:</label>
    <select id="routeSelect">
        <option value="route 1">Route</option>
        <option value="route 2">Route_1</option>
    </select>

    <button onclick="getBusScheduleFromUser()">Find Next Bus</button>

    <h2>Next Bus Arrival:</h2>
    <ul id="scheduleList"></ul>

    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.15.0/firebase-firestore.js"></script>
    <script src="script.js"></script>
</body>
</html>

# Run
[commands]

### Project Documentation
For Software:

# Screenshots (Add at least 3)
![Screenshot1](Add screenshot 1 here with proper name)
*Add caption explaining what this shows*

![Screenshot2](Add screenshot 2 here with proper name)
*Add caption explaining what this shows*

![Screenshot3](Add screenshot 3 here with proper name)
*Add caption explaining what this shows*

# Diagrams
![Workflow](Add your workflow/architecture diagram here)
*Add caption explaining your workflow*

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

# Build Photos
![Team](Add photo of your team here)


![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

### Project Demo
# Video
[[Add your demo video link here]](https://drive.google.com/file/d/1e-jEsAFnNzJae7t7-qLw7hq7K9fKtk3i/view?usp=drivesdk)
*Explain what the video demonstrates*

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- Arundhathy: Ideation, Logo Designing
- Ashmin: Backend Code
- Sandra: website Designing

---
Made with ❤️ at TinkerHub
