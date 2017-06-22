# Question
> Imagine you have a input stream and you have to get _m_ samples evenly distributed acrossing the input stream.(The size of input stream is larger than m)

1. Get some names from phone book
2. Get sample transaction data from Walmart during "ThanksGiving".

## Simple Solution
Assigning a random value on each element in the stream then get the top _m_ numbered elements from the stream. This is similar to how a SQL Query with ORDER_BY_RAND() works. There would be a O(n) space complexity.

## Resevoir Sampling
> To get _m_ samples, we just store _m_ elements in the reservoir.

1. Storing first _m_ elements. If there are only _m_ elements, that's it.
> For the _i_th element(i > m), the probability it be sampled should eauql to the probability of each element sampled in the list of m elements, which is (m / i). 

2.For the _i_th element(i > m), we will set its probability to be added in the reservoir as (m / i). As for the elements in the reservoir, we will choose one randomly and replace it with the _i_th element.

    haha


## Weighted Sampling
TBD
=======
-------
