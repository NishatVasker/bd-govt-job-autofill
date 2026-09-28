# BD Govt Job Autofill (Chrome Extension)

Applying for government jobs through Teletalk (`*.teletalk.com.bd`) means typing the exact same biographical, academic, and address details dozens of times across different circulars. 

I built this lightweight Chrome extension (Manifest V3) to solve that headache. It stores your application profile locally on your machine and autofills standard Teletalk forms in one click.

---

## Privacy First

Your personal information (NID, phone numbers, addresses, family details) is sensitive. 

- **100% Offline & Local:** Everything is saved directly in your browser's local storage (`chrome.storage.local`).
- **Zero Tracking:** No external servers, no background network calls, and no analytics scripts. You can inspect every line of code in `popup.js`, `schema.js`, and `content.js` to see for yourself.

---

## Features

- **One-Click Autofill:** Maps and populates Personal Data, Contact Info, Permanent/Present Addresses, and Academic records (SSC, HSC, Honors).
- **Handles Nested Dropdowns:** Correctly triggers change events for dependent fields like Division ➔ District ➔ Upazila/Thana.
- **Form Normalization:** Works across varying field names and schemas used by different ministries and tax zones.
- **Includes Test Fixtures:** Comes with Python unit/smoke tests and mock HTML fixtures to verify selector matching before deployment.

---

## 📁 Repository Structure

```text
├── manifest.json              # Extension manifest (V3)
├── popup.html / popup.js      # User interface & profile storage logic
├── popup.css                  # UI styling
├── content.js                 # Content script injected into active pages
├── teletalk-exact.js          # Direct DOM mapping engine
├── schema.js                  # Data structure definitions
└── tests/
    ├── dropdown_test.py       # Validates cascading select elements
    ├── smoke_test.py          # Quick sanity test runner
    ├── tax1_exact_test.py     # Specific tests for Tax Zone forms
    ├── teletalk-fixture.html  # Mock Teletalk page
    └── tax1-markup-fixture.html

## How to install this

git clone [https://github.com/NishatVasker/bd-govt-job-autofill.git](https://github.com/NishatVasker/bd-govt-job-autofill.git)

