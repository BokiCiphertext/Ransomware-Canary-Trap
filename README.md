# Ransomware Canary Trap & File Integrity Monitor (FIM)

### **The concept **
In the old days miners took a **Canary Bird** into mines. If there was dangerous gas, the bird would be affected first, warning the miners to run. 

This project does the same for your computer. I created a "Bait" file “The Canary”. If ransomware tries to encrypt or delete this file, my script catches it instantly and screams **Alert** before the rest of your data is touched.

### **How it works **
1. **The bait:** I created a folder called "Canary_Folder" with a fake file inside called “Passwords.txt”.
2. **The guard:** I used the Python **Watchdog** library to monitor this folder 24/7.
3. **Event detection:** The script uses "Event-Driven" logic. It doesn't waste CPU power; it only wakes up when the Operating System detects a file change.
4. **The alert:** If any program like Ransomware touches the bait, the script triggers a high-priority alert.

### **Tech stack**
* **Language:** Python 3.
* **Library:** Watchdog.
* **Operating System:** Kali Linux.

### **Usage**
1. Clone the repo.
2. Run the monitor: “python3 canary_trap.py”
3. Try to change the file in another terminal: “echo "hack" >> Canary_Folder/Passwords.txt”
4. Watch the alert trigger.
