# Advent of Code 2015 - Day 1: Not Quite Lisp 🎄

## Puzzle Description

Santa needs your help to save Christmas! His weather machine’s "snow" function is powered by stars, and he needs fifty stars to ensure a white Christmas.

Each day in the Advent calendar includes two puzzles. Solve the puzzles to earn stars. Here's the challenge for **Day 1**:

---

### Story

Santa is delivering presents in a tall apartment building, but the instructions he received are confusing! He starts on the **ground floor** (floor 0) and needs to figure out where the instructions will take him.

The instructions consist of a series of characters:
- `(` means **go up one floor**.
- `)` means **go down one floor**.

The building has no upper or lower floor limit, so Santa could end up very high or very deep in the basement.

---

### Examples

Here are some examples to clarify the rules:

- `(())` and `()()` both lead to **floor 0**.
- `(((` and `(()(()(` both lead to **floor 3**.
- `))(((((` also leads to **floor 3**.
- `())` and `))(` both lead to **floor -1** (the first basement level).
- `)))` and `)())())` both lead to **floor -3**.

---

### Puzzle Goal

Given a series of instructions (a long string of `(` and `)` characters), determine:

1. **To what floor will Santa end up?**

---

## Input

The input is a single string of characters containing only `(` and `)`.

You can obtain the puzzle input from the [Advent of Code website](https://adventofcode.com/2015/day/1).

---

## Solution Strategy

### Plan

1. Start with `floor = 0` (the ground floor).
2. Iterate through the characters in the input string:
   - Increment `floor` by 1 for every `(`.
   - Decrement `floor` by 1 for every `)`.
3. Output the final value of `floor`.

---

## Example Code in PHP

Here’s a basic PHP implementation:

```php
<?php
// Read the input (ensure the input.txt file contains your puzzle input)
$input = file_get_contents('input.txt');

// Initialize the starting floor
$floor = 0;

// Process each character in the input
foreach (str_split(trim($input)) as $char) {
    if ($char === '(') {
        $floor++;
    } elseif ($char === ')') {
        $floor--;
    }
}

// Output the result
echo "Santa ends up on floor: $floor\n";
?>


