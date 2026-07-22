# SOP-OPS-002: Standard Operating Procedure for Handling Negative Balance Protection (NBP)

| Document Metadata | Details |
| :--- | :--- |
| **SOP ID** | SOP-OPS-002 |
| **Category** | Risk Operations / Account Administration |
| **Version** | 1.0 |
| **Effective Date** | July 2026 |
| **Target Audience** | Tier 1 & Tier 2 Support Specialists, Risk Desk |
| **Review Cycle** | Annual |

---

## 1. Objective & Policy Statement

Negative Balance Protection (NBP) is a regulatory safeguard (mandated by regulators such as FCA, CySEC, and ASIC) ensuring that retail clients cannot lose more capital than they have deposited. 

When extreme market volatility, gapping, or slippage causes an account equity to fall below zero ($0.00), the brokerage resets the account balance back to zero at no additional cost to the trader. This SOP outlines the verification, execution, and audit procedures for processing NBP zero-out requests.

---

## 2. Eligibility Criteria & Constraints

### A. Covered Accounts
* **Account Types:** Retail Trading Accounts (MT4, MT5, cTrader).
* **Conditions:** Balance is negative due to closed market transactions or Stop Out executions during high-volatility events (e.g., central bank rate decisions, NFP releases, weekend gaps).

### B. Ineligibility Exclusions (Red Flags)
NBP will **NOT** be automatically applied under the following circumstances:
* **Professional / Institutional Clients:** Clients classified as Elective Professional or Institutional, where custom leverage/margin agreements apply.
* **Prohibited Trading Practices:** Accounts flagged by Risk Ops for abusive behavior, including balance abuse, platform manipulation, latency arbitrage, or hedging across linked accounts.
* **Pending Open Positions:** Accounts that still have open positions generating floating P/L.

---

## 3. Operational Workflow Step-by-Step

```text
[ Account Reaches Negative Balance ]
                 │
                 ▼
     [ Check for Open Positions ]
       ├── (Yes) ──► Wait for full liquidation / Stop Out
       └── (No)
                 │
                 ▼
     [ Automated / Manual Audit ]
       ├── (Flagged / Abusive) ──► Escalate to Risk Desk
       └── (Clean / Retail)
                 │
                 ▼
[ Process Balance Adjustment Credit ] ──► [ Notify Client via Email ]
``
### Phase 1: Client Request or System Identification
1. **Automated Trigger:** The Back Office Management System (BOMS) flags trading accounts where `Balance < 0` and `Open Trades = 0`.
2. **Manual Request:** If a client contacts support via email/chat reporting a negative balance following a stop-out:
   * Verify the account status in BOMS.
   * Confirm all trades on the account are fully closed.

### Phase 2: Verification Checklist (Tier 1 Support)
* [ ] **Open Orders Check:** Confirm `Open Positions = 0` and `Pending Orders = 0`.
* [ ] **Negative Value Confirmation:** Ensure equity and balance are strictly negative (e.g., `-$145.20`).
* [ ] **Account Categorization:** Confirm client classification is **Retail**.
* [ ] **Risk Flag Status:** Check for active security/risk restrictions on the CRM profile.

### Phase 3: Processing the Balance Reset
1. Log into the BOMS Financial Administration module.
2. Select **Balance Adjustment** -> Transaction Type: `NBP Credit / Negative Balance Reset`.
3. Input the exact absolute dollar value of the deficit (e.g., if balance is `-$145.20`, enter `+$145.20`).
4. Enter the mandatory internal reference note:
   > *"NBP Credit applied per SOP-OPS-002 due to Stop Out execution on EUR/USD during volatile event."*
5. Execute the adjustment and confirm the new ledger balance reads `$0.00`.

---

## 4. Communication Protocol

Once the reset is executed, send the standardized email notification or close the pending support ticket with the template below:

> **Subject:** Update Regarding Your Account Balance — [Account Number]
> 
> Dear [Client Name],
> 
> Following recent market activity, we noticed your trading account **#[Account Number]** incurred a negative balance as a result of stop-out executions.
> 
> As part of our commitment to client security and regulatory standards, **Negative Balance Protection** has been applied to your account. Your account balance has been successfully reset to **$0.00**, absorbing the negative equity.
> 
> You may now deposit funds to resume trading whenever you are ready. If you have any further questions, please do not hesitate to contact our support team.
> 
> Best regards,  
> **Trading Support Team**

---

## 5. Escalation & Audit SLA

| Scenario | Primary Action | Responsible Party | Target SLA |
| :--- | :--- | :--- | :--- |
| Standard NBP Reset (< $1,000) | Automated / Tier 1 Support Manual Processing | Tier 1 Support Specialist | < 30 minutes |
| High-Value Deficit (> $1,000) | Secondary Manager Approval Required | Tier 2 Support Lead | < 2 hours |
| Potential Arbitrage / Hedging | Route to Risk Desk for Trade Log Audit | Risk & Operations Team | < 24 hours |
