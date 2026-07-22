# Case #03: Trade Execution Dispute — Negative Slippage During Volatile News (CPI)

**Date:** 2026-07-22  
**Channel:** Email / Support Ticket  
**Priority:** High (Dispute / Escalate)  
**Category:** Trading Operations / Execution Disputes  

---

### 📥 Customer Inbound Ticket

> **From:** Trader (Account #319402)  
> **Subject:** DISPUTE: Stop Loss Slippage on EURUSD - Order #774921  
>  
> "Your platform stole my money! I set a Stop Loss on EUR/USD at 1.0850, but my order closed at 1.0842 during the CPI news release today! That's 8 pips of slippage! I want an immediate refund of the extra loss or I will report you to the regulator."

---

### 📤 Agent Response

Dear Trader,

Thank you for contacting Broker Support regarding the execution of Order #774921. I understand how frustrating it is to experience execution price differences during high-impact news events.

I have conducted a full audit of your trade against our server price logs during the Consumer Price Index (CPI) release at 13:30 UTC:

1. **Order Execution Type:** A Stop Loss functions as a conditional trigger. Once the market price hits your specified Stop Loss rate (1.0850), the system automatically converts it into a **Market Order** to close the position at the next best available market price.
2. **Market Liquidity & Volatility:** During major macroeconomic releases like CPI, market volatility spikes dramatically while available liquidity thins out. As a result, market prices jump over price points without liquidity in between.
3. **Execution Review:** Our server logs confirm that at 13:30:02 UTC, the price gapped from 1.0852 directly down to 1.0842 due to institutional order flow. Your Stop Loss triggered at 1.0850 and was filled at 1.0842—which was the genuine, best available interbank market bid price at that exact millisecond.

Because our order execution operates under standard Best Execution practices, the trade was filled correctly according to live market availability. 

To help manage slippage risk during volatile events in the future, you may consider utilizing **Limit Orders** where supported or avoiding holding positions directly through major tier-1 economic releases.

Best regards,  
**Trading Operations & Escalations Team**

---

### ⚙️ Internal Handling & Audit Notes

* **Log Investigation:** Cross-referenced LP (Liquidity Provider) feed data for EUR/USD at 13:30:02 UTC. Server ticks confirm bid gap from 1.0852 to 1.0842 with zero bid liquidity at 1.0850.
* **Compliance Check:** Execution adhered strictly to the Order Execution Policy and Best Execution standards. No system latency error or platform discrepancy found.
* **Action Taken:** Educated client on market order mechanics during news volatility. Attached price feed tick log snippet for transparency. Ticket set to Pending Client Acknowledgment.
