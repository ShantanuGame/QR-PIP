# 🏭 QR-PIP — Production Batch Tracking Software

> A full-stack industrial software system for creating, managing, and tracking production batches using dynamic QR codes.

QR-PIP is designed for manufacturing and operations environments where each batch needs a unique identity, traceability, and quick retrieval through QR scanning.

This is not just an API — it is a complete batch tracking software backend that integrates with a frontend dashboard to provide real-time batch visibility.

---

## 🚀 Software Overview

QR-PIP enables organizations to:
- Create production batches with detailed metadata
- Automatically generate QR codes for each batch
- Track batches through unique scan-based URLs
- Retrieve historical batch data instantly
- Integrate seamlessly with a frontend management dashboard

Each batch becomes digitally traceable from creation to inspection.

---

## ✨ Core Capabilities

- 📦 Batch creation with structured production details
- 🔗 Automatic QR code generation for each batch
- 🗄️ Persistent batch storage using MongoDB
- 🕒 Timestamp-based batch tracking
- 🌐 Dynamic frontend view link generation
- ⚡ High-performance FastAPI backend engine
- 🛡️ Secure environment-based configuration
- 🏗️ Designed for scalable industrial usage

---

## 🧠 System Workflow

1. Operator creates a new batch entry  
2. System stores batch data in database  
3. Unique batch ID is generated  
4. QR code is created containing batch view link  
5. Scanning QR opens batch details in the software dashboard  

This ensures complete digital traceability of production batches.

---

## 🏗️ Technology Stack

| Component | Technology |
|-----------|------------|
| Backend Engine | FastAPI (Python) |
| Database | MongoDB |
| QR Generation | Python `qrcode` |
| Configuration | python-dotenv |
| Frontend | React (separate UI dashboard) |
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


---

## 📦 Functional Modules

### 1️⃣ Batch Creation Module
Creates and stores production batch data with:
- Batch Number
- Parent ID
- Lot Number
- Balls Count
- Roller with Cages Count
- Ball Cages Count

Each creation automatically generates a QR code.

---

### 2️⃣ QR Tracking Module
Every batch is assigned a unique QR code containing:
Scanning the QR opens the batch record inside the software dashboard.

---

### 3️⃣ Batch History Module
Retrieve all batches sorted by latest created for operational review and auditing.

---

### 4️⃣ Batch Detail Lookup
Fetch complete metadata of a single batch using its unique identifier.

---

## 🔐 Environment Configuration

Create a `.env` file:

```env
MONGO_URI=your_mongodb_connection_string
FRONTEND_URL=http://localhost:5173

1️⃣ Clone Repository
git clone https://github.com/ShantanuGame/QR-PIP.git
cd QR-PIP

2️⃣ Create Virtual Environment
python -m venv venv
venv\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Run Software Backend
uvicorn main:app --reload
