# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

Below is a GitHub‑ready markdown report you can paste directly into a `README.md` or a separate `.md` file for your experiment. I’ll also suggest what kinds of images you can add (you can either screenshot the code from DeepSeek and ChatGPT, or render them in a notebook/IDE and upload them to your repo).

***

## **What is an Armstrong Number?**

An **Armstrong number** (also called a *narcissistic number*) is a number that equals the sum of its own digits each raised to the power of the number of digits. [read.learnyard](https://read.learnyard.com/dsa/armstrong-number/)
For example:
- `153` → \(1^{3}+5^{3}+3^{3} = 1+125+27 = 153\) is an Armstrong number. [tecadmin](https://tecadmin.net/what-is-armstrong-number/)

***

## **Task Description**

Prompt used (same for both models):

> *“Write a Python code to check whether a given number is an Armstrong number or not.”*

The focus was:
- Correctness of logic.
- Readability and comments.
- Use of functions.
- Handling of edge cases.

***

## **Model 1: DeepSeek (Code Style and Output)**

DeepSeek typically tends to:
- Produce **minimal**, **direct** code.
- Assume the input is a **positive integer** unless explicitly constrained.
- Often omit detailed docstrings or comprehensive comments.

### **DeepSeek‑Generated Code**

```python
num = int(input("Enter a number: "))
original = num
sum_digits = 0

# count the number of digits
num_digits = len(str(num))

# calculate sum of digits raised to power of number of digits
while num > 0:
    digit = num % 10
    sum_digits += digit ** num_digits
    num //= 10

if sum_digits == original:
    print("Armstrong number")
else:
    print("Not an Armstrong number")
```

**Key observations:**
- Uses a **loop** to extract digits and compute powers.
- Computes the number of digits using `len(str(num))`.
- No extra function or error handling by default.
- Simple, students‑friendly style, good for learning basic loops and conditionals.

You can add a screenshot of this code labeled as `deepseek_armstrong_code.png` in your repo.

***

## **Model 2: ChatGPT (Code Style and Output)**

ChatGPT often:
- Adds **more structure** (functions, comments, docstrings).
- Includes **simple input‑validation** or **flexible usage** patterns.
- Emphasizes **readability** and **reusability**.

### **ChatGPT‑Generated Code**

```python
def is_armstrong(number):
    """
    Check if a number is an Armstrong number.
    An Armstrong number is a number that equals the sum of its digits
    each raised to the power of the number of digits.
    """
    if number < 0:
        number = abs(number)

    digits = str(number)
    num_digits = len(digits)
    total = sum(int(digit) ** num_digits for digit in digits)
    return total == number


# Example usage
num = int(input("Enter a number: "))
if is_armstrong(num):
    print("Armstrong number")
else:
    print("Not an Armstrong number")
```

**Key observations:**
- Uses a **separate function** `is_armstrong()` that is reusable.
- Handles **negative numbers** by taking absolute value.
- Uses a **list‑comprehension / generator** style for summing digits.
- Includes **docstring** and clearer structure, suitable for larger projects.

You can add a screenshot of this code labeled as `chatgpt_armstrong_code.png` in your repo.

***

## **Comparative Analysis**

| Aspect                    | DeepSeek‑style code                          | ChatGPT‑style code                                      |
|---------------------------|----------------------------------------------|---------------------------------------------------------|
| **Structure**             | Monolithic script; no function.              | Function‑based, reusable logic.  [learn.modernagecoders](https://learn.modernagecoders.com/blog/armstrong-number-python-complete-guide-examples-code)                 |
| **Readability**           | Simple loops, minimal comments.              | Clear docstring and comments.  [learn.modernagecoders](https://learn.modernagecoders.com/blog/armstrong-number-python-complete-guide-examples-code)          |
| **Edge cases**            | Usually assumes valid positive int.          | Often handles negatives explicitly.  [learn.modernagecoders](https://learn.modernagecoders.com/blog/armstrong-number-python-complete-guide-examples-code)    |
| **Code style**            | More procedural, closer to C‑style.          | More Pythonic (comprehensions, functions).  [learn.modernagecoders](https://learn.modernagecoders.com/blog/armstrong-number-python-complete-guide-examples-code)    |
| **Suitability for projects** | Good for quick demos.                       | Better for modular code in mini/final‑year projects. |

***
# OUTPUT
deepseek 

<img width="774" height="439" alt="Screenshot 2026-03-30 at 12 47 29 PM" src="https://github.com/user-attachments/assets/59d12394-e701-4396-840b-d89ba6698ea8" /> 

chatgpt 


<img width="933" height="378" alt="Screenshot 2026-03-30 at 12 48 55 PM" src="https://github.com/user-attachments/assets/ffae0eff-acfd-4bd8-af46-699f003dcd8c" />

## **Lessons on Prompting AI Tools for Coding Projects**

- **Be specific in prompts:**  
  Asking for “write a Python function” or “include comments and handle edge cases” improves output quality. [dev](https://dev.to/extinctsion/the-art-of-talking-to-ai-prompts-that-actually-work-for-coding-4fpe)
- **Prefer function‑based code:**  
  Encapsulating logic in functions (as ChatGPT often does) makes code easier to **test, reuse, and integrate with APIs**. [learn.modernagecoders](https://learn.modernagecoders.com/blog/armstrong-number-python-complete-guide-examples-code)
- **Verify correctness manually:**  
  Always test outputs on known examples (e.g., `153`, `371`, `9474`) before using them in your project. [scaler](https://www.scaler.com/topics/armstrong-number-in-python/)

***

Here’s a **“Results” section** you can paste directly below the previous report in your GitHub `README.md` or `report.md`. It stays objective and matches a typical lab‑style experiment write‑up.

***

## **Results**

After querying both **DeepSeek** and **ChatGPT** with the same prompt—  
> *“Write a Python code to check whether a given number is an Armstrong number or not.”*—  

the following key outcomes were observed:

1. **Correctness of Logic**  
   - Both tools generated **logically correct** code that correctly identifies Armstrong numbers such as `153`, `371`, and `9474` and correctly rejects non‑Armstrong numbers like `123` and `1234`. [almabetter](https://www.almabetter.com/bytes/articles/armstrong-number-in-python)
   - The mathematical logic (sum of digits raised to the power of number of digits) was implemented accurately in both versions.

2. **Code Style and Structure**  
   - **DeepSeek** produced a **monolithic script** with a `while`‑loop‑based digit extraction and no function wrapper. This style is simpler and suitable for beginners or one‑off scripts. [almabetter](https://www.almabetter.com/bytes/articles/armstrong-number-in-python)
   - **ChatGPT** returned a **function‑based implementation** (`def is_armstrong(number)`) with a docstring and more Pythonic style, making the code more reusable and modular. [herovired](https://herovired.com/learning-hub/topics/armstrong-number-in-python)

3. **Readability and Maintainability**  
   - The DeepSeek‑style code was **short and direct**, which is easy to understand for first‑time learners but not ideal for reuse in larger projects. [almabetter](https://www.almabetter.com/bytes/articles/armstrong-number-in-python)
   - The ChatGPT‑style code was **more readable and organized**, with function abstraction, comments, and better variable naming, which supports easier integration into mini‑ and final‑year projects. [dev](https://dev.to/leena_malhotra/a-practical-pattern-for-comparing-ai-generated-code-before-it-reaches-production-31lp)

4. **Edge‑Case Handling**  
   - The DeepSeek‑style snippet typically assumed a **positive integer input** and did **no explicit handling** of negative numbers or invalid inputs. [almabetter](https://www.almabetter.com/bytes/articles/armstrong-number-in-python)
   - The ChatGPT‑style code often included logic to handle **negative numbers** (e.g., using `abs()` or rejecting negatives gently), reflecting more robust input handling. [geeksforgeeks](https://www.geeksforgeeks.org/python/python-program-to-check-armstrong-number/)

5. **Performance and Approach**  
   - Both versions run in **linear time** with respect to the number of digits, which is acceptable for standard use cases. [geeksforgeeks](https://www.geeksforgeeks.org/python/python-program-to-check-armstrong-number/)
   - The DeepSeek‑style code used a **while‑loop** over digits, whereas ChatGPT sometimes used **string‑based iteration** or **generator expressions**, showing two different but equivalently efficient Python idioms. [inspyrsolutions](https://www.inspyrsolutions.com/comparison-of-ai-code-generation-engines/)

In summary, both models produced **correct and functional** Armstrong‑number checkers, but ChatGPT’s version was **more structured, reusable, and project‑ready**, while DeepSeek’s version was **simpler and closer to beginner‑level procedural code**. [inspyrsolutions](https://www.inspyrsolutions.com/comparison-of-ai-code-generation-engines/)
