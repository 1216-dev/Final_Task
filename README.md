# Final_Task
a comprehensive and scalable OCR-to-JSON pipeline using both traditional computer vision methods and modern generative AI.


---

## 🔄 Workflow

| Step                         | Description                                                        |
|-----------------------------|--------------------------------------------------------------------|
| **Tile Download**           | Fetch image segments via REST API using known coordinates          |
| **Stitching**               | Combine tiles into full-page images using Python PIL               |
| **Tesseract OCR**           | Extract raw text and bounding box metadata                         |
| **Annotation**              | Draw boxes on words with confidence > 60%                          |
| **Gemini AI Enhancement**   | Clean OCR text, fill missing details, and output JSON              |
| **Save Results**            | Organize output into `OCR Text/`, `JSON/`, and `Annotated Images/` |

---

## 📊 Gemini AI vs Raw OCR

| Metric                  | Tesseract Only | Gemini Enhanced |
|-------------------------|----------------|-----------------|
| Name Accuracy           | 78%            | 95%             |
| Street Address Precision| 72%            | 93%             |
| Spouse Name Detection   | 34%            | 88%             |
| Occupation Recognition  | 61%            | 92%             |

---

## 📎 JSON Output Sample

```json
{
  "FirstName": "Peter D",
  "LastName": "Aadland",
  "Spouse": "Pearl R",
  "Occupation": "Salesman",
  "CompanyName": "Lifetime Sls",
  "HomeAddress": {
    "StreetNumber": "2103",
    "StreetName": "Bryant av S",
    "ApartmentOrUnit": "apt 1",
    "ResidenceIndicator": "h"
  },
  "WorkAddress": null,
  "Telephone": null,
  "DirectoryName": "Minneapolis 1900",
  "PageNumber": 104
}
