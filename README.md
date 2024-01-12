Email Client Front-End README
This README provides instructions and information for designing the front-end of an email client that interacts with a provided API for sending and receiving emails. The project is built using Django and requires the implementation of JavaScript, HTML, and CSS to create a single-page email client.

Getting Started
Download the distribution code from mail.zip and unzip it.
In your terminal, navigate to the mail directory.
Run python manage.py makemigrations mail to create migrations for the mail app.
Run python manage.py migrate to apply migrations to your database.
Start the web server using python manage.py runserver.
Open the web server in your browser and register for a new account using the "Register" link.
Understanding the Code
The project structure includes a Django project called project3 with a single app called mail.
The application is a single-page app with JavaScript used to control the user interface.
The main template for the Inbox page is mail/inbox.html, and JavaScript functionality is implemented in mail/static/mail/inbox.js.
The application supports three mailboxes: Inbox, Sent, and Archive.
API Routes
The provided API supports the following routes:

GET /emails/<str:mailbox>: Returns a list of emails in the specified mailbox.
GET /emails/<int:email_id>: Returns details of a specific email.
POST /emails: Sends a new email.
PUT /emails/<int:email_id>: Updates the status of an email (read/unread, archived/unarchived).
Implementation Requirements
1. Send Mail
Implement JavaScript code to send emails by making a POST request to /emails.
The request should include values for recipients, subject, and body.
2. Mailbox
Load the appropriate mailbox when the user visits Inbox, Sent, or Archive.
Make a GET request to /emails/<mailbox> to retrieve emails for the selected mailbox.
Display emails in separate boxes, showing sender, subject, timestamp, and read/unread status.
3. View Email
When a user clicks on an email, display the content of that email.
Make a GET request to /emails/<email_id> to retrieve the email details.
Display sender, recipients, subject, timestamp, and body.
Mark the email as read after it has been clicked.
4. Archive and Unarchive
Allow users to archive and unarchive emails.
When viewing an Inbox email, provide a button to archive the email.
When viewing an Archive email, provide a button to unarchive the email.
Make a PUT request to /emails/<email_id> to update the email's status.
5. Reply
Allow users to reply to emails.
Provide a "Reply" button when viewing an email.
Prefill the composition form with the recipient, subject line, and body.
Hints
Use JavaScript to create HTML elements dynamically and add event listeners.
Edit mail/static/mail/styles.css to add any necessary CSS for styling.
Utilize JavaScript array methods, such as forEach, to loop over elements.
CSRF tokens are not required for this project, as the provided API routes are CSRF-exempt.
