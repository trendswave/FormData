# Form Data

This project is a simple Google Forms clone built with HTML, CSS, and JavaScript. It allows users to submit form data, which is then sent to a Google Sheet using a Google Apps Script.

## Features

- Collects user input through a form
- Sends form data to a Google Sheet
- Displays success or error messages upon form submission

## Technologies Used

- HTML
- CSS
- JavaScript
- Google Apps Script

## Setup

1. **Clone the repository:**
   ```sh
   git clone https://github.com/trendswave/FormData.git
   cd FormData

2. **Create a Google Sheet:**

Go to **Google Sheets** and create a new sheet.
Name the columns according to your form fields (e.g., name_of_student,etc.).


3. **Create a Google Apps Script:**

In your Google Sheet, go to Extensions > Apps Script.
Delete any code in the script editor and replace it with the following code:

```javascript
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var data = JSON.parse(e.postData.contents);
  
  sheet.appendRow([
    data.name_of_student,
    data.matric_number,
   (add you specific data entries)
  
  return ContentService.createTextOutput(JSON.stringify({ 'result': 'success' })).setMimeType(ContentService.MimeType.JSON);
} ```

3. Deploy the Script as a Web App:

Click on the "Deploy" button and select "New deployment".
Choose "Web app" as the type.
Set the access to "Anyone" and deploy.
Copy the URL provided; you will use this URL to send data to the Google Sheet.

4. Deploy the Script as a Web App:

Click on Deploy > New deployment.
Select Web app as the deployment type.
Set Execute as to Me and Who has access to Anyone.
Click Deploy and authorize the script.
Copy the Web App URL provided after deployment.
Update the JavaScript File:

Replace 'YOUR_GOOGLE_SHEET_API_URL' in FormData.js with the Web App URL you copied.

# Usage
1. Open index.html in a web browser.
2. Fill out the form and submit it.
3. Check your Google Sheet to see if the data has been appended correctly.

# Lincense
