
NOTE: THIS GUIDE IS NOT FOR GAME PIRACY, ONLY USE IT FOR GAMES THAT YOU LEGALLY OWN.

Also this guide was based on a (now deleted) guide to make work mac and windows unity games on linux (what is technically possible with mac too, but only with few games).

---------------------------------


Some very old Unity games on Steam are 32-Bits only, however, since Unity 4.2, they started supporting 64-Bits apps, and these games that are from Unity 4.2 and above were not made with 64-Bits architecture (maybe because developer ignorance, laziness, or problems while converting to 64-bits), so let's do it on our own.

(This guide is just to replace 32bits UnityPlayer with a 64bits one)



##Checking Game Unity Version##

- Download The Game (obvious)

- Get Into the Game Folder

- Right Click the Game and select "Show Package Contents"

- Search the "data" folder, not every game have it in the same place, if you see that the folder have some "level0, level1..." files, then Open Terminal

- Write: "strings", add an space and Drag the "level0" file into the terminal window, then add: "| head -1" and you should already have the Unity version.

- You will see that the version ends with something like "p1" or "f2", this is important, that indicates some specific versions of this version (yeah), "p" is for patch, and "f" is for final (or just normal version), maybe will be a little more harder to find patched versions, betas, and release candidates

- IF THE UNITY VERSION IS BELOW 4.2, YOU CANT PORT THIS GAME (or at least not using this metod)


Well, now you got the Unity version that the game needs... now you need to download THE SAME Unity version, otherwise, the game simply wont launch.

##Obtaining UnityPlayer##

You can get the unity version you want from the official unity webpage, you dont need a license to download and unpack it (only for using Unity app), however, it looks like they updated some old unity packages to have a 2020 UnityPlayer instead of the needed, and it wont work if we want to port a very old game, so, its recommended to search the file you need on the archive.org wayback machine. (some working links on [This Page](https://github.com/M0REKZ/PortingMacGames/blob/Principal/Unity/Working%20Dowload%20Links.md))

- Download correspondent Unity Version (it may be a pkg file or a dmg)

- For pkg files you can install it.. or extract the contents with terminal or [The Unarchiver](https://apps.apple.com/us/app/the-unarchiver/id425424353?mt=12) (or just another software for that), in case that there are other pkg files inside, simply Right Click "Unity.pkg" and "Show Package Contents", then search the "Payload" File and change the name to "Payload.zip", now you can access to Unity app without installing it.

- For dmg simply drag Unity.app to somewhere on your computer, but if it is a pkg file, drag and drop it, and see the step above.

- Now that you have access to Unity application, Right Click it and "Show Package Contents", now you can see files inside Unity app.

- Now you need to enter to "PlaybackEngines" Folder, to "MacStandaloneSupport", and "Variations", (however, if you see a "Source" Folder inside "MacStandaloneSupport" and you find a xcode project file, it looks like you downloaded a package with a modern UnityPlayer, it wont work for needed game, you will need to found original pkg on archive.org wayback machine)

- You will see folders like "macosx64_development_mono" you will prefer to use the "x64_nondevelopment", "universal_nondevelopment" or "arm64_nondevelopment" ones but not the "x32_nondevelopment" one (Note: there are two types of universal apps, one that have "ppc","32bits","64bits" support, and other that have "64bits","arm64" support, the first one can be found on Unity 4.2 and above, but the second one only can be found in modern Unity versions along with the "arm64 only" app, so instead of using the first universal app, you may prefer to simply use the "x64" one)

- Copy your selected folder to somewhere in your computer, Right Click the app inside and select "Show Package Contents", go to "Contents", "MacOS", and you will find the UnityPlayer Binary, copy it to some place on your computer, do the same with the content in "Frameworks" Folder so you can have it close for the next steps

##Replacing Game UnityPlayer##

Time of Truth

Make a backup of your game app so, if you do something wrong, you can retry

Right Click the game app and "Show Package Contets", go to "Contents", "MacOS"

Copy your UnityPlayer Binary inside

Go back and go to Frameworks, copy the files that you got before.

Open terminal, drag "UnityPlayer" in the window, add a space, write "-logfile", add another space, and write "~/Desktop/gamelogfile.txt", run this command everytime you want to run UnityPlayer, so if the app crash/bugs, you can see what to do (sometimes some extra libraries is needed, you can found them inside Unity app, and search on internet for the third-party ones)

If you did all in the right way (and the game is really compatible), Congratulations!!, The game now are running on a modern mac!!, you may like to replace the original game binary inside "MacOS" folder with the UnityPlayer binary and change the name.


