# Deploy this desktop to any GitHub account — one command

## What you get
A full Cinnamon desktop (Firefox preinstalled) in a browser tab, private to your GitHub login.

- URL: `https://<codespace-name>-6080.app.github.dev`
- VNC password: `password` (change below before deploying if you want)

## Deploy (from any machine with the GitHub CLI logged into the target account)

```bash
gh repo fork AndnixSH/codespace-desktop --clone=false   # skip if you forked kasmweb fork already
gh codespace create -R <YOUR_USERNAME>/codespace-desktop -m basicLinux32gb
```

First build takes ~20-25 min (Cinnamon is heavy). Then:

```bash
gh codespace ports -c <codespace-name>   # shows the -6080.app.github.dev URL
```

Open the URL, sign in with GitHub, click Connect (password: `password`).

## Notes
- Free tier auto-stops after ~30 min idle; the desktop resumes when you reopen the URL.
- 2-core is fine for browsing; 4-core (paid) noticeably smoother.
- Rebuilding the codespace wipes nothing important — VNC password and noVNC are re-created by the devcontainer lifecycle scripts.
