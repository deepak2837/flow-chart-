graph TD
  A[Start] --> B[Initialize Express, Multer, AWS, Sharp, Path, and FS]
  B --> C[Load Environment Variables and Setup CORS]
  C --> D[Configure AWS Credentials]
  D --> E[Define Helper Functions]
  E --> F{HTTP POST /upload}
  F --> G[Upload Image to Server]
  G --> H[Read Uploaded Image File]
  H --> I[Upload Image to AWS S3]
  I --> J{On S3 Upload Success?}
  J -- No --> K[Return 500 Error]
  J -- Yes --> L[Generate Pre-signed URL for S3 Image]
  L --> M[Delete Local Image File]
  M --> N[Get Authentication Token from Adobe]
  N --> O{Token Retrieval Success?}
  O -- No --> P[Return 500 Error]
  O -- Yes --> Q[Send Image Processing Request to Adobe]
  Q --> R{Image Processing Success?}
  R -- No --> S[Return 500 Error]
  R -- Yes --> T[Generate Download URL for Processed Image]
  T --> U[Return Download URL to Client]
  U --> V[End]

  style A fill:#f9f,stroke:#333,stroke-width:2px;
  style B fill:#bbf,stroke:#333,stroke-width:2px;
  style C fill:#bbf,stroke:#333,stroke-width:2px;
  style D fill:#bbf,stroke:#333,stroke-width:2px;
  style E fill:#bbf,stroke:#333,stroke-width:2px;
  style F fill:#f96,stroke:#333,stroke-width:2px;
  style G fill:#bbf,stroke:#333,stroke-width:2px;
  style H fill:#bbf,stroke:#333,stroke-width:2px;
  style I fill:#bbf,stroke:#333,stroke-width:2px;
  style J fill:#96f,stroke:#333,stroke-width:2px;
  style K fill:#f66,stroke:#333,stroke-width:2px;
  style L fill:#bbf,stroke:#333,stroke-width:2px;
  style M fill:#bbf,stroke:#333,stroke-width:2px;
  style N fill:#bbf,stroke:#333,stroke-width:2px;
  style O fill:#96f,stroke:#333,stroke-width:2px;
  style P fill:#f66,stroke:#333,stroke-width:2px;
  style Q fill:#bbf,stroke:#333,stroke-width:2px;
  style R fill:#96f,stroke:#333,stroke-width:2px;
  style S fill:#f66,stroke:#333,stroke-width:2px;
  style T fill:#bbf,stroke:#333,stroke-width:2px;
  style U fill:#6f6,stroke:#333,stroke-width:2px;
  style V fill:#fff,stroke:#333,stroke-width:2px;
