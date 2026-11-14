# Likhitha Sindhu Geddam

**M.S. Data Science '27 @ Arizona State University**

```json
{
  "role": "CIS Research Aide @ W. P. Carey School of Business",
  "building": [
    "Applied AI",
    "Agentic Systems",
    "AI Evaluation & Reliability",
    "ML Systems",
    "Distributed Systems"
  ],
  "languages": ["Python", "Go", "SQL", "TypeScript"],
  "currently": "Turning AI experiments into systems that can be evaluated, observed, and trusted"
}
```

I work on applied AI, agent reliability, ML systems, and distributed infrastructure. I'm currently a **CIS Research Aide at the W. P. Carey School of Business**, working under **Professor Joseph Cazier**.

Most of my projects come from problems I wanted to understand by building them: how to tell whether an AI agent actually completed what it claimed, how to continuously evaluate hallucinations, how distributed jobs recover from failures, and how to keep generative models out of deterministic decision logic when reliability matters.

---

## Featured Projects

### [Silent Failure Auditor](https://github.com/likhitha281/silent-failure-auditor)

A tool for checking whether coding agents actually did what they said they did.

Coding agents can finish a run with a convincing answer even when commands failed, files were never created, or an edit had no effect. Silent Failure Auditor parses execution traces and compares an agent's claims against the evidence in its tool calls.

- Separates execution events, failures, claims, and supporting evidence from agent traces
- Classifies claims as supported, contradicted, or insufficiently evidenced
- Tracks whether failed operations were eventually recovered
- Detects patterns such as misread failures, hallucinated paths, no-op edits, and unresolved retries
- Runs as a Python CLI and can be integrated with GitHub Actions

**Python · Agent Evaluation · GitHub Actions · CI/CD · JSON/JSONL**

---

### [Vigil](https://github.com/likhitha281/vigil)

A two-stage risk detection pipeline for GitHub activity, built around the constraint that deep inspection is expensive.

Vigil first uses inexpensive event information to decide what deserves attention, then spends additional API calls only on suspicious activity. I used the project to explore the tradeoff between detection quality and inspection cost rather than assuming every event can be analyzed equally.

- Screens GitHub push events before triggering deeper inspection
- Looks for secret exposure, history rewrites, and unusual activity patterns
- Uses the GitHub Compare API when event metadata alone is insufficient
- Benchmarks TF-IDF + logistic regression against deterministic rules
- Includes a labeled evaluation suite for false positives, false negatives, and structural blind spots

**Python · Scikit-learn · GitHub API · Pytest · GitHub Actions**

---

### [Forge](https://github.com/likhitha281/forge)

A distributed execution system for experimenting with reliable and elastic workloads.

Forge uses a coordinator/worker architecture and persistent state to manage jobs across workers. The project grew into an exploration of when moving a running workload to a different resource allocation is actually worth the cost of checkpointing and restoration.

- Coordinator/worker communication over gRPC
- Lease-based job execution and recovery when workers disappear
- Persistent job state in PostgreSQL
- Checkpoint/restore support for moving running workloads
- Compares static, naive-elastic, and transition-aware scheduling strategies
- Prometheus and Grafana for runtime observability
- Docker-based environment with Kubernetes deployment support

In my measured experiments, transition-aware scheduling reduced median completion time by **21% across 75 trials** in the evaluated regime.

**Go · gRPC · PostgreSQL · Docker · Kubernetes · Prometheus · Grafana**

---

### [Hallucination Watchdog](https://github.com/likhitha281/HallucinationWatchdog)

An evaluation and observability pipeline for monitoring hallucinations in LLM applications over time.

Rather than treating hallucination evaluation as a one-time benchmark, the project records evaluations continuously so changes in model behavior can be observed.

- Evaluates query, context, and response triples for faithfulness
- Uses Arize Phoenix for evaluation and tracing
- Uses Gemini as the evaluator model
- Exposes an agent interface through Google ADK
- Sends OpenTelemetry traces for observability
- Tracks hallucination rates over time to surface quality drift
- Runs behind a FastAPI service with deployment to Google Cloud Run

**Python · Google ADK · Gemini · Arize Phoenix · FastAPI · OpenTelemetry · Google Cloud Run**

---

### [Orbital Collision Risk Agent](https://github.com/likhitha281/orbital-collision-risk-agent)

A risk-monitoring pipeline for orbital conjunction data from CelesTrak SOCRATES Plus.

The main design decision here was to keep the safety-critical part deterministic. The system calculates risk from the underlying data; an LLM can explain the result, but it does not decide the risk level.

- Ingests real orbital conjunction observations from CelesTrak
- Stores observations in SQLite instead of treating each update as an isolated snapshot
- Scores events using collision probability, urgency, and data freshness
- Compares observations over time to identify increasing, decreasing, or stable risk
- Produces dashboard, JSON, and Markdown outputs
- Uses scheduled automation for repeated ingestion and analysis

**Python · Pandas · SQLite · CelesTrak · GitHub Actions · Docker · Cloudflare Workers**

---

## Research

During my research internship at **IIIT Bangalore**, I worked on multimodal deepfake detection using a vision-language model.

I fine-tuned **SmolVLM2 (256M)** with LoRA for two tasks at once: deepfake classification and natural-language explanation. The training data contained **22,935 videos** from FaceForensics++, Celeb-DF, and CREMA-D.

A large part of the work was also data engineering. I built a streaming preprocessing pipeline that reduced a multi-hundred-GB dataset to under 10 GB and added checkpoint recovery so long training runs could resume after interruptions.

The resulting model achieved **91.8% classification accuracy** and **98.5% precision on real-video detection**.

---

## Tech I Work With

| Area | Stack |
|---|---|
| **Languages** | Python · Go · SQL · JavaScript · TypeScript |
| **ML** | PyTorch · TensorFlow · Scikit-learn · Transformers · NLP · Vision-Language Models · LoRA |
| **LLMs & Agents** | Agentic AI · Multi-Agent Systems · RAG · Tool-Using Agents · LLM Evaluation · Google ADK |
| **Backend & Systems** | FastAPI · REST APIs · gRPC · PostgreSQL · SQLite · Distributed Workers · Job Scheduling |
| **Data** | Pandas · NumPy · SQL · Apache Spark |
| **Infrastructure** | Docker · Kubernetes · GitHub Actions · CI/CD · AWS EC2 · Google Cloud Run · Azure · Cloudflare Workers |
| **Observability** | Prometheus · Grafana · OpenTelemetry · Arize Phoenix |

---

## Other Work

### [Cubbie Balance Together](https://github.com/likhitha281/cubbie-balance-together)

A privacy-aware multi-agent planning application where personal agents coordinate shared plans using selectively disclosed constraints instead of exposing each user's complete private context.

Built with **Next.js, TypeScript, Supabase, and multi-agent coordination**, with human confirmation before agents commit to a shared plan.

---

## Connect

📧 **Email:** [lgeddam1@asu.edu](mailto:lgeddam1@asu.edu)  
💻 **GitHub:** [likhitha281](https://github.com/likhitha281)  
💼 **LinkedIn:** [Likhitha Sindhu Geddam](https://in.linkedin.com/in/likhitha-sindhu-geddam-b92b8b226)
