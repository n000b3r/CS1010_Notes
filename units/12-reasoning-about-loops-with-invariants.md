# 12: Reasoning About Loops with Invariants

<details>

<summary>What is Loop Invariant?</summary>

* Assertion that's true at the following points:
  * Before the loop
  * After each iteration of loop
  * After the loop
* Helps us to argue the correctness of our code

</details>

<details>

<summary>Proving Validity of Invariant</summary>

* True before entering loop
* True at end of first iteration of loop
* If it is true at end of k-th iteration, then it is true at the end of (k+1) iteration
  * Arguing invariant is correct:
    * Assume that the invariant `sum1 == 2 * i - 1` holds at Line A
    * `i` increases by 1, so the invariant`sum1 == 2 * (i - 1) - 1` holds at Line B.
    * `sum1` increases by 2, so the invariant `sum1 == 2 * i - 3 + 2 == 2 * i - 1` holds at line C.&#x20;
* True when we exit the loop

</details>

<details>

<summary>Equivalence in Invariant</summary>

```
When i%3==0 --> i/3 == (i-1)/3+1
```

</details>
