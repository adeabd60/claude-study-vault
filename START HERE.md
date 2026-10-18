# Start here

This kit turns Claude into a tutor that teaches you each week's content from **your own lecture files** and gets you to the point where you can do the tutorial yourself. It's set up for University of Nottingham students but works anywhere. It's inspired by [amosblomqvist/learn](https://github.com/amosblomqvist/learn) and the video [*How I Use AI to Learn Things*](https://www.youtube.com/watch?v=kzcI5F4tGiU).

## 1. Pick your setup (defaults in bold)

| Choice | Default | Other options | Guide |
|---|---|---|---|
| How you use Claude | **Claude Projects** (laptop, iPad, phone) | Free chat · Cowork (desktop app, writes files for you) | [Projects](guides/claude-projects.md) · [Free chat](guides/claude-free-chat.md) · [Cowork](guides/claude-cowork.md) |
| Notes app | **OneNote** (comes with your UoN account) | Obsidian (recommended upgrade) · Notion · any Markdown app | [OneNote](guides/onenote.md) · [Obsidian](guides/obsidian.md) · [Others](guides/other-notes-apps.md) |
| Where lecture files live | **OneDrive** (UoN account) | iCloud · Google Drive · Dropbox · local | [Storage](guides/storage.md) |

Not sure? Use the defaults: they need nothing beyond your UoN login and a Claude account, and they work on iPad.

## 2. Fill in `kit/MY-SETUP.md`

Open it in any text editor (Notepad is fine) and change the lines that differ from the defaults: your notes app, Claude route, devices, year and course.

## 3. Set up Claude

Follow the guide for your Claude route above. In short:
- **Projects:** one Project per module; upload `kit/TEACHING-METHOD.md`, your `MY-SETUP.md` and `kit/templates/`.
- **Free chat:** attach those files at the start of each session.
- **Cowork:** copy `kit/` into your OneDrive study folder as `_system/` and give the chat access to that folder.

Then say: `set up new module CODE Name in Term 1`.

## 4. Each week

1. Save the week's slides, transcripts and tutorial sheet to `Uni/Year 2/Term 1/CODE Name/Week N/` in OneDrive.
2. `prep week N of CODE` → Claude writes the week's Notes, a Pack (its teaching plan) and a Tutorial Breakdown.
3. `teach me week N, I have 45 minutes` → a plan and a dependency map, then one idea at a time with check questions.
4. `coach me on week N question 3` → you attempt; Claude gives hints, one rung at a time.
5. `end session` → session note, flashcards, progress entry, to-dos.

Other phrases: `quiz me on CODE`, `check CODE` / `what's due?` (Moodle), `research X`.

## Academic integrity

Set the **tutorial policy** in each module's `_module.md`. If it's `assessed` or `unknown`, Claude only gives hints, never answers. Never paste assessed coursework or exam questions in for answers, and check the UoN and module guidance on using generative AI.

## If something goes wrong

- **Claude ignores the method:** start the chat with "Follow TEACHING-METHOD.md and MY-SETUP.md".
- **Claude forgot last session:** it only knows what's in the Project or attached. Check you saved the `PROGRESS.md` entry and updated Pack it gave you.
- **A PDF is unreadable:** it's probably scanned. Export a text version or tell Claude to skip it.
- **Pasted notes look like `**this**`:** see [OneNote › Pasting](guides/onenote.md#pasting-claudes-notes-in).
