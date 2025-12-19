# Scalable-Satellite-Imagery-Intelligence
The objective is to move from passive observation (images) to active inference (decision engines). This system is designed to bypass the 'noisy' nature of traditional spectral indices by utilizing local similarity-based deep learning."

graph TD
    subgraph "Data Orchestration Layer"
        A[Satellite Constellations: Sentinel-2 / PRISMA] --> B(STAC API Ingestion)
        B --> C{Preprocessing Pipe}
        C --> C1[Atmospheric/Terrain Correction]
        C --> C2[Cloud & Shadow Masking]
        C1 & C2 --> D[DVC: Data Versioning]
    end

    subgraph "The Inference Engine (Deep Learning)"
        D --> E[Spatial-Spectral Patch Extraction]
        E --> F[Dimensionality Reduction: 3D-CNN / Transformers]
        F --> G[Local Similarity-Based DNN]
        G --> H[Weight Optimization: Local Consistency Loss]
    end

    subgraph "MLOps & Distribution"
        H --> I[MLflow: Experiment Tracking]
        I --> J[Model Registry & Dockerization]
        J --> K[FastAPI: Risk Prediction Engine]
        K --> L[Output: GeoJSON / Risk Vector Layers]
    end

    style G fill:#f9f,stroke:#333,stroke-width:2px
    style D fill:#bbf,stroke:#333,stroke-width:2px
    style L fill:#bfb,stroke:#333,stroke-width:2px
