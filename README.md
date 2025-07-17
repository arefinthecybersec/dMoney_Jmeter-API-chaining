# dMoney JMeter API Chaining Test Suite

This project demonstrates performance and functional testing of the dMoney API using Apache JMeter. It simulates real-world transaction flows including login, agent/customer creation, deposits, send money, and merchant payments, following a chained execution pattern.

---

## 🔧 Prerequisites

- Java 8 or above
- Apache JMeter 5.x or above
- Git (optional, for cloning)

---

## 📁 Project Structure

```
├── scripts/
│   └── dmoney_chain_test.jmx         # Contains:
│       ├── Login Thread Group
│       │   └── JSON Extractor (token)
│       ├── Agent Deposit Thread Group
│       │   ├── CSV Data Config
│       │   ├── HTTP Request: Deposit
│       │   └── Response Assertion
│       ├── Customer Send Money Thread Group
│       └── Merchant Payment Thread Group
├── csv/
│   ├── sendMoney.csv
│   └── payment.csv
├── reports/
├── images/
├── README.md
```
---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/arefinthecybersec/dMoney_Jmeter-API-chaining.git
cd dMoney_Jmeter-API-chaining
```
### 2. Open JMeter and Run the Test Plan
- Open scripts/dmoney_chain_test.jmx using JMeter GUI.
- Ensure your CSV files are correctly referenced.
- Run the test using the green ▶️ button.

### 3. Generate Report from CLI (Optional)
```
jmeter -n -t scripts/dmoney_chain_test.jmx -l results.csv -e -o reports/
```
---

## 🔄 Test Flow Overview

1. Login
2. Agent to Customer [Deposit]
3. Customer to Customer [SendMoney]
4. Customer to Merchant [Payment]
   
Each stage is dependent on the previous one, making this a chained test structure.
---

## 🧪 Sample Output

View Result Tree Snapshot:
<img width="1366" height="716" alt="image" src="https://github.com/user-attachments/assets/61805780-30a8-4dfb-91d3-c0def1ec58f6" />

---

## 📊 Reports

After execution, HTML reports are generated in the /reports folder, which show metrics like throughput, latency, assertion results, and response times.

---

## 📌 Notes

- All requests are authenticated via token-based login.
- You can customize the CSV files to test with your data.
- Token is extracted and reused across thread groups.

---

## 📝 License

This project is licensed under the MIT License – see the LICENSE file for details.

---

## 🤝 Contributors

### 👤 Md Arefin Hossain - Author, Software Engineer in Test
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/arefin-hossain/)

### 👤 Salman Rahman - Reviewer/ Tester
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?logo=github&style=flat-square)](https://github.com/salmansrabon)
