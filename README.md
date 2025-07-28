# ⚡️ Automate Task Tracking from Emails to Notion using Zapier + AI

> Effortlessly turn emails into actionable tasks — structured, assigned, and tracked in Notion — all without a single line of code.

---

## 📖 Project Story

In fast-moving teams, tasks often get buried in emails. Important action points are missed. Follow-ups are delayed. Collaboration breaks.

We asked: _What if your email could automatically feed your project tracker?_

This project automates task extraction from Outlook emails, processes them using **AI by Zapier**, and updates a **Notion database** — seamlessly, instantly, and without manual copy-paste.

---

## 🎯 What This Project Does

- ✅ Extracts task details from any structured email  
- ✅ Identifies task owners and deadlines using AI  
- ✅ Breaks them into individual tasks using Formatter + Looping  
- ✅ Optionally looks up extra info in Excel  
- ✅ Sends each task to a Notion project dashboard  

Built 100% in Zapier. No code. Scalable. Smart.

---

## 🧠 Real-World Use Case

**Imagine this:**

You send a task list via email to your team.  
📩 Email arrives in Outlook  
🧠 AI reads and extracts all tasks (who, what, when)  
🔁 Tasks loop one by one  
📊 Optional lookup in Excel  
📋 Each task auto-populates your Notion workspace  
✅ Team sees everything — instantly!

---

## 🧰 Tools Used

| Tool            | Purpose                               |
|-----------------|----------------------------------------|
| 📨 Outlook       | Source of incoming task emails         |
| 🧠 AI by Zapier  | Extract structured tasks from email    |
| 🔧 Formatter     | Parse and format CSV content           |
| 🔁 Looping       | Handle each task individually          |
| 📊 Excel (opt)   | Lookup or cross-check task data        |
| 🗃️ Notion        | Store and visualize all team tasks     |

---

## 🧭 Workflow Overview

![Workflow Image](https://github.com/SachinSavkare/Automating-Task-Tracker-Zapier-Notion-/blob/main/Zapier%20Automation%20Model.JPG)  
*End-to-end flow from email to Notion via Zapier*

---

## 🚀 Step-by-Step Setup

### 1. Trigger: New Outlook Email

- App: Microsoft Outlook  
- Trigger: "New Email Matching Search"  
- Filter: e.g., subject contains "Tasks"

This starts the automation whenever a relevant task email arrives.

---

### 2. AI by Zapier – Task Extraction

- App: AI by Zapier  
- Action: "Extract from Text Prompt"

**Prompt to Use:**

```
You will receive the full body of an email.
Extract every task and return the result only as a single CSV string.

CSV rules:
• Use a comma (,) as the delimiter.
• Wrap every field in double quotes.
• If a field has quotes, escape by doubling ("").
• First row must be: "Task description","Person assigned","Due date (DD/MM/YYYY)","Start date (DD/MM/YYYY)"
• Convert all dates to DD/MM/YYYY.
• Repeat start/due date for each row if only mentioned once.
• Output CSV string only, with no commentary or extra lines.
```

---

### 3. Formatter by Zapier – Split CSV Lines

- App: Formatter → Text → Split Text  
- Input: Output of AI step  
- Split by: `\n` (new lines)  
- Remove Header (optional): Yes

This prepares the data for looping through each task.

---

### 4. Looping by Zapier – Process Each Task

- App: Looping by Zapier  
- Input: Line items (one per task)  
- Output: Task fields (description, person, due date, start date)

You now process each task one at a time.

---

### 5. (Optional) Excel Lookup

- App: Microsoft Excel  
- Action: Find Row  
- Use for: Verifying task duplication or fetching extra columns (e.g., team or priority)

---

### 6. Create Task in Notion

- App: Notion  
- Action: Create Database Item  
- Map Fields:
  - Task → Title
  - Person assigned → Assignee
  - Due Date → Due
  - Start Date → Start

Each task is now saved as a clean, structured item in your Notion project tracker.

---

## 📥 Sample Email Used

You can view the original sample email used in this project here:  
📎 [Task Mail.docx](https://github.com/SachinSavkare/Automating-Task-Tracker-Zapier-Notion-/blob/main/Task%20Mail.docx)

---

## 🧾 Example Output from AI by Zapier

```csv
"Task description","Person assigned","Due date (DD/MM/YYYY)","Start date (DD/MM/YYYY)"
"Create 3–4 comic-style chats for Instagram","Rutvik Savkare","07/07/2025","04/07/2025"
```

---

## ✅ Key Benefits

- No more manual task entry  
- Prevents missed deadlines  
- Live sync with Notion  
- Can adapt to any structured email  
- Saves hours every week  
- Zero code. 100% automation

---

## 🧪 Want to Try It?

1. Duplicate this Zap _(template coming soon)_  
2. Copy and paste the AI prompt from above  
3. Upload your sample email in Outlook  
4. Connect your Notion database  
5. Run your workflow — you're done! 🎯

---

## 👨‍💻 Built By

**Sachin Savkare**  
_AI for Productivity | Automation Developer_  
🔗 [Connect on LinkedIn](https://www.linkedin.com/in/sachin-savkare)

---

## 📎 License

This project is licensed under the **MIT License**.
