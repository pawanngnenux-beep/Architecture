# Architecture
flowchart LR
    User --> FE[Frontend App]
    FE --> APIGW[API Gateway]

    APIGW --> PS[Project Service]
    APIGW --> VS[Vendor Service]
    APIGW --> MS[Material Service]
    APIGW --> PRS[Pricing Service]

    PS -->|emit events| EB[(Event Bus)]
    VS -->|emit events| EB
    MS -->|emit events| EB
    PRS -->|emit events| EB

    EB --> DS[Design Service]
    EB --> RS[Rendering Service]
    EB --> NS[Notification Service]
    EB --> AI[AI Recommendation Service]
    EB --> AS[Analytics Service]
