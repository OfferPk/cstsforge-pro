# CSTSForge Pro (v1.0.0)

### CCSDS 921.1-B-2 & ISO 20211 Cross Support Transfer Services (CSTS) Studio

CSTSForge Pro is an aerospace-grade developer studio, Association state machine simulator, Monitored Data Service (MD-CSTS CCSDS 922.1-B-1) procedural engine, ASN.1 TLV PDU serializer, and 10-point normative compliance auditor designed for space agency ground networks (NASA DSN / Near Space Network, ESA ESTRACK, JAXA, MBRSC UAE) and commercial tracking station operators (KSAT, SSC, Viasat, Infostellar, AWS Ground Station).

---

## 🌟 Key Capabilities

- **Normative CSTS Association Engine (CCSDS 921.1-B-2)**: Manages four-state Association lifecycles (`UNBOUND`, `BINDING`, `BOUND`, `UNBINDING`) with peer identification and credential authentication.  
- **Monitored Data Service (MD-CSTS CCSDS 922.1-B-1)**: Implements procedural state machines (`STOPPED`, `STARTING`, `ACTIVE`) supporting `REAL_TIME`, `TIMELY`, and `COMPLETE` telemetry delivery modes.  
- **Earth Reception Time (ERT) Time Tagging**: Formats standardized CCSDS Day Segmented (CDS) timestamps with 16-bit day counts and 32-bit millisecond resolution alongside antenna tracking lock flags (Carrier Lock, Subcarrier Lock, Symbol Lock).  
- **ASN.1 Tag-Length-Value (TLV) Protocol Serialization**: Synthesizes and dissects binary PDUs across BIND, UNBIND, START, STOP, TRANSFER-DATA, and NOTIFY service primitives.  
- **Service Instance Identifier (SI-ID) Parsing**: Enforces hierarchical URI notation (`authority:dsn/service:md-csts/spacecraft:...`) for cross-support tracking pass allocation.  
- **10-Point Normative Compliance Auditor**: Automated verification engine enforcing rules `CSTS-001` through `CSTS-010`.

---

## 📂 Project Structure

csts-forge-pro/

├── source-code/

│   ├── csts-engine.js           \# Core CSTS Association, MD-CSTS & PDU codec

│   ├── csts-auditor.js          \# 10-point normative compliance auditor

│   ├── csts\_cli.py              \# Pure Python 3 CLI executable

│   ├── csts-cli.py              \# Pure Python 3 CLI alias

│   ├── test\_runner.py          \# 10-suite unit test runner

│   └── index.html               \# Interactive Mission Control operations console

├── build/

│   └── csts-forge-pro-v1.0.0.zip \# Standalone production bundle

├── documentation/

│   ├── CCSDS\_CSTS\_SPECIFICATION.md \# Normative protocol specification

│   └── CSTS\_COMPLIANCE\_MATRIX.md   \# 10-point requirement traceability

└── screenshots/

    ├── architecture-diagram.svg  \# System architecture diagram

    └── csts-studio-preview.svg    \# Operations console preview

---

## 🚀 Quick Start

### Running Automated Tests

python3 source-code/test\_runner.py \-v

### Command Line Interface

\# Simulate full CSTS Association Session (BIND \-\> START \-\> TRANSFER-DATA \-\> STOP \-\> UNBIND)

python3 source-code/csts\_cli.py \--mode session

\# Generate BIND-INVOCATION PDU

python3 source-code/csts\_cli.py \--mode pdu \--type bind \--initiator NASA-JPL-MOC \--responder DSN-GOLDSTONE-DSS14

\# Generate real-time TRANSFER-DATA PDU

python3 source-code/csts\_cli.py \--mode pdu \--type transfer

\# Run 10-Point Normative Compliance Audit

python3 source-code/csts\_cli.py \--mode audit

### Launching the Web Operations Console

Open `source-code/index.html` in any web browser to access the interactive Mission Control dashboard, Association state machine visualizer, PDU dissector, and 10-point compliance scorecard.