# Assignment Banana 🍌

[![Python Version](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![AI Model](https://img.shields.io/badge/Model-Gemini--2.5--Flash--Image-orange)](https://ai.google.dev/)

**Assignment Banana** is an experimental image generation utility designed to transform assignment concepts into visual representations. Leveraging Google's Gemini multimodal capabilities, it aims to bridge the gap between text-based academic requirements and high-quality visual outputs.

> [!IMPORTANT]
> **Current Status:** This project is in an experimental phase. While the core engine utilizes the `gemini-2.5-flash-image` model, users may encounter API limitations depending on their Google AI Studio tier.

---

## 🚀 Overview

The project serves as a specialized wrapper for Google's Generative AI SDK. Its primary objective is to automate the creation of assignment-related imagery—ranging from conceptual "nano-banana" culinary presentations to handwritten-style document simulations.

### Key Value Proposition
- **Rapid Prototyping**: Quickly visualize assignment prompts.
- **Gemini Integration**: Direct implementation of the latest Google GenAI models.
- **Simplified Workflow**: Minimal configuration required to start generating high-fidelity images.

---

## ✨ Features

- **Text-to-Image Generation**: Convert complex descriptive prompts into 1024x1024 (or model-default) images.
- **Environment Management**: Secure handling of API credentials via `.env` integration.
- **Automated Image Processing**: Uses `Pillow` to handle raw byte streams and save them directly to standard formats (PNG).
- **Flexible Prompting**: Pre-configured for high-detail, "fancy" thematic outputs.

---

## 🛠 Tech Stack

| Category | Technology |
| :--- | :--- |
| **Language** | Python 3.9+ |
| **AI Engine** | Google Generative AI (Gemini) |
| **Image Handling** | Pillow (PIL) |
| **Configuration** | Python-Dotenv |
| **API Client** | `google-genai` |

---

## 📂 Directory Structure

```text
├── .env.sample         # Template for required API credentials
├── .gitignore          # Standard Python and environment exclusions
├── gen.py              # Main execution script for image generation
└── README.md           # Project documentation
```

---

## 🚦 Getting Started

### Prerequisites

- Python 3.9 or higher
- A Google AI Studio API Key ([Get one here](https://aistudio.google.com/))

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/xevrion/assignment-banana.git
   cd assignment-banana
   ```

2. **Install dependencies:**
   ```bash
   pip install google-genai python-dotenv Pillow
   ```

3. **Configure Environment:**
   Copy the sample environment file and add your API key:
   ```bash
   cp .env.sample .env
   ```
   Edit `.env` and add your key:
   ```env
   GOOGLE_API_KEY=your_api_key_here
   ```

---

## 📖 Usage

To generate an image based on the default prompt (a "nano banana dish in a fancy restaurant"), simply run:

```bash
python gen.py
```

### Customizing the Output
You can modify the `prompt` variable in `gen.py` to change the generated content:

```python
prompt = "A handwritten physics assignment on a wooden desk, cinematic lighting"
```

The script will output `generated_image.png` in the root directory upon successful completion.

---

## 🔧 Troubleshooting

### Common Issues

| Issue | Solution |
| :--- | :--- |
| **403 Forbidden / Quota Exceeded** | Text-to-Image generation often requires a paid tier or specific region access in Google AI Studio. Ensure your API key has "Image Generation" permissions enabled. |
| **ModuleNotFoundError** | Ensure you have run `pip install -r requirements.txt` (or the manual install commands above). |
| **NoneType error on image save** | This occurs if the model returns text instead of image data. Check the console output for safety filter flags. |

---

## 🗺 Roadmap

- [ ] **PDF Integration**: Add functionality to parse text from PDF assignments to automatically generate prompts.
- [ ] **Handwriting Synthesis**: Fine-tune prompts to better simulate realistic student handwriting.
- [ ] **CLI Interface**: Add arguments for prompt input and output filename via terminal.
- [ ] **Batch Processing**: Support for generating multiple variations of a single assignment.

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 🙌 Acknowledgments

- Google Generative AI team for the Gemini API.
- The "Nano-Banana" concept inspiration.