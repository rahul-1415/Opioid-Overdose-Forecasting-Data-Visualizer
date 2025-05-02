
# Opioid-Overdose Forecasting Data Visualizer

This project is an interactive web application to visualize data collected for the Opioid Overdose Forecasting project at the Census Block Group (CBG) level across Arizona. It combines a FastAPI backend with a React + TypeScript frontend and is deployed using Google Cloud Run.

---

## 📁 Project Structure

```
Opioid-Overdose-Forecasting-Data-Visualizer/
│
├── backend/              # FastAPI backend with data filtering and API serving
├── frontend/             # React + TypeScript frontend for visualization
├── Dockerfile            # Unified container for frontend and backend
```

---

## 🌐 Live Application

Deployed on Google Cloud Run:  
👉 [https://opioid-visualizer-112451257803.us-central1.run.app/](https://opioid-visualizer-112451257803.us-central1.run.app/)

---

## ⚙️ How to Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Opioid-Overdose-Forecasting-Data-Visualizer.git
cd Opioid-Overdose-Forecasting-Data-Visualizer
```

### 2. Install Backend Dependencies

```bash
cd backend
pip install -r requirements.txt
```

### 3. Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

### 4. Build Frontend

```bash
npm run build
```

### 5. Serve the Full Application

Go back to the root folder and run FastAPI server:

```bash
cd ..
uvicorn backend.main:app --reload
```

Open your browser and navigate to:  
🔗 `http://localhost:8000`

---

## 🚀 Deployment to Google Cloud Run

### Step 1: Authenticate with GCP

```bash
gcloud auth login
gcloud config set project YOUR_PROJECT_ID
```

### Step 2: Build Docker Image

```bash
gcloud builds submit --tag gcr.io/YOUR_PROJECT_ID/opioid-visualizer
```

### Step 3: Deploy to Cloud Run

```bash
gcloud run deploy opioid-visualizer \
  --image gcr.io/YOUR_PROJECT_ID/opioid-visualizer \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

After deployment, GCP will return a URL (e.g., `https://opioid-visualizer-xyz.a.run.app`)

---

## 🧱 Tech Stack

- **Frontend:** React, TypeScript, React-Leaflet, CSS
- **Backend:** FastAPI, GeoPandas, CORS, GZip
- **Deployment:** Docker, Google Cloud Run
- **Data Sources:** ACS Census, ADHS Facilities, Life Expectancy, Opioid Prescriptions

---

## 📊 Features

- Heatmap of prescribed opioid dosage per CBG
- County and ZIP filtering
- Interactive sidebar with neighborhood-level details
- Scalable and cloud-deployable architecture

---

## 📄 License

MIT License

---

## 🙋‍♂️ Author

Rahul Babu  
LinkedIn: linkedin.com/in/rahulb1407/
Email: rahulb1407@gmail.com
