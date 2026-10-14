# AIORI-3-HACKATHON-PROJECTS
This repository will contain the code and resources for the AIORI-3 hackathon that will be developed during the AIORI-3
PS-035: Evidence-Based Operator Network Fault Localisation
> **AIORI Hackathon 3 | Category: Cybersecurity**
A software-based network fault localisation project that correlates network topology, syslog events, and active ping measurements to rank probable root causes and explain the evidence behind each diagnosis.
🎥 Project Video
PS-035 | Evidence-Based Operator Network Fault Localisation | AIORI Hackathon 3
📌 Problem Statement
When a network link or router fails, network operations teams may receive many related alarms, such as interface state changes, BGP session drops, and latency warnings. These alarms may be symptoms of one underlying fault, making manual root-cause identification time-consuming.
This project aims to build a fault-localisation engine for a controlled five-node network lab. It combines topology definitions, operator logs, and active measurements to rank likely faults and provide evidence for its predictions.
🎯 Objectives
Create a five-node instrumented network topology.
Implement five labelled, seeded fault scenarios.
Correlate topology information, syslog events, and active ping measurements.
Build an explainable rule-based diagnostic baseline first.
Optionally add one AI model after the baseline is working.
Report top-1 and top-3 diagnostic predictions with supporting evidence.
Evaluate performance on held-out test runs.
Identify cases where the available evidence is insufficient to support a conclusion.
🧠 Proposed Solution
Create the lab: Define five network nodes and their connections.
Inject a fault: Activate one of the controlled fault scenarios.
Collect evidence: Gather logs, topology details, and ping outcomes such as reachability, latency, and packet loss.
Normalise and correlate: Align timestamps and associate events and measurements with affected nodes, links, and paths.
Rank candidate causes: Use topology-aware rules to score possible faults.
Explain the result: Display the top-ranked candidates, supporting or conflicting evidence, and an insufficient-evidence status when appropriate.
Evaluate: Measure top-1 and top-3 accuracy on held-out runs. An optional AI model can be compared with the rule-based baseline.
> **Safety and scope:** The system is intended to diagnose faults in a controlled lab. It does not automatically remediate network faults and must not claim guaranteed root-cause identification.
🧪 Example Fault Scenarios
These are proposed scenarios; document the exact fault-injection method used in the final implementation.
Link failure — a connection between two nodes becomes unavailable.
Router failure — a node becomes unreachable.
High latency — delay is introduced on a link or path.
Packet loss — some packets are deliberately dropped.
Routing-session failure — a simulated BGP session goes down while the physical link may remain available.
🏗️ Proposed Technology Stack
Component	Proposed tools	Purpose
Network lab	Python simulation or Mininet	Model the five-node topology and inject faults
Processing	Python, Pandas	Parse and normalise events and measurements
Topology analysis	NetworkX or Python graph structures	Represent nodes, links, and paths
Diagnostic baseline	Python rule-based logic	Rank candidate root causes
Optional AI	scikit-learn	Train and evaluate one diagnostic model
Backend	Flask or FastAPI	Serve diagnostic results
Dashboard	Lightweight web interface	Display topology, alarms, rankings, and evidence
Evaluation	Python and scikit-learn metrics	Calculate held-out top-1/top-3 accuracy
These are proposed technologies, not a claim that every component has already been implemented.
📊 Evaluation Plan
The project will evaluate the diagnostic engine using held-out fault-injection runs.
Top-1 accuracy: Percentage of test cases where the first-ranked diagnosis matches the injected fault.
Top-3 accuracy: Percentage of test cases where the actual fault appears among the three highest-ranked diagnoses.
Evidence quality: Check whether the evidence shown genuinely supports the predicted fault.
Uncertainty handling: Check whether the system identifies cases where evidence is inadequate.
Baseline comparison: If an AI model is implemented, compare it with the rule-based baseline on the same held-out evaluation.
Results: Add accuracy values and performance claims only after experiments have been run. No results are claimed in this README.
📦 Expected Deliverables
Five-node fault-injection lab.
Labelled dataset for the fault scenarios.
Topology and log collection pipeline.
Active measurement module.
Rule-based correlation and diagnosis engine.
Optional AI diagnostic model.
Explanation interface for ranked predictions.
Held-out top-1/top-3 evaluation.
Analysis of unsupported conclusions.
Technical report and prototype demonstration.
🚀 Getting Started
The exact setup commands depend on the implementation in the repository. Once the code and dependency files are added, update this section with tested installation and run commands.
A typical Python project setup may look like:
```bash
git clone <YOUR-REPOSITORY-URL>
cd <YOUR-REPOSITORY-FOLDER>
python -m venv .venv
```
Activate the environment:
Windows (PowerShell):
```powershell
.venv\Scripts\Activate.ps1
```
macOS / Linux:
```bash
source .venv/bin/activate
```
Install dependencies after adding a `requirements.txt`:
```bash
pip install -r requirements.txt
```
Then follow the run instructions for the implemented application. These are setup examples, not a claim that the project is already runnable.
📁 Suggested Repository Structure
```text
.
├── README.md
├── data/
│   ├── raw/
│   └── processed/
├── topology/
├── simulator/
├── collectors/
├── diagnosis/
├── dashboard/
├── evaluation/
├── docs/
└── requirements.txt
```
This is a suggested structure; adjust it to match the actual repository.
🔐 Scope and Limitations
Designed for a controlled lab, not unrestricted production-network control.
Similar symptoms may have different causes; diagnosis should remain evidence-based.
The system should surface conflicting evidence and abstain from a definitive conclusion when evidence is insufficient.
Automated remediation is out of scope.
AI is optional; the rule-based baseline is the required starting point.
🤝 Collaboration and Hackathon Deliverables
For the AIORI-3 PS-035 submission, the problem statement specifies:
Create a private GitHub repository named after the team.
Add `aiori-hackathon` as a collaborator.
Follow the organisers' repository ownership-transfer instructions after collaboration is accepted.
Upload the PDF following `Proposed-structure-hackathon.pdf`.
Demonstrate the prototype to the mentor with a pseudocode snippet.
Follow the latest instructions provided by the hackathon organisers.
👥 Team
Team name: 'A3-PS005-TC016`
Team members: `Angel Shiju,N.Muthukrishnan`
📚 Reference
AIORI-3 Hackathon, PS-035: Evidence-Based Operator Network Fault Localisation.
Video: PS-035 | Evidence-Based Operator Network Fault Localisation | AIORI Hackathon 3
https://youtu.be/pOYqJGth2pU
Built for AIORI Hackathon 3 · Cybersecurity · PS-035
