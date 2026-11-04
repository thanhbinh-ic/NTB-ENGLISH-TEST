# NTB English Test

[![Vercel App](https://img.shields.io/badge/LIVE_DEMO-VERCEL_APP-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://ntbenglish.vercel.app)

A website for reviewing and testing English based on the “13 English tenses”
series by the I LOVE IELTS channel.
It is a static site: no server and no build command are needed.

## Home

The home page has two sections:

- **Review**: practice by lesson, no timer, tab switching allowed.
- **Test**: a combined test, 60 minutes, 40 questions.

## Review

- **Lesson 1 — Present Simple**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 2 — Present Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 3 — Present Perfect**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 4 — Present Perfect Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 5 — Past Simple**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 6 — Past Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 7 — Past Perfect**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 8 — Past Perfect Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 9 — Simple Future**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 10 — Near Future**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 11 — Future Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 12 — Future Perfect**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 13 — Future Perfect Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).

Review uses the same test interface: choose answers, write sentences,
move between questions with buttons or arrow keys, submit, then see the score
and the answers. Review has no timer and allows tab switching, but still
blocks copying and viewing source code. Review submissions always show
the answers, even when not all questions were answered.

Sources:

- Lesson 1 — Present Simple: https://youtu.be/BmKkDuO_nkk
- Lesson 2 — Present Continuous: https://youtu.be/dIIG9m649-g
- Lesson 3 — Present Perfect: https://youtu.be/QwrSs0SC5ow
- Lesson 4 — Present Perfect Continuous: https://youtu.be/A86yKxubFJw
- Lesson 5 — Past Simple: https://youtu.be/w096ct4263w
- Lesson 6 — Past Continuous: https://youtu.be/DLNAZDJ3apU
- Lesson 7 — Past Perfect: https://youtu.be/RaXptr8ZLOs
- Lesson 8 — Past Perfect Continuous: https://youtu.be/p22NpP_wUVM
- Lesson 9 — Simple Future: https://youtu.be/OnbMCBX-sQs
- Lesson 10 — Near Future: https://youtu.be/ZgUlJSCXixE
- Lesson 11 — Future Continuous: https://youtu.be/sQY2PHTrmyQ
- Lesson 12 — Future Perfect: https://youtu.be/k0d448RS9Tw
- Lesson 13 — Future Perfect Continuous: https://youtu.be/boSJ6etKouA

Questions were newly written by me based on the grammar points of the lessons,
not copied verbatim from the exercises in the videos.

## Test

- 10 test sets covering all 13 lessons. Each time a test starts, the system
  draws 40 questions at random from the 10 sets: 20 multiple choice,
  10 writing, and 10 ordering, with at least one question from every lesson.
  The question order and the answer order are shuffled.
- A new test never repeats the previous test's questions: the previous
  test's question IDs are stored in the browser and excluded from the draw
  (the IDs are saved when the test is drawn, so quitting mid-test and
  starting again also gives fresh questions; if the remaining pool ever
  runs short, the draw falls back to the full pool).
- Test questions are newly written and do not repeat the review questions.
- After submitting, the result is graded as Giỏi (90% or more),
  Khá (70–89%), Đạt (50–69%), or Chưa đạt (below 50%).
- Time limit: 60 minutes, counting down. The timer turns yellow with
  10 minutes left and red with 1 minute left; the test is submitted
  automatically when time runs out.
- Submitting with unanswered questions shows only the score and the time used,
  without answers or explanations. Exception: the admin account still sees
  the full answers.

## Mechanisms during the test

- Anti-copy: without logging in, text cannot be selected, copied, cut,
  and the right-click menu is blocked; typing and editing in the answer
  fields still work.
- Source-view shortcuts are blocked during the test: F12, Ctrl+Shift+I/J/C,
  Ctrl+U, Ctrl+S.
- Anti-cheat uses one shared counter: switching tabs, minimizing the window,
  losing focus, and resizing the window (counted only when the width changes
  by more than 200px). The first violation shows a warning; the second
  submits the test immediately. Signals less than 2 seconds apart count as
  one violation. The admin account is exempt from anti-cheat.
- Every dialog hard-locks the page behind it: while any dialog is open,
  background clicks, background scrolling (mouse wheel, touch, keyboard),
  and keyboard focus outside the dialog are blocked. Only the dialog's own
  content scrolls (for example the long account dialog), so the user must
  use the dialog's own buttons to continue.
- Arrow keys move to the previous/next question, except while typing in
  an input field, choosing an answer, or when a dialog is open.

## Accounts, statistics, and leaderboard

There is a single “Đăng nhập” button in the top-right corner. When nobody
is signed in, it opens a login dialog; signing in with the admin account
opens the admin interface, while any other account signs in as a normal
user. The dialog also links to registration and to forgot password, and
when someone is signed in, the same button (showing the avatar and the
username, or “Thanh Bình” for the admin) opens the account dialog, where
the user can change their avatar, change their username, or sign out.
Statistics are only on the home screen button, not in the account dialog,
so a test in progress cannot be abandoned through the account dialog
without being scored.
Registration needs a full name, a username, an email, and a password
(at least 6 characters, typed twice for confirmation); usernames and
emails must be unique, and the
username “admin” is reserved. After a
successful registration or login, the home page greets the user by username
above the buttons
and shows their current points, and a popup confirms the registration,
login, or sign-out (sign-out asks for confirmation first).
A signed-in user can change their username by tapping the small pencil
next to the username in the account dialog, which reveals an inline input
(press Enter or “Lưu tên mới” to save, “Hủy” to close); points,
statistics, and avatar are kept, and the new name must not be taken or
reserved.
Avatars are emoji: tapping one in the account dialog changes it
immediately, and it appears on the header button, the greeting, and the
leaderboard.

- **Statistics** (“Thống kê của tôi”): number of completed reviews, number
  of tests taken, number of passed tests, and ranking points.
- **Leaderboard** (“Bảng xếp hạng”): all accounts ranked by points,
  with the top 3 on a podium (2nd, 1st with a crown, 3rd). A new account
  starts with 100 points. After a test, passing
  (50% or more) adds 1 point per correct answer; failing subtracts
  10 points, and points never go below 0. Reviews do not change points.
  The points change is shown on the result screen.
- The leaderboard also shows 100 virtual accounts with Vietnamese
  nicknames, with points spread from low to high. Each virtual account's
  points shift slightly from day to day (derived from its name and the
  current date), so ranks move and the list shows “Thăng hạng” (moved up)
  or “Xuống hạng” (moved down) arrows compared with the previous day.
  Real accounts created on the browser appear in the same list, with the
  signed-in account marked “BẠN”.
- **Forgot password** is interface only: it asks for the registered email
  and shows a confirmation that a reset email was sent. No email is
  actually sent, because the site has no server.
- Accounts, statistics, and the leaderboard are stored in the browser's
  localStorage, so they only exist on the browser where the account was
  created, and the leaderboard only lists accounts created on that browser.
  Passwords are stored only as SHA-256 hashes.

## Login

The single “Đăng nhập” button in the top-right corner logs in to the admin account
when the admin username and password are entered.
While logged in, the correct answer for each question is shown during the test,
for testing the system. The login state is kept only for the current browser
session.

Note: this is a static site in a public repository and the answers are in
the page source, so the admin login is only a display gate for testing,
not real security. Change the password by replacing the SHA-256 hash in
`index.html` before sharing widely. Blocking source viewing on a static site
is only a deterrent: it cannot block the browser menu, `view-source:`,
or downloading the file.

## Reloading and results

Reloading the page in the middle of a test abandons it: the answers and
the timer are lost, the test is counted as taken and failed (−10 points,
no pass), and a notice is shown on the next load. Logging out during a
test also abandons it the same way and returns to the home screen, instead
of staying on the test screen. Renaming during a test does not dodge
scoring either: the result is recorded against the account that started
the test. Results are only calculated in the browser being used and are
not saved to a server.

## Add to home screen (iPhone / Android)

- iPhone: `apple-touch-icon.png` (180×180) is used as the home screen icon,
  and the page declares itself capable of running as a standalone web app
  with the title “NTB English Test” and the default status bar style.
- Android / Chrome: `icon-192.png` (192×192) is the app icon, with
  `mobile-web-app-capable` set.
- The tab favicon is still `favicon.svg` (same artwork).

## File structure

- `index.html`: interface, test engine, and Lesson 1 review questions.
- `favicon.svg`: tab favicon (blue “NTB” badge artwork).
- `apple-touch-icon.png`: 180×180 home screen icon for iPhone.
- `icon-192.png`: 192×192 app icon for Android/Chrome.
- `data.js`: Lesson 2, Lesson 3, Lesson 4, Lesson 5, Lesson 6, Lesson 7, Lesson 8, Lesson 9, Lesson 10, Lesson 11, Lesson 12, and Lesson 13 review questions, and the 10 test sets.

## Deploy to Vercel

Import this repository on Vercel, choose a static site, no build command,
keep the default root directory, and deploy.
