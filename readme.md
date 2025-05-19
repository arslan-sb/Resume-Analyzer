# Resume Analyzer

A sophisticated resume analysis and matching system that helps recruiters find the best candidates based on their requirements. The system uses natural language processing and machine learning techniques to analyze resumes and match them with job requirements.

## Features

- PDF Resume Parsing
- Information Extraction (Education, Experience, Skills, Projects)
- Date Range Analysis
- Experience Duration Calculation
- Similarity Matching using Cosine Similarity
- PostgreSQL Database Integration
- RESTful API Endpoints
- Modern Frontend Interface

## Project Structure

```
Resume-Analyzer/
├── Frontend/               # React-based frontend application
├── cvRetrival/            # Virtual environment
├── custom_cv_ner_model/   # Custom NER model for CV analysis
├── traindata/             # Training data for the model
├── readCV.py              # PDF parsing and information extraction
├── similarityCalulation.py # Similarity matching and API endpoints
└── postsqlDB.py           # Database operations
```

## Prerequisites

- Python 3.x
- PostgreSQL
- Node.js (for frontend)
- Virtual Environment

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd Resume-Analyzer
```

2. Set up the virtual environment:
```bash
source cvRetrival/bin/activate  # For Unix/Mac
# OR
.\cvRetrival\Scripts\activate  # For Windows
```

3. Install Python dependencies:
```bash
pip install -r requirements.txt
```

4. Set up PostgreSQL database:
- Create a database named "postgres"
- Create a user "admin1" with password "123"
- Ensure PostgreSQL is running on port 5432

5. Install frontend dependencies:
```bash
cd Frontend
npm install
```

## Usage

1. Start the backend server:
```bash
python similarityCalulation.py
```

2. Start the frontend development server:
```bash
cd Frontend
npm run dev
```

3. Access the application at `http://localhost:5173`

## API Endpoints

- `POST /process_query`: Process job requirements and return matching candidates
- `GET /get_cv/<candidate_id>`: Retrieve candidate's CV

## Database Schema

The PostgreSQL database uses the following schema:

```sql
CREATE TABLE candidates (
    ID SERIAL PRIMARY KEY,
    Education TEXT,
    Education_dates TEXT,
    Experience TEXT,
    Experience_dates TEXT,
    Skills TEXT,
    PDF_data BYTEA
);
```

## Technologies Used

- Backend:
  - Python
  - Flask
  - PyPDF2
  - scikit-learn
  - PostgreSQL
  - psycopg2

- Frontend:
  - React
  - Vite
  - Modern UI components

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.