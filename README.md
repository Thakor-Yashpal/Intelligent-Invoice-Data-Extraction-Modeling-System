# Intelligent-Invoice-Data-Extraction-Modeling-System


base
```
📂 Google Drive Folder
      ├── invoices/
      │     ├── invoice1.pdf
      │     ├── invoice2.png
      │     └── invoice3.jpg
      │
      └── invoice_dataset.xlsx   ← optional structured input

⏬
🔹 Step 1: OCR + Text Extraction (Tesseract)
🔹 Step 2: Regex-based Field Parsing (Invoice #, Date, Amount, Vendor)
🔹 Step 3: Data Modeling → SQLite + CSV
🔹 Step 4: Visualization (Matplotlib)
🔹 Step 5: Evaluation (Precision, Recall, F1)

```

### 🧠 Technologies Used

<li>Python 3.10+</li>

<li>PyTorch (optional for ML expansion)</li>

<li>Tesseract OCR – for text extraction</li>

<li>Matplotlib / Pandas / NumPy – for visualization and data analysis</li>

<li>SQLite3 – for structured data storage</li>

<li>Google Colab – for easy execution and Drive integration</li>

| Field            | Description                                      |
| ---------------- | ------------------------------------------------ |
| `invoice_number` | Invoice ID or number parsed from OCR text        |
| `invoice_date`   | Extracted and normalized invoice date            |
| `vendor_name`    | Detected supplier or vendor name                 |
| `total_amount`   | Parsed total or balance due                      |
| `line_items`     | List of description, quantity, unit price, total |


🧪 Evaluation Metrics

Evaluates accuracy on a labeled subset (ground truth .csv) using:

Precision, Recall, and F1-score per field

Overall weighted F1 score

Field-wise accuracy visualization

✅ Example Output:
```
📊 Field-Level Accuracy:
invoice_number     : 92.0%
invoice_date       : 88.5%
vendor_name        : 85.3%
total_amount (±$5) : 91.2%

🏆 Overall Weighted F1 Score: 0.89
```

⚙️ How to Run in Google Colab

Open the notebook in Google Colab.

Mount Google Drive:

```
from google.colab import drive
drive.mount('/content/drive')
```

| Approach                  | Pros                                    | Cons                     |
| ------------------------- | --------------------------------------- | ------------------------ |
| **Regex + OCR (current)** | Fast, no fine-tuning, works offline     | May miss complex formats |
| **OCR + LLM (optional)**  | Higher accuracy via GPT/Claude          | Requires API & cost      |
| **LayoutLMv3 / Donut**    | Vision-text alignment, better structure | GPU + dataset required   |

### Upload or reference your invoices folder or Excel dataset:
```
folder = "/content/drive/MyDrive/invoice_dataset/"
```
