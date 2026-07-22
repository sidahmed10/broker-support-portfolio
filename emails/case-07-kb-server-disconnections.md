# KB Article #07: Internal Escalation Matrix & Troubleshooting — MT4/MT5 Server Disconnections

**Article ID:** KB-OPS-104  
**Audience:** Internal Support Agents & Tier 1 Operations  
**Category:** Technical Support / Server Infrastructure  

---

## 📌 Article Overview
This document outlines standard diagnostic procedures for handling client reports of MetaTrader 4 (MT4) or MetaTrader 5 (MT5) server disconnections, high latency ("No Connection" / "Common Error"), and trade execution timeouts.

---

## 🔍 Diagnostic Checklist for Support Agents

### Step 1: Client-Side Isolation
Before escalating to Tier 2 Operations, verify client local network integrity:
1. **Rescan Access Points:** Guide client to click the connection status icon in the bottom right corner of MT4/MT5 and select **"Rescan Servers"**.
2. **Ping Test:** Run command prompt ping against the data center IP:
   `ping dc-uk.broker-server.com`
   * Acceptable Latency: `< 150ms`
   * High Latency / Packet Loss: Client ISP issue. Recommend switching access point or disabling local VPN/Firewall.

### Step 2: Server-Side Operational Audit
1. Open internal monitoring dashboard (**Datadog / Server Status Portal**).
2. Check real-time load on:
   * **Live Server 01 (EU Gateway)**
   * **Live Server 02 (US Gateway)**
   * **Live Server 03 (APAC Gateway)**

---

## 🚨 Escalation Workflow

| Scenario | Primary Action | Target Queue |
| :--- | :--- | :--- |
| **Isolated Client Issue** | Guide client to change access server / reinstall broker terminal setup. | Closed on Tier 1 |
| **Multiple Clients on Same Gateway** | Ping infrastructure engineer on duty via Slack (#ops-incidents). | Escalated to Tier 2 IT |
| **Bridge / LP Disconnection** | Verify Liquidity Provider fix protocol health; notify Trading Desk. | Escalated to Dealing Desk |

---

## 📝 Required Ticket Template (For Tier 2 Escalations)
When escalating to IT Operations, include:
* **Account ID:**
* **Server Name:** (e.g., Live-Server-02)
* **Client IP & Country:**
* **Terminal Version/Build:** (e.g., MT5 Build 3802)
* **Exact Time of Disconnection (UTC):**
