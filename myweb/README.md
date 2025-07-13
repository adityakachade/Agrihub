# Plant Disease Detection App

A React-based web application that uses AI to identify plant diseases from uploaded images and provides detailed treatment recommendations.

## Features

- **Image Upload & Capture**: Upload images from device or capture using camera
- **AI Disease Detection**: Simulated AI analysis to identify plant diseases
- **Detailed Diagnosis**: Comprehensive information about detected diseases including:
  - Disease name and confidence level
  - Severity assessment
  - Symptoms description
  - Treatment recommendations
  - Prevention measures
- **Plant Health Assessment**: Overall health percentage with visual indicators
- **Care Tips**: General plant care recommendations
- **Responsive Design**: Works on desktop and mobile devices
- **Drag & Drop**: Easy image upload with drag and drop functionality

## Technology Stack

- **React 18** with TypeScript
- **Tailwind CSS** for styling
- **Lucide React** for icons
- **Vite** for build tooling

## Getting Started

### Prerequisites

- Node.js (version 16 or higher)
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd plant-disease-detection-app
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open your browser and navigate to `http://localhost:5173`

## Usage

1. **Upload Image**: Click "Choose File" or drag and drop a plant image
2. **Take Photo**: Use "Take Photo" button to capture image with camera
3. **Analyze**: Click "Analyze Plant Health" to start the AI analysis
4. **View Results**: Review the detailed diagnosis and recommendations

## Project Structure

```
src/
├── components/          # Reusable React components
│   ├── DiseaseCard.tsx     # Disease information display
│   ├── HealthMeter.tsx     # Health percentage indicator
│   ├── ImageUpload.tsx     # Image upload component
│   └── PlantCareTips.tsx   # Care tips sidebar
├── types/              # TypeScript type definitions
│   └── index.ts
├── utils/              # Utility functions
│   ├── imageProcessing.ts  # Image handling utilities
│   └── mockData.ts         # Mock disease data
├── App.tsx             # Main application component
├── main.tsx           # Application entry point
└── index.css          # Global styles
```

## Features in Detail

### Disease Detection
The app simulates AI analysis and can detect various plant diseases including:
- Leaf Blight
- Powdery Mildew
- Root Rot
- Aphid Infestation

### Treatment Recommendations
For each detected disease, the app provides:
- Immediate treatment steps
- Prevention strategies
- Affected plant parts
- Severity assessment

### Plant Care Tips
General care recommendations covering:
- Proper watering techniques
- Light requirements
- Regular inspection practices

## Customization

### Adding New Diseases
To add new diseases, update the `mockDiseases` array in `src/utils/mockData.ts`:

```typescript
{
  id: 'unique-id',
  name: 'Disease Name',
  confidence: 85,
  severity: 'Medium',
  description: 'Disease description...',
  symptoms: ['Symptom 1', 'Symptom 2'],
  treatments: ['Treatment 1', 'Treatment 2'],
  prevention: ['Prevention 1', 'Prevention 2'],
  affectedParts: ['Leaves', 'Stems']
}
```

### Styling
The app uses Tailwind CSS. Modify styles by updating the className attributes or extend the Tailwind configuration in `tailwind.config.js`.

## Real AI Integration

To integrate with a real AI service:

1. Replace the mock analysis in `analyzeImage` function
2. Add API endpoints for image upload and analysis
3. Update the `AnalysisResult` interface if needed
4. Add error handling for API failures

Example integration:
```typescript
const analyzeImage = async () => {
  const formData = new FormData();
  formData.append('image', imageFile);
  
  const response = await fetch('/api/analyze', {
    method: 'POST',
    body: formData
  });
  
  const result = await response.json();
  setResult(result);
};
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support or questions, please open an issue in the repository.