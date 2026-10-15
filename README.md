On Plasma, try ```env -u KDE_FULL_SESSION -u XDG_CURRENT_DESKTOP kdenlive``` first. That was the cause for me.


This script is for bisecting your environment to find the variables that create the grey-screen bug. (assumes your audio DOES work)

Step 0: run ```env -i HOME="$HOME" PATH=/usr/bin:/bin XDG_RUNTIME_DIR="$XDG_RUNTIME_DIR" WAYLAND_DISPLAY="$WAYLAND_DISPLAY" DISPLAY="$DISPLAY" DBUS_SESSION_BUS_ADDRESS="$DBUS_SESSION_BUS_ADDRESS" kdenlive```

if this does not work, do not bother with this script. If this does work continue.

Step 1: Save the script as kdenlive-envhunt to your downloads folder.

Step 2: Open kdenlive, put a clip in your timeline, save the project as envtest.kdenlive in your home directory. (recommended to do this with step 0 command.)

Step 3: Run the script ```bash ~/Downloads/kdenlive-envhunt ~/envtest.kdenlive```

Step 4: Your Kdenlive will open, attempt to play the video and click on it.

Step 5: Close Kden, discard if it asks to save.

Step 6: Indicate with a y/n in the terminal if the video showed.

Step 7: Repeat till script displays Environment Variables that are conflicting with normal use.


Once you have your culprit(s) you can now launch Kdenlive using ```env -u KDE_FULL_SESSION -u XDG_CURRENT_DESKTOP kdenlive``` replace (KDE_FULL_SESSION) and (XDG_CURRENT_DESKTOP) with your results. If you have more than two, simply add another -u (PARAMETER, if you have less, delete one of the -u's and following parameter.
