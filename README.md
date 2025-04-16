# Automated Meeting Task Extraction and Airtable Mapping

<div>
    <a href="https://www.loom.com/share/81b7595c9f394b5891c17339f3800f45">
      <p>Task management automation - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/81b7595c9f394b5891c17339f3800f45">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/81b7595c9f394b5891c17339f3800f45-65d4d228d379dcf5-full-play.gif">
    </a>
  </div>

## Overview
This project automates the extraction of actionable tasks from meeting transcript PDFs. When a PDF is uploaded to a designated Google Drive folder, a Make scenario is triggered. The workflow extracts the transcript text, passes it to an LLM (for task name, description, assignee, and deadline extraction), and automatically maps the results to an Airtable Tasks table.

## Architecture & Workflow
1. **Trigger:** PDF upload to a specific Google Drive folder.
2. **Extraction:** Use a PDF parsing module to convert the meeting transcript to text.
3. **LLM Processing:** Send the text to an LLM endpoint that extracts:
   - Task Name
   - Task Description
   - Assignee
   - Deadline
4. **Mapping:** Insert the extracted data into an Airtable Tasks table.

## 🚀 Setup & Deployment

1. **Clone Repo**
   ```bash
   git clone https://github.com/mennatuallah-hefny/Meeting-Transcript-Task-Extraction.git
   cd Meeting-Transcript-Task-Extraction
   ```

2. **Import Make.com Scenario**
   - In Make.com: **Scenarios → Create a new scenario → Import** → upload `Meeting transcripts to Airtable tasks.json`

3. **Configure Connections**
   - Google Drive → [Connect Google Drive to Make](https://apps.make.com/google-drive)
   - PDF.co → [Connect PDF.co to Make](https://apps.make.com/pdfco)
   - OpenRouter → [OpenRouter API key](https://openrouter.ai/settings/keys)
   - Google Sheets OAuth → [Connect Airtable to Make](https://apps.make.com/airtable)
    
4. **Deploy**
   - Turn scenario **ON**

## Configuration Details
- **Google Drive:**  
  Link a specific folder for PDF uploads.
- **Airtable Table:**  
  Configure a table named `Tasks` with columns:
  - Task Name (Text)
  - Description (Long Text)
  - Assignee (Text)
  - Deadline (Date)

## Usage
1. Upload a PDF to the designated Google Drive folder.
2. The Make scenario automatically triggers:
   - PDF text extraction,
   - Task extraction via LLM,
   - Data mapping to Airtable.
3. Verify tasks in your Airtable dashboard.



