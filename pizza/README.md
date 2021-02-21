# Even More Pizza

## Steps:

1. Split `M` among teams.
2. Order these on the basis of number of large teams.
2. For each combination, 
    1. find the optimal distribution of pizzas.
    2. Calculate score
    3. if `score < max score` break (with some hysteresis)
3. return order details for `max score`.

## Ordered teams selection

Total = M

* Start with `min(M/4, T<sub>4</sub>)` 4-member teams
and so on for 3 and 2.
* Start reducing 4 or 3 member teams and increasing 3 or 2 member teams.

## Optimal pizza distribution

Given an array [n4, n3, n2] rep number of 4, 3 and 2 member teams calculate the best pizza distribution

0. for the largest team yet to be delivered to
1. make a set of all ing I<sub>i</sub>
2. take `i1` and find pizza having that ing and max other ing of that pizza in set-> p<sub>j</sub>
3. remove other ing of p<sub>j</sub> from set of all ing
4. if set is empty then break, else goto step 2.

0/1 knapsack problem maximixing value = number of uniq ing vs weights (e.g., each pizza has wt of 1)
