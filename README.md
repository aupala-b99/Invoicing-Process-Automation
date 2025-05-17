# 🤖 BoltInvoices — UiPath Automation Project

This UiPath automation project generates and sends PDF invoices automatically once a delivery confirmation email is received. It is designed to reduce invoice processing delays and streamline post-delivery invoicing for businesses managing thousands of orders.

---

## 🔧 Project Overview

- 📥 **Input**:  
  - Delivery confirmation emails (from `cody.baldwin@wisc.edu`)  
  - Order list (`Orders.xlsx`)  
  - Invoice template (`InvoiceTemplate.docx`)

- 📤 **Output**:  
  - Auto-filled PDF invoices named by order number  
  - Emailed invoices sent via Outlook 365  
  - Emails marked as read and moved to the “RPA” folder  

---

## 📂 Folder Structure

- `InvoiceTemplate.docx`: Template for invoices with placeholders  
- `Orders.xlsx`: Contains order numbers, totals, and customer info  
- `InvoiceFiles/`: Folder where generated invoices (PDFs) are saved  
- `Main.xaml`: The UiPath automation logic  
- `Project.json`: UiPath project settings  
- `Screenshots/`: [Optional] Visuals of workflow or outputs

---

## 🛠️ Automation Steps

1. Open `Orders.xlsx` spreadsheet.
2. Connect to Outlook 365 with default authentication.
3. Scan inbox for unread emails from `cody.baldwin@wisc.edu`.
4. If confirmation is found:
   - Use the template to create invoice.
   - Set current date and due date (+30 days).
   - Lookup amount due from the order list.
   - Save invoice as PDF in `InvoiceFiles/`.
   - Email the PDF invoice to the customer (send to self for testing).
   - Mark email as read and move to “RPA” folder.
   - Log order number using the `Write Line` activity.

---

## 🧰 Tools & Technologies

- UiPath Studio (Community Edition)
- Outlook 365 (Use Outlook 365 activity)
- Excel & Word automation activities
- DateTime manipulation
- File handling & email automation

---

## 🖼️ Demo / Screenshots (Optional)

> *(Add screenshots of the workflow, sample output PDFs, or email confirmation flow here if you’d like)*

---

## ✅ Status

- ✔️ Tested with multiple delivery confirmation scenarios
- 📈 Can scale to support 1000s of orders with minor adjustments
- 🔄 Modular and easy to adapt for other document automation use cases

---
