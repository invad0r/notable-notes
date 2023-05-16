---
tags: [c, Notebooks]
title: libc
created: '2023-05-08T13:01:19.322Z'
modified: '2023-05-09T11:23:57.040Z'
---

# libc

> c standard library - provides macros, type definitions and functions for tasks as string handling, math, i/o, memory management and os services

## usage

```c
assert.h 	    // 	    assert macro, used to assist with detecting logical errors and other types of bugs in debugging versions of a program
complex.h 	  // C99 	set of functions for manipulating complex numbers
ctype.h 	    //      set of functions used to classify characters by their types or to convert between upper and lower case in a way that is independent of the used character set
errno.h 	    //      testing error codes reported by library functions
fenv.h 	      // C99 	set of functions for controlling floating-point environment
float.h 	    // 	    macro constants specifying the implementation-specific properties of the floating-point library.
inttypes.h 	  // C99 	exact-width integer types
iso646.h 	    // NA1 	several macros that implement alternative ways to express several standard tokens. For programming in ISO 646 variant character sets
limits.h 	    // 	    macro constants specifying the implementation-specific properties of the integer types.
locale.h 	    // 	    localization functions
math.h 	      // 	    common mathematical functions.
setjmp.h 	    // 	    macros setjmp and longjmp, which are used for non-local exits
signal.h 	    // 	    signal-handling functions
stdalign.h 	  // C11  querying and specifying the alignment of objects
stdarg.h 	    //      accessing a varying number of arguments passed to functions
stdatomic.h   // C11 	atomic operations on data shared between threads
stdbool.h 	  // C99 	a boolean data type
stddef.h 	    // 	    several useful types and macros
stdint.h 	    // C99  exact-width integer types
stdio.h 	    // 	    core input and output functions
stdlib.h 	    // 	    numeric conversion functions, pseudo-random numbers generation functions, memory allocation, process control functions
stdnoreturn.h // C11 	For specifying non-returning functions
string.h 	    // 	    string-handling functions
tgmath.h 	    // C99  type-generic mathematical functions
threads.h 	  // C11  functions for managing multiple threads, mutexes and condition variables
time.h 	      // 	    date- and time-handling functions
uchar.h 	    // C11 	Types and functions for manipulating Unicode characters
wchar.h 	    // NA1  wide-string-handling functions
wctype.h 	    // NA1 	set of functions used to classify wide characters by their types or to convert between upper and lower case

// Normative Addendum 1 (NA1)
```

```sh
man stdio
```

## stdlib.h

```c
size_t              // unsigned integral type and is the result of the sizeof keyword
wchar_t             // an integer type of the size of a wide character constant
div_t               // structure returned by the div function
ldiv_t              // structure returned by the ldiv function

NULL                // macro is the value of a null pointer constant
EXIT_FAILURE        // is the value for the exit function to return in case of failure
EXIT_SUCCESS        // is the value for the exit function to return in case of success
RAND_MAX            // macro is the maximum value returned by the rand function
MB_CUR_MAX          // macro is the maximum number of bytes in a multi-byte character set which cannot be larger than MB_LEN_MAX

void *calloc (size_t nitems, size_t size)                             // allocates requested memory and returns a pointer to it
void free    (void *ptr)                                              // deallocates memory previously allocated by a call to calloc, malloc, or realloc
void *malloc (size_t size)                                            // allocates the requested memory and returns a pointer to it
void *realloc(void *ptr, size_t size)                                 // attempts to resize the memory block pointed to by ptr that was previously allocated with a call to malloc or calloc

void abort   (void)                                                   // causes an abnormal program termination
void exit    (int status)                                             // causes the program to terminate normally
void *bsearch(const void *key, const void *base, size_t nitems, size_t size, int (*compar)(const void *, const void *))   // performs a binary search
void qsort   (void *base, size_t nitems, size_t size, int (*compar)(const void *, const void*))                           // Sorts an array
void srand   (unsigned int seed)                                      // This function seeds the random number generator used by the function rand

int atoi  (const char *str)                                           // Converts the string pointed to, by the argument str to an integer (type int)
int atexit(void (*func)(void))                                        // causes the specified function func to be called when the program terminates normally
int system(const char *string)                                        // The command specified by string is passed to the host environment to be executed by the command processor
int abs   (int x)                                                     // Returns the absolute value of x
int rand  (void)                                                      // Returns a pseudo-random number in the range of 0 to RAND_MAX
int mblen (const char *str, size_t n)                                 // Returns the length of a multibyte character pointed to by the argument str
int mbtowc(whcar_t *pwc, const char *str, size_t n)                   // Examines the multibyte character pointed to by the argument str
int wctomb(char *str, wchar_t wchar)                                  // Examines the code which corresponds to a multibyte character given by the argument wchar

long int atol(const char *str)                                        // Converts the string pointed to, by the argument str to a long integer (type long int)
long int strtol(const char *str, char **endptr, int base)             // Converts the string pointed to, by the argument str to a long integer (type long int)
long int labs(long int x)                                             // Returns the absolute value of x

unsigned long int strtoul(const char *str, char **endptr, int base)   // Converts the string pointed to, by the argument str to an unsigned long integer (type unsigned long int)

double atof(const char *str)                                          // Converts the string pointed to, by the argument str to a floating-point number (type double)
double strtod(const char *str, char **endptr)                         // Converts the string pointed to, by the argument str to a floating-point number (type double)

char *getenv(const char *name)                                        // Searches for the environment string pointed to by name and returns the associated value to the string

div_t div(int numer, int denom)                                       // Divides numer (numerator) by denom (denominator)

ldiv_t ldiv(long int numer, long int denom)                           // Divides numer (numerator) by denom (denominator)

size_t mbstowcs(schar_t *pwcs, const char *str, size_t n)             // Converts the string of multibyte characters pointed to by the argument str to the array pointed to by pwcs
size_t wcstombs(char *str, const wchar_t *pwcs, size_t n)             // Converts the codes stored in the array pwcs to multibyte characters and stores them in the string str
```

