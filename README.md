# Course-Work
# Mathematical Algorithms and Numerical Methods in Python

This repository contains Python implementations of several mathematical
algorithms and numerical methods. The project demonstrates concepts such
as computing the **Greatest Common Divisor (GCD)**, approximating
**Euler's number (e)** using different mathematical techniques, and
checking whether a number is a **power of another number**.

## Project Overview

This project includes:

-   Implementation of the **Euclidean Algorithm** for GCD
-   Approximation of **Euler's number (e)** using:
    -   Limit definition
    -   Taylor series expansion
-   Error analysis of numerical approximations
-   Checking if a number is a **power of 2**
-   Checking if a number is a **power of another number**

------------------------------------------------------------------------

## 1. Greatest Common Divisor (GCD)

The Euclidean Algorithm efficiently computes the GCD of two integers.

``` python
def gcd(a, b):
    while b != 0:
        remainder = a % b
        a = b
        b = remainder
    return a
```

Example:

    Enter first number: 24
    Enter second number: 36
    The Greatest common divisor is: 12

------------------------------------------------------------------------

## 2. Euler's Number Approximation

Euler's number **e ≈ 2.71828** is approximated using two methods.

### Method 1: Limit Definition

e = (1 + 1/n)\^n

``` python
def euler_limit(n):
    step = 1 / float(n)
    base = 1 + step
    result = 1.0
    for _ in range(n):
        result *= base
    return result
```

### Method 2: Taylor Series Expansion

e = Σ (1/k!)

``` python
def factorial(k):
    if k == 0:
        return 1
    return k * factorial(k - 1)

def euler_sum(n):
    total = 0.0
    for k in range(n):
        total += 1 / factorial(k)
    return total
```

------------------------------------------------------------------------

## 3. Error Analysis

``` python
import math

def print_euler_sum_error(n):
    for i in range(1, n+1):
        print(f"For i={i}, error: {euler_sum(i) - math.exp(1)}")

def print_euler_limit_error(n):
    for i in range(1, n+1):
        print(f"For i={i}, error: {euler_limit(i) - math.exp(1)}")
```

------------------------------------------------------------------------

## 4. Checking if a Number is a Power of 2

``` python
def is_power_of_2(n):
    if n == 0:
        return False
    elif n == 1:
        return True
    else:
        for i in range(1, n):
            if 2**i == n:
                return True
        return False
```

------------------------------------------------------------------------

## 5. Checking if a Number is a Power of Another Number

``` python
def is_power(b, n):
    if n == 0:
        return False
    elif n == 1:
        return True
    else:
        for i in range(1, n):
            if b**i == n:
                return True
        return False
```

------------------------------------------------------------------------

## Requirements

-   Python 3.x
-   Standard Python library (`math`)

No external dependencies are required.

------------------------------------------------------------------------

## How to Run

1.  Clone the repository

```{=html}
<!-- -->
```
    git clone https://github.com/your-username/repository-name.git

2.  Navigate to the project folder

```{=html}
<!-- -->
```
    cd repository-name

3.  Run the notebook using **Jupyter Notebook** or **Google Colab**.

------------------------------------------------------------------------

## Learning Outcomes

This project demonstrates:

-   Implementation of mathematical algorithms
-   Recursive and iterative programming
-   Numerical approximation methods
-   Error analysis in computational mathematics
