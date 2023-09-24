---
description: Key concepts, insights from past yr papers, tutorials
---

# Cheatsheet

<details>

<summary>Qns with Multiple Options</summary>

* When the qn starts with " Which of the following..."

</details>

<details>

<summary>Modulo Formula</summary>

$$x \space \% \space n = x - ((x / n) * n)$$

</details>

<details>

<summary>Recursive Functions</summary>

```c
long mystery(long x) {
  if (x == 1) {
    return 1;
  }
  return 1 + mystery(x/2);
}
```

What's the return value of `mystery(10)`?

* `mystery(10)`&#x20;
* \= `1 + mystery(5)`&#x20;
* \= `1 + (1 + mystery(2))`
* &#x20;\= `1 + 1 + (1 + mystery(1))`&#x20;
* \= 4

### Qn: Returns true if m is subnumber of n

* Last digit matches and m/10 is subnumber of n/10. (eg: 123 subnumber of 9123)
* Last digit doesn't match but m is subnumber of n/10. (eg: 123 subnumber of 1237)
* Base case:
  * 0 is subnumber of all integers
  * If m is not 0, then if n == 0, m is not subnumber of n.

<pre class="language-c"><code class="lang-c">bool is_sub_number(long m, long n) {
if (m == 0) {
    return true;
}
if (n == 0) {
<strong>    return false;
</strong>}
return ((m % 10 == n % 10) &#x26;&#x26; is_sub_number(m / 10, n / 10)) || is_sub_number(m, n / 10);
}
</code></pre>

</details>

<details>

<summary>Loops</summary>

![](<.gitbook/assets/image (10).png>)

* Corresponding C code:

```c
if (a) {
  b();
}
if (c) {
  d();
} else if (e) {
  f();
}
g();
```

Which loops correctly compute the sum of all integers b/w i and j inclusive?

```c
long foo(long i, long j) {
  long sum = i;
    long x = i;
    while (x < j) { //Ends at j-1
      x += 1; //INCREMENTS X BEFORE ADDING
        sum += x;

    }
  return sum;
}

long bar(long i, long j) {
  long sum = 0;
    long x = i;
    do {
      sum += x;
        x += 1;
    } while (x <= j);
  return sum;
}

long qux(long i, long j) {
  long sum = 0;
    for (long x = j; x >= i; x = 1) {
      sum += x;
    }
  return sum;
}
```

All loops will compute the sum of all integers b/w i and j inclusive.

</details>

<details>

<summary>Integer Division</summary>

```c
double x = (1/2) * (2/3) * (3/4);
```

What's the value of x?

* 0: All the division results in 0.

How to solve it?

* Typecast either or both values to double so proper division occurs.

</details>

<details>

<summary>Imprecision due to Floating pt numbers</summary>

Qn: Explain why the loop may not terminate

```c
//change is of double type
while (change > 0) {
    if (change > 1) {
    one_dollar += 1;
    change = 1.0;
    } else if (change > 0.5) {
        fifty_cent += 1;
    change = 0.5;
    } else if (change > 0.2) {
        twenty_cent += 1;
        change = 0.2;
    } else if (change > 0.1) {
        ten_cent += 1;
        change = 0.1;
    }
}
```

* The > operators should instead be ≥ operators.&#x20;
* Imprecisions using floating-point values might mean that certain conditions may be evaluated incorrectly, and more importantly, that one may never reach change == 0

</details>

<details>

<summary>De Morgan's Law</summary>

Qn: Married if and only if either (i) he or she is at least 21 years old, or (ii) he or she is at least 16 years old and have the consent of the parents.&#x20;

Write function `cannot_get_married`

<pre class="language-c"><code class="lang-c"><strong>//Allow Marriage
</strong>(age >= 21) || (age >= 16 &#x26;&#x26; consent)

//Now apply De Morgan’s Law:
(age &#x3C; 21) &#x26;&#x26; !(age >= 16 &#x26;&#x26; consent) (age &#x3C; 21) &#x26;&#x26; (!(age >= 16) || !consent)
(age &#x3C; 21) &#x26;&#x26; (age &#x3C; 16 || !consent)
</code></pre>

</details>

<details>

<summary>Short-Circuiting</summary>

* Do cheaper operation first!

Qn: Write a recursive function has8 in C that, given an positive integer number, returns true if the digit 8 appears somewhere in the number, returns false otherwise. Your code should consist of a single return statement and appropriate use short-circuiting to avoid unnecessary checks.

Ans:

* `return (x % 10 == 8) || (x > 10 && has8(x/10));`
  * Since recursive calls use more resources, we should call `x % 10 == 8` condition first to allow short-circuiting.

</details>

<details>

<summary>Loop Invariant</summary>

* Assertion that's true at the following points:
  * Before the loop
  * After each iteration of loop
  * After the loop
* Always explain effects on variable in words
  * Eg: i += 1 --> i is incremented by 1 but the rest of the variables remain the same so we decrement i by 1, thus $$ya^{i - 1} == x^n$$.&#x20;
  * Eg: $$i = (i -1) /2$$. i is decremented and halved, but the rest of the variables remain the same. So we multiply i by 2 and increment it by 1, thus $$ya^{2i+1} == x^n$$
* Since i % 3 == 0 , (i/3) is the same as (i-1)/3 + 1&#x20;

Qn: Determine the loop invariant for:

```c
long foo(long n, long k) {
  long x = n;
  long y = 0;
  while (x >= k) {
     // Line C
     y += 1;
     x -= k;
    // Line D
  }
  // Line E
```

Ans:  `x == n - y*k`

Qn: Proof why loop invariant is true at Line D assuming Line C is true

Ans:&#x20;

* At line C, assuming `x == n - y*k`
* After `y+=1`, we have `x == n - (y+1)*k`
* After `x-=k`, we have `x-k == n - (y+1)*k`
* Simplifying, we get  `x == n - y*k`

### Qn: Specify loop invariant that relates res and i

<pre class="language-c"><code class="lang-c">long f(long n) {
<strong>    long i = 1;
</strong>    long res = 0;
    while (i &#x3C;= n) {
        if (i % 3 == 0) {
            res += 1;
        }
        if (i % 7 == 0) {
            res += 1;
        }
    i += 1;
    // Line A
    }
    // Line B
    return res;
}
</code></pre>

* Loop invariant is `res == (i-1)/3 + (i-1)/7`

### Qn: Argue why it holds

* Since the loop increments res every time i is divisible by 3 or i is divisible by 7, and i increments by 1 every time, starting from i . Just before i += 1 , we can assert that res == i/3 + i/7 .&#x20;
* At Line A, since i becomes bigger, the assertion res == (i-1)/3 + (i-1)/7 now holds. We can check if this assertion holds before the loop – yes it does!
* Now, assume it holds at the beginning of the loop. After the first if block, res == (i-1)/3 + (i-1)/7 might no longer holds. This happens if i % 3 == 0 . If this happens, we have the property that res == (i-1)/3 + (i-1)/7 + 1 after Line 7.&#x20;
* But, since i % 3 == 0 , i / 3 is the same as (i-1)/3 + 1 ! So, the assertion that holds after the first if block is res == i/3 + (i-1)/7 .&#x20;
* Similarly, after the second if block, we can update the assertion to res == i/3 + i/7 . At Line A, since i becomes bigger, the assertion res == (i-1)/3 + (i-1)/7 now holds again. We are back to the same assertion, showing that this is indeed an invariant for the loop.&#x20;

### Qn: Give an assertion relating n and i on Line B.&#x20;

* After we exit the loop, we can be sure that i == n + 1 .&#x20;

### Qn: What is the output of the function in terms of n ? Explain your answer based on the loop invariant and the assertion you have given above

* Combining this assertion with res = (i-1)/3 + (i-1)/7 , we can conclude that at Line B, res == n/3 + n/7 .

</details>

<details>

<summary>is_prime Algorithm</summary>

<pre class="language-c"><code class="lang-c"><strong>//Correct Algo (given n >= 2)
</strong><strong>bool is_prime(long n) {
</strong>    for (long i = 2; i &#x3C;= sqrt(n); i += 1) {
        if ((n % i) == 0) {
<strong>            return false;
</strong>        }
    }
    return true;
}

//Wrong as algo does not check for the case where i is sqrt(n).
//Counter-example: Number that is a square of a prime (eg: 4, 9, 25, ...) will be incorrectly determined as prime
bool is_prime(long n) {
    for (long i = 2; i &#x3C; sqrt(n); i += 1) {
        if ((n % i) == 0) {
            return false;
        }
    }
    return true;
}

//Wrong as function would return 2 as a non-prime.
bool is_prime(long n) {
    for (long i = 2; i &#x3C;= ceil(sqrt(n)); i += 1) {
        if ((n % i) == 0) {
            return false;
        }
    }
<strong>    return true;
</strong>}

</code></pre>

</details>
