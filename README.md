# com.valvesoftware.Steam.Utility.steamtinkerlaunch

Testing repo ahead of any use of the Flathub branch.

Unlikely to get used for much unless there's something _very_ experimental being tested.

# Reporting issues

If you find issues related to functionality of SteamTinkerLaunch that you definitely cannot pinpoint to being due to using Flatpak you can report them on the official SteamTinkerLaunch issue tracker:
https://github.com/frostworx/steamtinkerlaunch/

If you're using the Flatpak installed from Flathub you should post issues specifically with the Flathub version on the Flatpak issue tracker:
https://github.com/flathub/com.valvesoftware.Steam.Utility.steamtinkerlaunch

If you are using this experimental branch to _specifically test_ an **experimental** feature which isn't available on the Flathub version you can post on this issue tracker.

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
2. Run `flatpak remote-delete --user flathub`. This will remove the Flathub remote from the user (as well as any user installed packages, make sure you read what is being removed!).
3. You may also want to delete `~/.var/app/com.valvesoftware.Steam/.config/steamtinkerlaunch/`

# Credits

[@frostworx](https://github.com/frostworx) - glorious Steam Tinker Launch creator

[@TheEvilSkeleton](https://github.com/TheEvilSkeleton) - initial creation of the flatpak files for the project
