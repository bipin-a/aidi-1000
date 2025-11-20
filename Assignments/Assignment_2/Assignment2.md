# Assignment 2: Build Your First FastAPI Application  
**Due:** November 27, 2025 (End of Day)  
**Total Points:** 100 (110 with bonus)

### Objective
Set up a professional Python environment with uv and build a real, working FastAPI web API.  
You will submit code, a concise design document, and a 5–10 minute demo video.

### Submission – One ZIP folder only
```
YourName_FastAPI_Assignment/
├── main.py
├── pyproject.toml
├── uv.lock
├── requirements_writeup.md
├── architecture_diagram.pdf (or .png)
├── design_document.pdf (or .md)
├── demonstration_video.mp4 (5–10 min, face + clear audio required)
└── screenshots/                  # optional but helpful
```

────────────────────────────────────────
## Part 1 – Environment Setup (Follow Exactly)

**You must use Python 3.10.16**  
Why this exact version?  
Many Python packages contain compiled C extensions that are built for a specific Python version + CPU architecture. Even if Python 3.11 or 3.12 works on your friend’s laptop, it can (and usually will) fail on yours because of differences in CPU (Intel vs AMD vs Apple Silicon), Windows build, or pre-compiled wheels. Pinning 3.10.16 removes 90 % of the “it works on my machine” problems in this course.

1. Install uv (once per computer)  
   ```powershell
   powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
   ```
   Restart PowerShell → run `uv --version`

2. Install Python 3.10.16  
   ```powershell
   uv python install 3.10.16
   ```

3. Create your project  
   ```powershell
   mkdir fastapi-project && cd fastapi-project
   uv init
   uv python pin 3.10.16
   uv venv
   .venv\Scripts\Scripts\Activate.ps1   # do this every new terminal session
   ```

4. Install dependencies  
   ```powershell
   uv add fastapi "uvicorn[standard]"
   ```

5. Run the app  
   ```powershell
   uv run fastapi dev main.py
   ```
   → http://127.0.0.1:8000  Interactive docs: http://127.0.0.1:8000/docs

────────────────────────────────────────
## Part 2 – Code Requirements (main.py)

Your app must have at least these four working endpoints (feel free to add more):

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Hello, World!", "status": "running"}

@app.get("/health")
def health():
    return {"status": "healthy"}

@app.get("/greet/{name}")
def greet(name: str):
    return {"message": f"Hello, {name}!"}

@app.get("/calculate")
def calculate(num1: int, num2: int, operation: str = "add"):
    # implement add, subtract, multiply, divide
    # handle division-by-zero and invalid operation with proper errors
    # include clear docstring required
```

────────────────────────────────────────
## Part 3 – Written Deliverables

1. **requirements_writeup.md** (2–3 paragraphs total)  
   - What is a virtual environment and why is it important?  
   - What challenges did you face during setup and how did you solve them?  
   - What is one thing you learned that surprised you?

2. **Architecture Diagram + Design Document** (one PDF or Markdown file)  

1.FastAPI Layer  
   - Example endpoints you would expose in production (at least /predict, /health, /model-version)  
   - Rate limiting strategy  
   - How you handle scaling

2.Database & Features  
   - Which database(s) and why  
   - Example of one or two real features from your Assignment 1 model and exactly how they are computed and encoded  

     **Example (Netflix recommender)**:  
     “most_watched_genre_last_7d → one-hot encoded as 19 binary columns”  
     “avg_rating_given_by_user → normalised float stored in PostgreSQL”

3.ML Model Integration  
   - Where the trained model is stored (S3, MLflow, etc.)  
   - How FastAPI loads it (at startup or on-demand)  
   - Model versioning strategy and rollback plan

4.ETL / Data Pipeline  
   - How and when new features are calculated (daily Airflow job, real-time Kafka, etc.)

5.Deployment & Monitoring  
   - Cloud/provider, Docker/Kubernetes, auto-scaling rules  
   - Key metrics and alerts

6.Trade-offs  
   - At least two conscious trade-offs with justification (e.g. “chose PostgreSQL over DynamoDB for complex joins but accepted higher ops cost”)

────────────────────────────────────────
## Part 4 – Video Demonstration (10 minutes)

**How to Speak in the Video – Read this carefully**

**Clear speaking comes from clear thinking.**

You cannot explain something perfectly the first time you say it out loud — practice once or twice before hitting record.  
Do NOT read from a script. Speak naturally, as if you’re showing a friend what you built.  
It is completely fine to pause, think, or say “I’m not 100 % sure about the name, but here’s how it works…”.  
Authenticity and real understanding beat polished performance every time.

**Required content (in this order)**:
1. Face cam + quick intro (20–30 sec)
2. Terminal: show `uv --version`, `uv python list`, project folder, start the server
3. Browser: demonstrate root, /health, /greet, /calculate, and the /docs page
4. Screen-share your architecture diagram and explain it
5. Tell one real challenge you hit and how you solved it
6. One thing that surprised you
7. Face cam closing

────────────────────────────────────────
## Grading (100 points)

| Item                                         | Points |
|----------------------------------------------|--------|
| Environment correctly set up (uv + venv + 3.10.16) | 10     |
| Working FastAPI app with required endpoints + /docs | 20     |
| requirements_writeup.md (3 questions)        | 10     |
| Architecture diagram (complete & clear)       | 15     |
| Design document (all required sections)       | 25     |
| Video demo – clear, natural, all parts shown  | 20     |
| **Bonus** deeper reflection & AI usage disclosure | +10    |

────────────────────────────────────────
## Allowed / Not Allowed

**Allowed**  
- Use AI to debug specific errors  
- Read official FastAPI / uv docs and tutorials  
- Discuss concepts (not code) with classmates  

**Not Allowed**  
- Copy entire code or whole design documents from AI or others  
- Pretend you understand something you don’t  

Add a short “Resources & AI Usage” section in your design document listing exactly what you used.

────────────────────────────────────────
## Quick Troubleshooting

| Problem                              | Quick Fix |
|--------------------------------------|-----------|
| “uv not recognized”                   | Restart PowerShell |
| Activate.ps1 blocked                 | `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser` |
| ModuleNotFoundError: fastapi         | Make sure venv is activated or use `uv run` |
| Port 8000 in use                     | Use `--port 8001` or kill the old process |

Good luck!  

The students who are honest about their struggles (and show how they solved them) always score the highest — even if their diagram isn’t the prettiest.  

Clear thinking > perfection.  

See you in the videos :)
