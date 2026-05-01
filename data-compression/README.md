# ⚡ Web Page Text Compressor

A high-performance, browser-native implementation of Lempel-Ziv-Welch (LZW) and Shannon Entropy analysis, specifically designed to demonstrate structural redundancy compression in HTML documents.

## 🚀 Overview

The **Web Page Text Compressor** is a technical MVP built to showcase how dictionary-based compression algorithms (like LZW) exploit repeating patterns in web markup (tags, attributes, and boilerplate) to drastically reduce page weight.

### Key Features

- **Live Entropy Engine:** Real-time calculation of Shannon Entropy ($H$) to determine the theoretical lower bound of the source data.
- **LZW Pattern Discovery:** An adaptive dictionary builder that "learns" HTML tags (e.g., `</div>`, `class="btn"`) and replaces them with 12-bit indices.
- **Structural Insights:** Visualizes the "Dictionary Growth" as patterns are discovered in the document.
- **Zero-Dependency:** Written in pure Vanilla JavaScript (ES6+), making it portable and easy to audit.

## 🛠️ Usage

1. **Open `index.html`** in any modern web browser (Chrome, Firefox, Safari).
2. **Paste raw HTML** into the source editor.
3. **Observe the Metrics:**
   - Watch the **Entropy** value change as the data distribution shifts.
   - Monitor the **Savings Ratio** to see how much space is recovered.
   - Inspect the **Dictionary** to see which HTML tokens were successfully compressed.

## 🧬 Technical Background

### Dictionary Compression (LZW)
Unlike Huffman coding, which operates at the character level, LZW finds recurring sequences. In HTML, these sequences are usually structural tags. By mapping a 6-character tag (48 bits) to a single 12-bit index, we achieve significant savings.

### Entropy Analysis
The application calculates entropy using the standard formula:
$$H(X) = -\sum P(x_i) \log_2 P(x_i)$$
This provides a target metric to evaluate how close the compression algorithm is to the theoretical limit.

## 📜 License
MIT License - Developed for Academic & Portfolio demonstration.
