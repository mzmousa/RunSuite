# RunSuite
### Bash program to run a program against a test suite.

The file `suite-file` contains a list of stems, from which we construct the names of files containing the input and expected output of each test. For example, suppose our suite file is called suite.txt and contains the following entries:  
```
test1
test2
test3
```  
Then our test suite consists of three tests. The first one (test1) will use the file `test1.in` to hold its input, and test1.out to store its expected output. The second one (test2) will use the file `test2.in` to hold its input, and test2.out to store its expected output. The last one (test3) will use the file `test3.in` to hold its input, and reallyBigTest.out to store its expected output.  

A sample run of runSuite would be as follows:

./runSuite suite.txt ./myprogram

The script will then run ./myprogram three times, once for each test specified in suite.txt:

* The first time, it will run `./myprogram` with standard input redirected to come from `test1.in`. The results, captured from standard output, will be compared with `test1.out`.
* The second time, it will run `./myprogram` with standard input redirected to come from `test2.in`. The results, captured from standard output, will be compared with `test2.out`.
* The third time, it will run `./myprogram` with standard input redirected to come from `test3.in`. The results, captured from standard output, will be compared with `test3.out`.
* There is an optional file `testname.args`, which will cause `runSuite` to run `myprogram` with the contents of `testname.args`passed on the command line and the contents of `testname.in` used for input on stdin.

If the output of a given test case differs from the expected output, `runSuite` prints the following to standard output (assuming test `test2` failed):

```
Test failed: test2
Input:
(contents of test2.in)
Expected:
(contents of test2.out)
Actual:
(contents of the actual program output)
```
