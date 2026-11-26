# JavaScript Learning Quiz

A dependency-free command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Features

- Choose from three quiz categories:
  - JavaScript Basics
  - Node.js Fundamentals
  - General Programming
- Select the number of questions for a quiz.
- Shuffle questions using the Fisher–Yates algorithm.
- Track progress and view explanations as you play.
- See your score and review incorrect answers at the end.

Each category contains five questions. Questions, answers, and explanations are stored in `data/questions.json`.

## Technology Stack

- Node.js
- JavaScript ES modules
- Node.js built-in modules only, including `readline`
- No third-party dependencies

## Prerequisites

- Node.js **18 or later**
- npm, included with Node.js

## Getting Started

Clone the repository and open its directory:

```bash
git clone https://github.com/escribealucas-hub/test-app.git
cd test-app
```

No dependency installation step is required. Start the quiz with:

```bash
npm start
```

The application runs `node index.js` and guides you through the available categories and quiz options in the terminal.

## Usage

Run the interactive quiz:

```bash
npm start
```

Follow the terminal prompts to select a category and quiz length, answer questions, and review your results.

## Repository Structure

```text
.
├── data/
│   └── questions.json  # Categories, questions, answers, and explanations
├── src/
│   ├── colors.js       # ANSI terminal color helpers
│   ├── input.js        # Readline prompts and selections
│   └── quiz.js         # Quiz flow, scoring, and results
├── index.js            # Application entry point and main loop
└── package.json        # Project metadata, Node.js requirement, and scripts
```

## Configuration and Content

Quiz content is defined in `data/questions.json`. It contains the categories, questions, answers, and explanations used by the application.

## Testing

The package defines this test command:

```bash
npm test
```

It runs `node --test`. No test files were found in the repository analysis, so the presence or results of a test suite could not be confirmed.

## Build and Deployment

No build step or deployment instructions were identified. The application is run directly with Node.js using `npm start`.

## Dependencies

The project has no third-party dependencies and uses Node.js built-in modules.

## Troubleshooting

- **Node.js version error:** Confirm that Node.js 18 or later is installed.
- **Quiz content issues:** Check that `data/questions.json` is valid JSON and contains the expected quiz data.

## Contributing

No contribution guidelines were identified in the repository analysis. When proposing changes, keep quiz content in `data/questions.json` and application code in the relevant source files.

## License

License information could not be determined from the repository analysis.
