# com.valvesoftware.Steam.Utility.steamtinkerlaunch

Testing repo ahead of the tool being accepted on Flathub (maybe longer).

Will likely end up tracking certain Steam Tinker Launch commits instead of "stable" releases.

# Reporting issues

Currently all Steam Tinker Launch flatpak discussion is happening here: https://github.com/frostworx/steamtinkerlaunch/issues/27

# Want to test it?

1. Install the [Steam Flatpak](https://flathub.org/apps/details/com.valvesoftware.Steam) if you haven't. This will only work with the Steam Flatpak.

2. Open the terminal.

3. Run `git clone https://github.com/HanPrower/com.valvesoftware.Steam.Utility.steamtinkerlaunch` in the terminal and navigate in to the directory.

4. You'll need to Flathub for your user by running `flatpak remote-add --user --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`

5. Next `chmod +x fp-build.sh`. This is a file that just automates some of the fiddly flatpak-builder bits. Feel free to check the file first.

6. Run `./fp-build.sh com.valvesoftware.Steam.Utility.steamtinkerlaunch.yml`. You can safely ignore the Appstream check error.

7. Run `flatpak list --user | grep steamtinkerlaunch` to double check that it is installed.

8. Open the Steam Flatpak. You can run it from the application menu or by running `flatpak run com.valvesoftware.Steam` in the terminal.

9. Right click the game you want to test, then click "Properties", select "Compatibilty", and check "Force the use of a specific compatibility tool" and select "Steam Tinker Launch" from the dropdown.

10. Launch the game and you should see the steamtinkerlaunch menu. Press "MAIN MENU" to look at the menu.

# Sick of testing it?

If you want to revert everything, do the following:

1. Click "Properties" on any game you enabled Steam Tinker Launch for, select "Compatibilty", and uncheck "Force the use of a specific compatibility tool".

2. Run `flatpak remote-delete --user flathub`. This will remove the Flathub remote from the user.

# Credits

[@frostworx](https://github.com/frostworx) - glorious Steam Tinker Launch creator

[@TheEvilSkeleton](https://github.com/TheEvilSkeleton) - initial creation of the flatpak files for the project
