# SentinelVNC - Project Pitch (5 Minutes)

**Title:** SentinelVNC: Intelligent Defense for Remote Access Infrastructure
**Problem Statement:** Identification and protection of Virtual Network Computing (VNC) based data exfiltration attacks.

---

### **1. The Hook (30 Seconds)**
"Good morning judges. In today's interconnected world, VNC servers are the lifelines for remote administration, but they are also gaping holes in our security perimeter. The problem isn't just access; it's what happens *after* access is granted. Current firewalls see VNC traffic as a black box—encrypted noise. They can't tell the difference between an admin typing a command and an attacker copying a sensitive database password. SentinelVNC changes that. We've built a system that doesn't just block connections; it understands the conversation."

### **2. The Problem: The VNC Blind Spot (45 Seconds)**
"VNC (Virtual Network Computing) protocols like RFB (Remote Framebuffer) were designed for utility, not security.
*   **The Issue:** Once an insider or an attacker authenticates, the channel is trusted.
*   **The Attack Vector:** Data exfiltration happens seamlessly.
    *   **Clipboard:** Copying sensitive text (PII, Keys).
    *   **File Transfer:** Hiding files in seemingly normal traffic.
    *   **Visual:** Rapidly screenshotting documents.
*   **Existing Gap:** Standard tools see 'VNC Traffic.' They don't see 'Clipboard Copy' or 'File Transfer' inside that encrypted stream. We are blind to the *intent* of the user."

### **3. Our Solution: SentinelVNC (1.5 Minutes)**
"Our solution, SentinelVNC, acts as an intelligent middleware—a 'Smart Proxy' that sits transparently between the user and the server. It cracks open the protocol without breaking the encryption for the end-user.

Here is our 4-layer defense architecture:

1.  **Deep Protocol Inspection (The Eyes):**
    *   We built a custom Node.js proxy that parses the RFB protocol in real-time.
    *   It distinguishes between a mouse move, a keypress, a file transfer, and a clipboard paste.

2.  **Multi-Vector Detection Engine (The Brain):**
    *   **App Detector:** Analyzes clipboard text for Regex patterns (Credit Cards, API Keys).
    *   **Network Detector:** Calculates 'Shannon Entropy' on traffic bursts to detect encrypted or compressed files being smuggled out.
    *   **Visual Detector:** Monitors screen update rates to catch 'Screenshot Bursts'—a common manual exfiltration technique.

3.  **AI & Behavioral Analysis (The Intelligence):**
    *   We don't just use static rules. We use **Isolation Forests** (Unsupervised ML) to learn a user's 'normal' baseline.
    *   If 'User A' usually types commands but suddenly downloads a 500MB high-entropy file at 2 AM, our Risk Engine flags it immediately."

### **4. Response & Forensics (1 Minute)**
"Detection is useless without reaction. SentinelVNC implements a dynamic **Risk Scoring System (0-100)**.

*   **Real-time Response:**
    *   **Low Risk:** Log and monitor.
    *   **Critical Risk:** The system *automatically* kills the session instantly via the proxy.
*   **Immutable Forensics:**
    *   In security, logs can be tampered with. We solved this using **Blockchain**.
    *   Every critical incident is hashed into a Merkle Tree, and the root hash is anchored to the **Ethereum Sepolia Testnet**.
    *   This guarantees that the evidence we collect is mathematically potentially tamper-proof and admissible in court."

### **5. Impact & Conclusion (45 Seconds)**
"SentinelVNC effectively turns a dumb remote access pipe into a smart security checkpoint.
*   **We aligned perfectly with the problem statement:** We simulate and stop data exfiltration via Clipboard, Network, and Visual vectors.
*   **We went beyond:** Adding Machine Learning for anomaly detection and Blockchain for forensic integrity.

We are ready to deploy. The system is containerized, the dashboard is live, and the defense is active. Thank you."

---

### **Key Technical Keywords to Emphasize:**
*   **"RFB Protocol Parsing"** (Shows deep technical understanding)
*   **"Shannon Entropy"** (For detecting encryption/compression)
*   **"Isolation Forest"** (Unsupervised ML for anomalies)
*   **"Merkle Tree Anchoring"** (Blockchain integrity)
*   **"Man-in-the-Middle Proxy"** (The architecture)
