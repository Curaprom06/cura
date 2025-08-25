flowchart TB
  User[Usuario (Navegador)] --> CDN[Hosting estático (Vite build/ CDN)]
  CDN -->|HTTPS| Nginx[Nginx / Reverse Proxy]
  Nginx -->|HTTPS :443| API[Node.js API (Express/PM2)]
  API -->|TCP 3306| MySQL[(Base de datos MySQL)]
  API --> Logs[(Logs/Monitoreo)]
  API --> Redis[(Redis - opcional cache/sesiones)]

  classDef node fill:#ffffff,stroke:#000,stroke-width:2px;
  classDef core fill:#001f3f,stroke:#000,color:#fff,stroke-width:2px;
  class CDN,Nginx,API,MySQL,Logs,Redis node;
  class API core;
