# Multi-Chain DeFi Analytics Dashboard

A comprehensive full-stack application for tracking DeFi metrics across multiple EVM chains (Ethereum, Polygon, BSC).

## 🏗️ Project Structure

```
defi-analytics-dashboard/
├── README.md
├── .gitignore
├── docker-compose.yml
├── frontend/
│   ├── package.json
│   ├── next.config.js
│   ├── tailwind.config.js
│   ├── tsconfig.json
│   ├── src/
│   │   ├── app/
│   │   │   ├── layout.tsx
│   │   │   ├── page.tsx
│   │   │   └── globals.css
│   │   ├── components/
│   │   │   ├── Dashboard.tsx
│   │   │   ├── NetworkSelector.tsx
│   │   │   ├── MetricCard.tsx
│   │   │   ├── TokenList.tsx
│   │   │   └── charts/
│   │   │       ├── TVLChart.tsx
│   │   │       ├── VolumeChart.tsx
│   │   │       └── YieldChart.tsx
│   │   ├── hooks/
│   │   │   ├── useDefiData.ts
│   │   │   └── useWebSocket.ts
│   │   ├── services/
│   │   │   ├── api.ts
│   │   │   ├── theGraph.ts
│   │   │   └── covalent.ts
│   │   ├── types/
│   │   │   └── defi.ts
│   │   └── utils/
│   │       ├── formatters.ts
│   │       └── constants.ts
│   └── public/
│       └── icons/
├── backend/
│   ├── requirements.txt
│   ├── main.py
│   ├── app/
│   │   ├── __init__.py
│   │   ├── api/
│   │   │   ├── __init__.py
│   │   │   ├── routes/
│   │   │   │   ├── __init__.py
│   │   │   │   ├── analytics.py
│   │   │   │   ├── tokens.py
│   │   │   │   └── protocols.py
│   │   │   └── dependencies.py
│   │   ├── core/
│   │   │   ├── __init__.py
│   │   │   ├── config.py
│   │   │   └── database.py
│   │   ├── services/
│   │   │   ├── __init__.py
│   │   │   ├── data_aggregator.py
│   │   │   ├── cache_service.py
│   │   │   ├── the_graph_service.py
│   │   │   ├── covalent_service.py
│   │   │   └── aave_service.py
│   │   ├── models/
│   │   │   ├── __init__.py
│   │   │   ├── token.py
│   │   │   ├── protocol.py
│   │   │   └── analytics.py
│   │   └── utils/
│   │       ├── __init__.py
│   │       ├── helpers.py
│   │       └── validators.py
│   └── scripts/
│       ├── data_collector.py
│       └── setup_redis.py
└── deployment/
    ├── Dockerfile.frontend
    ├── Dockerfile.backend
    ├── nginx.conf
    └── k8s/
        ├── deployment.yaml
        ├── service.yaml
        └── ingress.yaml
```

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- Python 3.9+
- Redis
- Docker (optional)

### Environment Setup

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/defi-analytics-dashboard.git
cd defi-analytics-dashboard
```

2. **Environment Variables:**
Create `.env` files in both frontend and backend directories.

**Frontend (.env.local):**
```env
NEXT_PUBLIC_API_URL=http://localhost:8000
NEXT_PUBLIC_WS_URL=ws://localhost:8000/ws
NEXT_PUBLIC_COVALENT_API_KEY=your_covalent_key
```

**Backend (.env):**
```env
COVALENT_API_KEY=your_covalent_api_key
THE_GRAPH_API_KEY=your_graph_api_key
REDIS_URL=redis://localhost:6379
DATABASE_URL=postgresql://user:pass@localhost/defi_analytics
AAVE_API_URL=https://aave-api-v2.aave.com
COMPOUND_API_URL=https://api.compound.finance/api/v2
```

### Running with Docker (Recommended)

```bash
docker-compose up -d
```

### Manual Setup

**Backend:**
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

**Redis:**
```bash
redis-server
```

## 📁 File Contents

### Frontend Files

#### `frontend/package.json`
```json
{
  "name": "defi-analytics-frontend",
  "version": "1.0.0",
  "scripts": {
    "dev": "next
