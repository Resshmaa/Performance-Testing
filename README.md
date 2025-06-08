# Performance Testing – Magento Demo Site

This repository showcases a comprehensive **Performance Testing framework** using **Apache JMeter**, **BlazeMeter**, and **Taurus**. It simulates realistic user load on the [Magento Demo E-Commerce Site](https://magento.softwaretestingboard.com/) and analyzes performance across tools and environments. Actions include browsing product pages, navigating to checkout, and intentionally visiting an invalid URL to test error handling. 

---

## Key Highlights

1. Recorded user actions using the **BlazeMeter Chrome Extension**
2. Executed performance test locally via **Apache JMeter**
3. Ran command-line load tests using **Taurus (BZT + YAML)**
4. Integrated and executed test in **BlazeMeter Cloud**
5. Analyzed reports: average response time, error rate, and throughput

---

## Tech Stack & Tooling

| Tool/Tech            | Purpose                                |
|----------------------|----------------------------------------|
| **Apache JMeter**    | Core load testing tool                 |
| **BlazeMeter**       | Test recording + cloud execution       |
| **Taurus (BZT)**     | CLI-based performance automation       |
| **Python + pip**     | To install and run Taurus              |
| **BlazeMeter Plugin**| Record browser flows for JMeter export |
| **Excel**   | Manual analysis and reporting          |

---

## Project Structure

```
Magento-Performance-Testing/
│
├── Magento-Performance-Testing.jmx → JMeter test script
├── magento_test.yml → Taurus YAML configuration
├── screenshots/
│ ├── jmeter/ → Screenshots from JMeter run
│ ├── taurus/ → CLI and Taurus execution
│ └── blazemeter/ → BlazeMeter dashboard/report
├── reports/
│ ├── jmeter/JMeter_Test_Summary.xlsx → Summary of JMeter metrics
│ ├── taurus/Taurus_Test_Summary.xlsx → Taurus report summary
│ └── blazemeter/Blazemeter_Test_Summary.xlsx → BlazeMeter result snapshot
```

---

## Taurus CLI Execution Commands

```bash
python --version
pip --version
pip install bzt
bzt --version
bzt magento_test.yml
```

---

## BlazeMeter Cloud Execution

The same Magento-Performance-Testing.jmx file was uploaded to BlazeMeter for remote execution and visual reporting. The results are saved in /reports/blazemeter/Blazemeter_Test_Summary.xlsx

---

## Summary of Results

| Tool       | Avg Resp Time | Error Rate | Notes                                     |
| ---------- | ------------- | ---------- | ----------------------------------------- |
| JMeter     | \~1954 ms     | 30.3%      | Local test, recorded using BlazeMeter ext |
| Taurus     | \~1950 ms     | 30%        | Same .jmx file run via CLI                |
| BlazeMeter | \~1950 ms     | 30.3%      | Cloud report and graphs available         |

---

## Screenshots & Reports

All screenshots and exported test summaries are available under the /screenshots and /reports folders for each tool used

---

## Conclusion of the test

I ran a basic performance test on the Magento demo website to check how it handles a few users at the same time. Most pages responded fine, but some like the checkout and success pages took longer to load. I also added a broken link on purpose to see how errors are tracked, and it showed a proper 404 error.

Overall, the test went well. It gave me a clear idea of how the website performs and where it might slow down. The tools I used JMeter, BlazeMeter and Taurus helped collect useful data and reports for review.
