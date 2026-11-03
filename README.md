# NTB English Test

[![Vercel App](https://img.shields.io/badge/LIVE_DEMO-VERCEL_APP-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://ntbenglish.vercel.app)

A website for reviewing and testing English based on the “13 English tenses”
series by the I LOVE IELTS channel.
It is a static site: no server and no build command are needed.

## Home

The home page has two sections:

- **Review**: practice by lesson, no timer, tab switching allowed.
- **Test**: a combined test, 60 minutes, 85 questions.

## Review

- **Lesson 1 — Present Simple**: 32 questions (20 multiple choice, 9 writing/ordering, 3 reading).
- **Lesson 2 — Present Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 3 — Present Perfect**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 4 — Present Perfect Continuous**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).
- **Lesson 5 — Past Simple**: 20 questions (13 multiple choice, 3 writing, 2 ordering, 2 reading).

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

Questions were newly written by me based on the grammar points of the lessons,
not copied verbatim from the exercises in the videos.

## Test

- 3 different papers, each with 85 questions: 20 Present Simple +
  20 Present Continuous + 15 Present Perfect + 15 Present Perfect Continuous
  + 15 Past Simple.
- Every lesson block in a paper contains all three parts: multiple choice,
  writing, and ordering. Present Simple and Present Continuous blocks have
  14 multiple choice, 3 writing, and 3 ordering questions each; the
  Present Perfect, Present Perfect Continuous, and Past Simple blocks have
  9 multiple choice, 3 writing, and 3 ordering questions each.
- Each time the test starts, the system picks one of the 3 papers at random,
  then shuffles the question order and the answer order.
- Test questions are newly written and do not repeat the review questions.
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
- Arrow keys move to the previous/next question, except while typing in
  an input field, choosing an answer, or when a dialog is open.

## Login

The “Đăng nhập” button in the top-right corner logs in to the admin account.
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

Reloading the page in the middle of a test loses the answers and restarts
the timer. Results are only calculated in the browser being used and are
not saved to a server.

## File structure

- `index.html`: interface, test engine, and Lesson 1 review questions.
- `data.js`: Lesson 2, Lesson 3, Lesson 4, and Lesson 5 review questions, and the 3 test papers.

## Deploy to Vercel

Import this repository on Vercel, choose a static site, no build command,
keep the default root directory, and deploy.
