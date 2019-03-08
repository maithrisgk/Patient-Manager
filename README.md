# Patient-Manager
HTML5, CSS3, Vue.js, JSON-Server


The Patient Manager is a simple application created using Vue.js

This application's focus is to serve the front office person at any clinic.
Whenever a patient enters the clinic, the front office person can enter the details of the patient in the given text box, which would be added to the list.
The checkbox beside the patient name, is used to toggle the "line through" CSS styling.  This is done to make a note on whether the patient has been attended by a doctor or is yet to be attended.
The red round button with an 'x', is clicked to delete a patient entry from the list.

The JSON-Server is used to create a sample api "db.json" and the "axios js" is used to handle HTTP Requests.  The id is generated dynamically at runtime using UUID version 4. 
