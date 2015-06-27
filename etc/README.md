# /etc

Enhancements to scripts under the /etc folder:

- rc.local:
    - The original rc.local file would not give much time to pair my Bluetooth PS3 controllers. I've modified it a bit:
        - Detects if the Bluetooth driver is in a bad state and will restart the RPi
        - Initially ensures the driver is in PISCAN mode
        - Assuming the driver is in a good state, it will output a "Connect your controller(s) now!" message and wait 60s for the controllers to pair
        - Puts the driver in NOSCAN mode at the end
    - Future enhancements:
        - How to handle no controllers pairing in 60s? EmulationStation still requires a keyboard or SSH session to restart or shutdown the RPi.
    - Installation:
        - Installation is manual...
            0. Backup your original rc.local
            1. Overwrite it with this modified version
