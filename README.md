# LeetCodeOriginalAlgos
If an algo is not written by you originally, it's not worth using

Problem 9
Statement: Check if an int is a palindrom

Solution: 

All integer palindromes are a subset of reversed integers. 

When a number is subtracted by its reversed integer, it gives a resulting number that is a multiple of 9. 
As the number of digits grow, for all numbers with even number of digits give a resulting subtracted number that is a multiple of 9. 
All numbers with odd number of digits give a resulting subtracted number that is a multiple of 9 and 11, except when the first and last digits are same.
All of these and other cases have been handled here.

This can be observed simply by tabultating the results for a few cases:

x         |     reverse of x     |  result (abs)    | multiple of 9    | multiple of 11
81                    18              63              yes                 NA
213                   312             99              yes                 yes 
1234                  4321            3087            yes                 NA
12345                 54321           41976           yes                 yes

The reason why this works is because these numbers are base 10 numbers. All digits are base 10. So, whether you move some digit to left or right,
as is required in reversals, the subtracted digits become multiple of 9. For example, consider a number 81. The unit place is occupied by 1, and
10th place by 8. So, it can be represented as (10x8) + (1x1). It's reverse is 18, which can be represented by (10x1) + (1x8). If you subtract the
two, you will always get a multiple of 9 for each digit.

So, 10x-x + 10y-y = z OR 9(x-y) = z

This is what is used here.
