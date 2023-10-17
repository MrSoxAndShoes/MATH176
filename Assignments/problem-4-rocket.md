MATH 176, Problem 4, Spring 87

Objective: To learn how to read data from an input file (text 3.4)
           To learn how to write results to an output file (text 3.4)
           To learn about logical variables
           To learn about IF statements
           To learn about DO statements.

Problem: Modify the rocket problem as stated on page 96 of the text so
         that the following input data will be read from a data file
           line 1: Total time                  sample value: 100
           line 2: Distance for time change                   50
           line 3: Initial time increment                      2
           line 4: Final time increment                        0.5
         The output should look like that shown on page 99 of the text.
         The output information should be written to an output file.

Turn-In: 1. A listing of the input file
         2. A FTNLIST of the program
         3. A listing of th output file
         4. A sample hand calculation to verify the program results.

HINTS: -- Study the sample programs in the text ; Sections 3.4 and 3.5
       -- Construct the program in two steps;
          step 1: a correctly operating program using subroutine INPUT for
                  the program input and the terminal screen for output.
          step 2: change step 1 into the final end-product by changing the
                  input and output to files.
       -- A DO loop could be used to solve this problem. FORTRAN 77 on the
          HP3000 does have a form of the DO statement as follows:
                 DO WHILE (logical expression)
                     .
                     .
                     .
                 END DO
