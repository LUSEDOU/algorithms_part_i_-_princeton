
# Autograder Feedback

<body>

<p>
<em>
See the Assessment Guide for information on how to interpret this report.
</em>

</p><p>
<em>
Want to receive personalized feedback on this submission?
You can pay to have a teaching assistant read and provide
personalized feedback on your submission at https://mooc.codepost.io.
</em>

<br><br>

## ASSESSMENT SUMMARY
<pre>
Compilation:  <font color="#009900">PASSED</font>
API:          <font color="#009900">PASSED</font>

SpotBugs:     <font color="#009900">PASSED</font>
PMD:          <font color="#990000">FAILED (1 warning)</font>
Checkstyle:   <font color="#990000">FAILED (0 errors, 24 warnings)</font>

Correctness:  <font color="#1C9900">32/38 tests passed</font>
Memory:       <font color="#009900">8/8 tests passed</font>
Timing:       <font color="#009900">20/20 tests passed</font>

Aggregate score: 90.53%
[ Compilation: 5%, API: 5%, Style: 0%, Correctness: 60%, Timing: 10%, Memory: 20% ]
</pre>


<br><br>

<h2>ASSESSMENT DETAILS</h2>

<pre>
The following files were submitted:
----------------------------------
3.1K Jun  3 01:24 Percolation.java
2.3K Jun  3 01:24 PercolationStats.java


********************************************************************************
*  COMPILING                                                                    
********************************************************************************


% javac Percolation.java
*-----------------------------------------------------------

% javac PercolationStats.java
*-----------------------------------------------------------


================================================================


Checking the APIs of your programs.
*-----------------------------------------------------------
Percolation:

PercolationStats:

================================================================


********************************************************************************
*  CHECKING STYLE AND COMMON BUG PATTERNS                                       
********************************************************************************


% spotbugs *.class
*-----------------------------------------------------------


================================================================


% pmd .
*-----------------------------------------------------------
Percolation.java:108: The method body is empty. If this is your intent, document it with a comment. [UncommentedEmptyMethodBody]
PMD ends with 1 warning.


================================================================


% checkstyle *.java
*-----------------------------------------------------------
[WARN] Percolation.java:1:3: '//' or '/*' is not followed by whitespace. [WhitespaceAfter]
[WARN] Percolation.java:2:3: '//' or '/*' is not followed by whitespace. [WhitespaceAfter]
[WARN] Percolation.java:6:30: The constant 'top' must be ALL_UPPERCASE, with words separated by underscores. [ConstantName]
[WARN] Percolation.java:14:30: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:15:15: '&lt;=' is not followed by whitespace. [WhitespaceAround]
[WARN] Percolation.java:26:39: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:74:44: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:81:44: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:82:29: '&lt;=' is not followed by whitespace. [WhitespaceAround]
[WARN] Percolation.java:82:56: '&lt;=' is not followed by whitespace. [WhitespaceAround]
[WARN] Percolation.java:87:11: '//' or '/*' is not followed by whitespace. [WhitespaceAfter]
[WARN] Percolation.java:92:35: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:97:32: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:101:50: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] Percolation.java:108:43: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:9:5: Declare static variables before instance variables, constructors, and methods. [DeclarationOrder]
[WARN] PercolationStats.java:9:33: The constant 'const96' must be ALL_UPPERCASE, with words separated by underscores. [ConstantName]
[WARN] PercolationStats.java:12:47: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:22:21: Do not use the letter 'l' as a local variable name. It is hard to distinguish from the number '1'. [LocalVariableName]
[WARN] PercolationStats.java:35:25: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:40:27: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:45:33: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:50:33: '{' is not preceded with whitespace. [WhitespaceAround]
[WARN] PercolationStats.java:55:42: '{' is not preceded with whitespace. [WhitespaceAround]
Checkstyle ends with 0 errors and 24 warnings.

% custom checkstyle checks for Percolation.java
*-----------------------------------------------------------

% custom checkstyle checks for PercolationStats.java
*-----------------------------------------------------------


================================================================


********************************************************************************
*  TESTING CORRECTNESS
********************************************************************************

Testing correctness of Percolation
*-----------------------------------------------------------
Running 21 total tests.

