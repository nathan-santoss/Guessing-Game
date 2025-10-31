# 🎯 Number Guessing Game (Electron Desktop App)

This project is a simple yet robust desktop application developed with **Electron** to provide a native gaming experience. Its goal is to test the user's guessing skills in a limited-attempt challenge. It's a fundamental demonstration of building secure, cross-platform applications using web technologies.

## ✨ Key Features

The application provides a straightforward but engaging user experience, built entirely with native JavaScript, HTML, and Electron logic:

* **Random Number Generation:** A secret integer is generated randomly within a defined range (currently 1 to 100) at startup.
* **Limited Attempts:** The player has a set number of chances (**5 attempts**) to correctly guess the secret number.
* **Hint System:** The player can request a hint that narrows down the range in which the secret number is located.
* **Input Validation:** Robust checks ensure the user input is a valid number and within the expected range, providing clear feedback messages.
* **Real-time Feedback:** The user receives immediate notification upon winning, losing, or receiving a valid hint.

## ⚙️ Tech Stack & Architecture

The core value of this project lies in its correct implementation of the secure Electron architecture, separating the application's logic between the processes.

| Component | Technology | Role and Best Practices |
| :--- | :--- | :--- |
| **User Interface (UI)** | HTML & Pure JavaScript | The UI logic, state management (tracking attempts), and feedback rendering are handled by the `renderer.js`. |
| **Core Application Logic** | Electron (Main Process) | The `main.js` handles the window management. The logic for **random number generation** resides outside the main renderer, ensuring the secret number cannot be easily manipulated or inspected by the end-user. |
| **Secure Communication** | `contextBridge` (Preload Script) | Implements Electron's best practices by using **Context Isolation** (`contextIsolation: true`) and a `preload.js` script to securely expose necessary APIs (`window.api.checkGuess`, `window.api.getHint`) to the renderer process. |
| **Development Utility** | `electronmon` | Used for a streamlined developer experience, automatically restarting the application upon changes to the source files. |

## 🚀 Getting Started

To run this application locally and explore the code:

1.  **Clone the repository:**
    ```bash
    git clone [YOUR_REPOSITORY_LINK_HERE]
    cd [PROJECT_FOLDER_NAME] 
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Run the application in development mode:**
    ```bash
    npm start
    ```

The application will launch in an Electron window, ready for you to start guessing!
