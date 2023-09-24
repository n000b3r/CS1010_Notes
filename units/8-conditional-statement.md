# 8: Conditional Statement

<details>

<summary>If/Else</summary>

```c
if (<logical expression>) {
  "true block": statements to be executed if expression evaluates to true
} else {
  "false block": statements to be executed if expression evaluates to false
}
```

### Nested If/Else

```c
void print_score(double score) 
{
  if (score >= 8) {
    cs1010_println_string("A"); 
  } else {
    // Table 1
    if (score >= 5) {
      cs1010_println_string("B");
    } else {
      // Table 2
      if (score >= 3) {
        cs1010_println_string("C");
      } else {
        cs1010_println_string("D");
      }
    }
  }
}
```

![](<../.gitbook/assets/image (8).png>)

</details>

<details>

<summary>Ternary Operator</summary>

```c
condition ? true expression : false expression;
```

which is equivalent to:

```c
if (x > y) {
  max = x;
} else {
  max = y;
}
```

Example

```c
long factorial(long n)
{
  return n == 0 ? 1 : n * factorial(n - 1);
}
```

</details>

<details>

<summary>Common Pitfalls (IMPT)</summary>

* Comparing Real Numbers
  * Real numbers cannot be represented exactly in computers
  *   ```c
      double expected_value = 0.3;
      double sum = 0.1 + 0.2;
      if (sum == expected_value) { //Condition would not be evaluated as true!!!
       :
      }

      ```


  * What to do instead
  *   ```c
      double expected_value = 0.3;
      double sum = 0.1 + 0.2;
      if (fabs(sum - expected_value) < 0.000001) {
       :
      }
      ```


* Indentation
  * Nesting of blocks not required by C's syntax
  * However, it is good programming practice to do so.
* Curly Braces
  * C standard allows us to skip the curly braces `{` and `}` if block only contains one statement
  * Doing so is considered bad practice and should be avoided.
  *   ```c
      void print_score(double score)
      {
        if (score >= 8)
          cs1010_println_string("A"); //bad practice
        else if (score >= 5)
          cs1010_println_string("B");
        else if (score >= 3)
          cs1010_println_string("C");
        else
          cs1010_println_string("D");
      }

      ```


* Redundant Comparisons
  * A condition is redundant if it is always true or always false.
  *   ```c
      if (x > y) {
        max = x;
      }
      if (x <= y) { //Redundant comparison
        max = y;
      }

      ```



</details>

```
if (x > y) {
  max = x;
}
if (x <= y) {
  max = y;
}

```
