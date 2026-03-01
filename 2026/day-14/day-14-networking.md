# Day 14 – Networking Fundamentals & Hands-on Checks

## OSI vs TCP/IP

### OSI Model (7 Layers)
- L1 Physical – Hardware and signals.
- L2 Data Link – MAC addresses and switching.
- L3 Network – IP addressing and routing.
- L4 Transport – TCP/UDP communication.
- L5–7 Session/Presentation/Application – Application protocols like HTTP, DNS.

### TCP/IP Model
- Link – Physical + Data Link.
- Internet – IP routing.
- Transport – TCP/UDP.
- Application – HTTP, HTTPS, DNS, SSH.

Example:
curl https://google.com  
= HTTP (Application) over TCP (Transport) over IP (Network)

---

## Hands-on Checks

### Identity
Command:
hostname -I
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/5c85c41d-14c9-4b3f-ab04-69623b737e02" />

---

### Reachability
ping -c 4 google.com
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/341a5342-cece-4f9c-aa30-95cad2b47d5a" />

---

### Path
traceroute google.com
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/479aa0ae-3633-459a-b06f-d04d8fc08eee" />

---

### Ports
ss -tulpn
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/1f2e0df5-9fcf-4e55-a193-51bb17d27b16" />

---

### Name Resolution
dig google.com +short
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/e7c31bdd-2832-4b17-b512-dcd2b2f17abe" />

---

### HTTP Check
curl -I https://google.com
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/18f33403-643a-41cd-a6ef-513672bd627b" />

---

### Connections Snapshot
netstat -an | head
<img width="1109" height="235" alt="image" src="https://github.com/user-attachments/assets/c877fda4-c21e-437b-abe9-2c2b74208b3d" />

---

## Mini Task – Port Probe

Command:
ss -tulpn
<img width="1416" height="239" alt="image" src="https://github.com/user-attachments/assets/231e6fac-4e00-45e4-ac91-41a607b752f6" />

nc -zv localhost 22
<img width="746" height="50" alt="image" src="https://github.com/user-attachments/assets/045b07d0-ca2e-4669-a686-9298ed06bd03" />

Result:
Port 22 reachable locally. SSH service active.

Next check if failed:
systemctl status ssh 
<img width="1461" height="352" alt="image" src="https://github.com/user-attachments/assets/d7b658ce-588b-45d4-bf87-d6c14a35e424" />

---

## Reflection

1. Fastest signal when broken:
Ping or curl gives quick connectivity feedback.

2. If DNS fails:
Inspect Application layer first, then check resolver config and Internet layer.

3. If HTTP 500 shows:
Application layer issue. Next check service logs and backend.

4. Two follow-up checks:
- Check firewall rules (ufw or iptables).
- Inspect service logs using journalctl.
