# Custom Sponsor Logos and Inspection display bugs

## Custom Sponsor Logos

### Description

After adding custom sponsor logos to an instance of Tournament Manager, any new windows that are opened do not appear. This affects the following windows: both full and overlay audience displays, pit displays and field displays. Once the custom logos are removed, the displays open correctly. If TM is restarted with the custom logos, the main window also fails to open, but the taskbar icons do appear.

### To Reproduce

1. Using the Tools > Options > Sponsor Logos menu, add any number of custom logos to either the large or small sections.
2. Attempt to create new audience, pit or field displays.
3. If multiple field sets are used, select any field.

Upon restarting TM:

1. Select open existing tournament and select the database file with custom logos added.
2. The main TM window does not appear, but the small taskbar icons in the bottom right near the clock do appear.

### Expected Behavior

After adding custom sponsor logos, new displays should appear as requested and remain open until closed. If multiple field sets are used, the field set selection window should pop up first. When TM starts up, the main window should appear on screen.

### Impact to users

Minor if users are aware of the issue. If the server with custom logos crashes, reopening the existing DB file will not work, resulting in the event needing to fall back onto paper scoresheets if a backup DB file without the logos was not created. A possible workaround is to find where the included logos are saved on the device and to replace those images, however I could not locate them in the installation directory.

### Additional comments

Included in the repo are the images that were used to reproduce the issue but I believe any image will trigger the bugs. There is also a `logoTest.db` file that has logos added which causes the main window to not appear on startup.

## Inspection Audience Display view

### Description

The inspection view for displays does not display a team's inspection status correctly. The counts for checked in, not started, partial and passed at the top of the screen does update correctly, but the team's number does not change from black font to yellow/green based on status. Previous versions would switch the font colour/style based on the team's status.

### To Reproduce

1. Create a new tournament.
2. Start an audience display.
3. Mark a team as partially or fully passing inspection but not checked in.
4. Note that on the audience display, the counter at the top updates to recognise the change but the team's numbers do not switch styles.

### Expected Behaviour

The team numbers should switch from black text to orange/yellow when partially passing and green when fully passing inspection. Alternatively, TM could treat partially or fully passing inspection as also checking in as teams must be present and ready to compete.

### Impact to users

Minor/nil, teams will know that they have passed or not as inspectors verbally inform them and the team member must sign/initial to confirm.

## System and Software Specs

### Windows 11

- Hardware: Razer Blade 15 Advanced i7-11800H 16GB
- OS: Windows 11 23H2 Build 22631.3810
- TM Version: v2024_25.1.1, Build: v2024_25.1.1-gbb74e2f3 (July 8th 2024)

### macOS

- Hardware: Macbook Air M1 8GB
- OS: macOS Sonoma Version 14.4.1
- TM Version: v2024_25.1.1, Build: v2024_25.1.1-gbb74e2f3-dev (July 8th 2024)
