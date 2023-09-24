# 11: Loops

<details>

<summary>For loops</summary>

```c
for (<initialize>; <condition>; <update>) {
    <body>
}
```

* Initialize:
  * Set up the loop
* Condition:
  * Indicates when the loop should stop repeating
* Update
  * Statement that is executed after every loop
* Body
  * What is the action we want to do repeatedly

![](<../.gitbook/assets/image (7).png>)

</details>

<details>

<summary>While loop</summary>

```c
while (<condition>) {
    <body>
}
```

* Can interleave `<update>` and `<body>` or execute `<update>` before `<body>` , depending on the algorithm

</details>

<details>

<summary>do-while loop</summary>

```c
<initialize>
do {
    <body>
    <update>
} while (<condition>);
```

* Similar to `while` except that body of loop is guaranteed to be executed at least once

</details>
