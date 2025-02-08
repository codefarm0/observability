### **Summary: Installing Redis on Windows Using MSI**  

#### **Step 1: Download & Install Redis**  
- Download the **Redis MSI installer** from [tporadowski/redis](https://github.com/tporadowski/redis/releases).  
- Run the MSI installer and follow the installation steps.  
- By default, Redis installs to:  
  ```
  C:\Program Files\Redis
  ```
- Optionally, select **"Install Redis as a Windows service"** to run it automatically.

---

#### **Step 2: Start Redis Server**  
- Open **Command Prompt** as Administrator.  
- Navigate to the Redis installation directory:  
  ```sh
  cd "C:\Program Files\Redis"
  ```
- Start Redis manually:  
  ```sh
  redis-server.exe redis.windows.conf
  ```
- If installed as a service, check status:  
  ```sh
  sc query Redis
  ```

---

#### **Step 3: Open Redis CLI**  
- Open a **new Command Prompt window**.  
- Navigate to the Redis folder:  
  ```sh
  cd "C:\Program Files\Redis"
  ```
- Start Redis CLI:  
  ```sh
  redis-cli.exe
  ```

---

#### **Step 4: Basic Redis Commands**  

| Command | Description |
|---------|------------|
| `ping` | Check if Redis is running (returns **PONG**) |
| `set key value` | Store a value in Redis |
| `get key` | Retrieve a value from Redis |
| `del key` | Delete a key |
| `keys *` | List all keys |
| `flushall` | Delete all data from Redis |

---

✅ **Redis is now installed and running on your Windows machine!** 🎉  
Let me know if you need help with advanced Redis features like persistence, security, or clustering! 🚀
