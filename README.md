# 60-Minutes-of-Risk-Real-Time-Insights-from-One-Hour-of-Bank-Transactions.

## **1. Introduction**

This project, titled **“60 Minutes of Risk: Real-Time Insights from One Hour of Bank Transactions,”** analyzes financial transactions that occurred within a **single hour on January 17, 2025**. The data provides a unique opportunity to understand how fraud patterns emerge in real time and how factors like transaction type, network conditions, and timing may relate to fraudulent behavior.

This analysis is delivered as a **Power BI three-page report**:

1. **Bank Transactions**
2. **Fraud Detection**
3. **Transaction Details**

The report structure allows users to **drill through from key fraud indicators to detailed transaction-level insights**, offering a layered exploration of the potential drivers behind fraudulent activity. This design supports faster investigation, better risk identification, and operational decision-making.

---

## **2. Objective**

The primary objective of this project is to:

* **Identify when and how fraud spikes occur within the 60-minute window.**
* **Detect patterns** across various dimensions including transaction type, network slice, and latency.
* **Inform real-time fraud detection systems** by highlighting transactional and network characteristics of fraudulent behavior.
* Support **security and risk analysts** in uncovering vulnerabilities and high-risk periods.

---

## **3. Bank Transaction Dataset**

The dataset includes the following columns:

| **Column Name**                    | **Description**                                                             |
| ---------------------------------- | --------------------------------------------------------------------------- |
| `Transaction ID`                   | Unique identifier for each transaction.                                     |
| `Sender Account ID`                | Account ID of the person initiating the transaction.                        |
| `Receiver Account ID`              | Account ID of the transaction recipient.                                    |
| `Transaction Amount`               | The amount of money involved in the transaction.                            |
| `Transaction Type`                 | Type of transaction — e.g., Transfer, Deposit, Withdrawal.                  |
| `Timestamp`                        | Exact time the transaction occurred (within the one-hour window).           |
| `Transaction Status`               | Outcome of the transaction (e.g., Success, Failed).                         |
| `Fraud Flag`                       | Indicates whether the transaction was flagged as fraudulent (Yes/No).       |
| `Geolocation (Latitude/Longitude)` | Geographic coordinates where the transaction was initiated.                 |
| `Device Used`                      | Device or channel used (e.g., Mobile, ATM, Web).                            |
| `Network Slice ID`                 | ID of the 5G network slice through which the transaction was transmitted.   |
| `Latency (ms)`                     | Network delay experienced during the transaction, measured in milliseconds. |
| `Slice Bandwidth (Mbps)`           | Network bandwidth during the transaction, measured in megabits per second.  |
| `PIN Code`                         | Regional PIN code associated with the transaction origin.                   |

---

## **4. Tools Used**

* **Power BI**: For building a real-time interactive dashboard that enables fraud pattern detection.

---

## **5. Skills Demonstrated**

* **Fraud Pattern Recognition**: Identifying minute-level spikes and recurring conditions behind fraud.
* **Time-Based Analysis**: Comparing fraud volumes across timestamps within a constrained 60-minute window.
* **Data Visualization**: Crafting a one-page report to deliver insights with filters, charts, and time plots.
* **Network Insight Correlation**: Integrating 5G metrics (slice ID, latency, bandwidth) into behavioral analysis.
* **Business Insight Communication**: Transforming raw transactional data into actionable operational knowledge.

---

## **6. Conclusion and Recommendation**

### **Conclusion**

The analysis revealed that fraudulent transactions are **highly time-sensitive**, with major spikes occurring at **10:55 a.m., 10:05 a.m., and 10:49 a.m.**. These fraud events coincide with specific transaction types—**Transfers and Withdrawals**—and are often associated with certain network conditions (e.g., similar latency and bandwidth patterns). While **some fraud events occur consistently**, the majority emerge in **sudden bursts**, indicating **coordinated, rapid-fire activity**.

### **Recommendation**

* **Implement Minute-Level Monitoring**: Real-time dashboards should be set to flag abnormal volumes within short intervals (e.g., per 5-minute segment).
* **Correlate Network Metrics with Risk Models**: Transaction monitoring systems should factor in **network slice behavior**, latency, and bandwidth when evaluating risk.
* **Enhance Verification for High-Risk Windows**: Reinforce authentication protocols (e.g., 2FA or biometric confirmation) during previously observed high-risk minutes (10:49–10:56 a.m.).
* **Train AI models on Micro-Windows**: Use findings to train machine learning models that detect and predict bursts of fraud based on second/minute patterns and contextual features.

---

