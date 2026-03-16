# NY Solver — Letter Boxed Puzzle Solver

A browser-based solver and interactive player for the [NYT Letter Boxed](https://www.nytimes.com/puzzles/letter-boxed) puzzle.

## What is Letter Boxed?

Letter Boxed is a New York Times puzzle where 12 letters are arranged on the 4 sides of a square (3 letters per side). The goal is to use all 12 letters by forming a chain of valid English words.

**Rules:**
- Words must be at least 3 letters long
- Consecutive letters cannot come from the same side
- Each new word must start with the last letter of the previous word
- All 12 letters must be used

## Usage

No installation needed. Just open `letters.html` in any modern browser.

1. Enter 3 letters for each side: Top, Right, Bottom, Left
2. Click **Start Game**
3. Play manually by clicking letters on the board (Enter to submit, Backspace to delete)
4. Or click **Show Solution** to auto-solve

## How the Solver Works

The solver uses a depth-first search (DFS) algorithm with constraint-based pruning:

- Filters the dictionary to only words that can be formed on the current board
- Prioritizes words that cover the most distinct letters
- Indexes words by starting letter for efficient candidate lookup
- Iterates from shortest to longest solution (1–8 words)

## Dictionary

- Primary: fetches from remote word list (~286k words)
- Fallback: built-in list of ~2,000 common English words (embedded in the HTML)

## Tech Stack

- Pure HTML5 / CSS3 / JavaScript (ES6+)
- SVG for the interactive game board
- No build tools, no dependencies, no frameworks

## Project Structure

```
ny-solver/
├── letters.html         # Complete self-contained app (HTML + CSS + JS)
└── word_dictionary.txt  # Local word list (~286k words)
```
