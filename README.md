# VerseMuse 🪶

**VerseMuse** is a minimalist, privacy-first AI poetry assistant that runs **entirely offline** on your device.

![React](https://img.shields.io/badge/React-19-blue?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=for-the-badge&logo=typescript)
![Capacitor](https://img.shields.io/badge/Capacitor-Android-green?style=for-the-badge&logo=capacitor)
![AI](https://img.shields.io/badge/AI-Local_LLM-orange?style=for-the-badge)

## 📖 Overview

VerseMuse acts as a digital muse for poets. Unlike most AI tools that rely on cloud APIs and subscriptions, VerseMuse downloads a quantized Large Language Model (LLM) directly to the user's device. 

Once the initial download (~200MB) is complete, the app functions **100% offline**.

### Key Benefits
1.  **Zero Latency**: No network requests after initialization.
2.  **Total Privacy**: Your poems and prompts never leave your phone.
3.  **No Subscriptions**: No recurring server costs.

## ✨ Features

*   **Offline AI Generation**: Powered by `transformers.js` running `LaMini-GPT-124M` locally in the browser via WebGPU/WASM.
*   **Distraction-Free Editor**: A clean, paper-like interface designed for focus.
*   **Local Library**: Save and organize poems using an embedded SQLite database (`sql.js`).
*   **Smart Suggestions**: Generate poetry based on Topic, Style (Haiku, Sonnet, etc.), and Mood.
*   **Android Native**: Wrapped using **Capacitor** for a native mobile experience.
*   **Theming**: Beautiful Dark and Light modes.

## 🛠 Tech Stack

*   **Frontend**: React 19, TypeScript, Tailwind CSS
*   **AI Engine**: [@xenova/transformers](https://huggingface.co/docs/transformers.js) (ONNX Runtime)
*   **Database**: `sql.js` (SQLite compiled to WebAssembly)
*   **Mobile Runtime**: Capacitor (Android)
*   **Icons**: Lucide React

## 🚀 Getting Started

### Prerequisites
*   Node.js (v18+)
*   Android Studio (for mobile build)

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/versemuse.git
    cd versemuse
    ```

2.  **Install dependencies**
    ```bash
    npm install
    ```

3.  **Run Development Server**
    ```bash
    npm run dev
    ```

4.  **Build for Android**
    ```bash
    npm run build
    npx cap sync
    npx cap open android
    ```

## 📱 Architecture Note

1.  **Initialization**: On first load, the app fetches the model weights from Hugging Face CDN.
2.  **Caching**: These weights are cached in the browser/webview cache.
3.  **Inference**: When you click "Create Poem", the input is tokenized and passed to the ONNX runtime to generate text locally.
4.  **Storage**: Poems are saved to a binary SQLite file stored in LocalStorage as a base64 string for persistence across sessions.

## 🔒 Privacy Policy

VerseMuse is designed with privacy as a core feature.
*   **No Data Collection**: We do not collect analytics or user data.
*   **Local Processing**: All AI generation happens on your device.
*   **Local Storage**: Your library exists only on your phone/browser.

View the full [Privacy Policy](privacy_policy.html).

---

*Built with ❤️ by [Your Name]*
