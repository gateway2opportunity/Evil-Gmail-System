Evil Gmail System - portable copy
=================================

Double-click  local-ops\local-ops.exe

Works on any Windows 10 or 11 machine. Nothing to install first.


FIRST RUN ON A NEW MACHINE
--------------------------
1. The load portal runs three checks (boot, engine, data), then offers
   "start fresh" or "import".
2. Choose IMPORT and pick the .zip you made with
   Settings -> system transfer -> export system (.zip) on the machine that
   has your data. Contacts, templates, send profiles, campaigns, uploads and
   screenshots all come back.
3. After the import completes, press "enter the system".

You should not have to type anything. If the lock screen does appear, the
token is in  local-ops\data\admin_token.txt  on this machine.


IF THE WINDOW DOES NOT OPEN
---------------------------
The window uses the Microsoft Edge WebView2 runtime. Every normal Windows 10
and 11 install already has it.

If a machine somehow does not, the app notices on first launch, installs it
from the bundled  MicrosoftEdgeWebView2Setup.exe  (about a minute, offline),
and opens the window. If that install cannot run, the dashboard opens in your
normal browser instead at http://127.0.0.1:8765 - the system still works, you
just lose the native window and the tray icon.


ASHLEY'S VOICE
--------------
Drop your mp3s into  local-ops\voice\ashley\<cue>\  where <cue> is one of:

    startup    played when the window opens
    success    played when a load or import finishes clean
    error      played when something fails
    watchdog   played when a stalled campaign is restarted
    console    played when a console error is logged

The script and the voice settings for each cue are in
local-ops\voice\ashley\PROMPTS.md. If a folder is empty, Windows reads the
default line in a female voice instead. Nothing breaks either way.


WHAT IS NOT IN THIS FOLDER
--------------------------
No .env, no database, no admin token. That is deliberate: this copy carries
no secrets, so it is safe to copy, and it cannot be used to read another
machine's data. The first launch mints its own token, so you are never locked
out.


KEEP ONE COPY RUNNING
---------------------
Do not run two copies against the same folder at the same time. The app
refuses to start a second instance from one folder for exactly that reason.
