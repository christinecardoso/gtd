To create an action that allows you to add a new note in Obsidian from the Share button on your device, you can use Obsidian URI along with a shortcut on iOS (via Shortcuts app) or an Android automation tool like Tasker or MacroDroid.

For iOS (Shortcuts App)

1. Open Shortcuts and tap â€+â€ to create a new shortcut.

2. Add Action â†’ Select â€œGet Text from Inputâ€.

3. Add Action â†’ Select â€œURLâ€ and enter:

obsidian://new?vault=YOUR_VAULT_NAME&name={{Current Date}}&content={{Shortcut Input}}

Replace YOUR_VAULT_NAME with your Obsidian vaultâ€™s name.

  

4. Add Action â†’ Select â€œOpen URLâ€.

5. Tap Share Sheet Settings â†’ Enable â€œShow in Share Sheetâ€.

6. Tap Done and name it â€œAdd Note to Obsidianâ€.

  

Now, when you use the Share button on any app (e.g., Safari, Notes), select this shortcut to send the content to a new note in Obsidian.

For Android (Using Tasker)

1. Install Tasker and Obsidian URI Plugin (if needed).

2. Create a New Task â†’ Name it â€œAdd Note to Obsidianâ€.

3. Add Action â†’ â€œSend Intentâ€.

â€¢ Action: android.intent.action.VIEW

â€¢ Data:

obsidian://new?vault=YOUR_VAULT_NAME&name=%DATE&content=%CLIP

  

â€¢ Replace YOUR_VAULT_NAME with your vaultâ€™s name.

â€¢ %DATE auto-generates a timestamped note name.

â€¢ %CLIP refers to copied/shared text.

  

4. Set Trigger:

â€¢ Go to Profiles â†’ Event â†’ Share Received.

â€¢ Choose â€œTextâ€ as input type.

â€¢ Link it to the task you created.

  

Now, whenever you use the Share button, you can send text directly to a new note in Obsidian.

  

Would you like modifications based on your workflow?