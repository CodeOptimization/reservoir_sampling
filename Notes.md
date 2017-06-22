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

2.For the _i_ th element(i > m), we will set its probability to be added in the reservoir as (m / i). As for the elements in the reservoir, we will choose one randomly and replace it with the _i_ th element.

>> Proof: (Induction)

 
>>1. The probablity of one element in reservoir will be replaced equals the probablity of the _i_th element will be chosen(m / i) and the element in reservoir itself to be choosen in the reservoir (1 / m). (m / i) * (1 / m) = (1 / i). And the probablity it stays in the reservoir will be 1 - (1 / i) = (1000 / i). 
>>2. For the (_i_ + 1) th element: The probablity it would be chosed: (m / (i + 1)). The random replaced element E chosen from the reservoir is (1 / m), the probablity that E stays will be (1 - (m / (i + 1)) * (1 / m)) = (m / (i + 1)).

Code as below:

## Weighted Sampling

TBD


$$ x^{y^z}=(1+{\rm e}^x)^{-2xy^w} $$


Reference: https://gregable.com/2007/10/reservoir-sampling.html
=======
-------
