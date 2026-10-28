# 📝 Worksheet: 04 - More Functions & Loops

Do this worksheet **on paper, without a computer**. Each section ends with an **🤖 Explain It** prompt: write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Defaults and Keywords

```python
def price(amount, tax=0.0825, discount=0):
    return round(amount * (1 + tax) - discount, 2)
```

What does each call return?

1. `price(100)` → 108.25
2. `price(100, discount=10)` → 98.25
3. `price(100, 0)` → 100.0
4. `price(discount=5, amount=20)` → 16.65

> 🤖 **Explain It:** Why are keyword arguments easier to read than positional ones in a call like `price(100, 0, 10)`?
Keyword arguments are easier to read because they show what each value means, so we don’t have to remember the order.


---

## 🧠 Section 2: Scope

What prints? Explain why.

```python
count = 0

def add_one(count):
    count = count + 1
    return count

result = add_one(count)
print(count, result)
```

`Answer:` 0 1
The function changes its own local count, not the global one. So the original count stays 0, and result becomes 1.

> 🤖 **Explain It:** Describe the "room with two doors" model of a function in your own words.
The function has its own room with a separate count. Changing it doesn’t change the original count outside the function.

---

## 🧠 Section 3: Trace a While Loop

```python
balance = 100
years = 0
while balance < 150:
    balance = balance + 20
    years += 1
```

| pass | `balance` at the start | `balance < 150`? | `balance` after | `years` after |
|------|------------------------|------------------|-----------------|---------------|
| 1 | 100 | True | 120 | 1 |
| 2 | 120 | True | 140 | 2 |
| 3 | 140 | True | 160 | 3 |
| 4 | 160 | False| -   | - |

Final `years`: 3  Final `balance`: 160

What single change would make this an **infinite** loop?  
`Answer:` Removing balance = balance + 20,  balance will never change and it will become infinite loop.

---

## 🧠 Section 4: `for` or `while`?

| Task | `for` or `while`? | Why? |
|------|-------------------|------|
| Print each line of a file | for | Goes through each line.|
| Keep asking for a password until it's correct | while | Repeats until the password is correct.|
| Find the average of a list of prices | for | Goes through each price. |
| Double a number until it's over one million | while | Repeats until the condition is met. |

---

## 🧠 Section 5: Files

Given the file `pets.txt`:

```text
name,species
Rex,dog

# rescued in May
Tom,cat
```

1. How many times does `for line in f:` run? 5 time
2. Which lines should your code skip, and how would you detect each one?  
   `Answer:` ____________________________
3. Write the list of dictionaries a `read_pets` function should return:  
   `Answer:`
   [
    {"name": "Rex", "species": "dog"},
    {"name": "Tom", "species": "cat"}
]
> 🤖 **Explain It:** When is `try` / `except` a good idea, and when does it just hide bugs?
We can use try / except for expected errors, like a file not existing. It hides bugs when we want to catch every error without fixing the real problem.