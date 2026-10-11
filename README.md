<div align="center">
  <a href="#">
    <img src="https://img.youtube.com/vi/placeholder/0.jpg" alt="This 2.7GB Local OCR Model Changed My Workflow! (LightOnOCR-3 Review)">
  </a>
  <h3>📺 <a href="#">Watch the full tutorial on YouTube</a></h3>
</div>

# 🚀 LightOnOCR Document Vision Intelligence

> High-accuracy document understanding model that extracts full page text, spatial layout bounding coordinates, and structured chart tables in a single unified step.

| Step | Type | Action |
| :--- | :--- | :--- |
| **Step 1** | Input | Supply single document page image or PDF rendered at 400 DPI |
| **Step 2** | AI Action | LightOnOCR-3 processes visual tokens with native grounding detection |
| **Step 3** | Result | Emits structured markdown, labeled bounding boxes, and table data |

---

### 📦 Key Highlights

* 🧠 **Single Model Architecture**: Eliminates traditional multi-tool pipelines for layout detection, text transcription, and table reconstruction.
* 📍 **Dual Operation Modes**: Run with an empty prompt for raw clean reading-order text, or `"grounding"` for spatial bounding boxes.
* 📊 **Chart to Table Extraction**: Automatically identifies scientific and financial charts, converting visual plotted data into clean HTML tables.
* ⚡ **Open Weights & Local Deployment**: 4B parameter Qwen3.5 vision architecture ready for local inference via 4-bit GGUF quantization and multimodal projector.

---

### 🛠️ Prerequisites & Setup

Ensure Python 3.10+ is installed on your system.

```powershell
pip install ollama pillow
```

---

### 📥 Download GGUF Checkpoints (Model + Multimodal Projector)

Download both the 4-bit text-vision weights and the multimodal projector file directly into your `models/` directory:

```powershell
# 1. Download Core 4-Bit GGUF Model (2.71 GB)
hf download prithivMLmods/LightOnOCR-3-4B-GGUF LightOnOCR-3-4B.Q4_K_M.gguf --local-dir models

# 2. Download Multimodal Projector Adapter (676 MB)
hf download prithivMLmods/LightOnOCR-3-4B-GGUF LightOnOCR-3-4B.mmproj-bf16.gguf --local-dir models
```

---

### ⚙️ Register Model in Ollama

Register the dual-file combo into Ollama using `Modelfile`:

```powershell
ollama create lightonocr -f Modelfile
```

---

### ▶️ Run Document Analysis

Run the document analysis script on the sample input:

```powershell
python main.py
```

---

### 📂 Repository Structure

```text
├── Modelfile
├── README.md
├── inputs/
│   └── sample_document.pdf
├── main.py
└── models/
    ├── LightOnOCR-3-4B.Q4_K_M.gguf
    └── LightOnOCR-3-4B.mmproj-bf16.gguf
```

---

### 💡 Practical Use Cases

1. **Enterprise Financial Auditing**: Parse quarterly reports, balance sheets, and earnings graphs directly into structured tables without error-prone manual entry.
2. **Medical & Laboratory Records**: Digitize handwritten prescriptions, lab result sheets, and clinical reports with exact coordinate bounding boxes.
3. **Legal Contract Discovery**: Ingest complex multi-column legal agreements, retaining clause boundaries, headers, and footer page numbers for RAG citation.
4. **Scientific Paper Indexing**: Extract embedded equations, figure captions, and plotted experimental data points directly into research databases.
5. **Invoice & Receipt Processing**: Automate vendor receipt digitization, extracting line items, tax breakdown tables, and merchant logos with spatial precision.

---

### 🔮 Future Expansion Capabilities

1. **Multi-Page Batch Processing**: Concurrent multi-threading for continuous multi-page document volume processing.
2. **Direct Excel & CSV Exporter**: Automatic export of extracted chart HTML tables into clean spreadsheets.
3. **Interactive Visual Bounding Box Inspector**: Web viewer overlaying extracted bounding boxes on original document images.
4. **Custom Prompt Instruction Tuning**: Expansion beyond fixed grounding tokens to support arbitrary semantic entity querying.
5. **Edge Hardware Acceleration**: Specialized TensorRT-LLM and ONNX runtime optimizations for low-power mobile or edge devices.

---

<sub>**Keywords:** LightOnOCR-3, OCR, Document AI, Vision Language Model, Qwen 3.5, Ollama, GGUF, Multimodal Projector, PDF Parsing, Table Extraction, Bounding Boxes, Local AI, Offline OCR, Machine Learning</sub>
