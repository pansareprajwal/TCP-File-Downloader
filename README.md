# TCP Network File Downloader (Client)

## 📌 Overview
The **TCP Network File Downloader** is a C-based client application that utilizes low-level socket programming to connect to a remote server and download files over a TCP/IP network. It demonstrates core networking principles, reliable data transmission, and system-level file handling.

## 🚀 Core Features & Concepts Used
* **Socket Programming:** Implements the `sys/socket.h` and `netinet/in.h` libraries to establish a reliable, connection-oriented TCP stream.
* **Network Protocol Operations:** Handles IP address conversion (using `inet_pton`), port binding, and server connection handshakes.
* **Chunked Data Transfer:** Reads incoming network data in controlled 1024-byte chunks to prevent memory overflow and ensure safe file writing.
* **Custom Application Protocol:** Communicates with the server using a custom text-based header (e.g., `OK [FileSize]`) to verify file availability before downloading.
* **System-Level File I/O:** Uses low-level UNIX file descriptors (`open`, `read`, `write`, `close`) for optimized file creation and data storage.

## 🧠 System Architecture (How it Works)
1. **Socket Creation:** Initializes a TCP socket (`SOCK_STREAM`) using IPv4 (`AF_INET`).
2. **Server Connection:** Connects to the server using the provided IP address and Port number.
3. **File Request:** Sends the desired target filename to the server over the network.
4. **Header Parsing:** Reads the server's response header line-by-line to extract the incoming file's exact size.
5. **Stream & Save:** Opens a new local file and continuously reads byte chunks from the socket into a buffer, writing them to the disk until the exact file size is reached.

## 💻 How to Compile and Run

### Prerequisites
* A Linux/Unix environment or WSL (Windows Subsystem for Linux)
* GCC Compiler installed

### Compilation
1. Clone the repository to your local machine.
2. Open your terminal in the project directory.
3. Compile the C code:
   ```bash
   gcc client.c -o client

### Execution
The program requires exactly 4 command-line arguments to run:
./client 127.0.0.1 9000 ServerData.txt DownloadedData.txt

### 👨‍💻 Author
Prajwal Sanjay Pansare

GitHub: [@pansareprajwal](https://github.com/pansareprajwal)

LinkedIn: [Prajwal Pansare](https://www.linkedin.com/in/prajwalpansare/)
