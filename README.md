# bit-masks-app

A city timezone finder using bitwise operations, built with HTML, CSS, and JavaScript.

## About

Demonstrates how bit masks replace long chains of if/else conditionals. Each city is assigned a 25-bit sequence (one bit per GMT timezone from +12 to −12). Searching by GMT offset creates a bitmask and uses bitwise AND to find matching cities — no direct offset comparison used.

## Features

- [x] Vertical list of 16 cities with checkboxes and GMT offsets
- [x] GMT offset search input (−12 to +12)
- [x] Find Cities button using bitwise AND to match cities
- [x] Error message if GMT input is empty or out of range
- [x] NOT mode — find cities NOT in the entered GMT offset (bonus)
- [x] Summary count of cities matching the search criteria (bonus)
- [x] Live bit sequence display for checked cities
- [x] Mask visualizer showing search mask, city mask, and AND result

## How Bit Masks Work

Each GMT offset maps to a bit position (0–24):
```
Bit 0  = GMT +12
Bit 12 = GMT  0
Bit 24 = GMT -12
```

A city's bitmask has a `1` at the bit position for its GMT offset.  
A search mask has a `1` only at the searched GMT offset.  
Match check: `(cityMask & searchMask) !== 0`  
No `if (city.gmt === searchOffset)` comparisons used.

## Tech Stack

- HTML
- CSS
- JavaScript (vanilla, BigInt for 25-bit masks)

## How to run

Open `index.html` in your browser — no build tools needed.
