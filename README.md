# GitHub Copilot Workshop

## Enhance a Node Calculator app using GitHub Copilot

<img width="400" alt="Node Calculator image" src="./assets/Node%20calculator%20image.png">

The project contains a simple node.js application that exposes REST APIs to perform arithmetic on integers, and provides a test suite with mocha and chai.

## Features

### Supported Operations
- **Addition** (+): Add two numbers
- **Subtraction** (-): Subtract two numbers
- **Multiplication** (×): Multiply two numbers
- **Division** (÷): Divide two numbers
- **Power/Exponentiation** (^): Raise a number to a power ✨ *NEW*

### Power Operation (Exponentiation)
The calculator now supports the power operation (^) to calculate exponentiation. This feature allows you to:
- Calculate powers: `2 ^ 3 = 8`
- Calculate roots using fractional exponents: `4 ^ 0.5 = 2` (square root)
- Calculate reciprocals using negative exponents: `2 ^ -1 = 0.5`
- Any base to the power of zero: `42 ^ 0 = 1`

**Usage:**
- Click the `^` button on the calculator UI, or
- Press the `^` key on your keyboard

## Installation

```bash
npm install
```

## Running the Application

To start the server:
```bash
npm start
```

The calculator will be available at `http://localhost:3000`

## Running Tests

To run the test suite with coverage:
```bash
npm test
```

This will run all unit tests for arithmetic operations including the new power operation tests.

## Implementation Details

### Frontend (`public/client.js`)
- Added support for `^` operator in the `calculate()` function
- Extended keyboard event listener to recognize `^` as a valid operation
- Maps the `^` operator to `operation=power` for the backend API

### Backend (`api/controller.js`)
- Added `power` operation handler using `Math.pow(a, b)`
- Supports positive, negative, and fractional exponents
- Fully integrated with existing arithmetic operation handlers

### API Endpoint

```
GET /arithmetic?operation=power&operand1=<base>&operand2=<exponent>
```

**Example:**
```
GET /arithmetic?operation=power&operand1=2&operand2=3
Response: { "result": 8 }
```

## Testing

The power operation has been thoroughly tested with the following test cases:
- ✅ Raises 2 to the power of 3 → 8
- ✅ Raises 5 to the power of 2 → 25
- ✅ Raises a number to the power of 0 → 1
- ✅ Raises a number to a negative power → 0.5 (2^-1)
- ✅ Raises a number to a fractional power → 2 (4^0.5)

**Test Coverage:** 85.71% statements, 85% branches, 77.78% functions

## Acknowledgements

A special thanks to the following awesome Hubbers who have contributed in many different ways to this repository. 
[pierluigi](https://github.com/pierluigi), [parroty](https://github.com/yuichielectric), [yuichielectric](https://github.com/yuichielectric), [dchomh](https://github.com/dchomh), [nolecram](https://github.com/nolecram), [rsymo](https://github.com/rsymo), [damovisa](https://github.com/damovisa) and anyone else I've inadvertently missed.

_v1.1 Released November, 2025 - Power Operation Feature Added_

_v1.0 Released June, 2023_
