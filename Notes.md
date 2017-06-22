# Question
> Imagine you have a input stream and you have to get _m_ samples evenly distributed acrossing the input stream.(The size of input stream is larger than m)

1. Get some names from phone book
2. Get sample transaction data from Walmart during "ThanksGiving".

## Simple Solution
Assigning a random value on each element in the stream then get the top _m_ numbered elements from the stream. This is similar to how a SQL Query with ORDER_BY_RAND() works. There would be a O(n) space complexity.

## Resevoir Sampling

=======
-------
