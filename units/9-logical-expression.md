# 9: Logical Expression

<details>

<summary>Boolean in C</summary>

* `bool` data type can hold 2 values: `true` or `false`
* Need to include `stdbool.h` in your program
* Name `bool` variable with prefix `is_`, `has_`, or `can_`
* DO NOT REPRESENT TRUE/FALSE WITH NUMBERIC VALUES (1 OR 0)

</details>

<details>

<summary>Logical Operators</summary>

* `==`, `<`, `<=`, `<`, `>=`, `!=`, `&&`, `||` and `!`

<!---->

* `(birth_year >= 1995) && (birth_year <= 2005)` is valid c syntax unlike `1995 <= birth_year <= 200`

The table below summarizes the logical operations `&&`, `||` and `!`:

![](<../.gitbook/assets/image (6).png>)

</details>

<details>

<summary>Short-Circuiting (IMPT)</summary>

* If the program already knows, for sure, that a logical expression is true or false, there is no need to continue the evaluation
* Always put logical expression that involves more work in the second half of the expression
* For instance, checking prime involves more work than checking if number < 100000
  * ```c
    if (number < 100000 && is_prime(number)) { //Higher Efficiency
        :
    }
    ------------------------------------------
    if (number < 100000 && is_prime(number)) { //Lower Efficiency
        :
    }
    ```

</details>
