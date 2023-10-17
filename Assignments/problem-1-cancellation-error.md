# Problem 1: Cancellation Error

**OBJECTIVE**: This program accepts an input X value and computes a Y value
according to the formula:

```
    Y =        1
        ───────────────
          1 - (X - 1)
              ───────
                 X
```
The % error between the X and Y values is computed.

The input X, output Y, and % error are printed as output.

## SAMPLE PROGRAM:

```
$CONTROL USLINIT, INIT
      PROGRAM CANCEL
C
C     PROGRAM 1 BY (your name)
C
C     OBJECTIVE: TO DEMONSTRATE CANCELLATION ERROR
C
C     VARIABLES:    X = INPUT VALUE
C                   Y = COMPUTED VALUE
C               ERROR = PERCENTAGE ERROR BETWEEN X AND Y
C
C     FOPMULA FOR THE COMFUTATION OF Y:  Y = 1/(1-(X-1)/X)
C     FORMULA FOR PERCENTAGE ERROR:  ERROR = ((X-Y)/X)*100
C
C2345678901234567890
      REAL X,Y,ERROR
C
      PRINT ' TO END PROGRAM LET X <= 0'
   10 PRINT ' INPUT THE X VALUE'
C
      READ X
C
      IF(X .LE. 0) GO TO 20
      Y = 1/(1-(X-1)/X)
      ERROR = ((X-Y)/X)*100
C
      PRINT '     X = ',X
      PRINT '     Y = ',Y
      PRINT ' ERROR = ',ERROR
      PRINT ' '
      GO TO 10
C
   20 PRINT 'END OF PROGRAM'
      STOP
      END
```

**NOTES**: The error between the input and output values, which are
mathematically equal, is due to the fact that (x-1)/x cannot always be
represented in binary form with perfect accuracy: e.g. 8/9 will have a
round off error. This error is compounded by further calculations,
particularly the subtraction which is the next step in evaluating the
formula. This discrepancy is an illustration of cancellation error -
caused by the subtraction of two numbers roughly equal in magnitude.

The cancellation error can be very severe when the two numbers are
very close to one another. In this example program the proximity to (x-1)/x
and 1 causes the cancellation error. Since (x-1)/x approaches 1 as x
increases, this error becomes more severe as x increases...check this out!
