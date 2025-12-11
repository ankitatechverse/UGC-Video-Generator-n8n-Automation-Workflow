# ⭐ **UGC Video Generator — n8n Automation Workflow**

Automatically turn a single Telegram product photo into a **8-second vertical UGC video** using
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
3. After processing, the bot sends back a **finished 8-second UGC video (MP4)**.

Done. Automated. ✨

---

## 🧩 **Node-by-Node Breakdown (Simple & Clear)**

> ### **1) Telegram Trigger**
>
> Starts the workflow when a user sends a message or photo to your Telegram bot.

---

> ### **2) Set – Bot & Chat IDs**
>
> Stores the bot token and the user’s chat ID so later steps can reply correctly.

---

> ### **3) Get File Path from Telegram**
>
> Uses the image’s `file_id` to retrieve the actual `file_path` from Telegram.

---

> ### **4) Build Image URL**
>
> Converts the Telegram `file_path` into a public image URL for AI processing.

---

> ### **5) Analyze Image with Vision (OpenAI)**
>
> Extracts product details such as name, category, features, and design information.

---

> ### **6) Format Analysis**
>
> Cleans the data returned by Vision and structures it properly for the script generator.

---

> ### **7) Notify User — Video Progress Started**
>
> Sends a message letting the user know that video creation has started.

---

> ### **8) AI Agent — Build UGC Video Prompt**
>
> Generates a one-line UGC video script using the product data and user caption.

---

> ### **9) Create Video (KIE AI)**
>
> Sends the script and reference image to KIE AI to generate the UGC video and returns a task ID.

---

> ### **10) Wait**
>
> Pauses briefly before checking whether the video has been generated.

---

> ### **11) Get Video Status (record-info)**
>
> Checks KIE AI to see whether the video is finished and ready to be sent.

---

> ### **12) If — successFlag Check**
>
> Determines whether the video is ready. If not ready, waits and checks again.

---

> ### **13) Send Video — Telegram**
>
> Sends the completed UGC video back to the same chat where the user uploaded the image.

---

> ### **14) NoOp — End**
>
> Ends the workflow.

---

## 🏁 **Summary**

This workflow:
📸 Takes a product image →
🧠 Understands it with Vision →
✍️ Generates a UGC script →
🎥 Creates a video via KIE AI →
📨 Sends it back in Telegram

Fully automated. Perfect for brands, creators, agencies & e-commerce.
