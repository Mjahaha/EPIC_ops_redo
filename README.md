**Read Me of EPIC Ops Redo**

Notes on build
- Not meant as a comprehensive guide, meant to communicate a general workflow change, desired features, and a layout that makes existing features easier to access. 

These are the big architectural changes from current EPIC
- No notification anymore, only cases. If cases are made for the same reason / thing to investigate we can link cases to each other. 
- The case stages no longer exist, the status now are open -> closed 



Extra features not in the UI but should be mentioned in the UI under case notes 
- Officers raised the desire to be able to add emails from their mailbox to the a case easily. Suggested workflow:
email a specific mailbox your email (addEmail@EPIC..) -> look in subject for a record that represents a case number delimited by spaces (eg EPA-1234) -> trigger API to add to the case if the case is open, and officer has write permission to that case -> create attachment with description as subject and file as email file. 
- Say the notice compliance now is stored against the notice, not its own section. 

Summarise each Case tab 
Incident Details - fields have been moved out, some fields present are removed, some are inferred based off other data and listed in the summary page. 



Prompts to Codex:
Adjust the Vehicles table to also have column for Owner Details. Populate a row in the Vehicles table. Next to the Registration number add a button called Create Drives Request that opens a note when clicked. This note then says in it that this would create a DRIVES request with this vehicle chosen in it already. 

Adjust dashboard page not to be its own page, but instead open a note that says, shows similar stuff as My Work but this time for your whole team. Dashboard will also show who has had what action, case assigned to them for how long to show who is holding up the process if someone is. 

Can we have a variable that stores the existing name of the case, and this is what is displayed nicely with the case name. Currently called "EPA-1234 Odour Bathurst (our EPIC Ops Redo example case)". The case number "EPA-1234" needs to be static and unchangable. Besides the title should be an icon that indicates the field is editable, and when you hit it it changes the field to editable. Can the dispaly of the icon look the same but actually be in an input box that has edit property off? Then when he button is switched this changes to enable edit. But when its not editable it looks as it does now. 