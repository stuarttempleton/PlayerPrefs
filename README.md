# PlayerPrefs
 Simple tool for Godot Engine to add persistent player preferences. It's just a JSON file with data serialized.

 ## Get Set-up
 It's pretty simple. Most projects will only require 3 things:

 * Import/Clone/Copy into your project.
 * Add the PlayerPrefs scene to your Project Settings -> AutoLoad
 * Make sure you include *.json in your export profiles.

## Basic Use

Here's how I use PlayerPrefs in Starscan to set window settings:
```gdscript
func LoadWindowSettings():
  OS.window_fullscreen = PlayerPrefs.GetPref("window_fullscreen", true)
  if !OS.window_fullscreen:
    OS.window_size = Vector2(PlayerPrefs.GetPref("window_size", 1280).x,PlayerPrefs.GetPref("window_size", 720).y)
  
 ```
 
 And I set it like so:
 ```gdscript
 func SaveWindowSettings():
   PlayerPrefs.SetPref("window_fullscreen", OS.window_fullscreen)
   if !OS.window_fullscreen:
     PlayerPrefs.SetPref("window_size", {"x":OS.window_size.x,"y":OS.window_size.y})
  
 ```
 
 And if if I want to do something specific if we *do* have settings, you can check for the existence of a setting preference:
 ```gdscript
 if PlayerPrefs.HasPref("previous_difficulty_code"):
   default_difficulty = PlayerPrefs.GetPref("previous_difficulty_code", "DBFF")
   ApplyDifficultyFromCode(default_difficulty)
 
 ```
 
 ## Gotchas and Considerations
 
 * This probably doesn't serialize binary data very well.
 * If you want to use this in other "AutoLoaded" scripts, you might need to set it to load earlier (use the up arrow in the list so it is first)
 * You can change the file names, if so, you might make sure those export properly too.
