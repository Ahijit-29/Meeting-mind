[README.md](https://github.com/user-attachments/files/30991372/README.md)
# MeetingMind

## AI Meeting Assistant with Persistent Memory

MeetingMind is a Python-based AI meeting assistant that uses Hindsight as a persistent memory layer.

It helps prepare for upcoming meetings by remembering previous interactions, retrieving relevant information, identifying follow-ups, and generating a concise meeting briefing.

The core workflow is:

**Retain → Recall → Reflect**

## Problem

Important information from meetings is often forgotten or scattered across notes.

Previous meetings may contain decisions, commitments, deadlines, follow-up tasks, unresolved issues, and important discussion points.

MeetingMind uses persistent agent memory to make this process easier.

## Solution

MeetingMind stores information from previous meetings in Hindsight.

Before an upcoming meeting, it:

1. Retrieves relevant previous interactions.
2. Identifies potential commitments and follow-ups.
3. Uses Hindsight Reflect to generate a structured meeting briefing.
4. Presents the information to the user before the meeting.

## How It Works

```text
Previous Meeting
       |
       v
    RETAIN
       |
       v
Hindsight Memory
       |
       v
    RECALL
       |
       v
Relevant Previous History
       |
       v
   REFLECT
       |
       v
AI Meeting Brief
```

## Hindsight Integration

### 1. Retain

Meeting information is stored in the Hindsight memory bank.

```python
client.retain(
    bank_id=BANK_ID,
    content=meeting
)
```

### 2. Recall

Before an upcoming meeting, MeetingMind searches for relevant previous interactions.

```python
results = client.recall(
    bank_id=BANK_ID,
    query="Prepare me for my upcoming meeting with the selected contact. Find relevant previous interactions, decisions, commitments, deadlines, follow-ups, and unresolved items."
)
```

### 3. Reflect

MeetingMind uses Hindsight Reflect to generate a concise meeting briefing.

```python
briefing = client.reflect(
    bank_id=BANK_ID,
    query="Prepare me for my upcoming meeting using only supported memories. Include previous interactions, important decisions, outstanding commitments or follow-ups, and suggested talking points. Do not invent information."
)
```

## Example

### Previous Meeting

```text
Meeting with Alex.

We agreed that Alex would send the project requirements
before Friday.

We also planned to review the database design
during the next meeting.
```

When preparing for the next meeting with Alex, MeetingMind retrieves relevant information and prepares a briefing containing previous interactions, decisions, outstanding commitments, follow-up points, and suggested talking points.

## Project Structure

```text
MeetingMind/
├── main.py
├── requirements.txt
├── .gitignore
└── README.md
```

## Technologies Used

- Python
- Hindsight
- Hindsight Python Client
- AI/LLM-based reasoning
- API integration
- Environment variables

## Requirements

- Python 3.10 or later
- Hindsight API key
- Internet connection

## Installation

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd MeetingMind
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Environment Variables

Create a `.env` file:

```text
HINDSIGHT_API_KEY=your_api_key_here
```

Do not upload `.env` or your real API key to GitHub.

## Running the Application

```bash
python main.py
```

The application will prompt you to store a previous meeting, enter the person for the upcoming meeting, retrieve relevant previous interactions, and generate an AI meeting brief.

## Security

Add the following to `.gitignore`:

```text
.env
.venv/
__pycache__/
```

Never commit API keys or other credentials to the repository.

## Current Features

- Persistent meeting memory
- Meeting information retention
- Relevant memory retrieval
- Follow-up detection
- AI-generated meeting brief
- Hindsight Recall integration
- Hindsight Reflect integration
- Hindsight Retain integration

## Future Improvements

- Web-based user interface
- Meeting history dashboard
- Calendar integration
- Automatic meeting transcription
- Better task and deadline tracking
- Authentication and user-specific memory
- Project and contact-based organization
- Automated follow-up reminders
- Evaluation of memory retrieval accuracy

## Hindsight

MeetingMind uses Hindsight as its persistent memory layer.

- Hindsight GitHub: https://github.com/vectorize-io/hindsight
- Hindsight Documentation: https://hindsight.vectorize.io/
- Vectorize: https://vectorize.io/

## Author

Built as a learning project by a second-year B.Tech Computer Science Engineering student exploring AI agents, persistent memory, and Python.

## License

This project is intended for educational and experimental purposes.
