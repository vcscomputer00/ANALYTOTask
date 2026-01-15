# ANALYTOTask
automate the process of extracting invoice details from incoming PDFs and validating them against data in a simulated purchase order (PO) system.

Link for the Master Bot Folder - https://community.cloud.automationanywhere.digital/#/bots/repository/private/folders/32253312

User Name - vikas.jaiswal@tecnoprism.com (I created the community account when I was in Technoprism and am still using the same, as it's working fine)\
P@$$wo₹d - Myvcs@1431

INVOICE DATA EXTRACTION & VALIDATION BOT
Automation Anywhere A360 – Community Edition
================================================

1. OVERVIEW
-----------
This bot automates the process of extracting invoice data from PDF files,
validating it against Purchase Order (PO) data stored in Excel, and routing
the invoices based on validation results.

The bot is designed for Automation Anywhere A360 Community Edition and uses
native OCR and Excel actions only (no IQ Bot required).

Use Case:
- Accounts Payable Invoice Processing
- Invoice vs PO validation
- Exception handling and reporting


2. BOT NAME
-----------
Invoice_Main_Controller


3. FOLDER STRUCTURE
------------------
Create the following folder structure before running the bot:

C:\AA360_InvoiceBot\
│
├── Input\
│   └── Invoices\        (Place incoming invoice PDFs here)
│
├── Processed\           (Matched invoices)
├── Exceptions\           (Mismatched invoices)
├── Reports\              (Validation report CSV)
└── Logs\                 (Reserved for future logging)


4. INPUT FILES
--------------
A) Invoice PDF
Each invoice PDF should contain readable text such as:

Invoice Number: INV001
Vendor Name: ABC Pvt Ltd
Invoice Date: 01-01-2026
Amount: 10000

B) PO Data Excel
File Name: PO_Data.xlsx
Location: C:\AA360_InvoiceBot\

Columns required:
- InvoiceNumber
- VendorName
- Amount

Example:
INV001 | ABC Pvt Ltd | 10000
INV002 | XYZ Ltd    | 25000


5. WORKFLOW STAGES
-----------------
Stage 1: Intake
- Monitors the Input\Invoices folder
- Reads all PDF files

Stage 2: Extraction
- Uses native OCR to extract invoice text
- Parses Invoice Number, Vendor Name, and Amount

Stage 3: Validation
- Reads PO data from Excel
- Compares Invoice Number and Amount

Stage 4: Decision
- If match found:
  - Moves invoice to Processed folder
  - Marks status as "Matched"
- If mismatch:
  - Moves invoice to Exceptions folder
  - Marks status as "Exception"

Stage 5: Reporting
- Appends processing result to Invoice_Report.csv


6. OUTPUT FILES
---------------
A) Processed Invoices
Location:
C:\AA360_InvoiceBot\Processed\

B) Exception Invoices
Location:
C:\AA360_InvoiceBot\Exceptions\

C) Validation Report
File:
C:\AA360_InvoiceBot\Reports\Invoice_Report.csv

Report Columns:
- Invoice Number
- Vendor Name
- Amount
- Status


7. HOW TO RUN
-------------
1. Ensure folder structure is created
2. Ensure PO_Data.xlsx exists and is populated
3. Place invoice PDF(s) in Input\Invoices
4. Open Automation Anywhere A360 Community Edition
5. Open and run the bot: Invoice_Main_Controller
6. Review results in Processed / Exceptions / Reports folders


8. ASSUMPTIONS & LIMITATIONS
---------------------------
- Invoice PDFs must be text-readable (not scanned images)
- OCR accuracy depends on invoice format
- Matching logic is exact (no fuzzy match)
- Single-currency invoices assumed


9. FUTURE ENHANCEMENTS
----------------------
- IQ Bot integration for higher OCR accuracy
- Config.xlsx driven paths
- Email notifications for exceptions
- Enhanced logging framework
- Agent-based decision routing


10. AUTHOR / PURPOSE
--------------------
This bot is created for:
- Learning Automation Anywhere A360
- Community Edition practice
- Interview and demo purposes

================================================
END OF FILE

