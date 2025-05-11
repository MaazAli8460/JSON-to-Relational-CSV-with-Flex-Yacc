# JSON to Relational CSV Converter

This project implements a JSON-to-CSV converter as specified in the Compiler Construction Assignment 04. It uses Flex for tokenization, Yacc/Bison for parsing, and C for AST management, schema generation, and CSV output.

## Prerequisites
#### Ubuntu system
#### Flex, Bison, and GCC installed (see InstallationGuide.md)
### Installation
Install dependencies:
sudo apt-get update
sudo apt-get install flex bison gcc

### Alternative
```sh
sudo apt-get install flex
sudo apt-get install byacc
sudo apt-get install bison
sudo apt-get install bison++
sudo apt-get install byacc-j
```

## 1. Clone or extract the project files.

## 2. Building

### Run the following command to build the executable:
1. make clean
2. make
	This generates the json2relcsv executable.
3. Running
	Use the following command to run the tool:

	- ./json2relcsv <input.json> [--print-ast] [--out-dir] [DIR_NAME]
	- <input.json>: Path to the input JSON file.
	- [DIR_NAME]: Where you want your output files to go


	- --print-ast: (Optional) Prints the AST to stdout.
	- --out-dir DIR: (Optional) Specifies the output directory for CSV files (default: makes a DIR based on the name of .json file like <input.json> -> <input_out> ).
4. run <make clean> to remove previous bison generated .c files like <parser.tab.c> etc.

## Design Notes
### Lexer (scanner.l): 
	Tokenizes JSON input, handling strings, numbers, punctuation, and keywords. Tracks line/column for error reporting.



### Parser (parser.y): 
	Builds an AST using Yacc/Bison, validating JSON grammar.



### AST (ast.h, main.c): 
	Defines node structures for objects, arrays, pairs, and scalars. Supports AST printing and memory management.



### Schema Generation: 
	(Placeholder) Will traverse the AST to create table schemas based on conversion rules.



### CSV Output: 
	(Placeholder) Will write CSV files with headers and rows, handling large inputs efficiently.



### Error Handling: 
	Reports lexical and syntax errors with line/column information.

### Test Cases
	Test cases and their expected CSV outputs are included in the tests/ directory (to be added).

### Limitations
	Schema generation and CSV writing are currently placeholders and need implementation.
	Large JSON inputs (>30 MiB) may require further optimization.

# References:
- [Flex Manual](https://westes.github.io/flex/manual/)
- [Bison (Yacc) Manual](https://www.gnu.org/software/bison/manual/)
