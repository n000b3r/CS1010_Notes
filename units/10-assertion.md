# 10: Assertion

<details>

<summary>What is Assertion?</summary>

* Logical expression that must always be true for the program to be correct
* ```c
    if (score >= 8) {
      cs1010_println_string("A");
    } else {
      if (score >= 5) {
        // { score >= 5 } THIS IS AN ASSERTION
        cs1010_println_string("B");
      } else {
        // { score < 5 }
        if (score >= 3) {
          // { score < 5 && score >= 3 }
          cs1010_println_string("C");
        } else {
          // { score < 5 && score < 3 }
          cs1010_println_string("D");
        }
      }
    }

  ```

</details>

<details>

<summary>De Morgan's Law</summary>

* `!(e1 && e2)` is the same as `(!e1) || (!e2)`
* `!(e1 || e2)` is the same as `(!e1) && (!e2)`

</details>
