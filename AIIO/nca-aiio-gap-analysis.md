# NCA-AIIO Study Suite — Gap Analysis vs. Official Exam Guide

**Source:** NVIDIA Official Study Guide (NCA-AIIO, Feb 2026) + `nca-aiio-study-guide.md`
**Date:** 2026-03-14
**Current question bank:** 163 questions (50 original + 95 from NVIDIA practice tests 1-4 + 18 gap coverage, 5 duplicates removed)

---

## Coverage Map

### Domain 1: Essential AI Knowledge (38%) — 8 subtopics

| # | Official Subtopic | Coverage | Questions |
|---|---|---|---|
| 1.1 | NVIDIA software stack | Good | Q0,Q3,Q5,Q8,Q9,Q11,Q12,Q13,Q16 |
| 1.2 | Training vs inference requirements | Good | Q7,Q14,Q17 |
| 1.3 | AI vs ML vs DL | Thin (1q) | Q2 |
| 1.4 | AI adoption factors | Thin (1q) | Q4 |
| 1.5 | AI use cases & industries | Thin (1q) | Q15 (automotive only) |
| 1.6 | NVIDIA solutions purpose/use case | Good | Multiple |
| 1.7 | AI lifecycle software components | OK (2q) | Q6,Q18 |
| 1.8 | GPU vs CPU architecture | OK (2q) | Q1,Q10 |

### Domain 2: AI Infrastructure (40%) — 10 subtopics

| # | Official Subtopic | Coverage | Questions |
|---|---|---|---|
| 2.1 | Hardware requirements for AI tasks | Partial | Q23,Q26,Q31 |
| 2.2 | Scale GPU infrastructure | OK (2q) | Q29,Q37 |
| 2.3 | Power & cooling in data centers | Good | Q26,Q27,Q35 |
| 2.4 | On-prem vs cloud | Thin (1q) | Q28 |
| 2.5 | Cluster components | Partial | Q29 |
| 2.6 | Facility requirements | **NONE** | — |
| 2.7 | Networking requirements for AI | Good | Q19,Q20,Q21,Q37 |
| 2.8 | DC networking protocols & concepts | Good | Q22,Q25,Q30 |
| 2.9 | High-speed network options | Good | Q32,Q33,Q38 |
| 2.10 | DPU purpose & benefits | Thin (1q) | Q24 |

### Domain 3: AI Operations (22%) — 4 subtopics

| # | Official Subtopic | Coverage | Questions |
|---|---|---|---|
| 3.1 | DC management & monitoring | OK (3q) | Q39,Q46,Q48 |
| 3.2 | Orchestration & job scheduling | OK (3q) | Q41,Q42,Q47 |
| 3.3 | GPU monitoring metrics | Partial (2q) | Q43,Q45 |
| 3.4 | Virtualization for AI | Good (3q) | Q40,Q44,Q49 |

---

## Topics with ZERO Question Coverage

### 1. Facility Requirements (subtopic 2.6)
- Physical space, floor loading, weight per rack
- Fire suppression systems for high-density compute
- UPS and power redundancy (N+1, 2N)
- Electrical distribution and PDU considerations
- Physical security and access control

### 2. BMC (Baseboard Management Controller)
- Out-of-band remote hardware management
- Lights-out management (power cycle, BIOS, console access remotely)
- Mentioned in both the markdown study guide (section 2.7) and official suggested readings

### 3. GPUDirect Storage
- Direct path between storage devices and GPU memory (bypasses CPU and system memory)
- Distinct from GPUDirect RDMA (which is GPU-to-NIC)
- Mentioned in study guide section 2.8

### 4. NVIDIA Container Toolkit
- Enables Docker/Kubernetes containers to access host GPUs
- Lighter than VMs, preferred for AI workloads
- Deployed by GPU Operator in Kubernetes but also standalone
- Mentioned in study guide section 3.5

### 5. Containers vs VMs for AI
- Containers: lighter overhead, faster startup, preferred for AI
- VMs: stronger isolation, better multi-tenancy, more overhead
- Trade-offs and when to use each
- Mentioned in study guide section 3.5

### 6. NVIDIA Dynamo
- Next-generation inference engine
- Listed in markdown study guide software stack table
- No question coverage at all

### 7. Run:ai (now part of NVIDIA)
- GPU pooling across clusters
- Fractional GPU allocation
- Intelligent scheduling for AI workloads
- Listed in markdown study guide section 3.2

