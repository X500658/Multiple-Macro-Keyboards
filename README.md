# Multiple-Macro-Keyboards
Use extra keyboards as macro keyboards

Tom Scott Emoji Keyboard: https://www.youtube.com/watch?v=lIFE7h3m40U
Original Code from Taran: https://github.com/TaranVH/2nd-keyboard

1. Download and install LuaMacros and AutoHokey
2. Open LuaMacros then run multikeybs.lua and find your macro keyboard's device ID. The line "lmc_print_devices()" is responsible for this. Based on my experience, my 2 USB keyboard have their IDs beginning in "ID_"
3. uncomment (remove the "--") from the line "--lmc_device_set_name('MACROS1', "NP0303");" and replace NP0303 to your keyboard's ID
4. comment out (add "--" at the start of the line) the line "lmc_assign_keyboard('MACROS1')"
5. Replace the path in the "lmc spawn" and the "local file" lines to where you want the temporary file to be stored. I suggest commenting out the "lmc_minimize" lines for testing
6. Test the macro keyboard if it works, LuaMacros should show what you last pressed.

If you want multiple macro keyboards:
  a. add more "lmc_device_set_name('MACROS2', "ID_0002")" lines with the names being unique. 
  b. add more "lmc_set_handler('MACROS1', function(button, direction)" code blocks
  c. replace the keyboard name and the keyboard numbers in the "sendToAHK" line and the "print('Your key ID number is:   (1)' .. button)" line
  d. Don't forget to test


7. Now open multikeybs.ahk in your preferred text editor.
8. Replace the path in the "FileRead" line
9. Replace the code within the switch case line to what you want to do. TaranVH provides an if-else version if thats what you prefer. Ignore that all of them use a Runner function, that just what I did to separate the keypress and the macro.
10. Good Luck
