
# PS-035: Evidence-Based Operator Network Fault Localisation

**AIORI Hackathon 3 | Category: Cybersecurity**

A software-based network fault localisation system that correlates network topology, Syslog events, and active ping measurements to rank probable root causes and explain the evidence behind each diagnosis.

## Project Presentation

[Watch the Project Presentation on YouTube](https://youtu.be/pOYqJGth2pU)

## Problem Statement

When a network link or router fails, network administrators may receive multiple related alarms, including interface state changes, routing-session failures, latency warnings, and packet loss.

These alarms may be symptoms of a single underlying fault. Identifying the actual root cause manually can be time-consuming and requires correlating information from multiple sources.

This project proposes an evidence-based fault localisation engine for a controlled five-node network lab. It combines topology information, operator logs, and active network measurements to rank probable fault locations and provide supporting evidence.

## Objectives

- Design a five-node network topology for controlled testing.
- Define five labelled fault scenarios for evaluation.
- Collect and correlate topology, Syslog, and active ping measurements.
- Develop an explainable, rule-based diagnostic baseline.
- Optionally evaluate a machine-learning model against the baseline.
- Report Top-1 and Top-3 diagnostic accuracy on held-out test runs.
- Identify cases where the evidence is insufficient for a reliable diagnosis.

## Proposed Solution

The proposed system follows these steps:

1. **Network Lab Setup:** Define five network nodes and their connections.
2. **Fault Injection:** Introduce a controlled fault into the network.
3. **Evidence Collection:** Gather logs, topology information, reachability, latency, and packet-loss measurements.
4. **Normalisation and Correlation:** Align timestamps and associate events with affected nodes, links, and paths.
5. **Candidate Ranking:** Apply topology-aware rules to score probable fault locations.
6. **Evidence-Based Diagnosis:** Present ranked candidates with supporting or conflicting evidence.
7. **Evaluation:** Measure diagnostic performance on held-out fault-injection runs.

The system should report an inconclusive diagnosis when the available evidence does not justify a reliable conclusion.

## Fault Scenarios

| Fault Scenario | Description |
|---|---|
| Link Failure | A connection between two network nodes becomes unavailable. |
| Router Failure | A network node becomes unreachable. |
| High Latency | Artificial delay is introduced on a link or path. |
| Packet Loss | Some network packets are deliberately dropped. |
| Routing-Session Failure | A simulated BGP session fails while the physical link may remain available. |

The final implementation should document the actual fault-injection methods used for each scenario.

## Proposed Technology Stack

| Component | Proposed Technology | Purpose |
|---|---|---|
| Network Lab | Python simulation or Mininet | Model the topology and inject faults |
| Data Processing | Python, Pandas | Parse and normalise evidence |
| Topology Analysis | NetworkX or Python graph structures | Represent nodes, links, and paths |
| Diagnostic Engine | Python rule-based logic | Rank probable fault locations |
| Optional AI/ML | scikit-learn | Train and evaluate a diagnostic model |
| Backend API | Flask or FastAPI | Serve diagnostic results |
| Dashboard | Lightweight web interface | Display alarms, rankings, and evidence |
| Evaluation | Python and scikit-learn metrics | Calculate diagnostic performance |

**Note:** These technologies describe the proposed design. The final README should reflect the tools and components actually implemented.

## Evaluation Plan

The diagnostic engine will be evaluated using held-out fault-injection runs.

- **Top-1 Accuracy:** Percentage of test cases where the correct fault is ranked first.
- **Top-3 Accuracy:** Percentage of test cases where the correct fault appears among the three highest-ranked candidates.
- **Evidence Quality:** Whether the evidence presented supports the predicted fault.
- **Uncertainty Handling:** Whether the system identifies cases with insufficient evidence.
- **Baseline Comparison:** Compare the rule-based engine with an optional AI/ML model using the same held-out test cases.

Results and performance claims will be added only after experiments have been conducted. No experimental results are claimed in this README.

## Expected Deliverables

- Five-node network lab and fault-injection scenarios.
- Labelled dataset containing fault scenarios and ground truth.
- Topology and evidence collection pipeline.
- Active network measurement module.
- Rule-based fault correlation and diagnosis engine.
- Optional machine-learning diagnostic model.
- Interface for displaying ranked predictions and supporting evidence.
- Held-out Top-1 and Top-3 evaluation.
- Analysis of inconclusive diagnoses and system limitations.
- Technical report and prototype demonstration.

## Scope and Limitations

- Designed for fault diagnosis in a controlled network lab.
- Does not automatically repair or reconfigure network devices.
- Similar symptoms may have different underlying causes.
- Missing telemetry must not automatically be interpreted as a healthy device.
- The system should report uncertainty when evidence is insufficient or contradictory.
- AI/ML is optional; the rule-based diagnostic baseline is the starting point.
- Performance in a controlled lab does not guarantee equivalent performance in production networks.

## Hackathon Submission Requirements

For the AIORI-3 PS-035 submission, follow the latest instructions provided by the organisers:

- Create the required private GitHub repository using the team name.
- Add `aiori-hackathon` as a collaborator.
- Follow the organisers' repository ownership-transfer instructions after collaboration is accepted.
- Upload the PDF in accordance with `Proposed-structure-hackathon.pdf`.
- Demonstrate the prototype to the mentor, including a pseudocode snippet.

## Team

**Team Code:** `A3-PS005-TC016`

**Team Name:** `AstroX`

**Team Members:**
- Angel Shiju
- N. Muthukrishnan

**Mentor:**
- Rakoth Kandan Sambandam

## Reference

AIORI-3 Hackathon, Problem Statement PS-035: *Evidence-Based Operator Network Fault Localisation*.

**Project Video:** [Watch on YouTube](https://youtu.be/pOYqJGth2pU)

---

*Developed for AIORI Hackathon 3 | Cybersecurity | PS-035*
