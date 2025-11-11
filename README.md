# 🌱 Plant Health Monitoring System

AI-powered plant disease detection system that identifies diseases from leaf images. Supports 30+ disease classes across Apple, Corn, Grape, Potato, Tomato, Mango, Citrus, and Rice.

## Features

- AI disease detection with confidence scores
- Web interface with drag-and-drop image upload
- FastAPI backend + React TypeScript frontend
- Support for multiple model formats (TensorFlow, PyTorch, ONNX)

## Supported Plants

**Apple**: Scab, Black Rot, Cedar Apple Rust  
**Corn**: Cercospora Leaf Spot, Common Rust, Northern Leaf Blight  
**Grape**: Black Rot, Esca, Leaf Blight  
**Potato**: Early Blight, Late Blight  
**Tomato**: Bacterial Spot, Early/Late Blight, Leaf Mold, Septoria Leaf Spot, Spider Mites, Target Spot, Yellow Leaf Curl Virus, Mosaic Virus  
**Others**: Mango Anthracnose, Citrus Canker, Rice Blast

## Quick Start

### Prerequisites
- Python 3.11+
- Node.js 18+

### Installation

1. **Clone repository**
```bash
git clone https://github.com/Omzee15/Plant-Health-Monitoring.git
cd Plant-Health-Monitoring
```

2. **Backend setup**
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

3. **Frontend setup**
```bash
cd frontend
npm install
npm run dev
```

4. **Access application**
- Frontend: http://localhost:5173
- Backend API: http://localhost:8000
- API Docs: http://localhost:8000/docs

## API Usage

### Prediction Endpoint
```bash
# Upload image for prediction
curl -X POST "http://localhost:8000/predict" \
     -H "Content-Type: multipart/form-data" \
     -F "file=@plant_image.jpg"
```

### Response Format
```json
{
  "predictions": [{
    "class": "Tomato___Healthy",
    "confidence": 0.95,
    "treatment": "No treatment needed"
  }],
  "top_prediction": "Tomato___Healthy",
  "confidence": 0.95,
  "processing_time": 0.123
}
```

## Project Structure
```
Plant-Health-Monitoring/
├── backend/           # FastAPI application
├── frontend/          # React TypeScript app
├── scripts/           # Utility scripts
└── PlantDiseaseDetection.ipynb  # Training notebook
```

## Contributing
1. Fork the repository
2. Create feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit pull request

## License
MIT License - see [LICENSE](LICENSE) for details.

---
**Plant Health Monitoring System** - AI-powered disease detection for sustainable agriculture.