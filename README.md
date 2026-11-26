# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts. It runs on Node.js and uses built-in terminal input and file-system APIs; no third-party runtime packages are required.

## Table of contents

- [Overview](#overview)
- [Features](#key-features)
- [Technology stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation and running](#installation-and-running)
- [How to play](#how-to-play)
- [Question data](#question-data)
- [Repository structure](#repository-structure)
- [Build, deployment, and tests](#build-deployment-and-tests)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

Quiz CLI presents multiple-choice questions in the terminal. Choose a subject and quiz length, answer questions by entering the option number, and review your score and any incorrect answers at the end. Questions and explanations are loaded from `data/questions.json`.

The project also serves as an example of JavaScript fundamentals, including ES modules, asynchronous code, file-system access, input handling, classes, array methods, and error handling.

## Key features

- Three included categories: JavaScript Basics, Node.js Fundamentals, and General Programming.
- Choose all questions, or a shorter set of three or five when the category has enough questions.
- Question order is shuffled for each quiz.
- Immediate correctness feedback, explanations, and a visual progress bar.
- Final score, performance message, and review of missed questions.
- Option to play again without restarting the process.
- ANSI terminal colors implemented without external dependencies.

## Technology stack

- JavaScript using native ES modules.
- Node.js built-in APIs: `node:fs/promises`, `node:path`, `node:url`, and `node:readline`.
- JSON for the quiz question bank.
- The npm test script invokes Node.js's built-in test runner.

## Prerequisites

- Node.js 18 or later, as declared in `package.json`.
- A terminal capable of interactive standard input/output.
- npm to run the package scripts. There are no third-party dependencies declared in the package manifest.

## Installation and running

Clone the repository and enter its directory:

```sh
git clone <repository-url>
cd <repository-directory>
```

No dependency installation is needed for the current project because it uses Node.js built-in modules only. Start the quiz with:

```sh
npm start
```

Equivalent direct invocation:

```sh
node index.js
```

## How to play

1. Choose a category by entering its displayed number.
2. Choose the number of questions. Each included category has five questions, so all three choices (all, three, or five) are available.
3. Press Enter to begin, then enter a numbered answer for each question. Invalid option numbers are rejected and prompted again.
4. Read the immediate feedback and explanation, pressing Enter between questions.
5. Review your score and any missed answers. Enter `y` to play again; any other response ends the session.

There are no command-line arguments, configuration files, or environment variables defined by the current application.

## Question data

Questions live in `data/questions.json`. The file defines a `categories` object; each category has a display `name` and a `questions` array. Each question contains:

- `question`: prompt text.
- `options`: answer strings.
- `answer`: zero-based index of the correct option in `options`.
- `explanation` (optional): text shown after an answer.

To add or edit content, maintain this structure and ensure each `answer` index points to a valid option. The application reads this JSON at startup. Available question-count options depend on the category's question count: **All questions** is always available, while the three- and five-question choices appear only when the category contains at least that many questions. The selected questions are taken from the beginning of that category's array and then shuffled for presentation; choosing a shorter quiz does not randomly sample from the whole category.

## Repository structure

```text
.
├── data/
│   └── questions.json  # Quiz categories, questions, options, answers, explanations
├── src/
│   ├── colors.js       # ANSI color and style helpers
│   ├── input.js        # Readline prompts and menu selection
│   └── quiz.js         # Quiz state, question flow, scoring, and results
├── index.js            # Application entry point and main menu loop
├── package.json        # Package metadata, Node requirement, and npm scripts
└── README.md
```

## Build, deployment, and tests

No build or bundling step is defined. This is a local interactive Node.js CLI; the repository does not specify a deployment or publishing process.

Run the configured test command with:

```sh
npm test
```

This invokes `node --test`. No test files are present in the repository at this time, so a test runner is configured but no automated tests are checked in.

## Troubleshooting

- **`node` is not recognized or the version is too old:** Install Node.js 18 or later and verify with `node --version`.
- **Questions cannot be loaded or JSON parsing fails:** Check that `data/questions.json` exists and contains valid JSON.
- **The terminal is waiting for input:** Enter the number shown for an option and press Enter. At the play-again prompt, `y` continues; other responses finish the session.
- **Colors or box-drawing characters render incorrectly:** Use a terminal that supports ANSI escape sequences and Unicode characters. Colors are emitted directly using ANSI codes.

## Contributing

No formal contribution guide is included in the repository. Contributions should preserve the existing ES module style and question-data schema. For question additions, verify the answer index and explanation, and run `npm test` (noting that no test suite is currently included).

## License

The `package.json` declares the project license as **MIT**. A separate license text file was not present in the repository; consult the project owner for the authoritative license terms.
