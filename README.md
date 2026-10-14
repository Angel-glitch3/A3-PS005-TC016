# PS-035: Evidence-Based Operator Network Fault Localisation

**AIORI Hackathon 3 | Category: Cybersecurity**

## Team Details

- **Team Code:** A3-PS005-TC016
- **Team Name:** AstroX
- **Team Members:**
  - Angel Shiju
  - N. Muthukrishnan
- **Mentor:** Rakoth Kandan Sambandam

## Project Overview

Evidence-Based Operator Network Fault Localisation is a cybersecurity project designed to identify, rank, and explain possible network faults using network topology, system logs, and active connectivity measurements.

The system aims to help network operators locate faults more efficiently by combining multiple sources of evidence and reporting uncertainty when the available information is insufficient to identify a fault confidently.

## Project Presentation

[Watch the project presentation on YouTube](https://youtu.be/pOYqJGth2pU)

## Problem Statement

Network faults such as link failures, router failures, high latency, packet loss, and routing-session failures can disrupt connectivity. Identifying the exact source of a fault is challenging when operators must manually analyse network topology, logs, and connectivity measurements.

The project proposes an evidence-based approach that correlates these sources to identify likely fault locations and provide explanations for the generated predictions.

## Objectives

- Develop a controlled five-node network laboratory for fault simulation.
- Collect and analyse network topology information, Syslog events, and active ping measurements.
- Correlate evidence from multiple sources to identify possible fault locations.
- Rank suspected faults according to their supporting evidence.
- Provide understandable explanations for each fault prediction.
- Report uncertainty or inconclusive findings when evidence is insufficient.
- Evaluate the proposed approach using controlled fault scenarios.

## Proposed Solution

The proposed system follows these steps:

1. **Network Setup:** Create a controlled five-node network topology using a network simulation environment.
2. **Fault Simulation:** Introduce controlled faults such as link failures, router failures, latency, packet loss, and routing-session failures.
3. **Evidence Collection:** Collect topology information, Syslog events, and active ping measurements.
4. **Evidence Correlation:** Combine the collected information to identify relationships between observed symptoms and possible faults.
5. **Fault Ranking:** Rank suspected fault locations using rule-based logic and evidence scores.
6. **Explainable Output:** Display the suspected fault, supporting evidence, and reasons for the prediction.
7. **Uncertainty Reporting:** Provide an inconclusive result when the evidence does not support a sufficiently confident conclusion.

## Fault Scenarios

| Fault Scenario | Expected Observation |
|---|---|
| Link Failure | Connectivity loss between affected network nodes |
| Router Failure | Multiple connectivity failures involving the affected router |
| High Latency | Increased ping response times |
| Packet Loss | Missing ping responses or an elevated packet-loss rate |
| Routing-Session Failure | Connectivity or routing-related symptoms associated with a failed session |

## Proposed Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| Network Simulation | Mininet |
| Data Processing | Pandas |
| Network Topology Analysis | NetworkX |
| Fault Analysis | Rule-based logic |
| Optional Machine Learning | scikit-learn |
| Backend API | Flask or FastAPI |
| Dashboard | Web-based dashboard |
| Evidence Sources | Network topology, Syslog, and active ping measurements |

## Evaluation Plan

The proposed system will be evaluated using controlled network fault scenarios.

- **Top-1 Accuracy:** Check whether the highest-ranked fault matches the injected fault.
- **Top-3 Accuracy:** Check whether the actual fault appears among the three highest-ranked candidates.
- **Evidence Quality:** Assess whether each prediction includes relevant supporting observations.
- **Uncertainty Handling:** Verify whether the system reports inconclusive findings when evidence is insufficient.
- **Baseline Comparison:** Compare the proposed approach with a simpler fault-localisation method.

Actual performance results will be documented after implementation and testing.

## Expected Deliverables

- A controlled five-node network simulation.
- Scripts for generating and collecting network evidence.
- A fault-localisation and ranking engine.
- Explainable fault predictions with supporting evidence.
- An uncertainty-reporting mechanism.
- A dashboard for presenting fault rankings and observations.
- An evaluation report covering the selected fault scenarios.

## Scope and Limitations

The initial implementation focuses on a controlled network environment with a limited set of predefined fault scenarios. The accuracy of the system depends on the quality and availability of topology data, logs, and active measurements.

The system is intended to assist network operators rather than replace their judgement. It should not claim a confirmed fault when the available evidence is insufficient.

## References

- [Mininet Documentation](http://mininet.org/)
- [NetworkX Documentation](https://networkx.org/documentation/stable/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [scikit-learn Documentation](https://scikit-learn.org/stable/)

## Project Presentation Video

[https://youtu.be/pOYqJGth2pU](https://youtu.be/pOYqJGth2pU)

---

Developed for AIORI Hackathon 3 | Cybersecurity | PS-035
