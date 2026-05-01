# Presentation Script: Web Page Text Compressor

## 1. The Core Problem
"Most web pages are filled with repeating HTML tags like `<div>`. Standard character encoding is wasteful because it treats every `<` and `>` as a new piece of info. We are targeting this 'Structural Redundancy'."

## 2. Our Solution: LZW
"We implemented the Lempel-Ziv-Welch (LZW) algorithm. It works by building a dictionary 'on the fly'. Instead of sending the string `</div>` (6 bytes) every time, we eventually send a single 12-bit index. This is the foundation of standards like GZIP."

## 3. Why did the size increase for small text?
"In our demo, you might notice that very small HTML snippets get LARGER. This is NOT a bug; it is a fundamental property of compression. Because our indices are 12 bits (1.5 bytes), we have a 50% overhead on single characters. Compression only 'breaks even' and starts saving space once the dictionary learns enough patterns (usually after the first ~500-1000 characters)."

## 4. The Entropy Metric
"The Shannon Entropy (H) shown in the sidebar is our 'Speed Limit.' It tells us the absolute minimum bits needed per character based on the frequency of the data. Our goal as engineers is to get our Average Bit Length (L) as close to H as possible."

## 5. Summary of the JavaScript Logic
- `calculateEntropy()`: Implements the Shannon formula using a frequency map.
- `lzwEncode()`: Implements a greedy dictionary builder. It pre-populates with the first 256 ASCII characters and then adds new patterns as it encounters them.
