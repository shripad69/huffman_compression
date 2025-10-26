# Huffman Coding Compression & Decompression in C++

## 🚀 Overview

This project implements the Huffman Coding algorithm in C++ for file compression and decompression.  
Huffman Coding is a popular lossless method that assigns variable-length binary codes based on character frequency, minimizing file sizes.

---

## 📁 File Structure

| File/Folder    | Purpose                                        |
|----------------|------------------------------------------------|
| `huffman.hpp`  | Huffman tree and compressor class definitions  |
| `huffman.cpp`  | Huffman class member functions implementation  |
| `encode.cpp`   | Main program for compression (encoding)        |
| `decode.cpp`   | Main program for decompression (decoding)      |
| `output.txt`   | (Example) Output file from runs                |

---

## 🔧 Requirements

- C++17 compiler (g++)
- Works on Linux, Windows, Mac

---

## 🛠️ Compilation

**Only compile one main file at a time (each has its own `main()`).**

### For Compression
g++ -std=c++17 encode.cpp huffman.cpp -o huffman_encode


### For Decompression
g++ -std=c++17 decode.cpp huffman.cpp -o huffman_decode

---

## 📝 Usage Examples

### Compress a File
./huffman_encode input.txt output.huff

- `input.txt`: file to compress
- `output.huff`: compressed output

### Decompress a File
./huffman_decode output.huff recovered.txt

- `output.huff`: compressed (encoded) file
- `recovered.txt`: decoded/restored file

---

## 🧩 How It Works

1. **Frequency Table:** Reads the file, counts ASCII 0–127 occurrences.
2. **Heap/Min-Tree:** Builds a min-heap for fast huffman tree construction.
3. **Huffman Tree:** Combines least-frequent nodes into a binary tree.
4. **Code Generation:** Assigns binary codes (left=`0`, right=`1`) to each character.
5. **Encoding:** Converts input to bit strings and writes as bytes with meta-data/header.
6. **Decoding:** Reconstructs tree from header, traverses codes to restore the original data.

---

## 📦 Encoded File Format

- **1st Byte:** Number of unique characters in tree.
- **Next N bytes:** Each node's char + code (with separator and padding).
- **Main segment:** Encoded data in bytes.
- **Last Byte:** Padding meta (number of bits padded).

---


## 🏆 References

- GeeksforGeeks: Huffman Coding in C++
- Programiz: Huffman Coding Algorithm
- W3Schools DSA: Huffman Coding


