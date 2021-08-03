# Voron 2.4 Pre Flight Check

![Image of Voron 2.4](http://vorondesign.com/images/voron2.4.jpg)

Step 1: Motor Check
- In Octoprint terminal, Buzz all motors by typing "STEPPER_BUZZ STEPPER=[ ]
    - stepper_x
    - stepper_y
    - stepper_z1
    - stepper_z2
    - stepper_z3
    - extruder

Step 2: Endstop Check
- Type "QUERY_ENDSTOPS" to check microswitch endstops.
- Check again while depressing each endstop.

Step 3: Motor Direction
- Type "G28 X" and make sure the tool head is homing in the correct direction.
- Repeat with Y "G28 Y".
- Any reversed motor will need the "dir" pin inverted in the firmware.
- During this process, you may notice the Z-axis moves up, this is the expected behaviour.
- If you hear a clicking or the Z-axis moves down, you must diagnose the reversed motors and invert their "dir" pins(in.cfg).

Step 4: Z Endstop Configuration
- Home X & Y axis
- Using "G1" move commands, carefully move your printhead until it is directly over the "Z" pin.
- Note the coordinates and save in .cfg in "home-xy-positions".

Step 5: Induction Probe Testing
- Type "QUERY_PROBE", should return open with no metal item. With metal item, should return "TRIGGERED".
- Type "PROBE_ACCURACY" and value for.

Step 6: PID Tuning
- To PID tune hotend, move toolhead to X150 Y180 Z10.
- Type "M140 S110" to set the bed to 110°c.
- Type "M106 S64" to set part cooling fan to 25%.
- Type "PID_CALIBRATE HEATER = EXTRUDER TARGET = 245"
- Let it run for about 5min.
- To PID tune bed, type "PID_CALIBRATE HEATER=heater_bed TARGET=100".

Step 7: Install Plugins
- In Octoprint, click the 🔧 to open up the settings.
- In the left sidebar, navigate to "Plugin Manager" and click "Get More".
- In the search bar, type "Astroprint" and install.
- After installing, log into Astroprint and go to account settings to get the key.
- Copy and paste the key in Astroprint tab in Octoprint.

Step 8: G Code Scripts
- In Octoprint, click the 🔧 to open up the settings.
- Nagivate to G code scripts and enter:
    - Before print job starts = "flash_blue".
    - After print job completes = "flash_green".
    - After print job is cancelled = "print_end" & "flash_red".