Tests 1 through 7 create a Percolation object using your code, then repeatedly
open sites by calling open(). After each call to open(), it checks the return
values of isOpen(), percolates(), numberOfOpenSites(), and isFull() in that order.
Tests 12 through 15 create a Percolation object using your code, then repeatedly
call the methods open(), isOpen(), isFull(), percolates(), and, numberOfOpenSites()
in random order with probabilities p = (p1, p2, p3, p4, p5). The tests stop
immediately after the system percolates.

Tests 18 through 21 test backwash.

Except as noted, a site is opened at most once.

Test 1: open predetermined list of sites using file inputs
  * filename = input6.txt
  * filename = input8.txt
  * filename = input8-no.txt
  * filename = input10-no.txt
  * filename = greeting57.txt
  * filename = heart25.txt
==&gt; passed

Test 2: open random sites until the system percolates
  * n = 3
  * n = 5
  * n = 10
  * n = 10
  * n = 20
  * n = 20
  * n = 50
  * n = 50
==&gt; passed

Test 3: open predetermined sites for n = 1 and n = 2 (corner case test)
  * filename = input1.txt
  * filename = input1-no.txt
  * filename = input2.txt
  * filename = input2-no.txt
==&gt; passed

Test 4: check predetermined sites with long percolating path
  * filename = snake13.txt
  * filename = snake101.txt
==&gt; passed

Test 5: open every site
  * filename = input5.txt
==&gt; passed

Test 6: open random sites until the system percolates,
        allowing open() to be called on a site more than once
  * n = 3
    - numberOfOpenSites() returns wrong value after 3 sites opened
    - student   numberOfOpenSites() = 4
    - reference numberOfOpenSites() = 3

  * n = 5
    - numberOfOpenSites() returns wrong value after 2 sites opened
    - student   numberOfOpenSites() = 3
    - reference numberOfOpenSites() = 2

  * n = 10
    - numberOfOpenSites() returns wrong value after 11 sites opened
    - student   numberOfOpenSites() = 12
    - reference numberOfOpenSites() = 11

  * n = 10
    - numberOfOpenSites() returns wrong value after 23 sites opened
    - student   numberOfOpenSites() = 24
    - reference numberOfOpenSites() = 23

  * n = 20
    - numberOfOpenSites() returns wrong value after 32 sites opened
    - student   numberOfOpenSites() = 33
    - reference numberOfOpenSites() = 32

  * n = 20
    - numberOfOpenSites() returns wrong value after 27 sites opened
    - student   numberOfOpenSites() = 28
    - reference numberOfOpenSites() = 27

  * n = 50
    - numberOfOpenSites() returns wrong value after 53 sites opened
    - student   numberOfOpenSites() = 54
    - reference numberOfOpenSites() = 53

  * n = 50
    - numberOfOpenSites() returns wrong value after 30 sites opened
    - student   numberOfOpenSites() = 31
    - reference numberOfOpenSites() = 30

==&gt; <font color="#990000"><b>FAILED</b></font>

Test 7: open random sites with large n
  * n = 250
  * n = 500
  * n = 1000
  * n = 2000
==&gt; passed

Test 8: call methods with invalid arguments
  * n = 10, (row, col) = (-1, 5)
  * n = 10, (row, col) = (11, 5)
  * n = 10, (row, col) = (0, 5)
  * n = 10, (row, col) = (5, -1)
  * n = 10, (row, col) = (5, 11)
  * n = 10, (row, col) = (5, 0)
  * n = 10, (row, col) = (-2147483648, -2147483648)
  * n = 10, (row, col) = (2147483647, 2147483647)
==&gt; passed

Test 9: call constructor with invalid argument
  * n = -10
  * n = -1
  * n = 0
==&gt; passed

