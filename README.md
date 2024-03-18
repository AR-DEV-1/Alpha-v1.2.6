# Minecraft Alpha-v1.2.6

This is based off of real Minecraft Alpha v1.2.6, the decompiled source code has been ported to TeaVM with as minimal changes as possible. Worlds and settings are saved to your browsers local storage using IndexedDB, worlds are compressed using jzlib's `GZIP`, existing uncompressed worlds will be loaded uncompressed and be compressed when the game writes to the file.

![Screenshot (23)](https://github.com/PeytonPlayz595/Alpha-v1.2.6/assets/106421860/84c133e9-935e-4edf-8ced-66b752bc5800)

### [Play the official release (No download required)](https://peytonplayz595.github.io/Alpha-v1.2.6/web/)

### [Download offline HTML file](https://github.com/PeytonPlayz595/Alpha-v1.2.6/blob/main/offline_download/Alpha_Offline_Download.html)

# Making a client

### Gradle
After modifying files in `src/main/java` you can compile your changes to the javascript client by running `gradlew generatejavascript`, for linux run `./gradlew generatejavascript`. This will then transpile the Java code into javascript files in `web/js/`.

### Textures
The textures are compiled into `resources.mc` using [Laxdude](https://github.com/lax1dude)'s EPK Compiler. The resources are located in `resources/`, after modifying the resources you can compile them using `CompileEPK`, and for Linux use `./CompileEPK.sh`.

### Offline Download
As of right now there is no system to compile an offline download, so you will have to manually copy and paste the javascript from `web/js/app.js` into the HTML file, for the `resources.mc` just encode the file using [Base64](https://www.base64encode.org/) and paste it into the assets div.

# Muliplayer
Multiplayer has been successfully rewritten and thoroughly tested. It seems to be pretty stable but it had to be removed due to a glitch in Singleplayer's chunk loading, the issue lies within Alpha's multiplayer code somewhere and I am unable to pinpoint the exact cause of the issue so until I am able to figure it out, multiplayer will not be avalible.

If you are really impatient and cannot wait then go through the commit history and find commit 62af5c9 titled "oops" and download the offline download from there, **THIS VERSION IS BUGGED AND CHUNK LOADING IN SINGLEPLAYER IS EXTREMELY BUGGY, SOME CHUNKS MAY NOT EVEN SAVE AT ALL!**

If you do decide to use this version (not recommended) just download the Alpha v1.2.6 server software from web archive and use websockify to proxy it to websockets.

# Texture Packs
This is pretty much self explanitory, just make sure the textures have the same structure as in `resources/`, and then add it to a ZIP file, if a texture pack does not work then most likely it is not for this version of Minecraft. You're probably gonna have to make your own texture pack, texture packs for Alpha are very rare these days.

# How to decompile older Minecraft versions
To decompile older Minecraft versions you can use RetroMCP!

RetroMCP is a rewrite of MCP that adds support for many different older versions of Minecraft that were never supported by MCP. To get started head over to the [RetroMCP GitHub](https://github.com/MCPHackers/RetroMCP-Java/releases) and download the latest release. Make sure you have Java 8 (or higher) installed in order to run and decompile Minecraft versions.

# Code used within this project

- Modified version of Lax1dude's OpenGL Emulator from [0.30-WebGL](https://github.com/PeytonPlayz595/0.30-WebGL/)
- Decompiled Minecraft Alpha v1.2.6 source code
