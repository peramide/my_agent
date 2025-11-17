# 📘 **my_agent — ADK Python Agent**

This project is built using the **Google Agent Development Kit (ADK)** for Python.
It provides a simple example of how to create, configure, and run an AI agent powered by the **Gemini 2.5 Flash model**.

---

## 🚀 **Requirements**

Before getting started, ensure you have:

* **Python 3.9 or later**
* **pip** package manager
* (Optional but recommended) A **Python virtual environment**
* A **Gemini API Key** from Google AI Studio

---

## 📦 **Installation**

Install ADK using pip:

```bash
pip install google-adk
```

(Optional) Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate   # On Windows
```

---

## 🛠️ **Create an Agent Project**

You can create a new ADK agent project with:

```bash
adk create my_agent
```

This will generate:

```
my_agent/
    agent.py
    .env
    __init__.py
```

---

## 📁 **Project Structure**

### `agent.py`

Contains the main agent logic, including:

* Model configuration
* Agent description
* Instructions
* Optional tools

### `.env`

Stores environment variables such as:

```
GOOGLE_API_KEY="YOUR_API_KEY"
```

> ⚠️ Never commit this file to GitHub.

---

## 🧩 **Example Agent Code**

Below is an example tool and agent configuration (you can place this inside `agent.py`):

```python
from google.adk.agents.llm_agent import Agent

# Example tool
def get_current_time(city: str) -> dict:
    """Returns the current time in the specified city."""
    return {"status": "success", "city": city, "time": "10:30 AM"}

root_agent = Agent(
    model='gemini-2.5-flash',
    name='root_agent',
    description="Tells the current time for any given city.",
    instruction="You are a helpful assistant. Use 'get_current_time' tool to provide the time.",
    tools=[get_current_time],
)
```

---

## 🔑 **Set Up Your API Key**

Generate your Gemini API Key from Google AI Studio.
Then add it to your `.env` file:

```bash
echo 'GOOGLE_API_KEY="YOUR_API_KEY"' > my_agent/.env
```

---

## ▶️ **Run Your Agent**

### **1. CLI Mode**

Use the command-line interface:

```bash
adk run my_agent
```

If you are using Windows and see a symlink permission error,
simply **run PowerShell as Administrator** or enable **Developer Mode**.

---

### **2. Web Interface Mode**

Start the ADK web UI:

```bash
adk web --port 8000
```

Then open in your browser:

```
http://localhost:8000
```

Select **my_agent** at the top-left and start chatting.

---

## 📚 **Next Steps**

Now that your basic agent is running, explore:

* Custom Tools
* Memory & Sessions
* Plugins
* Multi-agent patterns
* Event and callback systems



## 📝 **License**

This project follows the standard Google ADK licensing terms.

---


✅ Generate a more advanced README
✅ Add badges (Python, ADK, License, etc.)
✅ Add a full example workflow
Just tell me!
