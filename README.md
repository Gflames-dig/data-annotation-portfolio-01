# data-annotation-portfolio-01
data-annotation-portfolio/ │ ├── README.md ├── requirements.txt │ ├── instruction_dataset/ │   ├── data.json │   └── README.md │ ├── ner_dataset/ │   ├── data.json │   └── README.md │ ├── sentiment_dataset/ │   ├── data.json │   └── README.md │ └── validation_script/     └── validate_json.py

2. Main README.md
# Data Annotation Portfolio (JSON)

This repository showcases my practical experience with data annotation using JSON for NLP and LLM training.

## 📌 Projects Included

### 1. Instruction Tuning Dataset
- Prompt-response pairs for LLM training
- Clean structured JSON format

### 2. Named Entity Recognition (NER)
- Annotated entities with labels and offsets
- Schema-compliant for NLP pipelines

### 3. Sentiment Analysis Dataset
- Text classification with metadata
- Includes annotator notes and confidence scores

---

## 🛠 Skills Demonstrated

- JSON dataset structuring
- NLP annotation (NER, classification, instruction tuning)
- Data validation and quality assurance
- Schema consistency and formatting

---

## ✅ Validation

All JSON files are validated using Python scripts to ensure correctness and usability.

---

## 🔗 Author

Goodnews Friday 
GitHub: https://github.com/gflames-dig

3. Instruction Dataset
instruction_dataset/data.json
[
  {
    "id": "inst_001",
    "instruction": "Summarize the text below.",
    "input": "Artificial intelligence is transforming industries by automating tasks and improving decision-making.",
    "output": "AI is transforming industries by automating tasks and improving decisions."
  },
  {
    "id": "inst_002",
    "instruction": "Explain photosynthesis simply.",
    "input": "",
    "output": "Photosynthesis is how plants use sunlight to make food from water and carbon dioxide."
  }
]
instruction_dataset/README.md
# Instruction Dataset

This dataset contains prompt-response pairs used for training language models.

## Format
- instruction: task description
- input: optional context
- output: expected response

- 4. NER Dataset
  5. ner_dataset/data.json
  6. [
  {
    "text": "Google was founded in California.",
    "entities": [
      {"text": "Google", "label": "ORG", "start": 0, "end": 6},
      {"text": "California", "label": "LOCATION", "start": 22, "end": 32}
    ]
  },
  {
    "text": "Elon Musk leads Tesla.",
    "entities": [
      {"text": "Elon Musk", "label": "PERSON", "start": 0, "end": 9},
      {"text": "Tesla", "label": "ORG", "start": 16, "end": 21}
    ]
  }
] 
ner_dataset/README.md
# Named Entity Recognition Dataset

This dataset includes labeled entities with character offsets.

## Labels
- PERSON
- ORG
- LOCATION

- 5. Sentiment Dataset
sentiment_dataset/data.json
[
  {
    "id": 101,
    "text": "The app is very useful and easy to use.",
    "label": "positive",
    "confidence": 0.96,
    "annotator_notes": "Clear positive feedback"
  },
  {
    "id": 102,
    "text": "The app crashes frequently after the update.",
    "label": "negative",
    "confidence": 0.94,
    "annotator_notes": "User complaint about performance"
  }
] 
sentiment_dataset/README.md
# Sentiment Analysis Dataset

This dataset classifies text into sentiment categories.

## Labels
- positive
- negative
- neutral
- 
- 6. Validation Script (IMPORTANT – This Makes You Stand Out)
validation_script/validate_json.py
import json
import os

def validate_json(file_path):
    try:
        with open(file_path, 'r') as f:
            data = json.load(f)
        print(f"[SUCCESS] Valid JSON: {file_path}")
        return True
    except json.JSONDecodeError as e:
        print(f"[ERROR] Invalid JSON in {file_path}")
        print(f"Details: {e}")
        return False

def scan_folder(folder):
    print(f"\nScanning folder: {folder}")
    for root, dirs, files in os.walk(folder):
        for file in files:
            if file.endswith(".json"):
                validate_json(os.path.join(root, file))

if __name__ == "__main__":
    base_dir = "../"
    scan_folder(base_dir) 

    7. requirements.txt
    # No external dependencies required
