# lgogdownloader
Dockerfile for lgogdownloader with Unraid.

Download in Unraid via Community Applications.
Select the paths where to store cache, login information and downloads.

Log into docker container via SSH shell `docker attach lgogdownloader` on Unraid or via Web-Terminal from Unraid Web-UI.
Change into right permission context via `su user`.
Login to GOG via `lgogdownloader --login`

**Important**: Set download folder `lgogdownloader --directory=/home/user/downloads --save-config`

Now you can download your catalogue via `lgogdownloader --download` or set other options.
See `lgogdownloader --help` for more information.