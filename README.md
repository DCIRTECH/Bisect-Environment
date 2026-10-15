This script is for bisecting your environment to find the variables that create the grey-screen bug. (assumes your audio DOES work)

Step 0: run "env -i HOME="$HOME" PATH=/usr/bin:/bin XDG_RUNTIME_DIR="$XDG_RUNTIME_DIR" WAYLAND_DISPLAY="$WAYLAND_DISPLAY" DISPLAY="$DISPLAY" DBUS_SESSION_BUS_ADDRESS="$DBUS_SESSION_BUS_ADDRESS" kdenlive"
if this does not work, do not bother with this script. If this does work continue.

Step 1: Save the script as kdenlive-envhunt to your downloads folder.
Step 2: Open kdenlive, put a clip in your timeline, save the project as envtest.kdenlive in your home directory. (recommended to do this with step 0 command.)
Step 3: Run the script "bash ~/Downloads/kdenlive-envhunt ~/envtest.kdenlive"
Step 4: Your Kdenlive will open, attempt to play the video and click on it.
Step 5: Close Kden.
Step 6: Indicate with a y/n in the terminal if the video showed.
Step 7: Repeat till script displays Environment Variables that are conflicting with normal use.
