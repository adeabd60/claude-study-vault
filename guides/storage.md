# Storage: where your lecture files live

## Default: OneDrive (UoN account)

UoN students get OneDrive through their university Microsoft 365 account. It's on the laptop, shows up in the iPad/iPhone **Files** app (install the OneDrive app and sign in with your UoN account), and it's where OneNote saves your notebooks anyway.

Suggested layout (the same one Claude assumes):

```
OneDrive/
  Uni/
    Year 2/
      _system/                    <- the kit (only needed for free chat and Cowork)
      Term 1/
        EXAMPLE101 Example Module/
          _module.md, PROGRESS.md (free chat / Cowork)
          Week 1/                 <- slides, transcripts, tutorial sheet
```

`starter-folders/` in this repo is a ready-made copy of the `Term 1/...` part.

## Alternatives

Set `Storage for lecture files:` in `MY-SETUP.md`. Claude only needs to know so it can give the right advice; the teaching doesn't change.

| Storage | Good for | Watch out for |
|---|---|---|
| **iCloud Drive** | Obsidian on iPad | Needs iCloud for Windows on a Windows laptop |
| **Google Drive** | If you already live there | Attach files from Drive into Claude yourself |
| **Dropbox** | Simple sync | Free plan is small (2 GB) |
| **Obsidian Sync** | Obsidian vault on every device | Paid; for notes, not big slide decks |
| **Local only** | Laptop-only with Cowork | No iPad access, no backup |

## Sync caveats

- Let sync finish before switching devices. Editing the same file on two devices before it syncs creates conflict copies.
- If you leave OneDrive files as "online-only" and you're offline, Claude (Cowork) can't read them. Right-click the module folder › **Always keep on this device**.
- Your UoN OneDrive is tied to your university account. Copy anything you want to keep before you graduate.
