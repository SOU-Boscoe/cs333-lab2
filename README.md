# cs333-lab2
JS event handlers + functions + loops: build a drum kit 🥁

Do each step below, and **answer the questions right here in this `README.md` file** as you go (type your answers under each question).

**How this lab works (two things to hand in):**
- **Your code:** make your own copy of this lab (click **Use this template**, or clone it),
  do your work, and **push it to your own GitHub repo** so I can see your code.
- **Your live drum kit:** **SFTP your lab folder to your web folder on `lampforall`** so it
  runs at `.../students/yourname/lab2/`.

You'll submit links to both in Moodle (see the last step).

> ⚠️ **Two rules that keep "it works on my laptop" working on the server too:**
> 1. **Relative paths only.** Write `sounds/snare.mp3`, never `/sounds/snare.mp3`. A leading `/`
>    means "the root of the whole server," and your site lives under `/students/yourname/lab2/`.
> 2. **Filenames are case-sensitive on the server.** The server runs Linux: `Snare.mp3` and
>    `snare.mp3` are *different files* there, even though your Mac/Windows laptop treats them as the
>    same. Match the spelling *exactly*, including capitals and hyphens.

## Part 1: clicking

1. Open `index.html` with live preview. Notice there's no `<script>` tag yet. Create your JS in
   `index.js` and add the `<script>` tag yourself. Where in the page should it go, and why?
   (Hint: what happens if your script looks for the buttons before they exist?)
2. Add an event listener to **each** drum button. Use a **loop**, not seven copies of the same code.
   (Hint: `document.querySelectorAll(".drum")`)
3. Inside your listener, `console.log` which button was clicked. Try `this.innerHTML`.
   Then try writing the listener as an **arrow function**. What happens to `this`, and why?
   (Look back at the `this` slides.)
4. Add a drum sound to the listener. Start with **one** sound for every button:
   ```js
   let sound = new Audio("sounds/tom-1.mp3");   // relative path!
   sound.play();
   ```
5. In `styles.css`, give each button a background image (`.w`, `.a`, `.s`, ...), using the files in `images/`.
   Note: paths in a CSS file are relative to **the CSS file**, not the HTML page.
   Check every filename against the real file *exactly* (case and hyphens count on the server).
6. Give each button its own sound that matches its image, so you have a playable drum kit.
   (Hint: a `switch` on the button's letter works well, and so does `if`/`else if`.)
   Watch out: the image and sound names don't match each other (`kick.png` vs `kick-bass.mp3`,
   `tom1.png` vs `tom-1.mp3`). Copy the real names.

## Part 2: the keyboard

7. Make the keyboard play the drums too: pressing `w` plays the same sound as clicking the `w` button.
   One way: add a `keydown` listener to the whole `document`, and use `event.key` to see which key was pressed.
8. Don't repeat yourself: clicking and typing should both call **the same function** that plays a sound
   for a given key. How did you organize that?
9. Use `console.log` to see what's happening while you build this. Important! **Leave these in your code.**
10. Comment your code in an educational way: not for the public, but to write down how everything works. I will be looking for this!
11. Optional: make the button visibly react when played (hint: there's a `.pressed` class in the CSS, plus `classList` and `setTimeout`).

## Deploy it

12. Test everything locally first.
13. However you have your SFTP set up, upload your lab folder to your web folder as `lab2/`.
    You don't need to upload the hidden `.git` folder (the server won't serve it anyway).
14. Link `lab2/` from your site's `index.html`, and link back to your home page from the drum kit.
15. Open your live drum kit at `https://lampforall.cis251296.projects.jetstream-cloud.org/students/yourname/lab2/`
    and make sure **every** image, sound and link works there, not just locally.
16. **Works locally but broken on the server?** Open DevTools (right-click → Inspect) → **Console** and **Network** tabs,
    and look for red **404** errors. Almost every time it's one of the two rules at the top:
    a leading `/` in a path, or a filename whose case or spelling doesn't match.
    Did you hit one? Which one, and how did you fix it?
17. Push this repo (your code **and** this README with your answers) to **your own GitHub repo**.
18. Submit in Moodle two links: (1) your GitHub repo, and (2) your live drum kit. Labs are submitted in Moodle every week. That is how I receive your work.
