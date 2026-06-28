# 🔌 TCP Device Communication System

A Python-based TCP/IP communication system that simulates communication between multiple network-connected devices. The project demonstrates socket programming, concurrent device communication using multithreading, and unit testing for validating read and write operations.

---

## 📌 Overview

Industrial automation and manufacturing systems often require reliable communication with multiple devices over a network. This project implements a simple TCP/IP communication framework capable of connecting to multiple devices simultaneously, sending commands, receiving responses, and managing communication through a centralized device manager.

A lightweight TCP server is included to simulate device behavior during testing, making the project self-contained and suitable for learning socket programming concepts.

---

## 🚀 Features

* 🔌 TCP/IP socket communication
* 📡 Simulated device server
* 🖥️ Connect to multiple devices simultaneously
* ⚡ Concurrent communication using multithreading
* 📥 Read data from connected devices
* 📤 Write data to connected devices
* 🧪 Unit tests for communication workflows
* 🏗️ Modular and extensible architecture

---

## 📂 Project Structure

```text
TCP-Device-Communication-System/
│
├── tcp_communication_assignment.py
├── README.md
└── requirements.txt
```

---

## 🛠️ Technologies Used

* Python
* Socket Programming
* Threading
* unittest

---

## 🔄 Project Workflow

### 1. Start TCP Servers

Two local TCP servers are launched to simulate external devices.

```
127.0.0.1:8080
127.0.0.1:8081
```

Each server waits for client connections and responds to read and write requests.

---

### 2. Register Devices

The `DeviceManager` creates `DeviceHandler` objects for each device and maintains a list of active connections.

---

### 3. Read Device Data

When a read operation is requested:

* A separate thread is created for each device.
* The client sends a `read` command.
* The server responds with sample data.
* Results are displayed in the console.

---

### 4. Write Device Data

When writing data:

* A thread is created for every connected device.
* The specified message is transmitted.
* The server acknowledges the received data.

---

### 5. Validate with Unit Tests

The project includes automated unit tests that verify:

* Reading data from multiple devices
* Writing data to multiple devices

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/TCP-Device-Communication-System.git
```

Navigate to the project directory:

```bash
cd TCP-Device-Communication-System
```

No external libraries are required. The project uses Python's standard library.

---

## ▶️ Running the Project

Start the server:

```bash
python tcp_communication_assignment.py
```

Run the unit tests:

```bash
python -m unittest tcp_communication_assignment.py
```

---

## 💻 Sample Output

### Reading from Devices

```text
Connected by ('127.0.0.1', 58438)
Connected by ('127.0.0.1', 58439)

Read from 127.0.0.1:8080 - sample data
Read from 127.0.0.1:8081 - sample data
```

### Writing to Devices

```text
Connected by ('127.0.0.1', 58440)
Received data: test data
Wrote to 127.0.0.1:8080 - test data

Connected by ('127.0.0.1', 58441)
Received data: test data
Wrote to 127.0.0.1:8081 - test data
```

---

## 🏗️ Project Architecture

### DeviceHandler

Responsible for communication with an individual device.

Responsibilities:

* Establish TCP connection
* Send commands
* Receive responses
* Close connections

---

### DeviceManager

Coordinates communication across multiple devices.

Responsibilities:

* Register devices
* Perform concurrent read operations
* Perform concurrent write operations
* Manage worker threads

---

### TCP Server

A lightweight server used to simulate external devices during testing.

It supports:

* Read requests
* Write requests
* Acknowledgement responses

---

## 📚 Learning Outcomes

Through this project, I explored:

* TCP/IP Socket Programming
* Client-Server Architecture
* Concurrent Programming using Threads
* Network Communication
* Unit Testing with Python
* Object-Oriented Design
* Resource Management using Context Managers

---

## ⚠️ Known Limitation

When the server is started multiple times without stopping previous instances, Windows may display the following error:

```text
OSError: [WinError 10048]
Only one usage of each socket address is normally permitted.
```

This occurs because the selected ports are already in use by another running server instance. Restarting the application or changing the port numbers resolves the issue.

---

## 🔮 Future Improvements

* Support configurable IP addresses and ports
* Add logging instead of console output
* Implement automatic device discovery
* Add timeout and retry mechanisms
* Support additional communication protocols (UDP, Modbus, MQTT)
* Build a graphical interface for monitoring device status

---

## 🎓 About This Project

This project was developed as part of a software engineering assignment to explore TCP/IP communication, multithreading, and object-oriented programming in Python. It demonstrates how multiple devices can be managed concurrently using socket programming and provides a foundation for building scalable communication systems.
