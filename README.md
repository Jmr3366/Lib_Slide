# Lib_Slide
![alt text](https://github.com/Jmr3366/Lib_Slide/blob/main/LibSlide.webp?raw=true)
- Video tutorial: coming soon

Library token for the Maptool VTT application.

This library token uses functionality that aligns an overlay with a token.  
While functional, Maptool **does not** directly support this.   

This Library Token does NOT fully support:
- Tokens that use odd offsets or layout edited values(**expect** misalignment).
- Some combinations of hex and no-snap to grid tokens.
- Tokens that are not equally sized (width and height values that are NOT equal)
- Overlay large tokens (width and height values greater than 4000 pixels when set at "Native Size").


## General Summary

The library token will only function on tokens that:
- Token needs "Has Sight" checked.
- Uses a busy loop to create a delay during movement.
  - This will execute local to each client.  It is important to understand this can impact the performance of client connected systems.  If a powerful PC user moves 10 tokens, this will execute code on every connected client (on that map), and slower performing systems, slow network connect clients, will not perform as expected.  Symptoms could include video artifacts like tokens that appear to jump around on the path or waypoints, tokens blink from half way to end, token disappears / reappears.  No artifacte should remain once movement completes. 

Configuration Options include 
- Using an overlay (CSS) to emulate sliding the token.
  - It will create an overlay to best mimic the token sliding / moving from the current location to the new location.
  - It will clear the checbox "Visible to players", set "Token Opacity" to 0, during the slide, and will reset these values to the prior state, once complete.
 
- Moving the token in steps from the current location to the new location.

Run the `Info` Macro once loaded in Maptool for more information.

