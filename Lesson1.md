## Lesson 1
In this course we will discuss the paradigm of OOP from 3 perspectives
    - The programmers perspective
    - The compilers perspective
    - The designers perspective

### Intro to C++
- C version of printing Hello World
```C
    #include<stdio.h>
    int main() {
        print("Hello World!\n")
        return 0;
    }
```
- Below is the respective C++ version for printing Hello World
```C++
    import <iostream>;
    using namespace std;
    int main() {
        cout << " Hello World!" << endl;
        return 0;
    }
```
- Note that main MUST return an int
    - void main() is illegal
- Return statement: returns status code to OS ($?)
- stdio, printf still available to C++
- referred C++ I/O header <iostream>
```c++
    std::cout << ... << ... << ... (... = data)
    std::endl = end of line + flush out buffer
```
- A buffer is a region of memory in which data is held while it is being moved from one place to another, once the output has enough characters, the program will output the buffered characters all at once
- stderrors are unbuffered (as when you have an error you want to know immediately), on the other hand stdout is buffered
- The act of outputing all buffered characters into a file is known as 'flushing'
- using namespace std lets you omit the std:: prefix
- I/O Operators 
    - << "put to" (output), >> "get from" (input)
    - cerr << x
    - cin >> x

Add 2 #'s
```C++
    import <iostream>
    using namespace std;
    int main() {
        int x, y:
        cin >> x >> y;
        cout << x + y << endl;
    }
```
- By default, cin skips leading whitespace (space, tab, newline)
- What an error occurs, e.g
    - input doesn't comntain an integer next
    - input too large/small to fit in a variable
    - out of input (EOF)
- Then the statement will fail
- If the read failed, cin.fail() will be true
- If EOF, cin.fail() and cin.eof() will both be true
- This whill only happen until the attempted read fails
- There is an implicit conversion from cin's type (istream) to bool
- Allows you to use cin as a condition (e.g whether or not an error has occured)
- cin converts to true, unless the stream has had a failure
- The following example below reads all ints from stdin + echo them, one per line, stdout, stop on bad input or eof
```c++
    int main() {
        int r;
        while (true) {
            cin >> r;
            if (cin.fail()) break;
            cout << r << endl;
        }
    }
```
- Note: >> is C's (and C++'s) right bitshift operator
- If a and b are ints, a >> b shifts a's bits to the right by 6 spots
