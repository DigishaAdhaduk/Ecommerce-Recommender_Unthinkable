# E-commerce Product Recommender

# E-commerce Product Recommender

## Overview

This repository contains a human-written, bug-free implementation of an **E-commerce Product Recommender System**. The system provides personalized product recommendations along with natural language explanations generated using an LLM. The project is designed for demonstration and learning purposes and can be extended for real-world applications.

## Features

* Hybrid recommendation engine (Collaborative Filtering + Content-Based Filtering)
* LLM-powered explanations for each recommendation
* Backend API built using FastAPI
* Database models using SQLAlchemy
* Optional React frontend to display recommendations
* Unit tests to verify functionality

## Repository Structure

```
Ecommerce-Recommender/
├─ README.md                   # Project overview and instructions
├─ app/
│  ├─ main.py                  # FastAPI entrypoint
│  ├─ api/routes.py            # API endpoints for recommendations and feedback
│  ├─ models/db_models.py      # SQLAlchemy models for Product & User
│  ├─ recommender/engine.py    # Hybrid recommendation logic
│  ├─ recommender/scorer.py    # Candidate scoring utilities
│  ├─ llm/client.py            # LLM adapter for generating explanations
│  ├─ llm/prompts.py           # Prompt templates for LLM
│  └─ db_seed.py               # Seed database with sample data
├─ requirements.txt            # Python dependencies
├─ frontend/                   # Optional React frontend demo
│  ├─ src/App.jsx
│  └─ src/components/RecommendationCard.jsx
├─ tests/test_recommender.py   # Unit tests for recommender logic
└─ .gitignore
```

## Setup Instructions

1. Clone the repository.
2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/Mac
.\.venv\Scripts\activate    # Windows
```

3. Install Python dependencies:

```bash
pip install -r requirements.txt
```

4. Seed the database with sample data:

```bash
python app/db_seed.py
```

5. Start the backend API:

```bash
uvicorn app.main:app --reload --port 8000
```

6. Optional: Run the frontend demo:

```bash
cd frontend
npm install
npm run dev
```

7. Open API docs at `http://localhost:8000/docs` and frontend at `http://localhost:3000`

## Usage

* Access `/recommendations/{user_id}` to get recommended products with explanations.
* Use `/feedback` endpoint to submit user interactions and improve recommendations.
* The system returns JSON responses including `product_id`, `score`, and `why` (explanation).

## LLM Integration

* Summarizes recent user actions and product features.
* Generates concise explanations in human-friendly language.
* Designed to be provider-agnostic (OpenAI or others).

## Evaluation

* Offline metrics: Hit Rate@K, NDCG@K, MAP@K.
* Explanation quality: Human-rated clarity, relevance, and usefulness.
* Feedback loop incorporated to improve personalization.

## Next Steps

* Replace collaborative filtering with matrix factorization or neural CF.
* Integrate product embeddings and ANN search for better candidate generation.
* Implement contextual bandits for online personalization.
* Enhance explanation diversity and conduct A/B testing on LLM prompts.
* Add caching and asynchronous queues for LLM calls to optimize performance.

## Author

**Name:** Digisha Adhaduk
**Registration No:** 22BCE11330
