# KB-OPS-104: Platform Disconnections & Emergency Escalation Protocol

| Article Metadata | Details |
| :--- | :--- |
| **Article ID** | KB-OPS-104 |
| **Category** | Platform Troubleshooting / Technical Operations |
| **Target Audience** | Tier 1 & Tier 2 Support Specialists, Trade Desk |
| **Last Updated** | July 2026 |
| **Status** | Published (Internal) |

---

## 1. Overview & Initial Diagnostics

When a client reports connectivity issues or trading platform disconnections (MT4, MT5, or cTrader), Support Specialists must swiftly differentiate between **client-side network/device issues** and **server-side datacenter/broker infrastructure disruptions**.

### Rapid Diagnostic Checklist (Tier 1 Support)

1. **System Health Check:** Check the internal monitoring dashboard for server node status across regional datacenters (e.g., Equinix NY4, LD4, TY3).
2. **Ping & Latency Test:** Instruct the client to run a trace route or check connection latency via the platform status bar (bottom right corner).
3. **Account Validation:** Confirm in the Back Office Management System (BOMS) that the account is active and not disabled due to routine maintenance or margin calls.

---

## 2. Technical Troubleshooting Matrix

### Scenario A: Client-Side Disconnection ("No Connection" / "Common Error")
* **Root Cause:** Local ISP routing instability, strictly configured local firewalls blocking ports `443` or `1950`, or an outdated broker server list.
* **Resolution Steps:**
  1. Guide the client to rescan servers by clicking the **Connection Bar** -> **Rescan Servers**.
  2. If unsuccessful, direct the client to manually enter the primary server IP address in the login window.
  3. Confirm that local security software allows traffic over trading ports (`443`, `1950`, `1951`).

### Scenario B: Server-Side Latency Spikes / Service Degradation
* **Root Cause:** Upstream Liquidity Provider (LP) cross-connect drops or extreme market volatility overloading server throughput.
* **Resolution Steps:**
  1. Post an internal alert to `#ops-trading-alerts` on Slack.
  2. Publish a live notification banner on the Client Portal Status Page.
  3. Route incoming client connections to secondary backup proxies if auto-failover latency exceeds 30 seconds.

---

## 3. Emergency Phone Trading & Order Liquidation Protocol

If a server outage occurs while clients hold high-risk open positions during volatile market hours, Tier 1 Support must execute the following protocol:

> ⚠️ **CRITICAL:** Support Specialists must NEVER execute, modify, or close trades without explicit verbal authentication and verified security checks.

1. **Client Identity Authentication:** Verify Full Legal Name, Account ID, and the 4-digit Telephone Security PIN.
2. **Order Verification:** Confirm specific Ticket ID, Symbol, Volume (Lots), and intended action (e.g., *Close Position at Market*).
3. **Dealing Desk Handoff:** Pass authenticated details immediately to the Emergency Dealing Desk Hotline (Ext. 4099) for manual execution at the best available market price.
4. **CRM Logging:** Record the ticket details, execution timestamp, and call recording ID in the client’s BOMS interaction history.

---

## 4. Incident Escalation Matrix

| Issue Severity | Trigger Condition | Escalation Target | Response SLA |
| :--- | :--- | :--- | :--- |
| **Low (L1)** | Isolated user connection drop / ISP routing | Tier 1 Support | < 15 minutes |
| **Medium (L2)** | Multiple clients on the same server reporting drop | Tier 2 Systems Admin / Network Ops | < 5 minutes |
| **Critical (L3)** | Core trading server outage or LP disconnect | Head of Operations / Trade Desk | Immediate (< 2 minutes) |
