# 🏥 vEdayug

vEdayug is an AI-powered telehealthcare platform designed to bridge the gap between patients and medical professionals. It features real-time video consultations, secure payment gateways, and AI-driven medical report analysis.

**Note:** This project is transitioning to a unified Python backend architecture to seamlessly integrate with our Machine Learning and NLP microservices.

##  Detailed Documentation

For specific setup commands, API routes, and team workflows, please refer to the dedicated module documentation:

*    **[Frontend Documentation](./frontend/README.md)**
*   **[Backend Documentation](./backend/README.md)**
*    **[ML & Chatbot Services](./team-docs/)** *(Coming soon)*

##  Team BMH

This project is developed and maintained by **Team BMH**:

*   **Frontend Team:** Anurag Sinha, Ananya Kumari
*   **Backend API Team:** Arya, Nirwan Jain
*   **Machine Learning Team:** Tamsil Sameera, Satyabrath Sahaa

---

##  Repository Structure

\`\`\`text
HealthVision/
├── frontend/              # React.js frontend application (Vite + Tailwind)
├── backend/               # Python Core API (Handles Auth, Payments, MongoDB)
├── healthvision-chatbot/  # Independent symptom chatbot service (Python)
├── ml-service/            # Python AI/ML service for OCR and report analysis
└── team-docs/             # Project documentation & design assets
\`\`\`

---

## Tech Stack

### Frontend (Client)
*   **Framework:** React.js (Vite)
*   **Styling:** TailwindCSS
*   **Real-time:** WebRTC (SimplePeer)
*   **State Management:** React Context API

### Backend & AI (Server)
*   **Framework:** Python (FastAPI / Flask)
*   **Database:** MongoDB (via Motor/PyMongo)
*   **Authentication:** JWT & bcrypt
*   **Payments:** Razorpay
*   **AI/ML:** Tesseract/PyMuPDF (OCR), scikit-learn, custom NLP

---

## 🛠️ Local Development Setup

### 1. Frontend Setup
\`\`\`bash
cd frontend
npm install
npm run dev
\`\`\`

### 2. Python Services Setup (Backend, Chatbot, ML)
Each Python directory (`backend`, `healthvision-chatbot`, `ml-service`) requires its own virtual environment.

\`\`\`bash
# Example for the core backend:
cd backend
python -m venv venv

# Activate the virtual environment:
# On Windows: venv\Scripts\activate
# On macOS/Linux: source venv/bin/activate

pip install -r requirements.txt
python main.py  # (or uvicorn main:app --reload)
\`\`\`

---

##  Core System Flows

1. **Authentication:** The Python `backend` handles JWT creation and MongoDB user storage.
2. **Appointments & Payments:** The `backend` generates Razorpay orders and verifies webhook signatures for timeslot booking.
3. **AI Report Analysis:** Uploaded PDFs are passed to the `ml-service` for OCR extraction and data parsing.
4. **Interactive Chatbot:** The frontend queries the `healthvision-chatbot` for NLP-driven symptom triage and urgency badging.

---

##  Collaborative Workflow

1. **Do not push directly to `main`.**
2. Create a branch for your task: `git checkout -b feature/your-feature-name`.
3. Commit your changes with descriptive messages.
4. Push your branch and open a Pull Request for team review.
