---

```markdown
# 🗒️ AI Sticky Notes (MCP App)

**AI Sticky Notes** is a simple tool built with [MCP (Multi-Modal Command Protocol)](https://github.com/openai/mcp) that allows users to save, read, and summarize sticky notes through tool and resource calls. This server provides endpoints for interacting with a file-based notes system using an AI interface.

---

## 🚀 Features

- ✅ Add sticky notes
- 📖 Read all saved notes
- 📌 Get the most recent note
- 🧠 Generate a summary prompt for current notes

---

## 🧰 Tech Stack

- **Python**
- **[FastMCP](https://github.com/openai/mcp)** — a fast way to expose tools/resources to AI models
- Local file-based storage (`notes.txt`)

---

## 📂 File Structure

```

.
├── server.py       # MCP server exposing tools and resources
├── notes.txt       # File where all sticky notes are stored (auto-created)

````

---

## 🔧 How It Works

### Tools

#### `add_note(message: str) -> str`
Appends a note to `notes.txt`.

```python
add_note("Remember to review the PR before 6 PM.")
# Returns: "Note saved!"
````

---

#### `read_notes() -> str`

Reads all notes and returns them as a string.

```python
read_notes()
# Returns all saved notes or "No notes yet!" if empty.
```

---

### Resources

#### `get_latest_note() -> str`

Fetches the most recently added note.

```python
get_latest_note()
# Returns last line from notes.txt or "No notes yet!"
```

---

### Prompt Generator

#### `note_summary_prompt() -> str`

Generates a prompt asking the AI to summarize all notes.

```python
note_summary_prompt()
# Returns something like:
# "Summarize the current notes: Note1. Note2. ..."
```

---

## 🛠️ Setup Instructions

1. **Clone this repository**

   ```bash
   git clone https://github.com/yourusername/ai-sticky-notes.git
   cd ai-sticky-notes
   ```

2. **Install dependencies**
   *(Assumes you already have MCP installed — if not, install it from its GitHub repo.)*

3. **Run the server**

   ```bash
   python server.py
   ```

---

## 📓 Notes

* The `notes.txt` file will be automatically created in the same directory if it doesn't exist.
* This app assumes the MCP agent or client will call these tools/resources accordingly.

---

## 🧠 Use Case

Perfect for:

* AI assistants remembering important user reminders
* Lightweight local memory interface for chatbots
* Prototyping AI-to-file interaction workflows

---

## 📜 License

MIT License

---
