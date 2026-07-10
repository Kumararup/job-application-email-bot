# job-application-email-bot
This workflow automatically reads a list of job opportunities from Google Sheets, generates a personalized cover letter (though currently hardcoded), downloads your pre-uploaded CV from Google Drive, and emails it to the company's HR contact. It runs on a schedule (e.g., every hour) so you don't have to manually send applications.
Schedule Trigger: Runs the workflow automatically based on a time interval (currently set to run every hour).

Google Sheets (Get Rows): Fetches rows from your spreadsheet. It expects fields like email, Internship Location, Country, etc. (The row_number 2 and 3 in your earlier screenshot show exactly what data it pulls).

Edit Fields (Set): Adds a hardcoded emailBody (the cover letter) to the data.

Google Drive (Download): Downloads the CV PDF using the File ID: 1ktfTcnLin6Wiv6uSdKFv5954SgCs6Oun.

Note: It downloads the same CV for every single internship row.

Gmail (Send): Sends an email to the address found in the spreadsheet ({{ $json.email }}), using the hardcoded cover letter as the body.
