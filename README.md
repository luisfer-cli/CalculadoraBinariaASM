# Binary Calculator in Assembly

Interactive calculator developed in x86 assembly language (MASM) that performs basic arithmetic operations with binary numbers.

## Description

This program implements a text-mode calculator that allows users to input binary numbers and perform basic mathematical operations. Results are also displayed in binary format.

## Features

- **Interactive menu interface** with the following options:
  1. Addition
  2. Subtraction
  3. Multiplication
  4. Division
  5. Help
  6. Exit

- **Binary number input**: User enters numbers in binary format (e.g., 1011, 1101)
- **Automatic conversion**: The program internally converts the entered binary numbers
- **Binary results**: Operation results are displayed in binary format

## Requirements

- MASM-compatible assembler (Microsoft Macro Assembler)
- DOSBox or environment compatible with DOS interrupts (INT 21h)
- Memory model: Small
- Stack: 64 bytes

## Code Structure

### Data Segments

- `numero1`, `numero2`: Variables to store operands
- `dos`: Constant variable used in conversions
- Menu and help messages

### Main Procedures

1. **imprimir**: Displays messages on console
2. **recibirDato**: Captures user input
3. **parsearDato1** and **parsearDato2**: Convert binary input to numeric format
4. **numeroACaracter**: Converts numeric result to binary representation for display

### Operations

- **sum**: Performs addition of two binary numbers
- **res**: Performs subtraction of two binary numbers
- **multi**: Performs multiplication of two binary numbers
- **divi**: Performs division of two binary numbers (integer result)

## Usage

1. Compile the `ProyectoASM.asm` file with MASM
2. Run the program in DOSBox or compatible environment
3. Select the desired operation from the menu (1-6)
4. Enter the first number in binary format
5. Enter the second number in binary format
6. View the result in binary format
7. The program returns to the main menu for new operations

### Usage Example

```
Calculadora binaria
Digite 1 para realizar sumas
Digite 2 para realizar restas
Digite 3 para realizar multiplicaciones
Digite 4 para realizar divisiones
Digite 5 para ayuda
Digite 6 para salir
1

Digite el primer numero = 101
Digite el segundo numero = 11
1000
```

In this example: 101 (5 in decimal) + 11 (3 in decimal) = 1000 (8 in decimal)

## Compilation

```bash
# With MASM
masm ProyectoASM.asm;
link ProyectoASM.obj;

# Or with TASM
tasm ProyectoASM.asm
tlink ProyectoASM.obj
```

## Limitations

- Only accepts positive integers
- Division only shows the quotient (integer part)
- Number size is limited by 8-bit registers (values 0-255)

## Technical Notes

- Uses the `small` memory model
- DOS interrupts (INT 21h) are used for I/O
- Binary to decimal conversion is performed through successive multiplication by 2
- Decimal to binary conversion is performed through successive division by 2
