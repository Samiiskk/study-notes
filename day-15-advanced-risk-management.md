# Day 15 — Advanced Risk Management & Threat Detection

**Date:** June 18, 2026
**Source:** Advanced Cybersecurity Risk Management 
**Achievement:** - Module 1 Complete

---

## Risk Analysis Methods

### Qualitative Risk Analysis
- Subjective evaluation — Low, Medium, High
- Uses expert judgment and historical data
- Quicker, simpler, good for initial assessments
- Limited data scenarios

### Quantitative Risk Analysis
- Uses numerical data and statistical models
- Techniques: Monte Carlo simulations, decision trees
- More precise but complex and data-intensive
- Best for high-impact risks needing cost estimates

**Best practice:** Start with Qualitative, then apply Quantitative to high-priority risks.

---

## Risk Assessment Tools

| Tool | Purpose |
|------|---------|
| Risk Matrix | Plots risks by likelihood and impact — prioritizes high-high risks |
| FMEA | Identifies failure modes, rates severity/occurrence/detectability, calculates RPN |
| Monte Carlo | Runs thousands of simulations using probability distributions |
| Bowtie Analysis | Maps causes → controls → risk event → consequences → mitigations |
| Sensitivity Analysis | Shows how changes in key variables affect risk outcomes |

---

## Measuring Impact & Likelihood

**Impact:** Potential consequences (financial, operational, reputational, legal)
**Likelihood:** Probability of risk occurring within timeframe

**Methods:**
- Risk matrix — visual plotting
- Probability impact chart — multiply numerical scores
- Scenario analysis — hypothetical situations

---

## Risk Appetite vs Risk Tolerance

| | Risk Appetite | Risk Tolerance |
|-|---------------|----------------|
| Definition | Overall level willing to accept | Acceptable deviation from appetite |
| Type | Broad strategic guideline | Specific operational thresholds |
| Example | "Tech startup = high appetite" | "Bank loan defaults < 2%" |

---

## Risk Response Strategies

| Strategy | What it does | When to use |
|----------|-------------|------------|
| **Avoidance** | Eliminate risk by changing plans or declining projects | High-impact, hard to manage |
| **Transfer** | Share risk with third party — insurance, contracts, outsourcing | Costly or complex risks |
| **Mitigation** | Reduce likelihood or impact with controls | Most common approach |

**Layered approach:** Use all three together. Example: Airline handles weather risk with avoidance (cancel routes), transfer (insurance), mitigation (maintenance).

---

## Cost-Benefit Analysis (CBA)

Evaluates financial pros/cons of implementing a risk control.

**Steps:**
1. Identify all costs — implementation, maintenance, training, opportunity costs
2. Estimate benefits — avoided losses, prevented fines, reputation protection
3. Calculate net benefit = Total Benefits - Total Costs

**Best practice:** Include direct AND indirect costs/benefits.

---

## Risk Controls

| Type | What it does | Example |
|------|-------------|---------|
| **Preventive** | Stop risks before they occur | Access restrictions, security policies |
| **Detective** | Identify risks in progress | IDS, audits, log monitoring |
| **Corrective** | Address risks after they occur | Incident response, data recovery |

**Control types by method:**
- **Administrative** — policies, procedures, training
- **Physical** — locks, cameras, biometrics
- **Technical** — firewalls, encryption, EDR
- **Financial** — insurance, contracts

---

## Business Continuity (BC) & Disaster Recovery (DR)

**BC:** Keeps critical business functions running during disruptions
**DR:** Restores IT systems and data after disruption

**Key metrics:**
- **RTO** — Recovery Time Objective — how fast to restore
- **RPO** — Recovery Point Objective — how much data loss acceptable

**Steps to develop:**
1. Business Impact Analysis (BIA) — assess risks, prioritize functions
2. Develop response/recovery strategies
3. Establish communication protocols
4. Conduct training and drills
5. Regularly update plans

---

## Organizational Resilience

**Definition:** Ability to anticipate, prepare, respond, and recover from disruptions while maintaining operations.

**Key steps:**
1. Assess vulnerabilities — identify weaknesses
2. Foster resilience culture — training, communication, empowerment
3. Invest in redundancy — backup systems, alternative suppliers
4. Regular testing and drills — prepare teams

**Real example:** Energy company implemented backup power, pre-positioned fuel, and annual storm drills — maintained service during hurricanes.

---

## Crisis Management

**Elements:**
- Risk assessment
- Designated Crisis Management Team (CMT)
- Communication plan
- Clear roles and responsibilities

**Communication during crisis:**
- **Transparency** — honest about situation
- **Timeliness** — fast updates
- **Empathy** — acknowledge impact

---

## Risk Governance Frameworks

**Key components:**
- Risk policies and guidelines
- Risk committees — oversee efforts
- Define risk appetite and tolerance
- Regular assessments and monitoring
- Reporting and escalation protocols

**Benefits:**
- Improved decision-making
- Enhanced stakeholder confidence
- Regulatory compliance
- Organizational resilience

---

## Major Frameworks

### ISO 31000
- Global, versatile across industries
- Systematic cycle: identify → assess → treat → monitor

### NIST Cybersecurity Framework
- Five functions: **Identify, Protect, Detect, Respond, Recover**
- US government and private sector focus
- Flexible, outcome-focused

### COBIT
- IT governance aligned with business goals
- Covers all IT-related risks
- Bridges technical teams and leadership

---

## Automation in Risk Management

**Benefits:**
- Improves efficiency — reduces manual effort
- Enhances accuracy — minimizes human error
- Real-time monitoring — continuous assessment
- Scalable — handles large data volumes

**Tools:**
- SIEM — collects and analyzes logs
- IDS/IPS — monitors network traffic
- EDR — monitors and responds on endpoints
- Incident Response Platforms — automate and coordinate

---

## Threat Detection & Response Tools

| Tool | Purpose |
|------|---------|
| IDPS | Monitors and blocks suspicious network traffic |
| SIEM | Aggregates and analyzes logs for threat insights |
| EDR | Real-time endpoint threat detection |
| NTA | Detects anomalies in network behavior |
| XDR | Integrates multiple tools for unified visibility |

---

## Cloud-Based Security Solutions

| Solution | What it does |
|----------|-------------|
| CASB | Enforces policies in cloud apps, visibility |
| SWG | Filters malicious web traffic |
| Cloud Firewall | Controls network traffic |
| IAM | Manages user authentication and permissions |
| DLP | Prevents unauthorized data sharing |

**Benefits:**
- Reduce costs — no on-premises infrastructure
- Rapid deployment — quick to implement
- Scalability — grows with organization
- AI-powered threat detection

---

## Evaluating Security Tool Effectiveness

**Key metrics:**
- **Detection Rate & Accuracy** — identifies threats with minimal false positives
- **Incident Response Enablement** — impact on response speed and automation

**Evaluation methods:**
- Penetration testing — simulates attacks
- Incident simulations — mock incidents
- Measure response times and tool reliability

---

## Key Takeaways
- Qualitative = quick assessment, Quantitative = precise cost estimates
- Risk Matrix plots likelihood vs impact — focus on high-high quadrant
- CBA = compare costs of control against benefits of avoiding risk
- Three response strategies: Avoid, Transfer, Mitigate — use all together
- BC keeps running, DR restores — both essential
- NIST = Identify, Protect, Detect, Respond, Recover
- Automation is key to real-time, scalable risk management
- SOC analysts directly execute the "Detect" and "Respond" functions
- Cloud solutions offer scalability but shared responsibility with providers
