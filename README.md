# ELEVATE-TASK-5

# Network Traffic Analysis with Wireshark

This README documents the steps taken to analyze network traffic using Wireshark, with tests conducted on the target: [http://testphp.vulnweb.com](http://testphp.vulnweb.com).

## Objective

To capture, filter, and analyze network traffic in order to identify protocols, packet details, and overall behavior using Wireshark.

## Steps Performed

1. **Install Wireshark**  
   Wireshark was installed from the official website: https://www.wireshark.org/

2. **Start Capturing on Active Network Interface**  
   Wireshark was launched and packet capture was started on the active interface (Wi-Fi).

3. **Generate Network Traffic**  
   The website [http://testphp.vulnweb.com](http://testphp.vulnweb.com) was accessed using a web browser to generate traffic.

4. **Stop the Capture After a Minute**  
   After approximately one minute of interaction with the site, the packet capture was stopped.

5. **Filter Captured Packets by Protocol**  
   Filters were applied to isolate specific protocols:
   - `http`
   - `dns`
   - `tcp`

6. **Identify at Least 3 Different Protocols**  
   The following protocols were identified during analysis:
   - **DNS** – Domain name resolution for `testphp.vulnweb.com`
   - **HTTP** – Web traffic to and from the test site
   - **TCP** – Underlying transport protocol used for HTTP communication

7. **Export the Capture as a .pcap File**  
   The captured data was exported and saved as `vulnweb_capture.pcap`.

8. **Summary of Findings**

   - **Observed Protocols:**  
     - DNS  
     - HTTP  
     - TCP

   - **DNS Queries:**  
     - Query and response for `testphp.vulnweb.com`, resolved to a public IP.

   - **HTTP Traffic:**  
     - HTTP GET requests to retrieve resources from the web server.  
     - Response status codes such as `200 OK`.

   - **TCP Details:**  
     - Standard TCP 3-way handshake observed.  
     - Port 80 used for HTTP communication.  
     - Source and destination IPs corresponded to local and remote hosts.

   - **Other Notes:**  
     - User-Agent string and Host headers were visible in HTTP requests.  
     - Multiple packets showed content exchange including HTML and image data.

## File

- `vulnweb_capture.pcap` – Wireshark capture file of the session with `http://testphp.vulnweb.com`.

## Disclaimer

This test was conducted on a publicly available, intentionally vulnerable web application designed for security testing and research. All traffic analysis was done within the bounds of ethical use.


