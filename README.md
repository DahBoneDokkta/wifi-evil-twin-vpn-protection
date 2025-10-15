# Wi-Fi Evil Twin & VPN Protection

### 🧠 Overview
This project was part of my final thesis in the **.NET Developer 23–25** program.  
The goal was to explore **security risks in open Wi-Fi networks**, focusing on *Evil Twin* and *Deauthentication* attacks, and to test how **VPN encryption** can protect user data against Man-in-the-Middle exploits.

We built a custom lab using an **OpenWRT-based GL.iNet Mango router** and a **Wi-Fi Pineapple clone** from GitHub to simulate attacks in a controlled environment.

---

### ⚙️ Methodology
All tests were conducted on our own networks and devices in a controlled lab setup.  
The process followed a qualitative, hands-on approach:

1. Configure the GL.iNet Mango (OpenWRT) router with Pineapple clone firmware.  
2. Create a fake open SSID (“SecurityTest”) to simulate an Evil Twin network.  
3. Connect a test client (iPhone) to the fake AP and capture traffic with **tcpdump** and **Wireshark**.  
4. Repeat the same test while connected through **WireGuard VPN**.  
5. Compare packet captures with and without VPN active.

---

### 🧰 Tools & Equipment
| Category | Tools / Hardware |
|-----------|------------------|
| Router | GL.iNet Mango (OpenWRT) |
| Wi-Fi Adapters | External USB adapters supporting monitor mode & packet injection |
| Software | Pineapple clone (GitHub), Wireshark, tcpdump |
| Client | iPhone (iOS 18) |
| VPN | WireGuard (Integrity VPN) |
| OS | Linux |

#### 💡 Hardware Notes
The Wi-Fi adapters used in this project were chosen specifically for their support of **monitor mode** and **packet injection** - two critical features required to capture and inject wireless frames during testing.  
This capability allowed the Mango router (running the Pineapple clone) to broadcast fake SSIDs and capture client traffic at the packet level.  

In practice, many consumer adapters lack this functionality, so compatible USB adapters were sourced online after verifying chipset support (e.g., Realtek-based models).  
This step was essential to replicate real-world Evil Twin behavior accurately and to validate VPN protection in a realistic wireless environment.

---

### 📊 Key Findings
- **Evil Twin and Deauthentication attacks are easy to perform** with inexpensive, open-source tools.  
- **Unencrypted traffic (HTTP)** revealed login credentials and session data in plaintext.  
- **VPN encryption (WireGuard)** completely blocked data visibility in Wireshark.  
- **Wi-Fi management frames are unprotected by design**, making networks inherently vulnerable without WPA3 or PMF (802.11w).  
- VPN is the **most effective and accessible defense** for everyday users.

---

### 🔐 Ethical Considerations
All experiments were carried out **only on our own networks and devices**.  
The purpose was educational - to raise awareness about public Wi-Fi vulnerabilities and promote safer usage, not to perform unauthorized attacks.

---

### 🧩 Conclusion
Wi-Fi remains convenient but inherently insecure due to unencrypted management frames and user trust in open networks.  
Even simple setups can expose sensitive data - but **VPNs provide a strong, practical layer of protection** that’s easy for anyone to use.

---

### 📄 Full Report (Swedish)
The full thesis (in Swedish) includes theoretical background, methodology, results, and recommendations.

📘 [Download full report (PDF)](./Examensarbete_Simon_Arnar_Jessie_Mårtensson.pdf)

---

### 📚 References
- OpenWRT Project – https://openwrt.org  
- GL.iNet Mango – https://www.gl-inet.com/products/gl-mt300n-v2/  
- Wireshark – https://www.wireshark.org/  
- WireGuard – https://www.wireguard.com/  
- Hak5 Wi-Fi Pineapple community

---

### 👥 Authors
**Simon Arnar & Jessie Mårtensson**  
.NET Developer Students (2023–2025)  
🔗 [Portfolio](https://simonarnardev.netlify.app/)  
🔗 [LinkedIn](https://www.linkedin.com/in/simon-arnar/)