Test 10: create multiple Percolation objects at the same time
        (to make sure you didn't store data in static variables)
==&gt; passed

Test 11: open predetermined list of sites using file inputs,
         but permute the order in which methods are called
  * filename = input8.txt;  order =     isFull(),     isOpen(), percolates()
  * filename = input8.txt;  order =     isFull(), percolates(),     isOpen()
  * filename = input8.txt;  order =     isOpen(),     isFull(), percolates()
  * filename = input8.txt;  order =     isOpen(), percolates(),     isFull()
  * filename = input8.txt;  order = percolates(),     isOpen(),     isFull()
  * filename = input8.txt;  order = percolates(),     isFull(),     isOpen()
==&gt; passed

Test 12: call open(), isOpen(), and numberOfOpenSites()
         in random order until just before system percolates
  * n = 3, trials = 40, p = (0.4, 0.4, 0.0, 0.0, 0.3)
  * n = 5, trials = 20, p = (0.4, 0.4, 0.0, 0.0, 0.3)
  * n = 7, trials = 10, p = (0.4, 0.4, 0.0, 0.0, 0.3)
  * n = 10, trials = 5, p = (0.4, 0.4, 0.0, 0.0, 0.3)
  * n = 20, trials = 2, p = (0.4, 0.4, 0.0, 0.0, 0.3)
  * n = 50, trials = 1, p = (0.4, 0.4, 0.0, 0.0, 0.3)
==&gt; passed

Test 13: call open() and percolates() in random order until just before system percolates
  * n = 3, trials = 40, p = (0.5, 0.0, 0.0, 0.5, 0.0)
  * n = 5, trials = 20, p = (0.5, 0.0, 0.0, 0.5, 0.0)
  * n = 7, trials = 10, p = (0.5, 0.0, 0.0, 0.5, 0.0)
  * n = 10, trials = 5, p = (0.5, 0.0, 0.0, 0.5, 0.0)
  * n = 20, trials = 2, p = (0.5, 0.0, 0.0, 0.5, 0.0)
  * n = 50, trials = 1, p = (0.5, 0.0, 0.0, 0.5, 0.0)
==&gt; passed

Test 14: call open() and isFull() in random order until just before system percolates
  * n = 3, trials = 40, p = (0.5, 0.0, 0.5, 0.0, 0.0)
  * n = 5, trials = 20, p = (0.5, 0.0, 0.5, 0.0, 0.0)
  * n = 7, trials = 10, p = (0.5, 0.0, 0.5, 0.0, 0.0)
  * n = 10, trials = 5, p = (0.5, 0.0, 0.5, 0.0, 0.0)
  * n = 20, trials = 2, p = (0.5, 0.0, 0.5, 0.0, 0.0)
  * n = 50, trials = 1, p = (0.5, 0.0, 0.5, 0.0, 0.0)
==&gt; passed

Test 15: call all methods in random order until just before system percolates
  * n = 3, trials = 40, p = (0.2, 0.2, 0.2, 0.2, 0.2)
  * n = 5, trials = 20, p = (0.2, 0.2, 0.2, 0.2, 0.2)
  * n = 7, trials = 10, p = (0.2, 0.2, 0.2, 0.2, 0.2)
  * n = 10, trials = 5, p = (0.2, 0.2, 0.2, 0.2, 0.2)
  * n = 20, trials = 2, p = (0.2, 0.2, 0.2, 0.2, 0.2)
  * n = 50, trials = 1, p = (0.2, 0.2, 0.2, 0.2, 0.2)
==&gt; passed

Test 16: call all methods in random order until almost all sites are open
         (with inputs not prone to backwash)
  * n = 3
  * n = 5
  * n = 7
  * n = 10
  * n = 20
  * n = 50
==&gt; passed

Test 17: substitute WeightedQuickUnionUF data type that sets root nondeterministically;
         call all methods in random order until almost all sites are open
         (with inputs not prone to backwash)
  * n = 3
  * n = 5
  * n = 7
  * n = 10
  * n = 20
  * n = 50
==&gt; passed

Test 18: check for backwash with predetermined sites
  * filename = input20.txt
    - isFull() returns wrong value after 231 sites opened
    - student   isFull(18, 1) = true
    - reference isFull(18, 1) = false

  * filename = input10.txt
    - isFull() returns wrong value after 56 sites opened
    - student   isFull(9, 1) = true
    - reference isFull(9, 1) = false

  * filename = input50.txt
    - isFull() returns wrong value after 1412 sites opened
    - student   isFull(22, 28) = true
    - reference isFull(22, 28) = false

  * filename = jerry47.txt
    - isFull() returns wrong value after 1076 sites opened
    - student   isFull(11, 47) = true
    - reference isFull(11, 47) = false

  * filename = sedgewick60.txt
    - isFull() returns wrong value after 1577 sites opened
    - student   isFull(21, 59) = true
    - reference isFull(21, 59) = false

  * filename = wayne98.txt
    - isFull() returns wrong value after 3851 sites opened
    - student   isFull(69, 9) = true
    - reference isFull(69, 9) = false

==&gt; <font color="#990000"><b>FAILED</b></font>

Test 19: check for backwash with predetermined sites that have
         multiple percolating paths
  * filename = input3.txt
    - isFull() returns wrong value after 4 sites opened
    - student   isFull(3, 1) = true
    - reference isFull(3, 1) = false

  * filename = input4.txt
    - isFull() returns wrong value after 7 sites opened
    - student   isFull(4, 4) = true
    - reference isFull(4, 4) = false

  * filename = input7.txt
    - isFull() returns wrong value after 12 sites opened
    - student   isFull(6, 1) = true
    - reference isFull(6, 1) = false

==&gt; <font color="#990000"><b>FAILED</b></font>

Test 20: call all methods in random order until all sites are open
         (these inputs are prone to backwash)
  * n = 3
    - isFull() returns wrong value after 5 sites opened
    - student   isFull(3, 3) = true
    - reference isFull(3, 3) = false

    - failed on trial 4 of 40

  * n = 5
    - isFull() returns wrong value after 16 sites opened
    - student   isFull(3, 5) = true
    - reference isFull(3, 5) = false

    - failed on trial 2 of 20

  * n = 7
    - isFull() returns wrong value after 27 sites opened
    - student   isFull(7, 2) = true
    - reference isFull(7, 2) = false

    - failed on trial 1 of 10

  * n = 10
    - isFull() returns wrong value after 69 sites opened
    - student   isFull(7, 9) = true
    - reference isFull(7, 9) = false

    - failed on trial 1 of 5

  * n = 20
    - isFull() returns wrong value after 220 sites opened
    - student   isFull(18, 12) = true
    - reference isFull(18, 12) = false

    - failed on trial 1 of 2

  * n = 50
    - isFull() returns wrong value after 1490 sites opened
    - student   isFull(39, 46) = true
    - reference isFull(39, 46) = false

    - failed on trial 1 of 1

==&gt; <font color="#990000"><b>FAILED</b></font>

Test 21: substitute WeightedQuickUnionUF data type that sets root nondeterministically;
         call all methods in random order until all sites are open
         (these inputs are prone to backwash)
  * n = 3
    - isFull() returns wrong value after 6 sites opened
    - student   isFull(3, 1) = true
    - reference isFull(3, 1) = false

    - failed on trial 16 of 40

  * n = 5
    - isFull() returns wrong value after 16 sites opened
    - student   isFull(3, 3) = true
    - reference isFull(3, 3) = false

    - failed on trial 7 of 20

  * n = 7
    - isFull() returns wrong value after 30 sites opened
    - student   isFull(7, 3) = true
    - reference isFull(7, 3) = false

    - failed on trial 2 of 10

  * n = 10
    - isFull() returns wrong value after 65 sites opened
    - student   isFull(7, 9) = true
    - reference isFull(7, 9) = false

    - failed on trial 1 of 5

  * n = 20
    - isFull() returns wrong value after 209 sites opened
    - student   isFull(7, 17) = true
    - reference isFull(7, 17) = false

    - failed on trial 1 of 2

  * n = 50
    - isFull() returns wrong value after 1473 sites opened
    - student   isFull(27, 8) = true
    - reference isFull(27, 8) = false

    - failed on trial 1 of 1

==&gt; <font color="#990000"><b>FAILED</b></font>


Total: 16/21 tests passed!


================================================================
********************************************************************************
*  TESTING CORRECTNESS (substituting reference Percolation)
********************************************************************************

Testing correctness of PercolationStats
*-----------------------------------------------------------
Running 17 total tests.

Test 1: check formatting of output of main()
  % java-algs4 PercolationStats 20 10
  mean                    = 0.5905
  stddev                  = 0.07520158095264871
  95% confidence interval = 0.5438895772266427, 0.6371104227733574

   - line 2 of output in student solution: 
     '95% confidence interval = 0.5438895772266427, 0.6371104227733574'
   - the required format is:
     '95% confidence interval = [&lt;double&gt;, &lt;double&gt;]'

  % java-algs4 PercolationStats 200 100
  mean                    = 0.5907682499999999
  stddev                  = 0.01051021620300165
  95% confidence interval = 0.5887082476242116, 0.5928282523757882

   - line 2 of output in student solution: 
     '95% confidence interval = 0.5887082476242116, 0.5928282523757882'
   - the required format is:
     '95% confidence interval = [&lt;double&gt;, &lt;double&gt;]'

==&gt; <font color="#990000"><b>FAILED</b></font>

Test 2: check that methods in PercolationStats do not print to standard output
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 3: check that mean() returns value in expected range
  * n =   2, trials = 10000
  * n =   5, trials = 10000
  * n =  10, trials = 10000
  * n =  25, trials = 10000
==&gt; passed

Test 4: check that stddev() returns value in expected range
  * n =   2, trials = 10000
  * n =   5, trials = 10000
  * n =  10, trials = 10000
  * n =  25, trials = 10000
==&gt; passed

Test 5: check that PercolationStats constructor creates
        trials Percolation objects, each of size n-by-n
  * n =  15, trials =  15
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 6: check that PercolationStats.main() creates
        trials Percolation objects, each of size n-by-n
  * n =  15, trials =  15
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 7: check that PercolationStats calls open() until system percolates
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 8: check that PercolationStats does not call open() after system percolates
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 9: check that mean() is consistent with the number of intercepted calls to open()
        on blocked sites
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 10: check that stddev() is consistent with the number of intercepted calls to open()
         on blocked sites
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 11: check that confidenceLo() and confidenceHigh() are consistent with mean() and stddev()
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 12: check that exception is thrown if either n or trials is out of bounds
  * n = -23, trials =  42
  * n =  23, trials =   0
  * n = -42, trials =   0
  * n =  42, trials =  -1
  * n = -2147483648, trials = -2147483648
==&gt; passed

Test 13: create two PercolationStats objects at the same time and check mean()
         (to make sure you didn't store data in static variables)
  * n1 =  50, trials1 =  10, n2 =  50, trials2 =   5
  * n1 =  50, trials1 =   5, n2 =  50, trials2 =  10
  * n1 =  50, trials1 =  10, n2 =  25, trials2 =  10
  * n1 =  25, trials1 =  10, n2 =  50, trials2 =  10
  * n1 =  50, trials1 =  10, n2 =  15, trials2 = 100
  * n1 =  15, trials1 = 100, n2 =  50, trials2 =  10
==&gt; passed

Test 14: check that the methods return the same value, regardless of
         the order in which they are called
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 15: check that no calls to StdRandom.setSeed()
  * n = 20, trials = 10
  * n = 20, trials = 10
  * n = 40, trials = 10
  * n = 80, trials = 10
==&gt; passed

Test 16: check distribution of number of sites opened until percolation
  * n = 2, trials = 100000
  * n = 3, trials = 100000
  * n = 4, trials = 100000
==&gt; passed

Test 17: check that each site is opened the expected number of times
  * n = 2, trials = 100000
  * n = 3, trials = 100000
  * n = 4, trials = 100000
==&gt; passed


Total: 16/17 tests passed!


================================================================
********************************************************************************
*  MEMORY (substituting reference Percolation)
********************************************************************************

Analyzing memory of PercolationStats
*-----------------------------------------------------------
Running 4 total tests.

Test 1a-1d: check memory usage as a function of T trials for n = 100
            (max allowed: 8*T + 128 bytes)

                 T        bytes
--------------------------------------------
=&gt; passed       16          184         
=&gt; passed       32          312         
=&gt; passed       64          568         
=&gt; passed      128         1080         
==&gt; 4/4 tests passed


Estimated student memory = 8.00 T + 56.00   (R^2 = 1.000)

Total: 4/4 tests passed!


================================================================



********************************************************************************
*  TIMING (substituting reference Percolation)
********************************************************************************

Timing PercolationStats
*-----------------------------------------------------------
Running 4 total tests.

Test 1: Call PercolationStats constructor and instance methods and
        count calls to StdStats.mean() and StdStats.stddev().
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 2: Call PercolationStats constructor and instance methods and
        count calls to methods in StdRandom.
  * n = 20, trials = 10
  * n = 20, trials = 10
  * n = 40, trials = 10
  * n = 80, trials = 10
==&gt; passed

Test 3: Call PercolationStats constructor and instance methods and
        count calls to methods in Percolation.
  * n =  20, trials =  10
  * n =  50, trials =  20
  * n = 100, trials =  50
  * n =  64, trials = 150
==&gt; passed

Test 4: Call PercolationStats constructor and instance methods with trials = 3
        and values of n that go up by a multiplicative factor of sqrt(2).
        The test passes when n reaches 2,896.

     The approximate order-of-growth is n ^ (log ratio)

         n  seconds log ratio
     ------------------------
       724     0.15       2.6
      1024     0.35       2.6
      1448     1.03       3.1
      2048     2.52       2.6
      2896     6.28       2.6
==&gt; passed


Total: 4/4 tests passed!


================================================================



********************************************************************************
*  MEMORY
********************************************************************************

Analyzing memory of Percolation
*-----------------------------------------------------------
Running 4 total tests.

Test 1a-1d: check that total memory &lt;= 17 n^2 + 128 n + 1024 bytes

                 n        bytes
--------------------------------------------
=&gt; passed       64        39096         
=&gt; passed      256       598200         
=&gt; passed      512      2375864         
=&gt; passed     1024      9470136         
==&gt; 4/4 tests passed


Estimated student memory = 9.00 n^2 + 32.00 n + 184.00   (R^2 = 1.000)


Test 2 (bonus): check that total memory &lt;= 11 n^2 + 128 n + 1024 bytes
   -  bonus available only if solution passes backwash correctness test
==&gt; <font color="#990000"><b>FAILED</b></font>


Total: 4/4 tests passed!


================================================================



********************************************************************************
*  TIMING
********************************************************************************

Timing Percolation
*-----------------------------------------------------------
Running 16 total tests.

Test 1a-1e: Creates an n-by-n percolation system; open sites at random until
            the system percolates, interleaving calls to percolates() and open().
            Count calls to connected(), union() and find().

                                       2 * connected()
                 n       union()              + find()        constructor
-----------------------------------------------------------------------------------
=&gt; passed       16          126                   240                   1         
=&gt; passed       32          756                  1226                   1         
=&gt; passed       64         2886                  4818                   1         
=&gt; passed      128        10961                 18902                   1         
=&gt; passed      256        47053                 78510                   1         
=&gt; passed      512       185960                311980                   1         
=&gt; passed     1024       739870               1245098                   1         
==&gt; 7/7 tests passed


If one of the values in the table violates the performance limits
the factor by which you failed the test appears in parentheses.
For example, (9.6x) in the union() column indicates that it uses
9.6x too many calls.


Tests 2a-2f: Check whether the number of calls to union(), connected(), and find()
             is a constant per call to open(), isOpen(), isFull(), and percolates().
             The table shows the maximum number of union() and find() calls made
             during a single call to open(), isOpen(), isFull(), and percolates().
             One call to connected() counts as two calls to find().

                 n     per open()      per isOpen()    per isFull()    per percolates() 
---------------------------------------------------------------------------------------------
=&gt; passed       16        4               0               2               2         
=&gt; passed       32        4               0               2               2         
=&gt; passed       64        4               0               2               2         
=&gt; passed      128        4               0               2               2         
=&gt; passed      256        4               0               2               2         
=&gt; passed      512        4               0               2               2         
=&gt; passed     1024        4               0               2               2         
==&gt; 7/7 tests passed



Running time (in seconds) depends on the machine on which the script runs.


Test 3: Create an n-by-n percolation system; interleave calls to percolates()
        and open() until the system percolates. The values of n go up by a
        factor of sqrt(2). The test is passed if n &gt;= 4096 in under 10 seconds.

     The approximate order-of-growth is n ^ (log ratio)

                        log   union-find     log
         n  seconds   ratio   operations   ratio
     -------------------------------------------
      1448     0.24     2.8      5446048     2.0
      2048     0.60     2.7     10818238     2.0
      2896     1.62     2.9     21663310     2.0
      4096     3.87     2.5     43299790     2.0
==&gt; passed



Test 4: Create an n-by-n percolation system; interleave calls to open(),
        percolates(), isOpen(), isFull(), and numberOfOpenSites() until.
        the system percolates. The values of n go up by a factor of sqrt(2).
        The test is passed if n &gt;= 4096 in under 10 seconds.

                        log   union-find     log
         n  seconds   ratio   operations   ratio
     -------------------------------------------
      1024     0.10     2.1      3891990     2.0
      1448     0.25     2.6      7887610     2.0
      2048     0.64     2.7     15758410     2.0
      2896     1.82     3.0     31600924     2.0
      4096     4.16     2.4     63328752     2.0
==&gt; passed


Total: 16/16 tests passed!


================================================================




</pre>


</body></html>
