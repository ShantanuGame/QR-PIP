# 📦 QR Batch Tracker API

> A FastAPI-powered backend system to create, track, and retrieve production batches with dynamic QR code generation.

This API allows manufacturers or operations teams to:
- Create batches with metadata
- Generate QR codes for each batch
- Retrieve batch history
- View batch details via QR-linked URLs

---

## 🚀 Core Idea

Each batch created in the system automatically:
1. Stores batch details in MongoDB
2. Generates a unique QR code
3. Links the QR to a frontend view page
4. Enables real-time tracking of batches via scan

---

## 🧠 How It Works

1️⃣ User submits batch details  
2️⃣ API stores data in MongoDB  
3️⃣ Unique ID is generated  
4️⃣ QR code is created with a view URL  
5️⃣ Scanning QR opens batch details page  

---

## ✨ Features

- 📦 Batch creation with production metadata
- 🔗 Auto-generated QR codes for each batch
- 🗄️ MongoDB integration for persistent storage
- 📜 ISO timestamped batch tracking
- 🌐 Frontend view link generation
- ⚡ FastAPI high-performance backend
- 🔐 Environment variable based configuration
- 🛡️ Secure and scalable architecture

---

## 🏗️ Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | FastAPI |
| Database | MongoDB |
| QR Generator | Python `qrcode` |
| Config | python-dotenv |
| Deployment | Render / Docker Ready |

---

## 📂 Project Structure

QR-PIP/
│
├── Backend > main.py
├── Frontend >  all frontend files
├── requirements.txt # Dependencies
├── README.md
└── .gitignore


---

## 🔌 Batch data

{
  "batch_no": "BATCH001",
  "parent_id": "PARENT123",
  "lot_no": "LOT789",
  "balls": 50,
  "roller_with_roller_cages": 20,
  "balls_cages": 30
}

## Response
{
  "batch": {...},
  "qr_data_url": "data:image/png;base64,...",
  "view_url": "http://localhost:5173/view/<batch_id>"
}
