
NOTE: THIS GUIDE IS NOT FOR GAME PIRACY, ONLY USE IT FOR GAMES THAT YOU LEGALLY OWN.


Some very old Unity games on Steam are 32-Bits only, however, since Unity 4.2, they started supporting 64-Bits apps, and these games that are from Unity 4.2 and above were not made with 64-Bits architecture, so let's do it on our own.



#Checking Game Unity Version#

- Download The Game (obvious)

- Get Into the Game Folder

- Right Click the Game and select "Show Package Contents"

- Search the "data" folder, not every game have it in the same place, if you see that the folder have some "level0, level1..." files, then Open Terminal

- Write: "strings", add an space and Drag the "level0" file into the terminal window, then add: "| head -1" and you should already have the Unity version.

- You will see that the version ends with something like "p1" or "f2", this is important, that indicates some specific versions of this version (yeah), "p" is for patch, and "f" is for final (or just normal version), maybe will be a little more harder to find patched versions, betas, and release candidates

- IF THE UNITY VERSION IS BELOW 4.2, YOU CANT PORT THIS GAME (or at least not using this metod)


Well, now you got the Unity version that the game needs... now you need to download THE SAME Unity version, otherwise, the game simply wont launch.
