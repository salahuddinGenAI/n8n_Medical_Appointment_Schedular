# n8n_Medical_Appointment_Schedular
CareFlow is an AI-powered medical appointment scheduling system built using n8n, Google Calendar, Google Sheets, and Google Gemini.
It allows clinics to automate their entire appointment booking process through a website chat widget, providing a fast, accurate, and 24/7 scheduling experience.

This workflow acts as a smart conversational assistant — collecting patient details, checking calendar availability, creating appointments, updating or canceling them, and logging everything to a Google Sheet seamlessly.

📌 Features

💬 AI Chat-Based Appointment Booking
Patients interact through your website chat widget.

📅 Real-Time Slot Checking
Integrated directly with Google Calendar.

📝 Automatic Patient Data Logging
Logs every confirmed appointment into Google Sheets.

🔄 Update & Cancel Appointments
The agent handles modifications without asking users for event IDs.

🔔 Automated Reminder Logic (Foundations Included)
A scheduler runs every 30 minutes to detect upcoming appointments.

🧠 Conversation Memory for Natural Interactions
Maintains context using memory buffer windows.

⏰ Works 24/7
Never misses a patient query.

🧩 Technology Stack

n8n Workflow Automation

Google Calendar API

Google Sheets API

Google Gemini (PaLM)

JavaScript (for logic & filtering)

⚙️ Nodes Used in the Workflow
Core Interaction

Website Chat Widget (Chat Trigger Node)

CareFlow (AI Agent Node)

Conversation Memory (Buffer Window Node)

Google Gemini Chat Model (AI Language Model)

Appointment Logic

Check Availability – Google Calendar Tool

Create New Appointments – Google Calendar Tool

Cancel Appointments – Google Sheets Tool

Update Appointments – Google Calendar Event Handling

Get Upcoming Appointments – Google Calendar

Utility & Automation

JavaScript Code Node (Filter upcoming appointments)

Schedule Trigger Node (Runs every 30 minutes)

Appointment LogSheet (Google Sheets Tool)

📁 Workflow File

The complete workflow file is included in this repository:

Appointment Scheduler Agent (1).json

🚀 How It Works
1. User Interaction

The workflow starts when a user sends a message through the website chat widget.
The Chat Trigger node captures this, and the message is passed to the CareFlow AI Agent.

2. Collecting Patient Details

CareFlow collects:

Date & Time

Patient Name

Email

Phone Number

Reason for Visit

It asks only for missing information.

3. Checking Availability

The AI Agent calls:

check_availability


via the Google Calendar Tool to confirm open slots.

4. Booking the Appointment

If the slot is available, the agent triggers:

create_appointment


The event is added directly into Google Calendar.

5. Logging to Google Sheets

After successful booking, details are logged in a Google Sheet:

Date & Time

Patient Name

Phone

Email

Reason

6. Updating Appointments

CareFlow can update the date/time of existing appointments without asking the user for event IDs.

7. Canceling Appointments

If the user requests cancellation, the workflow triggers:

delete_event


and confirms the cancellation to the patient.

8. Scheduled Reminder Logic

A Schedule Trigger runs every 30 minutes.
It fetches upcoming appointments and uses a JavaScript Code node to filter appointments starting within 1 hour.

This logic can be extended to send automated reminders.

🛠️ Setup Guide
1. Configure n8n Credentials

You must add credentials for:

Google Calendar OAuth2

Google Sheets OAuth2

Google Gemini API Key

2. Import the Workflow

Go to n8n → Workflows → Import

Upload the file:
Appointment Scheduler Agent (1).json

3. Update Default Values

In the imported workflow:

Set your Google Calendar ID

Set your Google Sheet ID

Update chat widget settings

Adjust schedule interval if needed

4. Enable the Workflow

Turn on the workflow to activate CareFlow.

 
🏥 Business Use Cases

Medical Clinics

Private Doctors

Diagnostic Centers

Therapy & Wellness Centers

Telemedicine Platforms

CareFlow ensures:

✔ 24/7 response
✔ Zero missed appointments
✔ Reduced staff workload
✔ Faster patient service
✔ Accurate, organized record-keeping

🤝 Contributing

Pull requests are welcome!
If you wish to improve the workflow or add new features, feel free to contribute.

📄 License

This project is licensed under the MIT License.
You are free to modify and use it in your own automation systems.
