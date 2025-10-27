# 🤖 Amica.ai: Clinically-Informed Mental Wellness Companion

Amica.ai is a **single-page web application (SPA)** designed to provide immediate, empathetic, and clinically-informed mental wellness support. Built on the **Cognitive Behavioral Therapy (CBT)** framework, the application utilizes the **Google Gemini API** for its core intelligence and **Firebase** for secure user authentication and persistent journal data storage.

This project is a fusion of advanced AI (HCI) and secure frontend engineering, presented as a user-friendly web interface.

---

## ✨ Key Features

* **CBT-Based AI Companion:** The core intelligence, powered by the **Gemini 2.5 Flash API**, operates under a strict system prompt to deliver supportive, non-judgmental, and clinically-informed responses focused on self-awareness and coping skills.
* **Secure User Sessions:** Implements **Firebase Authentication** using anonymous sign-in or custom tokens for secure session management.
* **Persistent Journaling:** Utilizes **Firebase Firestore** to securely store and retrieve user journal entries (`/artifacts/{appId}/users/{userId}/notes`), ensuring user reflections are private and persistent.
* **Dynamic Client-Side Routing:** Simple JavaScript logic handles seamless switching between the **Welcome**, **Main Dashboard**, **Chatbot**, and **Robot Demo** pages without full page reloads.
* **Responsive & Modern UI:** Styled using **Tailwind CSS** for a clean, modern, and mobile-responsive design (Inter font family).
* **Demo Mode Fallback:** Automatically reverts to a fully functional **Demo Mode** if the Firebase or Gemini API configurations are missing, ensuring the application remains usable for testing.

---

## 🛠️ Technology Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | HTML5, JavaScript (ES modules) | Core application structure and logic. |
| **Styling** | **Tailwind CSS** | Utility-first framework for responsive design. |
| **AI/LLM** | **Google Gemini API** (`gemini-2.5-flash`) | Core intelligence for empathetic, CBT-guided responses. |
| **Backend/BaaS**| **Firebase Authentication** | Secure user sessions (anonymous/custom token sign-in). |
| **Database** | **Firebase Firestore** | Real-time, persistent storage for private user journal notes. |

---

## 🚀 Getting Started

Since this is a client-side web application, setup involves configuring your external services (Firebase and Gemini).

### Prerequisites

1.  A **Google AI API Key** (for the Gemini endpoint).
2.  A **Firebase Project** with **Authentication** and **Firestore** enabled.

### 1. Project Setup

Save the provided HTML code as **`index.html`** in your project directory.

### 2. Configure Environment Variables

The JavaScript code relies on global variables typically injected by a backend environment (like a server rendering template or a build process):

* `__firebase_config`
* `__initial_auth_token`
* `__app_id`

**For Local Testing/Demo:**

If you are running this file purely locally, you must **replace the placeholder values** in the `<script type="module">` block of `index.html` with your actual configuration.

1.  **Firebase Config:**
    Replace the `{}` in the following line with your Firebase project's configuration JSON:
    ```javascript
    const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {};
    // Example for testing (replace with your values):
    // const firebaseConfig = { apiKey: "...", authDomain: "...", projectId: "...", ... };
    ```
2.  **Gemini API Key:**
    Replace the empty string with your Gemini API key:
    ```javascript
    const apiKey = ""; // <-- REPLACE WITH YOUR GEMINI API KEY
    ```
    ***Note:*** *Exposing API keys in client-side code is a security risk. For production, keys should be proxied through a secure backend.*

### 3. Run the Application

Since this is a simple HTML file, you can run it in two ways:

1.  **Directly:** Open `index.html` in your web browser.
2.  **Via a Simple Server (Recommended):** Use a basic local server to avoid potential browser security restrictions (e.g., Cross-Origin Policy):
    ```bash
    # If you have Python installed
    python3 -m http.server
    ```
    Then, navigate to `http://localhost:8000`.

---

## ⚠️ Important Disclaimer

The application clearly states in its design and core prompt:

> **Amica AI is not a substitute for professional therapy, psychological, or medical advice.** It is an AI tool designed for supportive listening and informational purposes only. Amica’s core logic includes **crisis detection filters** and always prioritizes non-judgmental, empathetic validation. If you are experiencing a mental health crisis, please seek professional help immediately.
