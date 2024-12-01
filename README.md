# Multi-Threaded Proxy Server with and without Cache

This project implements a multi-threaded proxy server in C, inspired by [this Proxy Server project](https://github.com/vaibhavnaagar/proxy-server).

---

## Index

- [Project Overview](#project-overview)  
- [How to Run](#how-to-run)  
- [Demo](#demo)  
- [Contributing](#contributing)  

---

## Project Overview

### Introduction

This project demonstrates how a proxy server handles client requests using multi-threading and caching to enhance performance. 

### Basic Working Flow:  
![Proxy Server Flow](https://github.com/Lovepreet-Singh-LPSK/MultiThreadedProxyServerClient/blob/main/pics/UML.JPG)

### Multi-threading Implementation:
- **Semaphore** is used instead of `pthread_join()` and condition variables for thread synchronization.  
- `sem_wait()` and `sem_post()` don’t require thread IDs, making them simpler and more efficient.  

### Why This Project?  
To understand:  
- How client requests are processed by servers.  
- Handling multiple client requests simultaneously.  
- Concurrency control using locks and semaphores.  
- Caching mechanisms and their impact on performance.  

### Proxy Server Benefits:
- **Performance Boost**: Reduces server load and speeds up requests.  
- **Access Control**: Restricts specific websites.  
- **Anonymity**: Masks client IP addresses.  
- **Security**: Encrypts requests to prevent unauthorized access.

### OS Components Used:
- **Threading**  
- **Locks**  
- **Semaphores**  
- **Caching** (LRU algorithm)  

### Limitations:
- **Multiple Client Responses**: Each client’s response is cached separately, leading to incomplete website loading.  
- **Fixed Cache Size**: Large websites may not fit in the cache.  

### Future Enhancements:
- **Multiprocessing**: Boost performance through parallelism.  
- **Content Filtering**: Control access to specific websites.  
- **POST Requests**: Extend support for different HTTP methods.

---

## How to Run

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd MultiThreadedProxyServerClient
   ```
2. **Build the project:**
   ```bash
   make all
   ```
3. **Run the proxy server:**
   ```bash
   ./proxy <port-number>
   ```
4. **Test it by opening:**  
   `http://localhost:<port>/https://www.cs.princeton.edu/`  

### Notes:
- **Linux Only**: The proxy runs on Linux.  
- **Browser Cache**: Disable browser caching for accurate testing.  
- **Without Cache**: To disable caching, rename the Makefile entry from `proxy_server_with_cache.c` to `proxy_server_without_cache.c`.

---

## Demo

- **First Access**: If a website is opened for the first time, the cache will miss (`url not found`).  
- **Subsequent Access**: The cache retrieves the data, and `Data is retrieved from the cache` is displayed.  

---

## Contributing

Contributions are welcome! Feel free to submit pull requests.

---

Enjoy coding! 🎉 
