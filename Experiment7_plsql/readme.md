# Experiment 7: PL/SQL – Variables, Control Structures and Loops

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

***Program***
```
DECLARE
   a NUMBER := 80;
   b NUMBER := 45;
BEGIN
   IF a > b THEN
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || a);
   ELSE
      DBMS_OUTPUT.PUT_LINE('Greater number is: ' || b);
   END IF;
END;

```

**Expected Output:**  
<img width="775" height="738" alt="image" src="https://github.com/user-attachments/assets/9fb2b93f-b45c-4bae-b927-be29d92e6cc9" />



---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

***Program***
```
DECLARE
   n NUMBER := 10;
   i NUMBER := 1;
   sum1 NUMBER := 0;
BEGIN
   WHILE i <= n LOOP
      sum1 := sum1 + i;
      i := i + 1;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Sum of first 10 natural numbers is: ' || sum1);
END;
/
```

**Expected Output:**  
<img width="755" height="744" alt="image" src="https://github.com/user-attachments/assets/550c6707-d5bb-42ef-b614-cd10f652d136" />




---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

***Program***

~~~
DECLARE
   n NUMBER := 7;
   a NUMBER := 0;
   b NUMBER := 1;
   c NUMBER;
   i NUMBER := 1;
   fib VARCHAR2(100);
BEGIN
   fib := a || ', ' || b;

   WHILE i <= n - 2 LOOP
      c := a + b;
      fib := fib || ', ' || c;

      a := b;
      b := c;

      i := i + 1;
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || fib);
END;

~~~


**Expected Output:**  
<img width="745" height="297" alt="image" src="https://github.com/user-attachments/assets/2af6e3df-ac11-4950-b9ee-772a3bdff16e" />


---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

***PROGRAM***
~~~
DECLARE
   n NUMBER := 1535;
   rev NUMBER := 0;
   rem NUMBER;
BEGIN
   WHILE n > 0 LOOP
      rem := MOD(n,10);
      rev := rev * 10 + rem;
      n := TRUNC(n/10);
   END LOOP;

   DBMS_OUTPUT.PUT_LINE('Reversed number is: ' || rev);
END;

~~~

**Expected Output:**  
<img width="753" height="302" alt="image" src="https://github.com/user-attachments/assets/609b2437-5de5-4ebf-afc0-20a9884e1405" />


---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

  ***PROGRAM***

```
  DECLARE
   a NUMBER := 10;
   b NUMBER := 9;
   c NUMBER := 15;
BEGIN
   IF a > b AND a > c THEN
      DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || a);

   ELSIF b > a AND b > c THEN
      DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || b);

   ELSE
      DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || c);
   END IF;
END;
```
***Expected Output***  
<img width="768" height="303" alt="image" src="https://github.com/user-attachments/assets/7c6e92d3-ca2e-4a74-b659-f3ce0aecfc63"/>


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
