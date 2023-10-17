# Problem 2 - Accumulation Error

**Objective**: This program requests you to input a number of pennies (P) to be
added together to produce a total value expressed in dollars according to
the formula

```
                              P
                      TOTAL = Σ .01
                              K = 1
```

The error between the exact value of P pennies and the formula value is calculated.

## SAMPLE PROGRAM;
```
$CONTROL USLINIT, INIT
      PROGRAM ACCUM
C
C     PROGRAM 2 BY (your name)
C
C     OBJECTIVE: TO DEMONSTRATE ACCUMULATION ERROR
C
C     VARIABLES:    P = NUMBER OF F'ENNIES TO BE ADDED
C               TOTAL = TOTAL VALUE OF ACCUMULATED PENNIES
C                   K = COUNTER FOR NUMBER OF PENNIES ADDED
C               ERROR = DIFFERENCE BETWEEN EXACT AND FORMULA TOTALS
C
C2345678901234567890
      REAL ERROR, TOTAL, EXACT
      INTEGER K, P
C
      PRINT *, 'TO END PROGRAM LET P <= 0 '
   10 PRINT *, 'INPUT THE NUMBER OF PENNIES P '
C
      READ *, P
C
      IF (P .LE. 0) GO TO 20
      TOTAL = 0.0
      DO K = 1, P
         TOTAL = TOTAL + 0.01
      END DO
      EXACT = P/100
      ERROR = EXACT - TOTAL
C
      PRINT *, ' '
      PRINT *, ' EXACT VALUE = ', EXACT
      PRINT *, ' TOTAL VALUE = ', TOTAL
      PRINT *, '       ERROR = ', ERROR
      PRINT *, ' '
C
      GO TO 10
C
   20 PRINT *, ' '
      PRINT *, '********************'
      PRINT *, '** END OF PROGRAM **'
      PRINT *, '********************'
      PRINT *, ' '
      STOP
      END
```

**NOTES**: The output from this program is not mathematically expected- you
would expect zero error! There is a difference in the total value and the
exact value because the binary representation of 0.01 is slightly inexact.
This imprecision is compounded by the repeated addition. e.g. when counting
20,000 pennies there is, on some computers, an error of 3 pennies.

See if you can find a relationship between the number of pennies counted and
the size of the error? (IF YOU TRY COUNTING 2,000,000 PENNIES ON AN IBM PC
IT WILL REQUIRE 2.5 HOURS....BE CAREFULL!!!)

BOTH of these first two programs can be improved in terms of the measured
error by:

   1) improvement of programming logic.
   2) the use of double precision numbers.
   3) the use of BCD (binary coded decimal) numbers.

REFERENCES; N.R. Scott, COMPUTER NUMBER SYSTEMS AND ARITHMETIC,
Prentice Hall 1985, a detailed description of BCD arithmetic.
