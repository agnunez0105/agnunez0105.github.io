# Employee Health Manager Dashboard

A JavaFX-based desktop application designed for managers to monitor real-time and historical employee health metrics.
The application tracks data such as **BPM (Beats Per Minute)**, **Readiness Scores**, and **Daily Step Counts** using a
local SQLite database.

---

## Prerequisites
* Java 17 or higher
* IntelliJ IDEA

---

## Key Features
* **Real-time Dashboard:** A centralized `TableView` to monitor all employees at a glance.
* **Advanced Filtering:** Search by name or filter by health thresholds (e.g., "Show employees with BPM > 90").
* **Data Persistence:** Integrated **SQLite** database to store historical health data across sessions.
* **Asynchronous Processing:** Database operations run on background threads using `javafx.concurrent.Task` to ensure a
* smooth, lag-free UI.
* **Modular Design:** Dedicated windows and controllers for adding new employees and recording metrics.

---

## Tech Stack!
* **Language:** Java 17+
* **Framework:** JavaFX
* **Database:** SQLite (Relational)
* **Connectivity:** JDBC (Java Database Connectivity)
* **Architecture:** DAO (Data Access Object) Pattern

---

## Database Schema
The project uses a relational structure to link employees to their time-stamped health metrics:

* **`employees` Table:** Stores basic worker information (`id`, `name`).
* **`metrics` Table:** Stores time-series health data (`id`, `employee_id`, `bpm`, `recorded_at`).

---

## Setup & Installation (For Teammates)

### 0. JavaFX SDK
1. Download JavaFX 17+ SDK from https://gluonhq.com/products/javafx/
2. Extract it in a standard place on your machine 
3. In IntelliJ, go to **File → Project Structure → Global Libraries → +**.
4. Navigate to where you extracted the jar file for JavaFX.
5. Choose the `lib/` folder inside the extracted JavaFX SDK and name it `javafx`.
6. In **Run/Debug Configurations**, add to VM options:
   --module-path /path/to/javafx-sdk/lib --add-modules javafx.controls,javafx.fxml

### 1. Other Dependencies 
This project requires the following libraries. Download each JAR and follow the setup instructions for your IDE below.

| Library | Version | Download |
|---|---|---|
| Gson | 2.10.1 | [gson-2.10.1.jar](https://repo1.maven.org/maven2/com/google/code/gson/gson/2.10.1/gson-2.10.1.jar) |
| Eclipse Paho MQTT v3 | 1.2.5 | [org.eclipse.paho.client.mqttv3-1.2.5.jar](https://repo1.maven.org/maven2/org/eclipse/paho/org.eclipse.paho.client.mqttv3/1.2.5/org.eclipse.paho.client.mqttv3-1.2.5.jar) |
| SQLite JDBC | 3.51.3.0 | [sqlite-jdbc-3.51.3.0.jar](https://repo1.maven.org/maven2/org/xerial/sqlite-jdbc/3.51.3.0/sqlite-jdbc-3.51.3.0.jar) |

Place all JARs in the `libs/` folder in the project root before following the IDE setup steps below.


### 2. Docker
1. Download Docker desktop AMD64 version.



### 3. IntelliJ IDEA
1. Open the project in IntelliJ.
2. Go to **File → Project Structure → Modules → Dependencies**.
3. Click **+** → **JARs or Directories**.
4. Select all JARs from the `libs/` folder.
5. Click **Apply** and **OK**.


---


## To Run Application 

### 1. Docker
1. Open docker desktop 
2. In the terminal in docker, go to our repository folder
3. `cd` into `mqtt` and run `docker compose up`

### 2. IntelliJ
1. Run Main.main()

### 3. Your Watch
1. Choose an employee ID from one of our hardcoded employees ("04", "12", "35", "27", "72") and enter that as your employee id on your watch
2. Send the connection message including the employee IDs and the ID number of your watch.


---


## Known Bugs
1. Adding an employee after leaving the "add employee" page does not reset the fields to empty.


## License
MIT License

Copyright (c) 2026 Zoe Kirkman, John Balasbas, Josh Schelonka, Arianna Nunez

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.