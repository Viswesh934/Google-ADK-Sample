# 📸 Smart Hashtag Generator using Google ADK

This project demonstrates a smart social media assistant built with the **Google Agent Development Kit (ADK)** and **Gemini Flash model**, capable of generating relevant hashtags based on the mood and intent of a given user phrase.

---

## 🚀 Features

* Detects **mood** (e.g., happy, sad, motivational) and **intent** (e.g., marketing, personal, informative).
* Generates relevant **hashtags** based on detected context.
* Built with:

  * `google-adk`
  * `litellm` (for multi-model support)
  * Gemini 2.0 Flash (`gemini-2.0-flash`) model
* Uses `Runner` and `Agent` pattern from ADK for structured conversation flow.
* Includes **mocked logic** for mood/intent classification and fallback tag generation.
* Interactive **async runner** simulates chat-based conversations.

---

## 🛠️ Setup Instructions

### 1. Install Dependencies

```python
!pip install google-adk -q
!pip install litellm -q
```

### 2. Set Your API Key

```python
from google.colab import userdata
os.environ["GOOGLE_API_KEY"] = userdata.get("GOOGLE_API_KEY_1")
```

Make sure to add your API key using the Colab secret manager or directly in your environment.

---

## 🧠 How It Works

### Core Components

* **`generate_smart_hashtags(phrase)`**
  Detects mood/intent and returns hashtag suggestions. Uses mock maps for demonstration.

* **`Agent`**
  Uses Gemini model and `generate_smart_hashtags` tool to simulate conversation and hashtag generation.

* **`Runner`**
  Manages the interaction lifecycle between user and agent.

* **`call_agent_async`**
  Sends queries to the agent and parses structured agent responses.

---

## 🧪 Example Usage

```python
await run_conversation()
```

Sample outputs:

```
>>> User Query: Generate hashtags for travel photography.
<<< Agent Response: Okay! Here are some hashtags for travel photography: #travel, #photography.

>>> User Query: I need some fitness motivation hashtags.
<<< Agent Response: Here are some fitness motivation hashtags: #fitness, #motivation.
```

---

## ⚠️ Notes

* This project **mocks** the NLP logic — the mood and intent mappings are hardcoded.
* Google ADK's `tools` integration is used for routing logic through a real LLM model.
* For a production-ready version, you should:

  * Replace mock mappings with actual NLP classifiers.
  * Add content moderation and sanitization.
  * Improve hashtag curation using embeddings or topic modeling.

---

## 📂 File Structure

```
.
├── GoogleADK.ipynb       
├── README.md                    
```

---

