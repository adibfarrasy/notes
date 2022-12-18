# Crylia's Awesome WM Setup Breakdown

## root folder
rc.lua - for importing all the setups (in sequence)
src/ - where most of the code implementations are
mappings/ - contains keymaps and binding to tags
crylia_bar/ - contains modular bar settings

## src/
assets/ - (single file) rules, wallpapers and icons
core/ - contains codes for error handling, notifications, rules and signals
    - what is a signal?
modules/ - contains codes for notifications, brightness, powermenu, titlebar, and volume
    - what is 'osd' for brightness and volume? ON-SCREEN DISPLAY, THE POPUP IN THE MIDDLE OF THE SCREEN.
scripts/ - contains shell scripts bt.sh, mic.sh, pfp.sh, and vol.sh
theme/ - contains codes for colors and theme & user variables
tools/ - seems to be miscellaneous lua scripts. contains auto starter and icon handler codes
widgets/ - custom widgets. the widgets are audio, battery, bluetooth, clock, cpu_info, date, gpu_info, kblayout, layout_list, network, power, ram_info, systray, taglist and tasklist

## mappings/
bind_to_tags.lua - append Super+#Tag, Super+Ctrl+#Tag, and Super+Shift+#Tag to the globalkeys via gears.table.join then root.keys.
client_buttons.lua - mappings for manipulating clients with a mouse. if called, returns a table for button bind for 1 (activate client?), Super+1 (activate client and move), and Super+3 (activate client and resize)
    - what is button 1? is it a mouse click? YES IT'S A LEFT CLICK. BUTTON 3 IS A RIGHT CLICK.
client_keys.lua - mappings for manipulating clients with keybinds. if called, returns a table for keybinds for toggle fullscreen, close focused client, toggle floating window, toggle maximize client, and toggle hide client.
global_buttons.lua - mappings for previewing tags with a mouse. declares root.buttons with a table containing button map. scroll up for next tag, scroll down for previous tag.
global_keys.lua - mappings for global keybinds. returns a table for keybinds for opening cheatsheet, view previous/ next tag, go back to the last tag, focus previous/ next client by index, swap with previous client by index, focus to next/ previous screen, jump to urgent client, open terminal, reload awesome, increase/ decrease client width, increase/ decrese number of tag columns, select previous/ next layout, run rofi, run file manager, show session options, increase/ decrease audio volume, increase/ decrease brightness, manipulate play/pause media, and load rules

## crylia_bar/
center_bar.lua - configures center bar. returns a function with screen and widgets as input. creates the popup, prepares the widgets, sets up, and configures to multiple connect_signals
    - what is connect_signals? is it analogous to events?
dock.lua - creates the popup, sets up and configures to multiple connect_signals for the dock. not really my thing for now, so I will not bother.
init.lua - configures the bars (and the widgets diplayed within it) and the dock. NOTE: apparently you can add whatever property you want in there.
left_bar.lua - setup for the left bar
right_bar.lua - setup for the right bar. only differs to left_bar.lua by one line (screen selection)

## src/assets/icons
contains svg icons for audio, battery, bluetooth, brightness, clock, cpu, date, kblayout, network, notifications, power, powermenu, and titlebar. also includes arch logo png.

## src/assets/layout
contains svg icons for the window layouts

## src/assets/userpfp
profile picture for the logged in user

## src/assets
contains wallpapers fuji.jpg, space.jpg and wallpaper.png. Also has rules.txt
    - what's the rules.txt for? the lines are to be appended to the ruled.client.append_rule method in rules.lua

## src/modules/
error_handling.lua - runs when the configuration causes an error.
    - is this the same as the default one? IT'S NOT. IT HAS CONNECT SIGNAL.
notifications.lua - has various naughty.connect_signals, i.e. request::icon, request::display, destroyed and invoked. signal destroyed has empty function callback (not implemented), and invoked reads the Spotify program and controls based on ids i.e. 'skip-prev', 'play-pause', 'skip-next'
rules.lua - contains awesome rules such as showing titlebar and load rules from src/assets/rules.txt
signals.lua - contains custom signals for screen.connect_signals, client.connect_signals and widget.connect_signals.
    - how does the connect_signals work?

## src/modules/
brightness_osd.lua - on-screen display settings for the brightness
powermenu.lua - config for the powermenu display on the rightmost right bar, and the signal configurations for showing/ hiding the powermenu
titlebar.lua - interaction configuration with the titlebar. probably won't need it as I plan to hide the titlebar.
volume_controller.lua - SUPER LONG configuration for speaker and mic
volume_osd.lua - on-screen display settings for the speaker volume

## src/scripts/
bt.sh - list paired devices' names and battery percentage. Not very useful.
mic.sh - requires additional args, for get/ set mic volume, mute and toggle mute and set source
pfp.sh - requires single additional arg, get the logged in user's profile picture, name and host. Not very useful.
vol.sh - requires additional args, for get speaker volume, mute and set sink

## src/theme/
colors.lua - contains a table with almost all Material colors.
init.lua - create a theme object, add some properties and setup beautful.wallpaper and beautiful.init(theme)
    - what is Lua's dofile for? is it for inlining?
theme_variables.lua - for injecting Theme properties
user_variables.lua - has user-level settings such as autostart, network, font, default applications, modkey, wallpaper, namestyle, etc. 

## src/tools/
auto_starter.lua - small scripts to run terminal commands from a list of commands in ipairs. used in the last line of rc.lua.
icon_handler.lua - a helper to get icons from a program by name. basically trying to find the program icon from /usr/share/icons by image name

## src/widgets/
audio.lua - TODO
battery.lua - TODO
bluetooth.lua - TODO
clock.lua - TODO
cpu_info.lua - TODO
date.lua - TODO
gpu_info.lua - TODO
kblayout.lua - TODO
layout_list.lua - TODO
network.lua - TODO
power.lua - TODO
ram_info.lua - TODO
systray.lua - TODO
taglist.lua - TODO
tasklist.lua - TODO
