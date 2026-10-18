# Claude route: Cowork (laptop, optional)

The most automatic route. In the **Claude desktop app**, a Cowork chat can be given access to a folder on your laptop, so Claude reads your lecture files and writes notes straight into the folder. Laptop only; for iPad sessions use [Projects](claude-projects.md).

## Set up (once)

1. Install the Claude desktop app (Windows or Mac) and sign in.
2. Copy the `kit/` folder into your study folder in OneDrive as `_system/`, e.g. `OneDrive/Uni/Year 2/_system/`, and fill in `_system/MY-SETUP.md` with `Claude route: Cowork`.
3. Open a **Cowork** chat (one per module works well) and give it access to `Uni/Year 2`. Menu names may differ a little between versions.
4. Say:

   > Read _system/TEACHING-METHOD.md, then set up new module EXAMPLE101 Example Module in Term 1.

## How it works with each notes app

- **Obsidian / Markdown app** with the vault in the same folder: Claude writes everything (Notes, Pack, Session, Flashcards, Home) into the vault.
- **OneNote**: Claude can't write into OneNote. It writes its working files (`_module.md`, `PROGRESS.md`, Packs, Tutorial Breakdowns, Home) as `.md` files in the OneDrive folder, and gives you the Notes, Session note and flashcards in chat to paste into OneNote.

## Optional: Claude in Chrome

With the Claude in Chrome extension and you signed in to Moodle, `check EXAMPLE101` or `what's due?` reads your Moodle page (read only: Claude never submits or posts anything) and updates the Home page. Without it, paste the Moodle page text into the chat.
