## Installation
### GNU C Compiler
    g++ -std=c++11 -fopenmp -O3 -o bin/grep src/grep.cpp

### Makefile
    make
    make install
    
### Intel C Compiler
    icc -std=c++11 -openmp -O3 -o bin/grep src/grep.cpp
    
### Makefile
    make icc
    make install

## Usage
### Command Syntax:
    grep [-A <#> | -f <file> | -h | -r | -v | -V | -w] <search term>

### Modes:

    -A    After Context         grep will grab a number of lines after the line containing the
                                <search term>. This does not work with search inversion.
                                
    -f    Single File Search    Signals grep to only search the <file> for the <search term>. If -f is not
                                used, grep will search the entire directory from where grep is called from.

    -h    Include Hidden        Will include hidden files in the search. Default search behavior is to
                                ignore hidden files.

    -r    Recursive Search      Recursively searches through the directory and all sub directories for the 
                                given <search term>. Will not do anything if the [-f <file>] flag is given.

    -v    Search Inversion      Search for every line that does not include the <search term>.

    -V    Enable Verbose        The file path to the file will be printed along with the search result.
    
    -w    File Parallelism      Signals grep to perform single-threaded searches of multiple files. Default
                                search behavior is to search files one at a time with mulitple threads.
                                This is optimal when the files are small, similar size, or there are many.