### 8. Grace Hopper Superchip
- Combined Grace CPU + H100 GPU in a single module
- For workloads requiring tight CPU-GPU coupling
- Distinct from Grace CPU paired via NVLink-C2C (Q36 only covers Grace CPU)
- Listed in study guide section 2.1

### 9. GPU Generation Comparisons
- A100: 80GB HBM2e, Ampere architecture
- H100: 80GB HBM3, Hopper architecture
- H200: 141GB HBM3e (memory-enhanced H100)
- B100/B200: Blackwell architecture (latest generation)
- No question tests ability to distinguish or select appropriate GPU by generation

### 10. Omniverse / Digital Twins
- Manufacturing use case: predictive maintenance, quality inspection, digital twins
- NVIDIA Omniverse platform
- Mentioned in study guide section 1.5

---

## Topics with Thin Coverage (1 question only)

### 1.3 AI vs ML vs DL (Q2 only)
**Missing angles:**
- Supervised vs unsupervised vs reinforcement learning
- Key architectures: CNNs, RNNs, Transformers
- When to use ML vs DL (data size, complexity trade-offs)

### 1.4 AI Adoption Factors (Q4 only)
**Missing angles:**
- Transfer learning and pre-trained models lowering barrier
- Cloud GPU-as-a-Service democratizing access
- Transformer architecture breakthrough (attention mechanism)

### 1.5 AI Use Cases & Industries (Q15 only — automotive)
**Missing industries:**
- Healthcare: drug discovery, medical imaging, genomics
- Finance: fraud detection, algorithmic trading, risk assessment
- Manufacturing: predictive maintenance, quality inspection, digital twins (Omniverse)
- Retail: recommendation engines, demand forecasting
- Telecom: network optimization, 5G
- Energy: grid optimization, exploration

### 2.4 On-prem vs Cloud (Q28 only)
**Missing angles:**
- CAPEX vs OPEX trade-off
- Hybrid approach (cloud for experimentation/burst, on-prem for production)
- Time-to-deploy differences (minutes vs weeks)
- Shared resources / "noisy neighbor" in cloud
- Cloud provider GPU availability constraints

### 2.10 DPU Benefits (Q24 only)
**Missing angles:**
- BlueField DPU runs its own OS (BlueField OS, Linux-based)
- "Third pillar" alongside CPU and GPU
- Enables secure multi-tenancy and workload isolation
- NVMe-oF storage offload
- Zero-trust security model at the infrastructure level

### 3.3 GPU Monitoring Metrics (Q43 ECC, Q45 DCGM-Exporter)
**Missing metrics:**
- Thermal throttling thresholds (~83-90C depending on GPU)
- PCIe throughput monitoring
- NVLink throughput monitoring
- Clock speed (base vs boost, throttling indicators)
- GPU utilization vs memory utilization interpretation
- Power draw relative to TDP

---

## Data Issue Found

| Question | Issue | Resolution |
|---|---|---|
| Q41 (Slurm) | `domain: "infra"` but `domainLabel: "AI Operations"` | Mapped to AI Operations using `domainLabel` as source of truth |

---

## Summary

| Status | Count |
|---|---|
| Well-covered subtopics | 13 of 22 |
| Thin coverage (1 question) | 6 subtopics |
| Zero coverage | 1 subtopic (2.6 Facility Requirements) |
| Missing technologies | 10 (BMC, GPUDirect Storage, Container Toolkit, Containers vs VMs, Dynamo, Run:ai, Grace Hopper Superchip, GPU generations, Omniverse, facility topics) |

**Update (2026-03-14):** 18 gap-coverage questions (Q145-Q162) added addressing all priority areas:
- Facility Requirements (2.6): Q145 (UPS 2N), Q146 (floor loading), Q147 (fire suppression) — **no longer zero coverage**
- Industry Use Cases (1.5): Q148 (healthcare), Q149 (finance), Q150 (manufacturing/Omniverse)
- GPU Monitoring (3.3): Q151 (thermal throttling), Q152 (power draw/TDP)
- On-prem vs Cloud (2.4): Q153 (CAPEX/OPEX), Q154 (noisy neighbor)
- Missing Technologies: Q155 (GPUDirect Storage), Q156 (Container Toolkit), Q157 (Grace Hopper), Q158 (H200), Q159 (containers vs VMs), Q160 (BMC)
- AI/ML/DL (1.3): Q161 (supervised learning), Q162 (CNNs)
- Total question bank: **163 questions** (145 original + 18 gap coverage)
