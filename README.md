# 🖥️ TCP Server Client Pro

This project is an advanced simulation of a TCP server-client connection, implemented using **WebSockets**. It features a rich, interactive web-based client (TCP Server Client Pro) that communicates with a Node.js WebSocket server.

The client interface allows for sending commands, managing a virtual file system, performing calculations, and viewing connection stats, all in real-time.

## 🧑‍💻 Project by

* **Harshit Tiwari**
* **Awijeet Singh**
* **Devesh Mishra**

---

## ✨ Key Features

* **Real-time Connection:** Connects to the WebSocket server with a specified IP and Port.
* **Interactive Terminal:** Send commands and receive live responses from the server, just like a real console.
* **Virtual File System:** Remotely **CREATE**, **READ**, **WRITE**, **APPEND**, and **DELETE** files on the server's in-memory file system.
* **Live File Browser:** The `LIST` command automatically populates a visual file browser, showing all files and their sizes.
* **Command History:** All sent commands are saved to `localStorage` and can be revisited, exported as JSON, or cleared.
* **Client-Side Calculator:** A handy built-in calculator for simple arithmetic (Add, Subtract, Multiply, Divide).
* **Session Persistence:** The client uses `localStorage` to remember the state of the virtual file system, command history, and session stats, even after closing the browser.
* **Robust Simulation Mode:** If the WebSocket server connection fails or is unavailable, the client **seamlessly switches to a built-in simulation mode** with full functionality, ensuring a great demo experience.

---

## 🛠️ Technology Stack

* **Frontend:** HTML5, CSS3, and modern JavaScript (ES6+).
* **Backend:** Node.js
* **Protocol:** WebSockets (using the `ws` library for Node.js)

---

## 🚀 How to Run

You can run this project in two ways: with the live server for a true client-server experience, or using the client's built-in simulation mode.

### 1. The Server (Optional, due to Simulation Mode)

This step runs the Node.js backend.

1.  Ensure you have [Node.js](https://nodejs.org/) installed on your machine.
2.  Install the `ws` (WebSocket) library by running this command in your terminal:
    ```bash
    npm install ws
    ```
3.  Save the server code as `server.js`.
4.  Run the server from your terminal:
    ```bash
    node server.js
    ```
5.  The server will start and listen on `ws://localhost:5566`.

### 2. The Client (Main Interface)

This is the web-based UI.

1.  Save the HTML/CSS/JS code as `index.html`.
2.  **Open the `index.html` file in any modern web browser** (like Chrome, Firefox, or Edge).
3.  The page will load. The default IP (`127.0.0.1`) and Port (`5566`) are already set.
4.  Click the **"🔌 Connect"** button.
    * **If the `server.js` is running:** The client will connect, and the status will turn green.
    * **If the `server.js` is NOT running:** The client will fail to connect and **automatically enter simulation mode**, allowing you to use all features.

---

## 💬 Available Server Commands

Here is a list of all commands implemented by the server and understood by the client:

| Command | Example | Description |
| :--- | :--- | :--- |
| **TIME** | `TIME` | Displays the current server date and time. |
| **ECHO** | `ECHO Hello World` | The server sends back the provided message. |
| **LIST** | `LIST .` | Lists all files in the server's virtual file system. |
| **READ** | `READ readme.txt` | Displays the contents of a specific file. |
| **CREATE** | `CREATE newfile.txt` | Creates a new, empty file on the server. |
| **WRITE** | `WRITE data.txt Hello` | Overwrites a file's content with new content. |
| **APPEND** | `APPEND data.txt World` | Adds new content to the end of an existing file. |
| **DELETE** | `DELETE newfile.txt` | Deletes a file from the server. |
| **STATS** | `STATS` | Shows server-side statistics (uptime, file count). |
| **UPTIME** | `UPTIME` | Displays the server's current uptime in seconds. |
