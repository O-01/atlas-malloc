# C - Malloc
#### Concepts
*For this project, we expect you to look at this concept:*
- [[EYNTK] Writing your own dynamic allocation library](https://intranet.atlasschool.com/concepts/922)
## Resources
#### Read or watch:
- [Hack the Virtual Memory: malloc, the heap & the program break](https://blog.holbertonschool.com/hack-the-virtual-memory-malloc-the-heap-the-program-break/)
- [Everything you need to know to write your own malloc](https://intranet.atlasschool.com/concepts/922)
#### man or help:
- `sbrk`
- `brk`
- `malloc`
## Learning Objectives
At the end of this project, you are expected to be able to [explain to anyone](https://fs.blog/feynman-learning-technique/), **without the help of Google**:
### General
- What is a program break
- How to play with a program break in order to allocate memory dynamically
- How the glibc `malloc` and `free` functions work
- What is ASLR
- What is memory alignment
- What is a memory page
- How to encapsulate the memory management in order to hide it from the user
## Requirements
### General
- Allowed editors: `vi`, `vim`, `emacs`
- All your files will be compiled on Ubuntu 14.04 LTS
- Your C programs and functions will be compiled with `gcc 4.8.4` using the flags `-Wall` `-Werror` `-Wextra` and `-pedantic`
- All your files should end with a new line
- A `README.md` file, at the root of the folder of the project, is mandatory
- Your code should use the `Betty` style. It will be checked using [betty-style.pl](https://github.com/hs-hq/Betty/blob/main/betty-style.pl) and [betty-doc.pl](https://github.com/hs-hq/Betty/blob/main/betty-doc.pl)
- You are not allowed to have more than 5 functions per file
- The prototypes of all your functions should be included in your header file called `malloc.h`
- Don’t forget to push your header files
- All your header files should be include guarded
- You are allowed to use `global` variables
- You are allowed to use `static` variables
### Betty Compliance
- All the C source files in your directory and subdirectories must be [Betty-compliant](https://github.com/hs-hq/betty)
### Allowed Functions and System Calls
- Unless specified otherwise, you are allowed to use the C standard library
- Of course, you’re not allowed to use the `malloc` family from the C library…
### Tests
- It is strongly advised to test your functions against real programs, like a shell, or your old projects for example.
- To do so, you can name your functions `malloc`, `free`, `realloc` and `calloc` (just like they're named in the glibc), and compile them into a shared library that you would load when executing a program using `LD_LIBRARY_PATH` and `LD_PRELOAD`
- [Here’s a tutorial on how to do it](https://www.cprogramming.com/tutorial/shared-libraries-linux-gcc.html)
## More Info
### Important
It is not required that your `_malloc`, `free`, `calloc` and `realloc` behave exactly like the glibc `malloc`, `free`, `calloc` and `realloc`:
- You are free to use any data structure that suits you as long as their purpose is well defined
- You are free to handle the heap as it suits you, as long as the returned pointers (for the functions that return a pointer) are aligned as required and that enough space is available
- You are free to extend the program break as it suits you, as long as it is extended by a multiple of the virtual memory page size, and as long as it is reduced when needed
- You decide of your implementation. During the correction, we will mainly focus on the strength and reliability of your functions, so make sure to handle big allocations :)
#
## Tasks
#### 0. Naive malloc
Read carefully the [concept page for this project](https://intranet.atlasschool.com/concepts/922)

Build the naive malloc that is presented in the concept page.
- Prototype: `void *naive_malloc(size_t size);`
- Where `size` is the size needed to be allocated for the user
- Your function must return a pointer to the allocated memory that is suitably aligned for any kind of variable
- You naive malloc should be able to:
    - Allocate enough memory to store
        - A `size_t` as the chunk header
        - The size requested as parameter
    - Allocate memory pages only
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `naive_malloc.c`, `malloc.h`
#
#### 1. malloc
Write you own `malloc` function that allocates space in the heap
- Prototype: `void *_malloc(size_t size);`
- Where `size` is the size needed to be allocated for the user
- Your function must return a pointer to the allocated memory that is suitably aligned for any kind of variable
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `malloc.c`, `malloc.h`
#
#### 2. free
Write you own `free` function that frees a memory space
- Prototype: `void _free(void *ptr);`
- Where `ptr` is a pointer to the memory space to be freed
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `free.c`, `malloc.c`, `malloc.h`
#
## Advanced Tasks
#### 3. calloc
Write you own `malloc` function that allocates space in the heap
- Prototype: `void *_calloc(size_t nmemb, size_t size);`
- Where `nmemb` is the number of elements in the array, and `size` is the size of each element
- Your function must return a pointer to the allocated memory that is suitably aligned for any kind of variable
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `calloc.c`, `free.c`, `malloc.c`, `malloc.h`
#
#### 4. realloc
Write you own `malloc` function that allocates space in the heap
- Prototype: `void *_realloc(void *ptr, size_t size);`
- Where `ptr` is a pointer to the memory space to resize, and `size` is the new size needed to be allocated for the user
- Your function must return a pointer to the new allocated memory that is suitably aligned for any kind of variable
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `realloc.c`, `free.c`, `malloc.c`, `malloc.h`
#
#### 5. Multithreading
Handle multithreading !

Your functions `_malloc`, `_free`, `_realloc`, and `_calloc` must be thread safe

Your functions will be compiled and linked with the flag `-pthread`

Resources:
- [pthread.h](https://pubs.opengroup.org/onlinepubs/7908799/xsh/pthread.h.html)
- [Thread safety](https://en.wikipedia.org/wiki/Thread_safety)
#
#### Repo:
- GitHub repository: `atlas-malloc`
- File: `malloc.c`, `free.c`, `realloc.c`, `calloc.c`, `malloc.h`
#
## Files
| **File** | **Description** |
|----------|----------------:|
|malloc.h| Header file for Programs|
|naive_malloc.c| Simple memory allocation|
|malloc.c| Recreating malloc function|
|free.c| Freeing allocated memory|
|calloc.c| Recreating the calloc function|
|realloc.c| Recreating the realloc function|
## Authors / Contact info
- **Sammy Ansari** **|** [Github](https://github.com/O-01) **|** [LinkedIn](https://linkedin.com/in/sammy-ansari) **|** [Email](mailto:sam.ansari@atlasschool.com)
- **Logan Savage** **|** [Github](https://github.com/SavageLM) **|** [LinkedIn](https://www.linkedin.com/in/logan-m-savage/) **|** [Email](mailto:logan.savage@atlasschool.com)  
#
![Atlas School](https://assets-global.website-files.com/6571f4826e9363343bcd2acd/658c333153345aa78869f0b3_logo-atlas-school-blue-lightning-bug.svg)
#