# iPhone Reminders sync (optional)

> [!note] Only for Markdown Home pages
> This needs each module's Home page to be a Markdown file (`CODE Home.md`) in OneDrive, i.e. Obsidian or another Markdown app, or the Cowork route. It doesn't work with OneNote. If you use it, set `iPhone Reminders sync: yes` in `MY-SETUP.md`.

A Shortcut on your iPhone reads each module's Home page from OneDrive and:

1. **Ticks on the Home page** anything you completed in Reminders.
2. **Adds to Reminders** any open `- [ ]` task that isn't there yet, with its 📅 due date.

Reminders go into one list, **Uni**, titled like `EXAMPLE101 · Check Moodle for Coursework 1 deadline`. Set it to run automatically a few times a day.

> [!warning] Untested
> This was written from the Shortcuts action names, without building it on a real phone. If an action's name or option differs on your iOS version, pick the closest match. Test it once by hand before automating, and back up your Home pages first: the Shortcut overwrites them.

## Before you start

- Install the **OneDrive** app on the iPhone, sign in with your UoN account, and check that `Uni › Year 2` appears in the **Files** app under OneDrive. (Another cloud drive works too if its app appears in Files.)
- In Reminders, create a list called **Uni**.

## Build the Shortcut

Open Shortcuts › **+** › name it `Uni to-do sync`. Add these actions in order. "Set Variable" names are in **bold**. Below, `<study folder>` means OneDrive › Uni › Year 2 (or wherever your Home pages live).

**A. The module list**
1. **Dictionary** with one Text entry per module (paths relative to the study folder):
   - `EXAMPLE101` → `Term 1/EXAMPLE101 Example Module/EXAMPLE101 Home.md`
   - add one line per module you set up
2. **Repeat with Each** item in Dictionary (this gives each key, e.g. `EXAMPLE101`). Inside the repeat:
3. **Set Variable** **Code** to Repeat Item.
4. **Get Dictionary Value** for key **Code** in Dictionary. **Set Variable** **Path**.
5. **Get File from Folder**: Folder = `<study folder>`, File Path = **Path**, Error If Not Found = off.
6. **Get Text from Input** (the file) › **Set Variable** **Note**.

**B. Reminders → Home page (tick completed tasks)**

7. **Find Reminders** where List is `Uni`, Title begins with **Code**, Is Completed is true.
8. **Repeat with Each** reminder:
   - **Get Details of Reminders**: Title.
   - **Replace Text**: find `[Code] · ` (the Code variable, then space, middot, space) in the title, replace with nothing › **Set Variable** **Task**.
   - **Replace Text**: in **Note**, find `- [ ] [Task]`, replace with `- [x] [Task]` › **Set Variable** **Note**.
9. End Repeat.
10. **Save File**: input **Note**, Ask Where to Save = off, Destination = `<study folder>`, Subpath = **Path**, Overwrite If File Exists = on.

**C. Home page → Reminders (add new tasks)**

11. **Match Text**: pattern `(?m)^- \[ \] (.+)$` in **Note**.
12. **Repeat with Each** match:
    - **Get Group from Matched Text**: group 1 › **Set Variable** **Raw**.
    - **Match Text**: pattern `\d{4}-\d{2}-\d{2}` in **Raw** › **Set Variable** **Due**.
    - **Replace Text** (Regular Expression on): find `\s*📅.*$` in **Raw**, replace with nothing › **Set Variable** **Clean**.
    - **Text**: `[Code] · [Clean]` › **Set Variable** **Title**.
    - **Find Reminders** where List is `Uni` and Title is **Title** (completed or not), Limit 1.
    - **Count** › **If** Count is 0:
      - **If** **Due** has any value › **Add New Reminder** **Title** to list Uni, Due Date = **Due** › Otherwise › **Add New Reminder** **Title** to list Uni › End If.
    - End If.
13. End Repeat (matches). End Repeat (modules).

## Automate it

Shortcuts › Automation › **+** › **Time of Day**, e.g. 08:00, Daily, **Run Immediately** › Run Shortcut `Uni to-do sync`. Add a second one at 18:00 if you like.

## Rules that keep it working

- Write tasks only on the Home page's **To-do** list, as `- [ ] Task 📅 2026-10-20`.
- **Don't reword an open task** after it has synced. Tick it and add a new line instead, or you'll get duplicates.
- Tick things off **in Reminders**. The next sync ticks them on the Home page. If you tick on the Home page, tick the reminder too.
- **New module:** add one entry to the Dictionary in step 1.
- **If the OneDrive app hasn't synced recently**, the Shortcut may read an old copy and overwrite newer edits. Opening the OneDrive app first helps; avoid editing the Home page on two devices at once.
