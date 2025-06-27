# MULTITHREADED-FILE-COMPRESSION-TOOL

This C++ program implements a basic but functional version of Run-Length Encoding (RLE), a simple lossless data compression algorithm. The program allows users to either compress or decompress text files using RLE. It reads the contents of an input file, processes the data according to the selected operation, and then writes the result to an output file. The program is designed to work with text-based files and demonstrates fundamental file handling, string manipulation, and character processing in C++.

Purpose and Functionality
Run-Length Encoding works by reducing the size of repeating character sequences. For example, the string "AAAAABBBCC" would be encoded as "A5B3C2" using RLE. This method is efficient for data that contains many consecutive repeated characters, such as simple images, basic text files, or binary patterns with high redundancy.

The program supports two primary operations:

Compression: It scans through the input data and compresses it using RLE by replacing consecutive repeated characters with a single instance of the character followed by the number of repetitions.

Decompression: It reverses the process by reading the compressed format and expanding it back to the original sequence based on the character and count.

How the Program Works
The program starts by prompting the user to choose between two options:

1 for compression

2 for decompression

It then requests the names of the input and output files. The input file is read entirely into a string. Depending on the user’s choice, the program either compresses or decompresses the string using RLE and writes the result to the specified output file.

Compression Logic
The compression function iterates through the string, counting the number of consecutive characters. When it encounters a new character or reaches the end of the string, it appends the previous character and its count to the result string. For example, "AAAB" becomes "A3B1".

Decompression Logic
The decompression function reads characters and then collects the digits that follow, interpreting them as the count of times the character should be repeated. For instance, "A3B1" is expanded back to "AAAB". It uses a loop to extract numbers following each character and repeats the character based on the parsed count.

Error Handling and Limitations
The program includes basic error checking to ensure that input and output files can be opened. If the files cannot be accessed, an appropriate error message is displayed and the program exits gracefully.

However, the implementation does assume that the input format is well-formed. For decompression, it expects every character to be followed by one or more digits. If the input is corrupted or doesn't follow this structure, it may result in undefined behavior or runtime errors. Enhancing the error handling for malformed input could make the program more robust.

Another limitation is that the program works well only with text files and is not optimized for binary data. Additionally, the RLE algorithm itself is only effective when the input data contains many repeating characters. For more complex or already compressed data (like PDFs or JPEGs), RLE may not offer any benefit and could even increase the file size.

Conclusion
This C++ program is a simple yet practical demonstration of Run-Length Encoding, showcasing how a basic compression algorithm can be implemented using fundamental programming concepts such as loops, conditionals, strings, and file I/O. It serves as a great educational tool for understanding the principles of data compression, and it can be extended to include more advanced features, such as binary file support, error handling improvements, or integration into larger systems that require simple compression techniques
