# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## Lubindher S - 212222240056
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2025-10-04 132206" src="https://github.com/user-attachments/assets/1ad07341-fe18-4444-ae21-1d0828be5da9" />
<img width="1920" height="1080" alt="Screenshot 2025-10-04 132247" src="https://github.com/user-attachments/assets/233b9732-53f6-4407-afe1-36c2b597e325" />
<img width="1920" height="1080" alt="Screenshot 2025-10-04 134456" src="https://github.com/user-attachments/assets/d7dfbc60-32e2-4a03-b234-a08fb7d9d9dd" />
<img width="1920" height="1080" alt="Screenshot 2025-10-04 134542" src="https://github.com/user-attachments/assets/a8b2fad7-87b9-46bb-95d0-74cfb55a4147" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 134622" src="https://github.com/user-attachments/assets/5de1826b-5332-4736-ac5e-69a8e86bb5e5" />
Captured Web Activity and Email Header Information

## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

