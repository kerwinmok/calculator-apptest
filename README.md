# Calculator App Test (Java Swing)

I built this project as a desktop calculator in Java Swing to practice GUI layout, event handling, and expression state management.

## What this app does

- Basic arithmetic: add, subtract, multiply, divide
- Decimal input support
- Percent conversion (`%`)
- Sign toggle (`(-)`)
- Delete one character (`Del`)
- Clear all state (`C`)
- Expression preview line above the main display

## Tech stack

- Java
- Swing (`JFrame`, `JPanel`, `JButton`, `JLabel`)
- AWT events (`ActionListener`)

## How I structured it

- `src/App.java`: entry point that starts the calculator window
- `src/Calculator.java`: UI construction and button event logic

The calculator keeps two display labels:

- `expressionLabel`: shows the in-progress expression (for example `12 +`)
- `displayLabel`: shows the current number or result

## How the calculation flow works

1. I read button input through one `ButtonClickListener`.
2. Number buttons append to the display.
3. When an operator is clicked, I store:
	- `num1`
	- `operator`
4. When `=` is clicked, I parse `num2`, apply the selected operation, and display `result`.

## Hard parts I solved

- Keeping expression state and display state synchronized without confusing the user.
- Handling integer-looking results cleanly (hiding trailing `.0` for whole-number outputs).
- Defensive handling for invalid number parsing and divide-by-zero.

## Run locally

From repo root:

```powershell
javac -d out src\*.java
java -cp out App
```

## Notes

- This app is intentionally focused on core calculator behavior.
- Next improvement I would make is adding keyboard input and calculation history.
