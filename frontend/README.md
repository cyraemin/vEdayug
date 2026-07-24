# vEdayug - Frontend Application

This is the client-side application for **vEdayug**, an AI-powered telehealthcare platform. 

**Frontend Team:** Anurag Sinha & Ananya Kumari (Team BMH)

## Tech Stack

*   **Framework:** React.js bootstrapped with Vite
*   **Styling:** TailwindCSS
*   **State Management:** React Context API
*   **HTTP Client:** Axios
*   **Real-time Communication:** Socket.io-client (Signaling) & SimplePeer (WebRTC for Video)

---

## Directory Structure

```text
frontend/
├── public/                # Static assets (favicons, etc.)
├── src/
│   ├── assets/            # Images, icons, and global CSS
│   ├── components/        # Reusable UI elements (DoctorCard, Navbar, PublicRoute)
│   ├── context/           # React Context providers (AuthContext, ThemeContext)
│   ├── layouts/           # Global page wrappers (DashboardLayout, AuthLayout)
│   ├── pages/             # Main application views (Login, Chatbot, VideoConsultation)
│   ├── services/          # API call logic (Axios instances, ML service bridges)
│   ├── App.jsx            # Main router and component tree
│   └── main.jsx           # React DOM rendering entry point
├── index.html             # Vite entry HTML
├── package.json           # Frontend dependencies
└── vite.config.js         # Vite configuration

---

## Getting Started

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed on your machine.

### Installation
Navigate to this `frontend` directory and install the dependencies:

\`\`\`bash
npm install
\`\`\`

### Running the Development Server
Start the local Vite development server:

\`\`\`bash
npm run dev
\`\`\`
The application will typically be available at `http://localhost:5173`.

---

## Core UI Flows

1. **Authentication:** 
   * Handled in `pages/Login.jsx` and `pages/Signup.jsx`. 
   * Uses `components/PublicRoute.jsx` to prevent logged-in users from seeing the login screen.
2. **Video Consultation:** 
   * Handled in `pages/VideoConsultation.jsx`.
   * Requests camera/microphone permissions and connects to the backend Socket.io server to initiate the WebRTC stream.
3. **Interactive Chatbot:** 
   * Handled in `pages/Chatbot.jsx`.
   * Maintains real-time scrolling and renders urgency badges based on the NLP response from `vedayug-chatbot`.
4. **Report Upload:**
   * Handled in `pages/ReportUpload.jsx`.
   * Features a drag-and-drop UI and a polling mechanism to wait for the backend OCR analysis.

---

##  Development Guidelines

*   **Component Modularity:** Keep components small and strictly focused. If a file exceeds 200 lines, consider breaking it down into smaller sub-components in the `src/components/` folder.
*   **API Calls:** Do not write `fetch` or `axios` calls directly inside components. Abstract all backend communication into dedicated functions within the `src/services/` folder.
*   **Styling:** Use Tailwind utility classes directly in the `className` attributes. Avoid writing custom CSS unless absolutely necessary for complex animations.