## stdlib.h

```c
size_t        // unsigned integral type and is the result of the sizeof keyword
FILE          // object type suitable for storing information for a file stream
fpos_t        // object type suitable for storing any position in a file

NULL                                // macro is the value of a null pointer constant
_IOFBF, _IOLBF and _IONBF           // macros which expand to integral constant expressions with distinct values and suitable for the use as third argument to the setvbuf function
BUFSIZ                              // macro is an integer, which represents the size of the buffer used by the setbuf function
EOF                                 // macro is a negative integer, which indicates that the end-of-file has been reached
FOPEN_MAX                           // macro is an integer, which represents the maximum number of files that the system can guarantee to be opened simultaneously
FILENAME_MAX                        // macro is an integer, which represents the longest length of a char array suitable for holding the longest possible filename
L_tmpnam                            // macro is an integer, which represents the longest length of a char array suitable for holding the longest possible temporary filename created by the tmpnam function
SEEK_CUR, SEEK_END, and SEEK_SET    // macros are used in the fseek function to locate different positions in a file
TMP_MAX                             // macro is the maximum number of unique filenames that the function tmpnam can generate
stderr, stdin, and stdout           // macros are pointers to FILE types which correspond to the standard error, standard input, and standard output streams

void clearerr(FILE *stream)                 // clears end-of-file and error indicators for the given stream
void rewind  (FILE *stream)                 // sets file position to the beginning of the file of the given stream
void setbuf  (FILE *stream, char *buffer)   // defines how a stream should be buffered
void perror  (const char *str)              // prints a descriptive error message to stderr. First the string str is printed followed by a colon and then a space

int fclose(FILE *stream)                                          // Closes the stream. All buffers are flushed
int feof(FILE *stream)                                            // Tests the end-of-file indicator for the given stream
int ferror(FILE *stream)                                          // Tests the error indicator for the given stream
int fflush(FILE *stream)                                          // Flushes the output buffer of a stream
int fgetpos(FILE *stream, fpos_t *pos)                            // Gets the current file position of the stream and writes it to pos
int fseek(FILE *stream, long int offset, int whence)              // Sets the file position of the stream to the given offset. The argument offset signifies the number of bytes to seek from the given whence position
int fsetpos(FILE *stream, const fpos_t *pos)                      // Sets the file position of the given stream to the given position. The argument pos is a position given by the function fgetpos
int remove(const char *filename)                                  // Deletes the given filename so that it is no longer accessible
int rename(const char *old_filename, const char *new_filename)    // Causes the filename referred to, by old_filename to be changed to new_filename
int setvbuf(FILE *stream, char *buffer, int mode, size_t size)    // Another function to define how a stream should be buffered
int fprintf(FILE *stream, const char *format, ...)                // sends formatted output to a stream
int printf(const char *format, ...)                               // sends formatted output to   stdout
int sprintf(char *str, const char *format, ...)                   // sends formatted output to a string

int vfprintf(FILE *stream, const char *format, va_list arg)       // sends formatted output to a stream using an argument list
int vprintf(const char *format, va_list arg)                      // sends formatted output to stdout   using an argument list
int vsprintf(char *str, const char *format, va_list arg)          // sends formatted output to a string using an argument list

int fscanf(FILE *stream, const char *format, ...)                 // reads formatted input from a stream
int scanf(const char *format, ...)                                // reads formatted input from stdin
int sscanf(const char *str, const char *format, ...)              // reads formatted input from a string
int fgetc(FILE *stream)                                           // Gets the next character (an unsigned char) from the specified stream and advances the position indicator for the stream
int fputc(int char, FILE *stream)                                 // Writes a character (an unsigned char) specified by the argument char to the specified stream and advances the position indicator for the stream
int fputs(const char *str, FILE *stream)                          // Writes a string to the specified stream up to but not including the null character
int getc(FILE *stream)                                            // Gets the next character (an unsigned char) from the specified stream and advances the position indicator for the stream
int getchar(void)                                                 // Gets a character (an unsigned char) from stdin
int putc(int char, FILE *stream)                                  // Writes a character (an unsigned char) specified by the argument char to the specified stream and advances the position indicator for the stream
int putchar(int char)                                             // Writes a character (an unsigned char) specified by the argument char to stdout
int puts(const char *str)                                         // Writes a string to stdout up to but not including the null character. A newline character is appended to the output
int ungetc(int char, FILE *stream)                                // Pushes the character char (an unsigned char) onto the specified stream so that the next character is read

long int ftell(FILE *stream)                                      // Returns the current file position of the given stream

char *fgets(char *str, int n, FILE *stream)    // reads a line from the specified stream and stores it into the string pointed to by str. stops when either (n-1) characters are read, the newline character is read, or the end-of-file is reached
char *gets(char *str)                          // reads a line from stdin and stores it into the string pointed to by, str. stops when either the newline character is read or when the end-of-file is reached, whichever comes first
char *tmpnam(char *str)                        // Generates and returns a valid temporary filename which does not exist

FILE *fopen  (const char *filename, const char *mode)                     // Opens the filename pointed to by filename using the given mode
FILE *freopen(const char *filename, const char *mode, FILE *stream)       // Associates a new filename with the given open stream and same time closing the old file in stream
FILE *tmpfile(void)                                                       // Creates a temporary file in binary update mode (wb+)

size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream)          // reads data from the given stream into the array pointed to by ptr
size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream)   // Writes data from the array pointed to by ptr to the given stream
```

