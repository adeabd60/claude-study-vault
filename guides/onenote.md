# Notes app: OneNote (default)

OneNote comes with your UoN Microsoft 365 account, saves to your UoN OneDrive automatically, and works on Windows, Mac, iPad and phone with the same login. Nothing to install on most laptops.

## Set up

1. Open OneNote, sign in with your UoN account, and create a notebook, e.g. `Year 2`.
2. Mirror the kit's layout:
   - **Section group** per term: `Term 1`, `Term 2`
   - **Section** per module: `EXAMPLE101 Example Module`
   - **Pages** in each section: `EXAMPLE101 Home`, then per week `Week 1 - Notes`, `Week 1 - Session 2026-10-20`, `Week 1 - Flashcards`
3. In `MY-SETUP.md`, keep `Notes app: OneNote`.

## Pasting Claude's notes in

Claude writes notes as normal formatted text in the chat (not code), so:

1. Use the copy button under Claude's reply, or select the reply text and copy.
2. Paste into the OneNote page. Headings, bold, lists and tables carry over. If formatting comes through as raw `#` and `**` symbols, select the reply text itself instead of using the copy button.

## What's different from Obsidian

- **Diagrams**: OneNote can't draw Mermaid. Claude shows a diagram in chat when it can (screenshot it in) or gives an indented outline instead.
- **Maths**: simple maths comes as normal symbols (x², ∀, ≤). Bigger equations also come as LaTeX: in OneNote use **Insert › Equation**, then paste the LaTeX (supported in recent OneNote for Windows and Mac).
- **Flashcards**: a Question | Answer table. To review them properly, set `Flashcards go to: Anki` or `Quizlet` in `MY-SETUP.md` and Claude gives you an import-ready list.
- **To-do**: use OneNote checkboxes (Ctrl+1) on the Home page. The iPhone Reminders Shortcut doesn't work with OneNote.
- **Links between notes**: Claude writes "see Week 2 Notes"; add a OneNote link yourself if you want one (right-click a page › Copy link to page).
