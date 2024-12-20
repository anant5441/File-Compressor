# FileCompressor

FileCompressor is a C++ program that implements a file compression and decompression utility using the **Huffman Coding Algorithm**. It compresses text files to save storage space and decompresses them back to their original form.

## Features

- Compress any text file using the Huffman algorithm.
- Decompress the compressed file to its original format.
- Optimized memory usage with the efficient handling of trees and bit-level manipulations.

## How It Works

1. **Compression**

   - Characters and their frequencies are calculated from the input file.
   - A Huffman Tree is built based on the character frequencies.
   - Binary codes for each character are generated and used to encode the file.

2. **Decompression**

   - The header in the compressed file contains the Huffman Tree structure.
   - The tree is reconstructed to decode the binary representation back into the original file contents.

### Huffman Coding Process Diagram

Below is an example Huffman tree constructed based on character frequencies.

```
          (*, 15)
         /      \
      (*, 6)    (*, 9)
     /   \     /     \
   (A,3) (B,3) (*,4)  (C,5)
           /  \
        (D,2) (E,2)
```

Each path represents a binary code:

- A: `00`
- B: `01`
- D: `100`
- E: `101`
- C: `11`

## Demonstration

### Example Input

**Text File:** `example.txt`

```txt
BEE SEEN SEA
```

### Step 1: Compression

Command:

```bash
./file_compressor -c example.txt compressed.huff
```

**Output File:** `compressed.huff`

### Visualization of Encoding

The text is encoded into binary, and the resulting compressed file appears as follows (hex representation):

```
0A 4B 7F A2 ...
```

### Step 2: Decompression

Command:

```bash
./file_compressor -d compressed.huff decompressed.txt
```

**Output File:** `decompressed.txt`

### Final Output

```txt
BEE SEEN SEA
```

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/FileCompressor.git
cd FileCompressor
```

2. Compile the project:

```bash
g++ -o file_compressor Huffman.cpp
```

3. Run the program:

```bash
./file_compressor [options]
```

### Options

- `-c` : Compress a file.
- `-d` : Decompress a file.


## Challenges

- **Padding Bits:** Ensuring bit-level operations align with 8-bit boundaries for accurate storage.
- **Tree Reconstruction:** Efficiently rebuilding the Huffman Tree from the header for decompression.

## Future Enhancements

- Add support for other file formats (images, videos, etc.).
- Integrate with graphical user interfaces (GUI) for easier usability.

## Author

Developed by **Anant Bhardwaj**. Contributions and suggestions are welcome!

## License

This project is licensed under the MIT License.