## string.h

```c
size_t      // unsigned integral type and is the result of the sizeof keyword
NULL        // macro is the value of a null pointer constant

void *memchr (const void *str, int c, size_t n)           // searches for the first occurrence of the character c (an unsigned char) in the first n bytes of the string pointed to, by the argument str
void *memcpy (void *dest, const void *src, size_t n)      // copies n characters from src to dest
void *memmove(void *dest, const void *src, size_t n)      // another function to copy n characters from str2 to str1
void *memset (void *str, int c, size_t n)                 // Copies the character c (an unsigned char) to the first n characters of the string pointed to, by the argument str

int memcmp (const void *str1, const void *str2, size_t n) // compares first n bytes of str1 and str2
int strcmp (const char *str1, const char *str2)           // compares string pointed to, by str1 to the string pointed to by str2
int strncmp(const char *str1, const char *str2, size_t n) // compares at most the first n bytes of str1 and str2
int strcoll(const char *str1, const char *str2)           // compares string str1 to str2. The result is dependent on the LC_COLLATE setting of the location

char *strcat  (char *dest, const char *src)               // appends string pointed to, by src to the end of the string pointed to by dest
char *strncat (char *dest, const char *src, size_t n)     // appends string pointed to, by src to the end of the string pointed to, by dest up to n characters long
char *strchr  (const char *str, int c)                    // searches for the first occurrence of the character c (an unsigned char) in the string pointed to, by the argument str
char *strcpy  (char *dest, const char *src)               // copies the string pointed to, by src to dest
char *strncpy (char *dest, const char *src, size_t n)     // copies up to n characters from the string pointed to, by src to dest
char *strerror(int errnum)                                // searches an internal array for the error number errnum and returns a pointer to an error message string
char *strpbrk (const char *str1, const char *str2)        // finds the first character in the string str1 that matches any character specified in str2
char *strrchr (const char *str, int c)                    // searches for the last occurrence of the character c (an unsigned char) in the string pointed to by the argument str
char *strstr  (const char *haystack, const char *needle)  // finds the first occurrence of the entire string needle (not including the terminating null character) which appears in the string haystack
char *strtok  (char *str, const char *delim)              // breaks string str into a series of tokens separated by delim

size_t strcspn (const char *str1, const char *str2)       // calculates the length of the initial segment of str1 which consists entirely of characters not in str2
size_t strlen  (const char *str)                          // length of string str up to but not including the terminating null character
size_t strspn  (const char *str1, const char *str2)       // calculates length of the initial segment of str1 which consists entirely of characters in str2
size_t strxfrm (char *dest, const char *src, size_t n)    // transforms the first n characters of the string src into current locale and places them in the string dest
```

## see also

- [[c]]
- [[ar]]
- [tutorialspoint.com/c_standard_library/](https://www.tutorialspoint.com/c_standard_library/)
