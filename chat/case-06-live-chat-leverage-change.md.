# Case #06: Live Chat — Leverage Change Rejection & Margin Requirements

**Date:** 2026-07-22  
**Channel:** Live Chat  
**Priority:** Medium (Real-Time Inquiry)  
**Category:** Live Chat Simulations / Account Management  

---

### 💬 Live Chat Transcript

**[14:05:12] Trader:** Hey, I'm trying to change my account leverage from 1:100 to 1:500 in the portal, but it keeps giving me an error saying "Request Denied". Why can't I change my leverage?

**[14:05:45] Agent (Broker Support):** Hello! Thank you for contacting Broker Support live chat. I'd be happy to check that for you right away. May I please have your trading account number?

**[14:06:02] Trader:** Sure, account #882041.

**[14:06:40] Agent (Broker Support):** Thank you. I am auditing your account details now... I see the reason for the error. 

You currently have two open positions on EUR/USD and XAU/USD. To prevent sudden margin calls or unintended liquidation, our system automatically restricts leverage modifications while trades are actively open on the account.

**[14:07:15] Trader:** Oh I see. So if I close my trades, can I change it immediately?

**[14:07:50] Agent (Broker Support):** Exactly! Once all open orders are closed (or pending orders cancelled), you can instantly apply the 1:500 leverage update through your Client Portal under **Account Settings > Change Leverage**. 

*Please note: Increasing your leverage to 1:500 reduces your required margin per lot, but also increases exposure to market volatility. Make sure your risk management strategy aligns with higher leverage prior to re-opening trades.*

**[14:08:20] Trader:** Got it! Makes total sense. Thanks for the quick explanation!

**[14:08:42] Agent (Broker Support):** You're very welcome! Is there anything else I can assist you with today?

**[14:09:05] Trader:** Nope, that's all. Have a great day!

**[14:09:15] Agent (Broker Support):** You too! Happy trading, and feel free to reach out anytime. *(Chat closed by agent)*

---

### ⚙️ Internal Handling & System Notes

* **System Check:** Queried account status in CRM Admin Tool. Account `#882041` confirmed active with active margin utilization ($420 margin in use).
* **Policy Applied:** Leverage changes are blocked dynamically when `Open Equity != Free Margin` to prevent margin call triggers resulting from leverage recalibration.
* **Resolution:** Client educated on real-time margin mechanics; ticket tagged under `Account Management / Leverage` and resolved on first contact.
