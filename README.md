# NV Series Autoswitch Module

Two variations of the Autoswitch module can be found in this repository with example Designer files.

# Simplified Autoswitch

This plugin provides automatic video switching of an 'HDMI Decoder' or even an 'AV Router' block with a memory of what the last selected sources were. If the currently selected source is disconnected it will fall back to whatever the last selected source that is still currently active.

If no sources are currently active then it will default into an idle state. Simply wire up the Idle Pin into whatever you would like to achieve when there are no active sources. Some suggestions below.

1. Default to a graphic on the HDMI Decoder block
2. Trigger 'HDMI Display' block to send black video
3. Turn a displays back light off or even power off


All this block requires is you to wire the 'HDMI AV Output Valid Format' pins from your sources into the 'Active' pins of the plugin. Then the 'Select' pins into the corresponding selection buttons on the Decoder or AV Router and the 'Idle' pin to an appropriate endpoint.

# Advanced Autoswitch BETA

This is a test version that expands upon the simplified plugin. The end result of this version is to not only provide autoswitching but also provide dynamic selection buttons that only display when a corresponding source is active. This means you can keep your Q-SYS UCIs much cleaner dynamically removing buttons that will have no effect if corresponding source is not active

It utilises Named Components to select an HDMI Decoder and return you the options for all the available source selections in that block. It requires you to set up your Decoder and all your sources as Named Components enabling Script Access. 
(see following link for more details: https://q-syshelp.qsc.com/Content/Control_Scripting/Code_Name_Script_Access.htm#:~:text=Q%2DSYS%20will%20automatically%20assign,hovering%20over%20with%20the%20pointer.)

Set up will go as follows:

1. Select your decoder from the dropdown box
2. For each of the available selections it detects available set from the dropdown menus the name of the source block as well as the corresponding Decoder selection
3. Give each of these selections a user friendly name for the UCI (this is required)
4. Select what graphic it will default to when the plugin is 'Idle'
5. Wire up the 'HDMI AV Output Valid Format' from the source blocks into the 'Active' pins on the script
6. Take your selection buttons and display names from the 'UCI Elements' tab onto your UCI
7. Optionally you can also take the current source to the UCI
8. Happy autoswitching!

This is still very much work in progress and any feedback would be greatly appreciated. Please send any queries to jasper.murrell@qsc.com

Some planned features include:
1. HDMI Output 2 support
2. Automatic mapping of the Valid Format control when source block is selected via Named Components
3. AV Router support

