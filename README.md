# ChatGPT Recent Pop Quiz for Anki

Automatically generate and open a multiple-choice pop quiz after every 20
reviews, using the cards in that review batch. The add-on remembers reviewed
cards and unfinished batch progress in each Anki profile and records quiz
attempts locally. Answer choices are shuffled locally with matching answer keys.

## Installation

1. Install `ChatGPT_Recent_Pop_Quiz.ankiaddon` from Anki's Tools > Add-ons >
   Install from file menu, then restart Anki.
2. Install Codex CLI if it is not on this computer. A ChatGPT account with
   Codex access is required; ChatGPT Plus is not required for every account,
   but usage limits depend on the user's ChatGPT plan. The add-on finds a PATH
   installation and common editor-extension installs automatically. Use the
   connection-settings button to select `codex.exe` if it cannot find it.
3. Study 20 cards and the quiz opens automatically. Complete OpenAI's browser
   sign-in if prompted. Change the interval under Tools > ChatGPT Recent Pop
   Quiz > Automatic Quiz Interval (0 disables pop-ups). Generate Pop Quiz
   remains available for manual quizzes from your most recent cards.

The add-on is portable between devices and Anki profiles. Each person
connects their own ChatGPT account on the device they use; no account, login
password, or API key is included in the add-on package. Sign-in happens in
OpenAI's browser flow. The connection is stored by Codex on that device, not
in this add-on folder, so it is not transferred when you share the
`.ankiaddon` file.

The first sign-in uses OpenAI's own login page. Codex remembers and refreshes
the ChatGPT login on this computer. The add-on never asks for your password or
an API key. Later quizzes generate inside Anki without copying prompts or
visiting the ChatGPT website. Your Codex access and usage limits apply.

Review snapshots and quiz scores are stored locally in this add-on's
`user_files` directory, separated by Anki profile. They are not added to your
Anki cards and are not included when the clean `.ankiaddon` package is shared.
The most recent card contents are sent to the signed-in Codex service when
you generate a quiz. By default, rendered card sides and note fields are sent;
set `include_note_fields` to `false` if you want to send less context. Generated
questions should still be checked for accuracy.

Codex is a separate OpenAI product from ChatGPT web chats. This add-on uses
your ChatGPT account to authenticate Codex, but does not read your ChatGPT
conversation history or ChatGPT memory.

## Quiz controls

Set the number of questions, choices, difficulty, and generation speed in the
quiz window. Normal mode keeps the familiar study-question style. Exam style
uses more application-focused questions and closer misconception-based
distractors while staying grounded in the reviewed cards. Fast generation uses
lower reasoning effort, compact prompt data, and shorter explanations;
Balanced sends more context and gives Codex more reasoning time for difficult
material. Fast is intended to reduce latency, but network and service load can
still make one quiz slower than another.

The defaults can also be changed under Tools > ChatGPT Recent Pop Quiz. If a
quiz cannot be generated, the reason appears in the window. Closing the window
stops any running generation process.

