# 60-Minutes-of-Risk-Real-Time-Insights-from-One-Hour-of-Bank-Transactions.
![20250508_2340_Bank Transactions Report_simple_compose_01jtrsy87pe2yvv696dnqh43cw](https://github.com/user-attachments/assets/9a89ccd3-58df-44de-a3d6-11246de6af0b)

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
| `Fraud Flag`                       | Indicates whether the transaction was flagged as fraudulent (TRUE/FALSE).       |
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

## **5.Data Transformation**

The bank transaction dataset required transformations to prepare it for analysis. Here are the key changes made:

* Split the "Longitude" and "Latitude" to enable map visualization.
* Duplicated and split the "Timestamp" column into "Transaction Date" and "Transaction Time" for clarity.

<img width="960" alt="data transformation" src="https://github.com/user-attachments/assets/ca014505-6284-4965-9faf-36550bc31a13" />

---

## **6. Skills Demonstrated**

* **Fraud Pattern Recognition**: Identifying minute-level spikes and recurring conditions behind fraud.
* **Time-Based Analysis**: Comparing fraud volumes across timestamps within a constrained 60-minute window.
* **Data Visualization**: Crafting a three-page report to deliver insights with filters, charts, and time plots.
* **Network Insight Correlation**: Integrating 5G metrics (slice ID, latency, bandwidth) into behavioral analysis.
* **Business Insight Communication**: Transforming raw transactional data into actionable operational knowledge.

---

### A. Transaction Patterns (Within One Hour)

<img width="801" alt="home page" src="https://github.com/user-attachments/assets/2d9e326e-66c7-436b-b337-67ab5324966c" />


To understand the overall transaction activity during this specific hour, we can examine several key dimensions:

**i. How many total transactions were recorded?**

A total of **1,000 transactions** were recorded during the one-hour analysis window, with a cumulative transaction value of **771.17K**, reflecting a high volume of activity within a very short time frame.

**ii. Which regions processed the most transactions?**

The geographical distribution of transactions reveals that **Northwest Africa** and **Western Europe** experienced a higher volume of transactions compared to other regions during this hour, as indicated by the size and intensity of the markers on the map.

**iii. Which time intervals within the hour had the most activity?**

Analyzing the transaction volume over time shows significant activity between **10:00 AM** and **10:25 AM**, with a notable **peak** of **25** transactions occurring around **10:25 AM**. However, the **highest** number of transactions recorded within this hour was **28**, occurring at approximately **10:55 AM**.

**iv. What is the distribution of transaction statuses (e.g., success vs. failed)?**

The transaction status breakdown indicates a near balance between outcomes within this hour. There were a total of **513 failed transactions** and **487 successful transactions**. This relatively high number of failed transactions warrants further investigation.

**v. Are certain transaction types more common or rare?**

Examining the types of transactions reveals that **Transfer** transactions were the most prevalent, accounting for **37.84%** of all transactions. This was closely followed by **Deposits at 32.68%**, while **Withdrawals** were the least common at **29.48%**. The dominance of *transfer* transactions could be a significant factor to consider in further analysis.


### B. Fraud Detection: Analyzing Flagged Transactions

<img width="801" alt="fraud detection" src="https://github.com/user-attachments/assets/7274f095-b280-42ef-81cc-d25ece225abd" />


This section delves into the characteristics of the transactions identified as potentially fraudulent within the one-hour period.

**i. What percentage of transactions were flagged as fraud overall?**

Out of the **1,000** total transactions recorded during this hour, **481(48.1%) transactions were flagged as fraudulent**, representing a significant portion of the activity. These fraudulent transactions amounted to a total value of **378.86K**.

**ii. Which regions have the highest fraud flag rate?**

The geographical distribution of flagged transactions indicates that **Northwest Africa, Western Europe, Eastern North America, and South East Asia experienced a higher concentration of potentially fraudulent activity** during this hour, as evidenced by the clustering of points in these regions on the map.

**iii. Do specific transaction types or statuses correlate with fraud?**

Analyzing the breakdown of fraudulent transactions by type reveals that **Transfers** accounted for the **highest percentage** of fraudulent activity at **35.73%**, followed closely by **Deposits at 34.33%**. **Withdrawals** had the **lowest percentage** of fraudulent transactions at **29.94%.**

Further examining the status of these fraudulent transactions:

* Among the **successful transactions** that were flagged as fraud (totaling **231 with a value of 182.94K)**, **Transfers** again led at **39.59%**, followed by **Deposits at 32.54%**, and **Withdrawals at 27.87%.**
* For the **failed transactions** that were flagged as fraud (totaling **250 with a value of 195.92K)**, **Deposits** had the **highest percentage at 36%**, followed by **Transfers at 32.13%**, and **Withdrawals at 31.87%.**

This suggests that while **transfers** are generally more prone to being **flagged as fraudulent when successful**, **deposits** show a higher rate of being **flagged as fraudulent when they fail**, potentially due to detection mechanisms at play.

**iv. Are fraud-flagged transactions more common in certain network slices or bandwidth levels?**

 **1. By Bandwidth (150–250 Mbps):** 
This bandwidth range showed the **highest concentration of fraudulent activity**, with a total of **228 flagged transactions**.

  * **111 of these attempts failed**, indicating that some fraud detection or transaction-blocking mechanisms were partially effective.
  * **117 fraudulent transactions were successful**, suggesting that nearly **half of the activity in this high-risk bandwidth range bypassed existing controls** a clear 
    vulnerability point that needs closer monitoring or intervention.


  **2. By Network Slice (Slice 2):**
Network Slice 2 experienced the **greatest fraud exposure**, registering **173 fraudulent transactions** overall.

* **92 of these were failed attempts**, showing signs of detection or disruption before completion.
* However, **81 fraudulent transactions went through successfully**, highlighting potential weaknesses in security measures specific to this slice or how it's provisioned and monitored in real-time.

This indicates certain infrastructure layers (like **Slice 2** or bandwidth range **150–250 Mbps**) may be more vulnerable or less monitored, making them preferred channels for fraud. 


**C. Time-Sensitive Anomalies**

To understand the temporal patterns of fraudulent activity within this critical hour, we can analyze when these incidents occurred and if they correlate with specific transaction types.

**i. At what minute or period in the hour did most frauds occur?**

The **peak** of fraudulent activity within this hour was observed at **10:55 AM, with 15 fraudulent transactions** taking place. Interestingly, **10:05 AM** recorded the **second-highest** number of **fraudulent transactions with 14 incidents**, followed by **10:49 AM** with **12**. In contrast, the **least** fraudulent activity occurred at **10:28 AM**, with only **2 transactions.**

**ii. Are there any spikes in fraud that coincide with spikes in certain transaction types?**

Examining the temporal distribution of fraudulent transactions by type reveals the following:

  * **Transfers:** Fraudulent transfer transactions experienced notable spikes at **10:23 AM, 10:49 AM, and 10:56 AM**, with **7 transactions** occurring at each of these times.
  
  * **Deposits:** The highest spike in fraudulent deposit transactions occurred at **10:51 AM, with 7 transactions**. Other notable peaks were at **10:38 AM and 10:16 AM**, both recording 6 fraudulent deposit transactions.

  * **Withdrawals:** Fraudulent withdrawal transactions showed more frequent, albeit smaller, spikes. The highest occurrences were at **10:17 AM, 10:25 AM, 10:50 AM, and 10:56 AM**, each with **5 fraudulent transactions.**

**iii. Does fraud occur consistently or suddenly?**

The data suggests that fraudulent activity within this hour was **not consistent but rather occurred in distinct bursts or spikes**. The significant peaks at specific minutes, particularly **(10:49–10:56 a.m.)**, and the varying spike times for different transaction types indicate **periods of concentrated fraudulent activity** rather than a steady stream throughout the hour. This pattern of sudden increases could suggest coordinated attempts or the exploitation of temporary vulnerabilities.


## **6. Conclusion and Recommendations**

## **Conclusion**

This one-hour transactional activity on **17th January 2025** offers a concentrated view into the dynamic landscape of real-time banking operations. Out of **1,000** transactions, nearly **half (48.1%) were flagged as fraudulent** indicating a significant exposure to risk within just 60 minutes. Patterns emerged across **regions**, **transaction types**, **network slices**, and **bandwidth levels**, highlighting concentrations of fraudulent activity in **Northwest Africa, Western Europe, and South Asia**.

Transfers were the most frequently exploited transaction type in fraud cases, especially among successful transactions. Spikes in fraudulent activity aligned with specific minutes in the hour suggesting deliberate, time-targeted actions. Additionally, **Network Slice 2** and **bandwidths between 150–250 Mbps** surfaced as common attributes in fraudulent behavior.

These insights, though limited to a short timeframe, emphasize how even a small window of real-time data can reveal concentrated fraud patterns when observed through the right analytical lens.

---

## **Recommendations**

1. **Implement Real-Time Monitoring Rules**
   Trigger alerts for spikes in transaction volume or fraud-prone activity during narrow time intervals (e.g., minute-by-minute analysis during peak fraud periods).

2. **Strengthen Controls on Transfers and Deposits**
   Since these were most exploited, especially during successful fraud, additional verification layers or delays for high-risk types may be effective.

3. **Geo-Targeted Fraud Prevention**
   Allocate more fraud detection resources to high-risk regions such as **Northwest Africa**, **Western Europe**, and **South Asia** based on observed clusters.

4. **Optimize Network Slice Security**
   Investigate and fortify **Network Slice 2**, which experienced the highest fraudulent activity—consider behavioral modeling or micro-segmentation.

5. **Bandwidth Sensitivity Settings**
   Pay closer attention to bandwidth levels of **150–250 Mbps** when configuring anomaly detection algorithms or thresholds.

6. **Expand Data Logging for Longer Analysis**
   To better understand patterns over time, integrate continuous logging to enable comparisons and track evolving trends.

---
This project was inspired by https://www.youtube.com/@DataChy
