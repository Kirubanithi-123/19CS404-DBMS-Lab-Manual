# Experiment 6: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80
## program:
```
DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 45;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSIF num2 > num1 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Both numbers are equal: ' || num1);
    END IF;
END;
/

```
## Output:
![Screenshot 2025-05-14 155518](https://github.com/user-attachments/assets/2cf9e8a0-fdd4-4a64-846d-04eb9113bbcb)

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55
Greater number is: 80
## program:
```
DECLARE
    n NUMBER := 10;     -- You can change this value as needed
    i NUMBER := 1;      -- Counter variable
    sum NUMBER := 0;    -- To store the result
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
## Output:
![image](https://github.com/user-attachments/assets/c04726f3-bd0f-4fde-a324-79419842eb8f)


---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---
## program:
```
DECLARE
    n NUMBER := 7;      -- Number of terms to generate
    a NUMBER := 0;      -- First term
    b NUMBER := 1;      -- Second term
    c NUMBER;           -- Next term
    i NUMBER := 3;      -- Loop counter starts from 3 since first two terms are already printed
BEGIN
    -- Print the first two Fibonacci numbers
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);

    -- Generate remaining Fibonacci numbers
    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
/

```
## Output:
![image](https://github.com/user-attachments/assets/6d6e4377-a59d-4602-a00e-ebbd4cb6f041)

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

---
## program:
```
DECLARE
    n NUMBER := 1535;        -- Original number
    digit NUMBER;
    reversed NUMBER := 0;    -- To store the reversed number
    original NUMBER := n;    -- To preserve the original number for output
BEGIN
    -- Loop to reverse the number
    WHILE n > 0 LOOP
        digit := MOD(n, 10);               -- Get the last digit
        reversed := (reversed * 10) + digit; -- Append digit to reversed number
        n := TRUNC(n / 10);                -- Remove last digit
    END LOOP;

    -- Display the reversed number
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;
/
```
## Output:
![image](https://github.com/user-attachments/assets/a9da8622-5b81-4096-bfb5-ea15adfa114a)

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## program:
```
DECLARE
    n NUMBER := 1535;        -- Original number
    digit NUMBER;
    reversed NUMBER := 0;    -- To store the reversed number
    original NUMBER := n;    -- To preserve the original number for output
BEGIN
    -- Loop to reverse the number
    WHILE n > 0 LOOP
        digit := MOD(n, 10);               -- Get the last digit
        reversed := (reversed * 10) + digit; -- Append digit to reversed number
        n := TRUNC(n / 10);                -- Remove last digit
    END LOOP;

    -- Display the reversed number
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;
/
```
## Output:
![image](https://github.com/user-attachments/assets/3c4a0979-eb6d-478b-999b-5ebee42a81e7)

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
