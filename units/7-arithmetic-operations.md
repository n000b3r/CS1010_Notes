# 7: Arithmetic Operations

<details>

<summary>Types of Operators</summary>

* `+`: Addition
* `-`: Subtraction
* `%`: Remainder
  * `x % n` is equivalent to `x - ((x / n) * n)`

<!---->

* &#x20;`+`, `-`, `*`, and `/` work on both integer types (`char`, `short`, `int`, `long`, `long long`) and real numbers (`float`, `double`).&#x20;
* &#x20;`%` works only on integer types.

</details>

<details>

<summary>Order  of Operations</summary>

* `*`, `/` and `%` takes precedence over `+` and `-`
* Operators are evaluated from left to right

</details>

<details>

<summary>Compound Operators</summary>

* `op=`,where `op` can be `+`, `-`, `*`, `/`, `%`, or other binary operators
* `a op= b;` is the same as `a = a op b;`
* Eg: `a += b;` is same as `a = a + b;`

</details>

<details>

<summary>Common Pitfalls (IMPT)</summary>

* Overflow
  * When there are not enough bits to store a value --> values stored is wrapped around
  *   Eg:&#x20;

      ```
      uint8_t c = 255;
      c += 1; //c becomes 0, unint8_t can store values 0 - 255
      ```


* Integer Division
  * `3/2` is 1 as C truncates the floating number and only store the integer part of the value
  * Have to type cast either 1 or both of the integers to `double`
  *   <pre class="language-c"><code class="lang-c"><strong>double half = 3/2 // Integer division
      </strong><strong>double half = 3/2.0; //No integer division
      </strong>double half = (double)3/(double)2; //No integer division
      </code></pre>


* `%` Operator
  * Is not the modulo operator since it can return negative number too
  * Given by formula `x % n` is equivalent to `x - ((x / n) * n)`
  * Remainder operator instead of modulo operator!!
* Increment/Decrement Operator
  * `++` or `--`
  * Banned due to its ability to return a value
  * Eg: `j = i++` --> increments i and assigns the pre-incremented value of i to j
  * Eg: `j = ++i` --> increments i and assign the post-incremented value of i to j
  * eg: `i = i++` --> undefined behavior

</details>

