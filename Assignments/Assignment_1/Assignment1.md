# Improved Data Stack Problem-First Comparison Assignment

## Assignment Overview

**Objective**: Understand AI/ML tools by focusing on the *problems* they solve, not just their features. You'll explore how real companies build AI systems by (1) comparing competing tools AND (2) analyzing how tools work together in an ecosystem.

**Format**: 10–14 slide presentation only

**Weight**: 10% of final grade

**Due**: Oct 17th 2025 11:59pm (There's a 1 hour grace period)

**Submission**:
- Slide deck as PDF
- Screen recording (mp4) presenting your slides with webcam and audio enabled. (Max 10 mins)

---

## Why This Assignment Matters

When learning about AI, it's easy to get lost in buzzwords like "scalable," "enterprise-grade," or "AI-powered" without understanding *why* these tools exist. This assignment teaches you to think like a data scientist or ML engineer: **start with the problem, then find the right tool**—not the other way around.

By the end, you'll understand:
- How AI/ML systems are actually built in industry
- Why there are so many different tools (and when to use each)
- How to evaluate technology critically, beyond marketing hype
- How tools work together to build complete AI systems

---

## Getting Started: Choose Your AI/ML Use Case

Select **ONE real-world AI application** that you'll use as context for **BOTH tasks**:

**Beginner-Friendly Options:**
1. **Music Recommendations**: Spotify suggesting songs based on your listening history
2. **Sentiment Analysis**: Analyzing if social media posts or product reviews are positive or negative
3. **Text Summarization**: Automatically summarizing long customer reviews or articles
4. **Image Recognition**: Detecting faces in photos or identifying objects in images
5. **Chatbots**: Customer service bots answering common questions
6. **Spam Detection**: Identifying spam emails or fake reviews
7. **Product Recommendations**: Amazon suggesting products you might like

**Your Foundation**: Briefly describe:
- What problem this AI system solves
- What kind of data it needs (text, images, numbers, etc.)
- What type of ML model might be used (you can research this—e.g., neural networks, decision trees, recommendation algorithms)

*This use case will ground both Task A and Task B in a realistic scenario.*

---

## Task A: Competing Tools Comparison

### Choose ONE Pre-Selected Tool Pair

Pick **ONE** of these curated tool comparisons (designed for beginners):

**Option 1: Model Training & Experiment Tracking**
- **Tools**: MLflow vs. Weights & Biases
- **Problem**: Training ML models requires running many experiments—how do you track what works?
- **Good for use cases**: Any AI application (recommendations, sentiment analysis, image recognition)

**Option 2: Data Storage for ML**
- **Tools**: AWS S3 vs. Google Cloud Storage
- **Problem**: ML projects need to store huge amounts of data (images, text, videos)—where do you put it all?
- **Good for use cases**: Image recognition, video analysis, large-scale text data

**Option 3: Model Deployment (Making Models Available to Users)**
- **Tools**: BentoML vs. TensorFlow Serving
- **Problem**: After training your model, how do you make it available for real users to use?
- **Good for use cases**: Any AI application that needs to serve predictions in real-time

**Option 4: Data Transformation & Preparation**
- **Tools**: dbt vs. Apache Spark
- **Problem**: Raw data is messy—how do you clean and prepare it for ML models?
- **Good for use cases**: Sentiment analysis, product recommendations, any tabular data

---

### What to Analyze for Task A

**1. The Problem** (1 slide)
- What specific challenge does this stage address in your AI use case which you picked earlier?
- Why is this challenging in the real world?
- Simple example: "Spotify runs 1,000+ experiments per week—without tracking, they'd forget which models worked best"

**2. Requirements** (1 slide)
- What do companies need from tools at this stage?
- List 3–4 requirements (keep it simple!)
  - Example: "Easy to learn," "Doesn't cost too much," "Works with popular ML libraries," "Good documentation" etc.

**3. Tool #1 Analysis** (1 slide)
- What is it? Who uses it?
- How does it solve the problem?
- **Marketing Claim vs. Reality**: Find ONE simple claim and verify it
  - *Focus on beginner-friendly claims like*: "user-friendly," "easy to set up," "free tier available," "great documentation"
  - *Avoid complex claims like*: "scales to petabytes" or "sub-millisecond latency"
- Simple trade-offs (e.g., "free but requires more setup" or "expensive but easier to use")
- Best use cases (when to pick this tool)

**4. Tool #2 Analysis** (1 slide)
- Same structure as Tool #1

**5. Decision Framework** (1 slide)
- When should someone choose Tool A vs. Tool B?
- 2–3 simple questions (e.g., "Do you have budget?" "Do you need fancy visualizations?" "Is setup time a concern?")
- Visual comparison—keep it simple! (table or basic flowchart)

---

## Task B: Complementary Tools Ecosystem

### Choose ONE Pre-Selected Tool Ecosystem

Pick **ONE** of these curated ecosystems:

**Option 1: Experiment Tracking → Deployment**
- **Tools**: MLflow + Docker
- **Problem**: You've trained a great model in MLflow—now you need to package it so others can use it
- **Integration**: MLflow saves your model → Docker packages it into a container → Ready to deploy
- **Good for**: Any ML use case

**Option 2: Data Storage → Processing**
- **Tools**: AWS S3 + Apache Spark
- **Problem**: Your raw data is stored in S3—now you need to clean and transform it for ML
- **Integration**: S3 stores raw data → Spark reads from S3, processes it → Saves cleaned data back to S3
- **Good for**: Large datasets (images, text, tabular data)

**Option 3: Container Packaging → Deployment**
- **Tools**: Docker + Kubernetes
- **Problem**: Your ML model is in a container—now you need to deploy it to handle thousands of users
- **Integration**: Docker packages your model → Kubernetes deploys and scales it automatically
- **Good for**: High-traffic applications (recommendations, chatbots)


**Option 4: Data Transformation → Model Training**
- **Tools**: dbt + MLflow
- **Problem**: Raw messy data needs to be cleaned and prepared before you can train ML models
- **Integration**: dbt transforms raw data using SQL → Saves clean tables → MLflow reads clean data for training
- **Good for**: Tabular data projects (customer churn prediction, sales forecasting, fraud detection) 
   - Because data transformations are usually in SQL, where the data inherintly is structured in a tabular format


**Option 5: Cloud Storage → Automated Processing**
- **Tools**: AWS S3 + AWS Lambda
- **Problem**: Every time new data arrives, you need to automatically process it without managing servers
- **Integration**: New file uploaded to S3 → S3 triggers Lambda function automatically → Lambda processes file → Saves result
- **Good for**: Event-driven ML workflows (process images on upload, run predictions on new data, ETL pipelines)

```
**NOTE**: You can come up with your own, just have approval before proceeding! 
```

---

### What to Analyze for Task B

**1. The Multi-Stage Problem** (1 slide)
- What workflow challenge requires multiple tools?
- Why can't one tool handle everything?
- Simple example: "After training a spam detector, you can't just email the model file to users—you need to package and deploy it"

**2. Requirements** (1 slide)
- List 3–4 requirements for the complete workflow
- Include ONE integration requirement (keep it simple!)
  - Example: "Tool B must be able to read Tool A's output format"

**3. Ecosystem Analysis** (1–2 slides)
- **Tool #1 Role**: What does it do? What does it output?
- **Tool #2 Role**: What does it do? What does it need as input?
- **How They Connect** (high-level, conceptual):
  - What data/files flow between them?
  - Example: "MLflow saves models as files → Docker reads those files and packages them"
  - You don't need to know APIs or code—just the concept!
- **Marketing Claim vs. Reality**: Pick ONE tool and check a claim about integration
  - *Focus on claims like*: "seamless integration," "works out of the box," "simple setup"

**4. Integration Checklist** (1 slide)

Use this simple template to organize your findings:

| **Question** | **Your Answer** |
|-------------|----------------|
| What does Tool 1 output? | (e.g., "CSV files," "model files," "Docker images") |
| What does Tool 2 need as input? | (e.g., "CSV files," "model files," "container images") |
| Are they compatible? | (Yes/No + brief explanation) |
| What's required to connect them? | (e.g., "Install a plugin," "Write a script," "Use cloud storage") |
| Common challenges? | (e.g., "Different file formats," "Setup complexity," "Version mismatches") |

**5. When to Use This Ecosystem** (1 slide)
- When is this combination worth it?
- 2–3 key considerations
- Simple workflow diagram showing how tools connect (boxes and arrows!)

---

## Presentation Structure (10–14 slides)

### Slide 1: Title Slide
- Your name, course, date
- Your chosen AI/ML use case
- Tools you're comparing (Task A) and ecosystem you're analyzing (Task B)

### Slide 2: AI Use Case Overview
- Describe your chosen AI application
- What problem does it solve?
- What data does it need?
- Simple concrete example (e.g., "Spotify predicting next song based on what you've liked")

---

### **TASK A SECTION** (5 slides)

### Slide 3: Task A - The Problem
- The ML stage you chose (e.g., "Model Training & Experiment Tracking")
- Why this is challenging for your AI use case
- Simple real-world scenario

### Slide 4: Task A - Requirements
- 3–4 key requirements
- Why each matters (1 sentence each)

### Slide 5: Task A - Tool #1 Analysis
- Tool name and brief description
- How it solves the problem
- **Marketing Claim vs. Reality** (simple claim only!)
- Key trade-offs
- Best use cases

### Slide 6: Task A - Tool #2 Analysis
- Same structure as Slide 5

### Slide 7: Task A - Decision Framework
- "When to choose Tool A vs. Tool B"
- 2–3 simple decision questions
- Visual comparison (simple table or flowchart)

---

### **TASK B SECTION** (5 slides)

### Slide 8: Task B - The Multi-Stage Problem
- Workflow you chose (e.g., "Experiment Tracking → Deployment")
- Why this requires two tools
- How it applies to your AI use case

### Slide 9: Task B - Requirements
- 3–4 requirements for the complete workflow
- Include one integration requirement
- Why each matters

### Slide 10: Task B - Tool Roles & Connection
- **Tool #1**: What it does, what it outputs
- **Tool #2**: What it does, what it needs as input
- **How they connect** (conceptual/high-level)

### Slide 11: Task B - Integration Analysis
- Use the integration checklist template
- **Marketing Claim vs. Reality** about integration
- Common challenges

### Slide 12: Task B - Ecosystem Guidelines
- When to use this ecosystem
- 2–3 key considerations
- Simple workflow diagram (boxes and arrows showing data flow)

---

### **CONCLUSION** (2 slides)

### Slide 13: Key Learnings & Reflection
- What surprised you in Task A (competing tools)?
- What surprised you in Task B (ecosystem)?
- How will you evaluate AI tools differently now?
- What was most challenging to understand?

### Slide 14: References
- 4–6 credible sources in APA format
- At least 2 sources for Task A
- At least 2 sources for Task B

---

## Research Requirements

**Required Sources: 4–6 Total** 

**For Task A (at least 2 sources):**
1. Official tool documentation or beginner's guide
2. User reviews/comparison (Reddit, YouTube, Medium, etc.)

**For Task B (at least 2 sources):**
1. Integration tutorial or guide
2. User experience or case study showing the ecosystem

**You can add 1–2 additional sources** if helpful, but 4 sources minimum is fine!

---

## Integration Analysis Template for Task B

Use this checklist to organize your Task B findings:

```
INTEGRATION CHECKLIST

1. What does Tool 1 produce/output?
   Answer: _________________________________

2. What format is that output? (files, data, images, etc.)
   Answer: _________________________________

3. What does Tool 2 need as input?
   Answer: _________________________________

4. Are they compatible out of the box?
   ☐ Yes, they work together easily
   ☐ No, you need extra steps
   
5. What's needed to connect them?
   Answer: _________________________________
   (Examples: "Install a plugin," "Write a small script," "Use cloud storage," "Just save and load files")

6. What could go wrong? (Common challenges)
   Answer: _________________________________
   (Examples: "File formats don't match," "Setup is complicated," "Different versions conflict")

7. Is the integration worth the effort?
   ☐ Yes, because: _________________________
   ☐ No, because: __________________________
```

---

## Grading Rubric (100 points)

| **Criteria** | **Points** | **What We're Looking For** |
|-------------|-----------|---------------------------|
| **AI Use Case Foundation (10 pts)** | 10 | Clear, realistic AI use case; well-explained and connects to both tasks |
| **TASK A: Problem & Requirements (10 pts)** | 10 | Clear problem for chosen stage; 3–4 relevant requirements; real-world context |
| **TASK A: Tool Comparison (15 pts)** | 15 | Good analysis of both tools; clear trade-offs; honest evaluation |
| **TASK A: Marketing Claims (8 pts)** | 8 | Both claims fact-checked (simple claims OK!); uses evidence from research |
| **TASK A: Decision Framework (7 pts)** | 7 | Practical framework; helpful visual; clear guidance |
| **TASK B: Workflow & Requirements (10 pts)** | 10 | Clear multi-stage problem; explains why two tools needed; integration requirement included |
| **TASK B: Ecosystem Analysis (15 pts)** | 15 | Clear explanation of each tool's role; how they connect (high-level is fine); realistic challenges |
| **TASK B: Integration Checklist (8 pts)** | 8 | Completed integration template/checklist; claim fact-checked; honest about challenges |
| **TASK B: Workflow Diagram (7 pts)** | 7 | Simple visual showing how tools connect; easy to understand (boxes and arrows is fine!) |
| **Reflection & Learning (5 pts)** | 5 | Thoughtful reflection; insights about problem-first thinking; honest about challenges |
| **Presentation Quality (10 pts)** | 10 | Clear slides; good flow; engaging delivery; not too text-heavy |
| **Research & Citations (5 pts)** | 5 | 4–6 credible sources; proper APA format; good variety |

---

## Tips for Success

### General Tips:
✅ **Start simple**—use the curated resources provided  
✅ **Use ONE AI use case** throughout both tasks  
✅ **Focus on understanding**, not becoming an expert  
✅ **Visuals over text**—diagrams, tables, simple flowcharts  
✅ **It's OK to say "I learned this is harder than I thought"**  

### Task A Tips:
✅ **Pick simple marketing claims** (like "user-friendly" not "petabyte-scale")  
✅ **Check Reddit/YouTube** for honest user opinions  
✅ **Focus on practical trade-offs** (cost, ease of use, setup time)  
✅ **Use comparison tables**—they're clear and visual  

### Task B Tips:
✅ **Use the integration checklist**—it guides your research  
✅ **Draw the workflow first**—boxes and arrows showing data flow  
✅ **High-level understanding is enough**—you don't need to know code or APIs  
✅ **Look for tutorials**—YouTube is great for seeing how tools connect  
✅ **Be honest if integration seems hard**—that's valuable learning!  

### What to Avoid:
❌ Trying to become an expert in every tool  
❌ Getting lost in technical details—stay high-level  
❌ Accepting marketing without checking  
❌ Making slides text-heavy—use visuals!  
❌ Picking complex claims you can't verify  

---

## Example: Spotify Music Recommendations

**AI Use Case**: Spotify recommending songs based on listening history

**Task A**: Model Training (MLflow vs. Weights & Biases)
- **Problem**: Spotify tests hundreds of recommendation algorithms—how do they track which works best?
- **Simple Claim Check**: 
  - MLflow: "Open source and free" → TRUE (checked GitHub and docs)
  - W&B: "Beautiful visualizations" → TRUE (YouTube tutorials show impressive dashboards)
- **Key Finding**: MLflow is free but needs setup; W&B is prettier but costs money for teams

**Task B**: Training → Deployment (MLflow + Docker)
- **Problem**: After finding the best model in MLflow, how do you package it so millions of users can get recommendations?
- **Integration**: MLflow saves the model → Docker packages it into a container → Ready to deploy to servers
- **Claim Check**: MLflow claims "easy Docker deployment" → MOSTLY TRUE but requires learning Docker basics first
- **Challenge**: You need to understand both MLflow AND Docker—learning curve for beginners


---

## Questions?

**"What if I don't understand the technical details?"**  
That's completely fine! Focus on the *concepts* and *why tools exist*. You're learning to evaluate, not build.

**"Can I use resources not on the curated list?"**  
Absolutely! The list is a starting point. Any credible source works.

**"What if I can't verify a marketing claim?"**  
Document what you tried! Saying "I couldn't find evidence" is valid research.

**"How long should this take?"**  
Plan 8–10 hours: 2 hours for use case, 3 hours Task A, 3 hours Task B, 2 hours for slides.

**"The integration seems complicated—is that OK?"**  
Yes! Being honest about complexity is valuable. Use the template and stay high-level.

---

**Remember**: This assignment is about learning to think critically, not becoming a tool expert. Focus on understanding *why* tools exist and *how* to evaluate them. That mindset will serve you throughout your tech career—even as tools change. Good luck! 🚀