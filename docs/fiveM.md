# FiveM

## What is FiveM
FiveM is a multiplayer game server for GTA V usually used for roleplay games and for multiplayer.

## Final Steps before running.

```
# Only change the IP if you're using a server with multiple network interfaces, otherwise change the port only.
endpoint_add_tcp "0.0.0.0:30120"
endpoint_add_udp "0.0.0.0:30120"

# These resources will start by default.
ensure mapmanager
ensure chat
ensure spawnmanager
ensure sessionmanager
ensure basic-gamemode
ensure hardcap
ensure rconlog

# This allows players to use scripthook-based plugins such as the legacy Lambda Menu.
# Set this to 1 to allow scripthook. Do note that this does _not_ guarantee players won't be able to use external plugins.
sv_scriptHookAllowed 0

# Uncomment this and set a password to enable RCON. Make sure to change the password - it should look like rcon_password "YOURPASSWORD"
#rcon_password ""

# A comma-separated list of tags for your server.
# For example:
# - sets tags "drifting, cars, racing"
# Or:
# - sets tags "roleplay, military, tanks"
sets tags "default"

# A valid locale identifier for your server's primary language.
# For example "en-US", "fr-CA", "nl-NL", "de-DE", "en-GB", "pt-BR"
sets locale "en-US" 
# please DO replace root-AQ on the line ABOVE with a real language! :)

# Set an optional server info and connecting banner image url.
# Size doesn't matter, any banner sized image will be fine.
#sets banner_detail "https://url.to/image.png"
#sets banner_connecting "https://url.to/image.png"

# Set your server's hostname. This is not usually shown anywhere in listings.
sv_hostname "<Your Server Hostname>"

# Set your server's Project Name
sets sv_projectName "<Server Project Name>"

# Set your server's Project Description
sets sv_projectDesc "<Your Server Project Description>"

# Nested configs!
#exec server_internal.cfg

# Loading a server icon (96x96 PNG file)
#load_server_icon myLogo.png

# convars which can be used in scripts
set temp_convar "hey world!"

# Remove the `#` from the below line if you want your server to be listed as 'private' in the server browser.
# Do not edit it if you *do not* want your server listed as 'private'.
# Check the following url for more detailed information about this:
# https://docs.fivem.net/docs/server-manual/server-commands/#sv_master1-newvalue
#sv_master1 ""

# Add system admins
add_ace group.admin command allow # allow all commands
add_ace group.admin command.quit deny # but don't allow quit
add_principal identifier.fivem:1 group.admin # add the admin to the group

# enable OneSync (required for server-side state awareness)
set onesync on

# Server player slot limit (see https://fivem.net/server-hosting for limits)
sv_maxclients 48

# Steam Web API key, if you want to use Steam authentication (https://steamcommunity.com/dev/apikey)
# -> replace "" with the key
set steam_webApiKey ""

# License key for your server (https://keymaster.fivem.net)
sv_licenseKey <Server Licence from keymaster.fivem.net> 
```

Note to replace the following lines of your allready existent server.cfg on the file is located at `/root/FXServer/server-data/server.cfg`
We recomend `vim` or `nano`

Edit the file.
```
vim /root/FXServer/server-data/server.cfg
```
Change the following at the end of the file (Line 78)

```
sv_licenseKey <Server Licence from keymaster.fivem.net> 
```
How it should looks like:.

```
sv_licenseKey licensekey9024fh902hf-0d3nd3 
```

Change also (Line 45)
```
sets sv_projectDesc "<Your Server Project Description>"
```

How it should looks like:.

```
sets sv_projectDesc "My Awesome Description"
```

Change (Line 42 and 39)
```
# Set your server's hostname. This is not usually shown anywhere in listings.
sv_hostname "<Your Server Hostname>"

# Set your server's Project Name
sets sv_projectName "<Server Project Name>"
```

Should Looks like this.
```
# Set your server's hostname. This is not usually shown anywhere in listings.
sv_hostname "My Awesome FIVEM Server"

# Set your server's Project Name
sets sv_projectName "RolePlay Game"
```
Change (Line 30 and 26)
```
# - sets tags "roleplay, military, tanks"
sets tags "default"

# A valid locale identifier for your server's primary language.
# For example "en-US", "fr-CA", "nl-NL", "de-DE", "en-GB", "pt-BR"
sets locale "en-US"
```

Should looks like this.

```
# - sets tags "roleplay, military, tanks"
sets tags "roleplay"

# A valid locale identifier for your server's primary language.
# For example "en-US", "fr-CA", "nl-NL", "de-DE", "en-GB", "pt-BR"
sets locale "fr-FR"
```
____

## Launch the server FiveM.

Wake the process.

```
cd ~/FXServer/server-data && bash ~/FXServer/server/run.sh +exec server.cfg
```