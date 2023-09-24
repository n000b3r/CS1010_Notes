# 5: First C Program

<details>

<summary>Function Syntax</summary>

![](<../.gitbook/assets/image (5).png>)



</details>

<details>

<summary>Function Declaration</summary>

* Function must be defined or declared before being used
* Function Declaration:
  * Return type
  * Function name
  * Parameters
  * WITHOUT FUNCTION BODY

```c
int square(int x); // declaring the function square

int main()
{
  int hypotenuse_square;

  hypotenuse_square = square(3) + square(4);
  return 0;
}

int square(int x)  // defining the function square
{
  return x * x;
}
```

</details>

<details>

<summary>Assignment Vs Equality</summary>

* All values must be initialized before use
* `=` is assignment operator
  * First, evaluate RHS of `=`
  * Second, value of RHS assigned to variable on LHS
* `==` is equality operator
  * Checks if LHS is equivalent to RHS

</details>

<details>

<summary>Parameter Vs Argument</summary>



</details>

<details>

<summary>Variable Scope</summary>

* Each declaration is valid only within the scope of its declaration
* Global variable&#x20;
  * Variable that can be accessed and modified from anywhere in the code&#x20;
  * Banned in CS1010 (Bug prone)
* Cannot re-declare the same variable (ie same name) wthin the same scope

```c
int main()
{
  int hypotenuse_square;

  hypotenuse_square = square(3) + square(4);
  int hypotenuse_square; // <-- redeclaration
  return 0;
}
```

</details>

<details>

<summary>Compilation Vs Run-Time Error</summary>

* Compilation Error:
  * Errors during compilation
* Run-Time Error:
  * Erros during the execution of program

</details>

