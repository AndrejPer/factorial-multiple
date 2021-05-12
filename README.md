# factorial-multiple

The project decsription goes as follows:
 Given a positive integer N, what is the minimum positive integer K such that K! is a multiple of the square of N?
Note that a is a multiple of b if a=b*k for some integer k.
Moreover, note that for any positive integer M, M! is the product of all positive integers whose value is at most M.
Constraints:
1<= T <= 200000
1<= N <= 200000

The general flow of the program is:
    - number is iputed as integer and converted to string of digit characters
    - variable for enumerating natural number is initiated with the same value (it' is charge of finding K)
    - after that, string representations are manupulated (by multiplication) to find the desired K
    - one challenge was finding a way to determine divisibility with number in this format, so I went with the option of looking for k by good ol' enumarating of naturals from 1... (k here refers to b = a * k, where b is a multiple of a)
    - this way of determening requires a lot of computations, but I tried reducing redundant ones as much as possible
 BOTTLENECKS:
    - current limits are theoretically set by string size for the "big value" that should be the multiple on N!, currently at 300 digits (not mentioning of course physical limitations of machines)

 OPTIMIZATIONS
    1) when calculating the divisibility of K! over N! ^ 2, we can see there are numbers that can be "eliminated"
        for exmple, 24! / (12! ^ 2) will acually be 24 * 23 * ... * 13 / 12 * 11 * ... * 1
    2) when checking for divisibility, instead of enumerating k from 1 till forever and checking for every possible value, we calculate the range of number of digits k can have and start from there
