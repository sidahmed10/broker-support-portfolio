# Case #02: MT5 "Invalid Account" Connection Error

**Date:** 2026-07-22  
**Channel:** Email / Chat Ticket  
**Priority:** High  
**Category:** Platform Technical Support (MT5)  

---

### 📥 Customer Inbound Ticket

> **From:** Trader (Account #882041)  
> **Subject:** URGENT: MT5 Invalid Account Error  
>  
> "I'm trying to log into my MT5 account on my desktop and it keeps saying 'Invalid Account' in the bottom right corner! I know my password is correct because I wrote it down. Is my account deleted? Fix this right now I have open trades!!"

---

### 📤 Agent Response

Dear Trader,

Thank you for contacting Technical Support. Please rest assured that your trading account has not been deleted, and your open positions remain secure on our servers.

The **"Invalid Account"** error in MetaTrader 5 almost always occurs when the trading platform cannot match your login credentials with the specific server selected.

Please try the following quick troubleshooting steps to restore your connection immediately:

1. **Verify the Server Name:**
   * Go to **File > Login to Trade Account** in MT5.
   * Ensure you have selected **`BrokerName-Live`** (or `BrokerName-Live2` if your registration email specified server 2) rather than the Demo server.

2. **Check Account Number & Password:**
   * Double-check that your **Login ID** is strictly numbers (e.g., `882041`).
   * Re-type your Master Password manually to avoid extra blank spaces if copying and pasting. *(Note: Ensure you are not accidentally entering your Read-Only/Investor Password).*

3. **Rescan Server Latency:**
   * Click on the red/green connection bars in the bottom right corner of MT5 and select **"Rescan Servers"**.

If you still receive the error after verifying the server, you can instantly reset your trader password through your **Client Portal** under *Account Settings > Trading Accounts > Reset Password*.

Best regards,  
**Trading Technical Support Team**

---

### ⚙️ Internal Handling & Technical Notes

* **Platform Diagnostic:** "Invalid Account" status code indicates authorization rejection by the Access Point server (incorrect credentials or mismatched broker server dropdown).
* **Position Safety Check:** Verified via CRM backend that Account #882041 is active, equity is intact, and open trades are being managed normally by server-side Stop Loss/Take Profit parameters.
* **Resolution Path:** Guided user through client-side troubleshooting; provided self-service password reset link via Secure Client Portal.
