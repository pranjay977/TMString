# TMString

A small, hand-rolled C++ string class (`TMString`) built on raw `char*` buffers. It implements many of the operators you'd expect from a string type — assignment, concatenation, repetition, relational comparisons, insertion, and stream output — without relying on `std::string`.

## Features

- **Construction & assignment** — build from a C string (`operator=(const char*)`) or copy from another `TMString` (`operator=(const TMString&)`).
- **Concatenation** — `operator+` (with a `const char*` or another `TMString`) and `operator+=` for in-place appending.
- **Repetition** — `operator*(int)` repeats the string content N times.
- **Relational operators** — `<`, `>`, `<=`, `>=`, `==`, `!=`, based on lexicographic (`strcmp`) ordering, with explicit handling for null/empty strings.
- **Insertion** — several overloads of `insert()` for splicing another `TMString`, a C string, a substring range, or a repeated character into an existing string at a given index.
- **Stream output** — `operator<<` for printing directly to `ostream`.

## Example Usage

```cpp
#include <tmstring.h>

int main()
{
    TMString a;
    a = "Hello";

    TMString b;
    b = "World";

    TMString c = a + " " + b; // "Hello World" (conceptually)

    if (a < b)
        cout << a << " comes before " << b << endl;

    return 0;
}
```

## Building

```bash
g++ -std=c++11 your_program.cpp -o your_program.exe -I ..\include -L ..\lib -l tmstring
```


## Requirements

- A C++11-capable compiler (e.g. `g++`)
- Standard library only — no external dependencies
