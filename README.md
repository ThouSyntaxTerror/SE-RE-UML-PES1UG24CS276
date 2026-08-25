<div align="center">

# ✈️ SE-RE-UML-Project

### Software Engineering — Requirements Engineering & UML

**Airport Lost Luggage Claim & Tracking Portal**

![Diagram](https://img.shields.io/badge/UML-Use%20Case%20Diagram-647687?style=flat-square)
![Requirements](https://img.shields.io/badge/Requirements-Traceability%20Table-2e7d32?style=flat-square)
![Spec](https://img.shields.io/badge/Spec-Use--Case%20Flow-b36b00?style=flat-square)

</div>

---

## 🗺️ System at a Glance

```mermaid
flowchart LR
    Passenger((Passenger))
    Agent((Baggage Service Agent))
    Scanner((Terminal Scanner System))

    subgraph Portal["Airport Lost Luggage Claim & Tracking Portal"]
        UC1([File Lost Baggage Claim])
        UC2([Match Claim to Scan Logs])
        UC3([Update Claim Status])
        UC4([Notify Passenger])
        UC5([Track Claim Status])
        UC6([Process Compensation])
    end

    Passenger --- UC1
    Passenger --- UC5
    Agent --- UC3
    Scanner --- UC2
    UC1 -. include .-> UC2
    UC1 -. include .-> UC4
    UC6 -. extend .-> UC3
```

## 🔁 Main Flow — File Lost Baggage Claim

```mermaid
sequenceDiagram
    actor P as Passenger
    participant S as System
    participant L as Scan Logs

    P->>S: Select "Report Lost Baggage"
    S-->>P: Show claim form
    P->>S: Submit flight #, bag tag, description, checkpoint
    S->>S: Validate input
    S->>S: Generate Claim ID (status: Investigating)
    S->>L: Match Claim to Scan Logs (include)
    S-->>P: Confirmation notification with Claim ID
```

## 👤 Actors

| Actor | Role |
|---|---|
| 🧳 **Passenger** | Files and tracks baggage claims |
| 🛎️ **Baggage Service Agent** | Updates claim status, processes compensation |
| 📡 **Terminal Scanner System** | Feeds scan logs used for automatic matching |

## 📋 Requirements Snapshot

| ID | Priority | Requirement |
|---|:---:|---|
| `FR-1` | 🔴 High | Cross-reference lost baggage reports against terminal scan logs |
| `FR-2` | 🔴 High | Allow passengers to submit a lost baggage report |
| `FR-3` | 🔴 High | Allow agents to update claim status with timestamp + agent ID |
| `FR-4` | 🟡 Medium | Auto-notify passengers whenever claim status changes |

*Full table with acceptance criteria and rationale → [`Requirements_Table.xlsx`](Requirements_Table.xlsx)*

## 📁 Contents

| File | Type | Description |
|---|---|---|
| [`Airport_baggage_use_caase.drawio`](Airport_baggage_use_caase.drawio) | 🗺️ UML Use Case Diagram | Actors and use cases with `include`/`extend` relationships. Open in [draw.io](https://app.diagrams.net/). |
| [`Requirements_Table.xlsx`](Requirements_Table.xlsx) | 📋 Requirements Table | Functional requirements with priority, acceptance criteria, and rationale. |
| [`UseCase_Flow_FileLostBaggageClaim.docx`](UseCase_Flow_FileLostBaggageClaim.docx) | 📝 Use-Case Flow Spec | Main success scenario and alternate flow for "File Lost Baggage Claim". |
| [`30_SE_Lab1_SE_Problem_Statements.pdf`](30_SE_Lab1_SE_Problem_Statements.pdf) | 📄 Problem Statement | Original Lab 1 assignment brief. |

---

<div align="center">

*Lab 1 Deliverables — Software Engineering*

</div>
