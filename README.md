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



Can you please look at the contents of the README and redo it. So this readme should not be a traditional readme, but rather an explanation of this is a wireframe for the EPA software EPIC, and this readme should be communicating that and the list of changes this wireframe represents. There are a bunch of notes in the readme right now that should inform some of that, however can you please go through each screen and case tab, write out what features are there at a high level. But especially the notes (except those that just say nothing here, just work as is) and anything that works all fancily in JS, and under a heading for each screen / case tab. Capture also, all the existing readme info which should give a good indication of other stuff the readme should have. Structure it to communicate what the wireframe does easily. 