# RunSuite
Bash program to run a program against a test suite.
A sample run of runSuite would be as follows:

./runSuite suite.txt ./myprogram

The script will then run ./myprogram three times, once for each test specified in suite.txt:

* The first time, it will run `./myprogram` with standard input redirected to come from `test1.in`. The results, captured from standard output, will be compared with `test1.out`.
* The second time, it will run `./myprogram` with standard input redirected to come from `test2.in`. The results, captured from standard output, will be compared with `test2.out`.
* The third time, it will run `./myprogram` with standard input redirected to come from `reallyBigTest.in`. The results, captured from standard output, will be compared with `reallyBigTest.out`.  
If the output of a given test case differs from the expected output, print the following to standard output (assuming test `test2` failed):

```
Test failed: test2
Input:
(contents of test2.in)
Expected:
(contents of test2.out)
Actual:
(contents of the actual program output)
```
