Power Automate Flow: Update Excel Rows Based on Email Approval
This repository contains a Power Automate flow that updates rows in an Excel file based on whether a person has approved a certain email. The flow triggers when a new email arrives, checks if the email contains approval information, and updates the corresponding row in an Excel table.

Prerequisites
A Microsoft Power Automate account
Access to Outlook for email triggers
An Excel file stored in a cloud location (e.g., OneDrive for Business, SharePoint)
An Excel table with relevant columns (e.g., Email, Approval Status)
Flow Overview
The flow performs the following actions:

Trigger: Activates when a new email arrives in the specified folder.
Condition: Checks if the email subject or body contains "Approved".
List Rows: Retrieves rows from the specified Excel table.
Apply to Each: Loops through the retrieved rows.
Condition: Checks if a row matches the email sender or another identifier.
Update Row: Updates the matching row to reflect the approval status.
Setup Instructions
1. Create a New Flow
Sign in to Power Automate.
Click on Create and select Automated cloud flow.
Name your flow and select When a new email arrives (V3) as the trigger.
2. Configure the Email Trigger
Choose the folder where the email will arrive (e.g., Inbox).
Set any additional filters if needed (e.g., only emails with a certain subject).
3. Add a Condition to Check for Approval
Add a Condition action.
Configure the condition:
In the "Choose a value" box, select Subject or Body.
Set the condition to check for keywords like "Approved".
4. List Rows from the Excel Table
Add the List rows present in a table action from the Excel Online (Business) connector.
Configure the action:
Select the location of your Excel file (OneDrive for Business, SharePoint, etc.).
Choose the file and table you want to update.
5. Loop Through the Rows
Add an Apply to each action.
Select the value from the previous List rows present in a table action.
6. Add a Condition to Find the Matching Row
Add a Condition inside the Apply to each loop.
Configure the condition:
In the "Choose a value" box, select the column to check (e.g., Email or Name).
Set the condition to check if it matches the email sender or another identifier.
7. Update the Matching Row
Add the Update a row action inside the condition's "If yes" branch.
Configure the action:
Select the same location, file, and table.
Provide the Key Column and Key Value (the identifier for the row).
Update the necessary columns, such as changing the status to "Approved" or "Not Approved".
8. Test the Flow
Save the flow.
Send an approval email to test the flow.
Verify that the corresponding row in the Excel file is updated correctly based on the email content.
Example Flow Diagram
Trigger: When a new email arrives
Condition: Email contains "Approved"
If Yes:
List rows present in a table
Apply to each row
Condition: Row matches identifier
If Yes: Update the row to "Approved"
If No: (Optional) Handle non-approval cases
Conclusion
This Power Automate flow automates the process of updating Excel rows based on email approvals, ensuring that your data is always up to date without manual intervention. Feel free to customize the flow to suit your specific needs.

License
This project is licensed under the MIT License.