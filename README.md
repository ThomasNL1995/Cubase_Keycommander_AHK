# June 2026 update: Now a standalone Windows and MacOS application, check it out here:

[birchlabs.thomasvanderburg.com](https://birchlabs.thomasvanderburg.com)

If you are still interested in the Autohotkey version, read along. But I highly recommend the new version!

![KeyCommander Website Preview](https://birchlabs.thomasvanderburg.com/wp-content/uploads/sites/2/2026/05/birchlabs_website_OG_image_v2.png)

# Cubase Keycommander #

_Made by Thomas van der Burg_  
**Version 1.0** _28-01-2025_



The Cubase Keycommander uses **AutoHotKey**, **Virtual MIDI**, and **Cubase MIDI Remote** to easily search for any command or macro available in Cubase and execute it without assigning any key manually.

### **How It Works**

After selecting your `keycommands.xml` file, the program will parse all commands and assign a **unique MIDI CC message** to each. This mapping is then written to a MIDI Remote Script. When selecting a command to execute, the program sends the MIDI CC message to Cubase via a virtual MIDI port.

### **Installation Guide**

1. **Download the Repository**
    
    - Download the contents of this repository and place the folder somewhere on your system.
2. **Install AutoHotKey V2.0**
    
    - Download and install AutoHotKey V2.0 from: [https://www.autohotkey.com/](https://www.autohotkey.com/)
3. **Install Virtual MIDI Port Software**
    
    - Download and install a program that creates virtual MIDI ports. I recommend loopMIDI by Tobias Erichsen: [https://www.tobias-erichsen.de/software/loopmidi.html](https://www.tobias-erichsen.de/software/loopmidi.html)
4. **Add a Virtual MIDI Port**
    
    - Once installed, open loopMIDI and add a virtual MIDI port. Give it a recognizable name, for example: `loopMIDI Keycommander`
5. **Copy MIDI Remote Script Files**
    
    - Copy the contents of the `Midi Remote Script` folder from this repository to the following location on your system:
        
        ```
        Documents\Steinberg\Cubase\MIDI Remote\Driver Scripts\Local
        ```
        
6. **Run the Script for Initial Setup**
    
    - Run the `Cubase_Keycommander_V1.ahk` script. The settings menu will appear the first time. Go through each setting and click **Save** when done. Make sure you are using shortcuts that you aren't using inside Cubase already.
7. **Restart Cubase**
    
    - Open Cubase. If it was already open, completely close and restart it.
8. **Load the MIDI Remote Script**
    
    - Go to **Studio > MIDI Remote Manager** inside Cubase. In the window that appears, click the **Refresh** button in the top right (`Reload Scripts`). A new script called `Thomasvanderburg_Keycommander` should now appear and under status it should say "Connected". Close the window.
9. **Use the Keycommander**
    
    - Inside Cubase, press your assigned hotkey to open the Keycommander. Search for a command (e.g., `Add Instrument Track`). Use the arrow keys to navigate the search results if needed. Press **Enter** to execute the command.
10. **Updating Key Commands**
    
    - If you make changes to your key commands or create new macros:
        1. Close Cubase.
        2. Restart the `.ahk` script or go to `File > Refresh` in the settings menu.
        3. This will re-parse the `keycommands.xml` file and update the necessary files.
11.  **Run on Startup**
	 - If you want the script to start automatically on startup, right click the .ahk file and create a shortcut. Move the created shortcut to your startup folder at:

	User\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup


### **Troubleshooting/FAQ**

- **Keycommander script doesn't appear in Cubase:**  
    Ensure that you moved the contents of the `Midi Remote Script` folder to the correct location. The path in the end should look like: 
    ```"Documents\Steinberg\Cubase\MIDI Remote\Driver Scripts\Local\Thomasvanderburg\Keycommander"```. 
    Also make sure you refreshed the **MIDI Remote Manager** in Cubase (Step 8).
    
- **Commands don't execute:**  
    Verify that your virtual MIDI port is set up correctly and the program is running in the background.
    
- **I Opened an old project and now it doesn't work anymore:**  
	You might have to re-add the MIDI remote. Redo step 8
    
- **Can I have more than the 20 results listed?**  
	You will have to edit the .ahk file. Open it in a text editor and change SEARCH_RESULT_MAX to a higher number. Might add this as an option in settings down the line.
    
---

If you encounter any bugs, please contact me via music@thomasvanderburg.com
