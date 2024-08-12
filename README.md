How to Run the Streamlit Apps
Install Streamlit: If you haven't already installed Streamlit, you can do so with the following command:

pip install streamlit

Run the Receiver Program:
streamlit run Receiver.py

Run the Sender Program:
streamlit run Sender.py

Project Overview: Data Compression for Backbone Network
Objective
The goal of this project is to demonstrate data compression and decompression for file transfer over a network, with the added functionality of showing the intermediate steps of the process. This is achieved using a web-based interface built with Streamlit, making the application accessible and easy to use.

Key Components
Data Compression Techniques

Zlib Compression: We use the zlib library, which provides a straightforward interface for data compression and decompression using the DEFLATE algorithm. It’s efficient and suitable for compressing and decompressing data streams.
File Compression: Files are read, compressed, and then sent over the network. On the receiver’s end, the compressed data is received, decompressed, and saved.
Tools and Technologies

Programming Languages: Python is used for writing the sender and receiver programs.
Libraries:
Zlib: For compressing and decompressing data.
Socket: For network communication between the sender and receiver.
Streamlit: For creating a web-based interface for user interaction.
File Handling: The application handles various file types by saving intermediate compressed and decompressed files in specific folders.
Program Structure

Sender Program:
Compresses the selected file.
Saves the compressed file to the "compressing" folder.
Sends the compressed data over a network socket to the receiver.
Receiver Program:
Receives the compressed data over a network socket.
Decompresses the received data.
Saves the decompressed data to the "decompressing" folder.
Stores the final file in the "received_data" folder.
Process Overview

Sender Side:
User selects a file to send via the Streamlit interface.
The file is compressed using zlib.
The compressed data is saved to a file in the "compressing" folder.
The sender transmits the compressed file data over the network to the receiver.
Receiver Side:
The receiver listens for incoming data over the network.
When data is received, it is decompressed using zlib.
The decompressed data is saved in the "decompressing" folder for inspection.
The final file is stored in the "received_data" folder in its original format.
User Interface

Streamlit is used to create the web-based interfaces for both sending and receiving files. The interface includes:
File upload or selection for sending.
A button to start sending or receiving files.
Status messages to inform users of the progress and completion of tasks.
Limits of Sharing

File Size: The provided implementation uses a buffer size of 1 MB for receiving data. For very large files, adjustments may be needed to handle data in chunks and ensure efficient memory usage.
File Types: The application handles various file types but assumes that the file formats are compatible with the compression and decompression process. Certain binary files might not display correctly in the .txt format, but this is handled appropriately by saving the files in their original formats.
Network Stability: The project assumes a stable network connection. For unreliable connections, additional error handling and retry mechanisms may be needed.
Summary
The project demonstrates how to implement a file transfer system with compression and decompression using Python. It integrates Streamlit for an easy-to-use web interface, making the compression and decompression process transparent to the user. The system supports a variety of file types and includes mechanisms to store intermediate steps for debugging and verification.

By using zlib for compression, socket programming for network communication, and Streamlit for the user interface, the project provides a comprehensive solution for efficient and user-friendly file transfer with built-in data processing.
