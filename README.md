[![FastAPI](https://img.shields.io/badge/FastAPI-%2300C7B7.svg?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Celery](https://img.shields.io/badge/Celery-37814A.svg?style=for-the-badge&logo=celery&logoColor=white)](https://docs.celeryq.dev/)
[![Redis](https://img.shields.io/badge/Redis-%23DC382D.svg?style=for-the-badge&logo=redis&logoColor=white)](https://redis.io/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-%23336791.svg?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-%23004888.svg?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)
[![Docker](https://img.shields.io/badge/Docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=for-the-badge&logo=minio&logoColor=white)](https://min.io/)
[![Firebase](https://img.shields.io/badge/Firebase-%23FFCA28.svg?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com/)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/)


## Vérité AI Backend

Backend infrastructure for **Vérité AI**, a tri-modal deepfake detection platform supporting **image**, **video**, and **audio** analysis with integrated **Explainable AI (XAI)** and **LLM-generated forensic explanations**.

## Research & Thesis

This project was developed as a Final Year Project at National University of Sciences and Technology under the title:

**“Vérité AI: A Deepfake Detection Website with Explainable AI”**

The project was awarded a **Gold Star** in recognition of its technical innovation and practical implementation in the field of AI-driven media forensics.

## Related Repositories

- Frontend: [Vérité AI Frontend](https://github.com/hba777/X-DetectRT-Frontend)
- Hugging Face Collection: [Explainable Deepfake Detection](https://huggingface.co/collections/Redgerd/explainable-deepfake-detection)

## Features

* **Tri-modal** deepfake detection:
  * Image
  * Video
  * Audio
* Explainable AI:
  * Grad-CAM heatmaps
  * Temporal audio attribution
  * LLM-generated forensic narratives
* Asynchronous processing using Celery + Redis
* JWT/Firebase authentication
* PDF forensic report generation
* Detection history for registered users
* Dockerized deployment
* REST API built with FastAPI


## System Architecture

<img width="1494" height="511" alt="FYP - Thesis_page67_image" src="https://github.com/user-attachments/assets/59e01f95-bf2a-4243-8b0e-6dadaf0600a7" />

## Core Modules

### Authentication

* Firebase JWT verification
* Protected API routes
* Role-based access control

### Detection Pipelines

#### Image Detection

* ViT-based deepfake classifier
* Grad-CAM explainability
* Synchronous inference

#### Video Detection

* Frame extraction pipeline
* Celery asynchronous task queue
* Aggregated frame-level predictions

#### Audio Detection

* WavLM-based spoof detection
* Temporal attribution visualization
* Segment-level aggregation


## Explainable AI (XAI)

### Visual Explainability

* Grad-CAM heatmaps
* Facial manipulation localization
* Attention overlays

### Audio Explainability

* Captum Integrated Gradients
* Temporal importance attribution
* Waveform visualization

### LLM Explanations

Natural-language forensic explanations generated using structured prompts and detection metadata.

Example:

> “Regions around the jawline and facial boundary exhibit blending inconsistencies and abnormal texture artifacts commonly associated with synthetic manipulation.”


## API Response Example

```json
{
  "verdict": "fake",
  "confidence": 0.94,
  "modality": "video",
  "explanation": "Facial blending artifacts detected near mouth region.",
  "heatmap_url": "/media/heatmaps/sample.png",
  "report_url": "/reports/report.pdf"
}
```


## Environment Variables

```env
DATABASE_URL=
REDIS_URL=
SECRET_KEY=
FIREBASE_CREDENTIALS=
OPENAI_API_KEY=
MINIO_ENDPOINT=
MINIO_ACCESS_KEY=
MINIO_SECRET_KEY=
```

## Running Locally

### Clone Repository

```bash
git clone https://github.com/your-username/verite-ai-backend.git
cd verite-ai-backend
```

### Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Start Redis

```bash
redis-server
```

### Start FastAPI

```bash
uvicorn app.main:app --reload
```

### Start Celery Worker

```bash
celery -A app.worker worker --loglevel=info
```

---

## Docker Deployment

```bash
docker-compose up --build
```
