# Quiz CLI

An interactive command-line quiz game built with Node.js ES modules. The app presents multiple-choice questions across programming categories and provides instant feedback, scoring, and answer review.

## Project Overview

Quiz CLI is a terminal-based learning tool that demonstrates core Node.js and JavaScript concepts, including:

- ES modules (`import` / `export`)
- Node.js `readline` input handling
- Async/await flows
- Object-oriented programming with classes
- Array methods and destructuring
- ANSI terminal colors

The quiz loads category-based questions from JSON, asks one question at a time, and displays a final score summary with a review of missed questions.

## Features

- Category selection
- Adjustable quiz length
- Randomized question order
- Progress bar during gameplay
- Correct/incorrect answer feedback
- Final score summary
- Review of wrong answers

## Setup

### Prerequisites

- Node.js 18 or newer
- npm (bundled with Node.js)

### Installation

```bash
git clone <repository-url>
cd test-app
npm install
```

> Note: This project does not use external runtime dependencies, so `npm install` is optional unless you want a lockfile generated locally.

### Run the Quiz

```bash
npm start
```

Or run directly:

```bash
node index.js
```

## Usage Examples

1. Launch the app.
2. Choose a quiz category.
3. Pick the number of questions.
4. Answer each multiple-choice question by entering the option number.
5. Review your score and missed questions at the end.

Example session flow:

```text
Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions
```

## How It Works

- `index.js` starts the CLI, loads question data from `data/questions.json`, and controls the main game loop.
- `src/input.js` wraps Node.js `readline` in Promise-based helpers for prompts, selections, confirmations, and pauses.
- `src/quiz.js` contains the quiz engine: shuffling, scoring, progress tracking, and results output.
- `src/colors.js` provides ANSI color helpers for terminal styling.
- `data/questions.json` stores quiz categories, questions, answer indexes, and explanations.

## Question Data Format

Questions are stored as category objects with the following structure:

- `name`: display name shown in the menu
- `questions`: array of quiz items
- each question includes:
  - `question`
  - `options`
  - `answer` (zero-based index)
  - `explanation` (optional)

## Notes

- The app is designed for terminal use only.
- Question order is randomized each time you start a quiz.
- Scores are calculated per quiz run and are not persisted.

## Tech Stack

- Node.js
- JavaScript (ES modules)
- Built-in `fs`, `path`, `url`, and `readline` modules

## License

MIT

