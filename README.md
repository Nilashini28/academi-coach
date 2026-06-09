<div align="center">

<!-- Animated Header SVG -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=200&section=header&text=AcademiCoach&fontSize=60&fontColor=ffffff&fontAlignY=38&desc=AI-Powered%20Academic%20Integrity%20%E2%80%94%20Built%20on%20Empathy&descAlignY=58&descSize=16&animation=fadeIn" width="100%"/>

<br/>

<!-- Animated typing SVG -->
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&pause=1000&color=A78BFA&center=true&vCenter=true&width=700&lines=Every+other+system+watches+the+exam.;AcademiCoach+watches+the+journey.;Because+the+journey+is+where+it+starts+%E2%80%94;and+where+it+can+be+stopped." alt="Typing animation" />

<br/><br/>

<!-- Badges row 1 -->
[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.110-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-IsolationForest-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)](https://scikit-learn.org)

<!-- Badges row 2 -->
[![WebSocket](https://img.shields.io/badge/WebSocket-Live%20Events-6366F1?style=for-the-badge&logo=socket.io&logoColor=white)]()
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?style=for-the-badge&logo=postgresql&logoColor=white)]()
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)]()

<!-- Hackathon badge -->
<br/>
[![Far Away Hackathon](https://img.shields.io/badge/%F0%9F%8F%86%20Far%20Away%20Hackathon-Agentic%20%26%20Autonomous%20Systems%20Track-7C3AED?style=for-the-badge)](.)

</div>

---

<br/>

## The Problem Nobody Is Solving

<table>
<tr>
<td width="50%">

```
Timeline of a student who cheats:

Week 1   ████████████  Engaged, on track
Week 3   ███████░░░░░  Missed two sessions  
Week 6   █████░░░░░░░  Quiz scores dropping
Week 9   ███░░░░░░░░░  Disengaged, isolated
Week 11  █░░░░░░░░░░░  Desperate, withdrawn
Week 14  ░░░░░░░░░░░░  
                    ↓
         [ PROCTORING ACTIVATES ]
                    ↓
              Too late.
```

</td>
<td width="50%">

**73%** of students who cheat show measurable disengagement **4+ weeks before** the incident.

The $8.5B academic integrity market was built to answer one question:

> *"Did the student cheat?"*

It activates for **2–3 hours** at the end of 14 weeks. It sees nothing before the exam starts. Nothing after it ends.

**AcademiCoach asks a different question:**

> *"Did we do everything in our power to make sure they never needed to?"*

</td>
</tr>
</table>

---

<br/>

## System Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                         AcademiCoach Platform                       │
│                                                                     │
│  ┌──────────────┐   ┌──────────────┐   ┌──────────────────────┐     │
│  │   FRONTEND   │   │   BACKEND    │   │     AGENT LAYER      │     │
│  │  React + TS  │◄──│  FastAPI     │◄──│                      │     │
│  │              │   │  WebSocket   │   │  ┌────────────────┐  │     │
│  │  Dashboard   │   │  REST API    │   │  │  Orchestrator  │  │     │
│  │  ExamMonitor │   │              │   │  │  (ReAct Loop)  │  │     │
│  │  Escalations │   │              │   │  └───────┬────────┘  │     │
│  └──────────────┘   └──────────────┘   │          │           │     │
│                                         │    ┌─────▼──────┐   │     │
│                                         │    │  Agents    │   │     │  
│                                         │  ┌─┤ Engagement │   │     │
│                                         │  │ │ Monitor    │   │     │
│  ┌──────────────────────────────────┐   │  ├─┤ Intervene  │   │     │
│  │          ML MODELS               │   │  ├─┤ Exam Guard │   │     │
│  │                                  │◄──┤  ├─┤ Escalation │   │     │
│  │  IsolationForest (per-student)   │   │  └─┤ Analytics  │   │     │
│  │  BehavioralBaseline (14wk FP)    │   │    └────────────┘   │     │
│  │  RiskClassifier (early warning)  │   └─────────────────────┘     │
│  └──────────────────────────────────┘                               │
│                                                                     │
│  ┌─────────────────────────────────────────────────────────────┐    │
│  │  PostgreSQL  │  Redis (event bus)  │  Model Registry        │    │
│  └─────────────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────────────┘
```

---

<br/>

## The Five Phases

<div align="center">

| Phase | What It Does | Key Tech |
|:---:|---|---|
| **LEARN** | Continuous monitoring across 14 weeks — attendance, quiz attempts, session depth, forum activity, submission patterns | Feature extraction pipeline + PostgreSQL time-series |
| **COACH** | Proactive AI-driven intervention — personalized study plans, peer group connections, faculty alerts, wellness nudges | `intervention_agent.py` + LLM reasoning |
| **CONDUCT** | Secure exam creation and session management with tamper-evident audit logs | FastAPI + JWT-gated sessions |
| **GUARD** | Context-aware monitoring comparing each student against **their own 14-week behavioral fingerprint** — not a class average | `IsolationForest` per student + `exam_guard_agent.py` |
| **ANALYZE** | Post-exam outcome intelligence to close the feedback loop and improve future interventions | `analytics_agent.py` + dashboard |

</div>

---

<br/>

## The Core Innovation: Behavioral Fingerprinting

> A student who has consistently scored **45%** across 10 practice assessments and suddenly answers at **near-perfect accuracy** with anomalous interaction patterns is flagged — not because they deviated from the class norm, **but because they deviated from themselves.**

```python
# backend/models/isolation_forest.py  (simplified)

class StudentIsolationForest:
    """
    One model per student. Trained on their own 14-week
    engagement history. Anomaly = deviation from self.
    """
    def fit(self, student_id: str, feature_history: pd.DataFrame):
        self.model = IsolationForest(contamination=0.05, random_state=42)
        self.model.fit(feature_history)
        self.baseline_stats = feature_history.describe()

    def score_exam_session(self, live_features: dict) -> AnomalyResult:
        score = self.model.decision_function([list(live_features.values())])[0]
        confidence = self._to_confidence(score)
        return AnomalyResult(
            anomaly_score=score,
            confidence=confidence,
            escalate=confidence > ESCALATION_THRESHOLD,  # confidence-gated
            deviation_from=self.baseline_stats
        )
```

---

<br/>

## ReAct Agent Loop

```
                    ┌─────────────────────────────────┐
                    │         Orchestrator             │
                    │                                  │
   Exam event ─────►│  PERCEIVE → REASON → ACT        │
                    │              │                   │
                    │              ▼                   │
                    │     Is confidence < threshold?   │
                    │         /           \            │
                    │       YES            NO          │
                    │        │             │           │
                    │        ▼             ▼           │
                    │  ESCALATE to    REPLAN &         │
                    │  human reviewer  continue        │
                    │  (faculty UI)   monitoring       │
                    └─────────────────────────────────┘
```

The orchestrator never auto-flags a student. When anomaly confidence exceeds the threshold, it **pauses and surfaces the moment to a human** — a faculty reviewer sees the behavioral deviation, the 14-week context, and makes the final call. This is the demo's centrepiece.

---

<br/>

## Quick Start

**Prerequisites:** Python 3.11+, Node 20+, Docker

```bash
# 1. Clone
git clone https://github.com/your-team/academicoach.git
cd academicoach

# 2. Environment
cp .env.example .env
# Fill in DATABASE_URL, SECRET_KEY, LLM_API_KEY, MODEL_PATH

# 3. Backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --port 8000

# 4. Frontend (new terminal)
cd frontend
npm install
npm run dev

# 5. Or run everything with Docker
docker-compose up --build
```

The app will be live at `http://localhost:5173`. The API docs are at `http://localhost:8000/docs`.

---

<br/>

## Project Structure

```
academicoach/
├── backend/
│   ├── agents/                  ← Orchestration layer
│   │   ├── orchestrator.py      ← ReAct loop (perceive → reason → act → replan)
│   │   ├── engagement_monitor_agent.py
│   │   ├── intervention_agent.py
│   │   ├── exam_guard_agent.py  ← Live anomaly detection
│   │   ├── escalation_agent.py  ← Confidence-gated human handoff
│   │   └── analytics_agent.py
│   ├── models/                  ← ML layer
│   │   ├── isolation_forest.py  ← Per-student anomaly scorer
│   │   ├── behavioral_baseline.py
│   │   └── risk_classifier.py
│   ├── api/                     ← FastAPI routes
│   │   ├── websocket.py         ← Live exam event bus → frontend
│   │   ├── students.py
│   │   ├── exams.py
│   │   └── escalations.py
│   └── services/
│       ├── feature_extractor.py
│       └── engagement_ingestor.py
├── frontend/
│   └── src/
│       ├── pages/               ← Dashboard, ExamMonitor, Escalations
│       ├── components/          ← RiskBadge, AnomalyAlert, LiveExamFeed
│       └── hooks/
│           └── useExamSocket.ts ← WebSocket bridge to backend
├── .env.example
└── docker-compose.yml
```

---

<br/>

## Key Environment Variables

```bash
# .env.example

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/academicoach

# Security
SECRET_KEY=your-secret-key-here
JWT_ALGORITHM=HS256
JWT_EXPIRE_MINUTES=480

# ML
MODEL_PATH=./backend/models/artifacts
ISOLATION_FOREST_CONTAMINATION=0.05
ESCALATION_CONFIDENCE_THRESHOLD=0.82

# LLM (for agent reasoning)
LLM_API_KEY=your-anthropic-or-openai-key
LLM_MODEL=claude-sonnet-4-20250514

# Redis (event bus)
REDIS_URL=redis://localhost:6379
```

---

<br/>

## Why This Wins

<div align="center">

| What judges look for | How AcademiCoach delivers |
|---|---|
| Full agentic ReAct loop | `orchestrator.py` — perceive, reason, act, replan on every exam event |
| Human-in-the-loop moment | Confidence-gated escalation with live faculty override UI |
| Novel ML application | Isolation Forest trained **per student** — not a global classifier |
| Real-world impact | 300M students, $8.5B market, zero prevention-focused competitors |
| Demo-able in 3 minutes | WebSocket live feed + anomaly alert fires mid-demo |

</div>

---

## License

MIT © 2025 AcademiCoach Team

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=120&section=footer" width="100%"/>
</div>
