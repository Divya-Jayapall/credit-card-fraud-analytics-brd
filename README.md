# 💳 Credit Card Fraud Analytics (BRD)

**Project Goal:** Identifying unusual spending behavior and mitigating transaction risks using SQL database analytics and interactive data modeling.

### 📁 Project Deliverables
* [📄 Business Requirement Document (BRD PDF)](BRD_CC%20Fraud%20Analytics%20-%20Divya%20Jayapall.pdf)
* [🔍 SQL Database Analytics Queries](CC_Fraud_analysis_SQLDB_queries_Divya.sql)
* [📊 Interactive Power BI Dashboard File](CC_Fraud_analysis_PBI_Dashboard.pbix) *(Download to view locally)*

## ⚙️ Core Fraud Analytics Architecture

```mermaid
flowchart TD
    %% Styling Nodes
    classDef startEnd fill:#f9f9f9,stroke:#333,stroke-width:2px;
    classDef process fill:#e1f5fe,stroke:#0288d1,stroke-width:1px;
    classDef decision fill:#fff9c4,stroke:#fbc02d,stroke-width:1px;
    classDef alert fill:#ffebee,stroke:#c62828,stroke-width:2px;
    classDef success fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;

    A([💳 Swipe / Online Transaction]) --> B{1. Rule-Based Filter}
    
    %% Velocity & Geo-location evaluation
    B -- Velocity / Location Check Failed --> C[🚫 Immediate Decline & Flag]:::alert
    B -- Normal Parameters --> D[2. Risk Scoring Engine]:::process
    
    %% Analytics & Scoring Models
    D --> E{Fraud Risk Score}:::decision
    
    %% Decision thresholds
    E -- High Risk > 85 --> C
    E -- Medium Risk 40-85 --> F[⚠️ Trigger Step-Up Auth]:::process
    E -- Low Risk < 40 --> G[✅ Approve Transaction]:::success
    
    %% Verification flow
    F --> H{OTP / Biometric Verification}:::decision
    H -- Verified --> G
    H -- Failed / Timeout --> C

    %% Apply Classes
    class A startEnd;
    class C alert;
    class G success;
```

## 📊 Dashboard Preview
![Fraud Analytics Dashboard](CC_Fraud_analysis_PBI_Dashboard.png)
