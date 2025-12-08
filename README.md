# ⭐ **UGC Video Generator — n8n Automation Workflow**

Automatically turn a single Telegram product photo into a **30-second vertical UGC video** using
**OpenAI Vision**, **AI Script Generation**, and **KIE AI Video Generation** — all sent back to the user inside Telegram.
No editing. No manual steps. Fully automated. 🚀

---

## 🔧 **Requirements**

* 🤖 Telegram Bot Token
* 🔍 OpenAI API Key → add under **OpenAI / LangChain OpenAI** credentials
* 🎥 KIE AI API Key → add under **HTTP Header Auth** as:
  `Authorization: Bearer <your_key>`
* 🧩 n8n instance (self-hosted or cloud)

---

## 🎯 **Final User Experience**

1. User sends a **product image + caption** to your Telegram bot.
2. Bot instantly replies: *“Creating your UGC video…”*
3. After processing, the bot sends back a **finished 30-second UGC video (MP4)**.

Done. Automated. ✨

---

## 🧩 **Node-by-Node Breakdown (Simple & Clear)**

### **1️⃣ Telegram Trigger**

Starts the workflow the moment a user sends an image or message.

### **2️⃣ Set – Bot & Chat IDs**

Stores the bot token and user chat ID so Telegram replies go to the correct person.

### **3️⃣ Get File Path from Telegram**

Uses Telegram’s API to convert `file_id` into the actual `file_path`.

### **4️⃣ Build Image URL**

Turns the Telegram `file_path` into a public image URL for analysis.

### **5️⃣ Analyze Image with Vision (OpenAI)**

Extracts structured product information (name, category, features, design details, etc.).

### **6️⃣ Format Analysis**

Cleans the extracted data and prepares it for the script generator.

### **7️⃣ Notify User — Video Progress Started**

Notifies the user that video creation has begun. 📩

### **8️⃣ AI Agent — Build UGC Video Prompt**

Creates a **one-line**, clean UGC script based on product details + caption.

### **9️⃣ Create Video (KIE AI)**

Sends the script + image to KIE AI, which begins generating the video.

### **🔟 Wait**

Pauses before checking the video generation status.

### **1️⃣1️⃣ Get Video Status (record-info)**

Checks if KIE AI has finished producing the video.

### **1️⃣2️⃣ If — successFlag Check**

If the video is ready → proceed
If not → wait and check again 🔄

### **1️⃣3️⃣ Send Video — Telegram**

Sends the finished UGC video straight back to the user. 🎬

### **1️⃣4️⃣ NoOp — End**

Marks the end of the workflow.

---

## 🏁 **Summary**

This workflow:
📸 Takes a product image →
🧠 Understands it with Vision →
✍️ Generates a UGC script →
🎥 Creates a video via KIE AI →
📨 Sends it back in Telegram

Fully automated. Perfect for brands, creators, agencies & e-commerce.
