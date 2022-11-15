# _printf
## About this project:
- This is a recreation of the C standard library function ```printf```.
- The function writes output to standard output.
- This project involves most of the major concepts of C programming language.
- The project calls in various variadic functions.
- The project was done as a team work with 2 contributors - [Victor Kalu](https://github.com/chesahkalu) and [Mayen Kalu](https://github.com/MayKay47),
 with the intention of learning more about team colaboration using Git and also enabling work flow with so many files.
## Description:
The function `_printf` uses the PROTOTYPE ```int _printf(const char *format, ...);```. 
The format string is composed of zero or more directives. See ```man 3 printf``` for more detail. 
**_printf** will return the number of characters printed (excluding the null byte used to end output to strings) and will write output to **stdout**,
the standard output stream.
The function writes under the control of a `format` string that specifies how subsequent arguments
(accessed via the variable-length argument facilities of `stdarg`) are converted for output.
## Useage:
- Prints a string to the standard output, returning the number of characters if succesful 0r -1 on error.
- To use the `_printf` function,compile all `.c` files in the repository and include the header `main.h` with
  any main function.
- Calling :`_printf("format string", arguments...)` `format string` contain either conversion specifiers,flags,length modfiers,field width,precision and regular characters.
### Conversion Specifiers
The conversion specifier (introduced by the character `%`) is a character that
specifies the type of conversion to be applied. The `_printf` function
supports the following conversion specifiers:

#### d, i
The `int` argument is converted to signed decimal notation.

Example `main.c`:
```
int main(void)
{
    _printf("%d\n", 7);
}
```
Output:
```
7
```
### Flag Characters
The character `%` may be followed by zero or more of the following flags:

#### #
  * For `o` conversions, the first character of the output string is prefixed
  with `0` if it was not zero already.
  * For `x` converions, `0x` is prepended for non-zero numbers.
  * For `X` conversions, `0X` is prepeneded for non-zero numbers.

Example `main.c`:
```
int main(void)
{
    _printf("%#x\n", 7);
}
```
Output:
```
0x7
```
### More Examples
**String**
* Input: ```_printf("%s\n", 'This is a string.');```
* Output: ```This is a string.```

**Character**
* Input: ```_printf("The first letter in the alphabet is %c\n", 'A');```
* Output: ```The first letter in the alphabet is A```

**Integer**
* Input: ```_printf("There are %i dozens in a gross\n", 12);```
* Output: ```There are 12 dozens in a gross```

**Decimal:**
* Input: ```_printf("%d\n", 1000);```
* Output:  ```1000```

# TASKS
- [x] Write function that produces output with conversion specifiers ```c```, ```s```, and ```%```.
- [x] Handle conversion specifiers ```d```, ```i```.
- [x] Create a man page for your function.
- [x] Handle conversion specifier ```b```.
- [x] Handle conversion specifiers ```u```, ```o```, ```x```, ```X```.
- [x] Use a local buffer of 1024 chars in order to call write as little as possible.
- [x] Handle conversion specifier ```S```.
- [x] Handle conversion specifier ```p```.
- [x] Handle flag characters ```+```, space, and ```#``` for non-custom conversion specifiers.
- [x] Handle length modifiers ```l``` and ```h``` for non-custom conversion specifiers.
- [x] Handle the field width for non-custom conversion specifiers.
- [x] Handle the precision for non-custom conversion specifiers.
- [x] Handle the ```0``` flag character for non-custom conversion specifiers.
- [x] Handle the custom conversion specifier ```r``` that prints the reversed string.
- [x] Handle the custom conversion specifier ```R``` that prints the rot13'ed string.
## File Description
* [_printf.c](./_printf.c): contains the  fucntion ```_printf```, which uses the prototype ```int _printf(const char *format, ...);```
* [get_flags.c](./get_flags.c): checks,confirms and returns active flags.
* [get_functions1.c](./get_functions1.c): contains functions to print `int`,`char`,`string`,`percent sign = %` and `unsigned number in binary` to stdout.
* [get_functions2.c](./get_functions2.c): contains functions to print unsigned number in `octal`, `hexadecimal`, `upper hexadecimal` and to print hexadecimal number in `upper` and `lower` to stdout.
* [get_functions3.c](./get_functions3.c): contains functions to print a string in `ROT13(conversion specier R)`, print a string in reverse, print ascii codes in hexa of non printable chars, and Print the value of a pointer variable to stdout.
* [get_precisions.c](./get_precisions.c): function to handle precision.
* [get_size.c](./get_size.c): function to handle size.
* [get_width.c](./get_width.c): function to handle width.
* [main.h](./main.h): ontains all function prototypes used for ```_printf```.
* [print_digits.c](./print_digits.c): contains functions to check if a char is a digit and printable, appends ascci code in hex.
* [print_handle.c](./print_handle.c): prints all handled specifiers
```
{'c', print_char}, {'s', print_string}, {'%', print_percent},
{'i', print_int}, {'d', print_int}, {'b', print_binary},
{'u', print_unsigned}, {'o', print_octal}, {'x', print_hexadecimal},
{'X', print_hexa_upper}, {'p', print_pointer}, {'S', print_non_printable},
{'r', print_reverse}, {'R', print_rot13string}, {'\0', NULL}
```

## Authors :black_nib:
[Victor Kalu](https://github.com/chesahkalu)

[Mayen Kalu](https://github.com/MayKay47)
