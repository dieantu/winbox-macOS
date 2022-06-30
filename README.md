# winbox for macOS
A simple automator script to open Winbox in a like-native enviorment on macOS.

## Run Winbox on macOS
To run Winbox64 the following steps are required.
1. Install latest Wine from the Wine macOS builds page and make sure you have downloaded the winbox64.exe executable from the MikroTik download page.
2. During installation, you must mark "64-bit support" (by default it is not checked).
3. In macOS terminal, make sure your set to use ZSH as the new shell, like this (and restart Terminal after this command): 
```
chsh -s /bin/zsh
```
4. Edit your zprofile file to add environment variables, pointing the wine64 command to the correct installation path of Wine Staging:
```
nano ~/.zprofile
```
5. The file should look like this (make sure your paths are correct here):
```
export PATH="/Applications/Wine Staging.app/Contents/Resources/wine/bin:$PATH"
export FREETYPE_PROPERTIES="truetype:interpreter-version=35"
export DYLD_FALLBACK_LIBRARY_PATH="/usr/lib:/opt/X11/lib:$DYLD_FALLBACK_LIBRARY_PATH"
```
Note: If you are running macOS Big Sur, instead of "nano ~/.zprofile", you have to edit "nano ~. / zshrc"
6. Restart (quit and reopen) your macOS terminal
7. Try to launch Winbox64 with wine64 like this:
 ```
wine64 "/Applications/winbox64.exe"
```
9. Move the automator script downloaded in this repository to /Applications like the winbox.exe file.
10. Done!
