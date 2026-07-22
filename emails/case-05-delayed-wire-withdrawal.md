# Case #05: Delayed Wire Withdrawal Investigation & Swift GPI Tracking

**Date:** 2026-07-22  
**Channel:** Email / High-Priority Ticket  
**Priority:** High  
**Category:** Payments & Withdrawal Operations  

---

### 📥 Customer Inbound Ticket

> **From:** Trader (Account #771039)  
> **Subject:** URGENT: Missing $3,500 Wire Withdrawal  
>  
> "I requested a $3,500 wire withdrawal 4 business days ago and my bank still hasn't received it! The money was already deducted from my MT5 balance. Where is my money? Give me a transaction tracking number now!"

---

### 📤 Agent Response

Dear Trader,

Thank you for reaching out to Broker Support. I understand your concern regarding the status of your $3,500 Bank Wire withdrawal, and I am happy to assist you with tracking these funds.

Upon auditing your account records:
1. **Processing Status:** Your withdrawal request was approved and processed by our Finance Operations department on July 18, 2026.
2. **Standard Timeline:** International Bank Wires generally take **3 to 5 business days** to settle, depending on correspondent banking routing networks and your receiving institution's clearing times.

To help your bank locate the incoming transfer, we have generated your official **SWIFT MT103 Document**, which serves as electronic proof of transfer. 

**Key Transaction Identifiers:**
* **SWIFT UETR (Unique End-to-End Transaction Reference):** `eb82f301-44a9-4d82-b1c4-90a12f67429d`
* **Beneficiary Account:** Ending in `...8492`
* **Sending Bank:** Barclays Bank PLC (Broker Operations Account)

*I have attached the full MT103 confirmation receipt (PDF) to this ticket for your records.* 

If the funds do not reflect in your bank balance by tomorrow morning, please provide this MT103 document directly to your bank’s **Wire Transfer / International Payments Department**—they will be able to use the **UETR code** to trace the exact location of the funds within the correspondent network.

Best regards,  
**Payments & Treasury Support Team**

---

### ⚙️ Internal Handling & Payment Notes

* **System Audit:** Cross-checked CRM payout log against Payment Gateway API. Batch ID `#PG-99023-W` marked as `SUCCESS / RELEASED`.
* **Routing Diagnostic:** Wire processed via correspondent intermediary bank. Delayed status attributed to standard recipient bank processing windows (no regulatory hold flags detected on SWIFT GPI tracker).
* **Action Taken:** Downloaded MT103 confirmation from Treasury Portal, attached to CRM ticket, provided UETR code to client, and scheduled follow-up ticket reminder for +24 hours.
