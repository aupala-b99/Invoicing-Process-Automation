# 🚀 BoltInvoices – Automating Invoicing in the Order-to-Cash Cycle

This project showcases how we applied **process mining** using Celonis, **process mapping** using Lucidchart, and **automation** using UiPath to optimize the invoicing step in the Order-to-Cash cycle at Bolt Socks.

> 📉 We identified that invoice creation lagged >1 day after delivery confirmations—leading to delays in cash flow. Using UiPath, we fully automated invoice generation and dispatch, saving hours of manual work and improving the hit rate against the 23-day throughput target.

---

## 🔍 Problem Statement

- **Current Challenge:** Invoices were being created manually, sometimes >1 day after delivery confirmation.
- **Impact:** Bottlenecks in cash collection, low target throughput hit rate (49%), delayed revenue realization.

---

## 🔬 Process Discovery

Using **Celonis Business Miner**, we analyzed over 5,000 cases from the Order-to-Cash cycle:

- ⏱️ **Median Throughput Time:** 23.6 days (Target: 23)
- 🎯 **Target Hit Rate:** 49%
- ⚠️ Bottleneck detected between **Confirmed Delivery** and **Invoice Creation**

> Visuals from Celonis:
- ![Throughput Time](ProcessMiningScreens/throughput-time.png)
- ![Process Flow](ProcessMiningScreens/process-explorer.png)
- ![Activities Overview](ProcessMiningScreens/activity-overview.png)

---

## 🗺️ Lucidchart Mapping

Mapped the O2C process to visualize human touchpoints and identify automation candidates.

![Lucidchart Process Map](Diagrams/lucidchart-process-map.png)

---

## 🤖 UiPath Automation: "BoltInvoices"

We built an RPA solution to generate and email invoices as soon as a delivery confirmation is received.

### 🔁 Workflow Summary

1. Read `Orders.xlsx`
2. Connect to Outlook 365
3. Check for unread emails
4. If delivery confirmation is found:
   - Fill out `InvoiceTemplate.docx` with:
     - Order info
     - Current date
     - Due date (+30 days)
     - Amount due
   - Save as PDF in `InvoiceFiles/`
   - Email invoice PDF to customer
   - Move email to “RPA” folder
   - Log processed order

### 🛠 Tools Used

- UiPath Studio
- Outlook 365 Activities
- Word & Excel Automation
- File System Automation
- Email Filtering & Logging

---

## 📦 Files Included

- `Orders.xlsx` — Sample order data
- `InvoiceTemplate.docx` — Dynamic template for invoice creation
- `Order-to-Cash.pdf` — Original business process flow
- `Main.xaml` — UiPath automation script
- `ProcessMiningScreens/` — Screenshots from Celonis dashboard
- `lucidchart-process-map.png` — Process map for handoffs and automation scope

---

## 💡 Outcomes

- ⏱️ Reduced invoice creation delay from 1 day to near real-time
- 📈 Increased throughput hit rate
- 📬 Achieved auto-emailing with proof of delivery
- 📁 Clean audit trail and storage of all generated invoices

---

