# Left-Truncatable Prime Counter

This C program efficiently calculates the number of left-truncatable primes for a given number of digits. It uses the `primesieve` library for high-performance prime generation.

A **left-truncatable prime** is a non-zero containing prime number that, when its leftmost (MSB) digit is successively removed, results in a sequence of primes. For example, 937 is a left-truncatable prime because:

* 937 is prime.
* Removing the leftmost '9' gives 37, which is prime.
* Removing the leftmost '3' from 37 gives 7, which is prime.

Left-truncatable primes must contain no zero digits. Prime numbers such as 103 are invalid because they contain a zero, which would produce leading zeros (e.g., 03) when the most significant digit is removed, violating the zerofree requirement.

There are 4260 [left-truncatable primes](https://en.wikipedia.org/wiki/Truncatable_prime). Based on the *current* [complete list](https://www.worldofnumbers.com/truncat.htm), the largest is 24 digits: `357686312646216567629137`.

-----

## Table of Contents

* [Features](#features)
* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)
* [License](#license)

-----

## Features

* **Efficient Prime Generation**: Leverages the `primesieve` library for rapid generation of prime numbers.
* **Correct Left-Truncatable Logic**: Implements the standard definition, ensuring all successive truncations (by removing the leftmost digit) are prime.
* **Flexible Digit Count**: Calculates left-truncatable primes for a user-specified number of digits.
* **Error Handling**: Includes basic error handling for memory allocation and invalid input.

-----

## Requirements

To build and run this program, you'll need:

1. **C Compiler**: A C99 compatible compiler (e.g., GCC, Clang).
2. **`primesieve` Library**: The `primesieve` C/C++ library must be installed on your system.
3. **CMake**: Used for building the `primesieve` library and this project.
4. **Homebrew (macOS only)**: For easy installation of `CMake`.

-----

## Installation

You can use the provided `setup.sh` script to automate the installation and compilation process.

### Using the `setup.sh` Script

The `setup.sh` script automates the setup and compilation process for UNIX users.

    chmod +x setup.sh
    ./setup.sh

-----

## Usage

To run the program, execute the compiled binary and provide the desired number of digits as a command-line argument.

    ./count_primes.out <number_of_digits>

**Example:**

To find the number of 8-digit left-truncatable primes:

    ./count_primes.out 8

Expected output (will list the primes first, then the count):

    ❯ ./count_primes.out 8
    Number of 8-digit left-truncatable primes: 521 (n = 5096876)
    Number of 7-digit left-truncatable primes: 429 (n = 586081)
    Number of 6-digit left-truncatable primes: 326 (n = 68906)
    Number of 5-digit left-truncatable primes: 192 (n = 8363)
    Number of 4-digit left-truncatable primes: 99 (n = 1061)
    Number of 3-digit left-truncatable primes: 39 (n = 143)
    Number of 2-digit left-truncatable primes: 11 (n = 21)
    Number of 1-digit left-truncatable primes: 4 (n = 4)

    Total number of left-truncatable primes up to 8 digits: 1621 (n = 5761455)

    Execution time: 248.898 milliseconds
    Execution time: 248897.834 microseconds
    Execution time: 248897834.000 nanoseconds

**Valid range for `<number_of_digits>`:** 1 to 19 to handle left-truncations up to 64-bit unsigned integers.

-----

## Resources

- Check out this [respository](https://github.com/EbodShojaei/Right-Truncatable-Primes) for calculating *right-truncatable* primes.

- Check out this [respository](https://github.com/EbodShojaei/Two-Sided-Primes) for calculating *two-sided* primes.

## License

This project is licensed under the MIT License.
