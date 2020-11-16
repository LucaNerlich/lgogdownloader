# lgogdownloader
Dockerfile for **lgogdownloader** with **Unraid**.

Download in **Unraid** via **Community Applications**.

Set the below paths via extra "path" variable:

["/home/user/.cache/lgogdownloader", "", "/home/user/downloads"]

Set the paths and following options: \
`cache` set to `/mnt/user/appdata/lgogdownloader/cache/` + `/home/user/.cache/lgogdownloader` \
`config` set to `/mnt/user/appdata/lgogdownloader/config/` + `/home/user/.config/lgogdownloader` \
`downloads` set to `/home/user/downloads` + `/mnt/user/Games_Network/GoG_Downloader/_downloads/` (create share in advance)\
Set `Extra Parameters` to: `-it` and `Console shell command` to `Bash`. 

Log into docker container via SSH shell `docker attach lgogdownloader` on Unraid \
or via Web-Terminal from Unraid Web-UI.
#### On first start:

Login to GOG via: \
`lgogdownloader --login`

**Important**: Set download folder with this command: \
`lgogdownloader --directory=/home/user/downloads --save-config`

You can set more options, for example see the following command: \
`lgogdownloader --language=de,en --platform=all --save-serials --threads 16 --info-threads 16 --save-config`

create downloads.sh file via unraid terminal with the following content:

```bash
lgogdownloader --download --include all --ignore-dlc-count --no-platform-detection --platform w+l --language en --save-changelogs --save-serials --xml-directory 'aaaMetadata'
```

See `lgogdownloader --help` for more information on this.

Now you can download your catalogue via `lgogdownloader --download` 

*Tip*: Delete unnecessary old files via `lgogdownloader --check-orphans | xargs -i rm "{}"`. 
