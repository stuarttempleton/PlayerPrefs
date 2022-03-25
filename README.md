# PlayerPrefs
 Simple tool for Godot Engine to add persistent player preferences. It's just a JSON file with data serialized.

 ## How To Use This
 It's pretty simple. Most projects will only require 3 things:

 * Import/Clone/Copy into your project.
 * Add the PlayerPrefs scene to your Project Settings -> AutoLoad
 * Make sure you include *.json in your export profiles.

 ## Gotchas and Considerations
 
 * This probably doesn't serialize binary data very well.
 * If you want to use this in other "AutoLoaded" scripts, you might need to set it to load earlier (use the up arrow in the list so it is first)
 * You can change the file names, if so, you might make sure those export properly too.
