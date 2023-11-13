# C Programming Foundations

## Introduction

Welcome to the world of C programming! In this guide, we'll cover functions and logical thinking techniques that will set the foundation for your journey into the programming realm.

## Functions: The Building Blocks of C Programming

Imagine you're a chef preparing a scrumptious dish. You wouldn't just toss all the ingredients into a pot and hope for the best. Instead, you'd carefully follow a recipe, breaking down the cooking process into manageable steps. Similarly, C programming utilizes functions to break down complex tasks into reusable and organized units. Think of it as building up a burger, you make each part separately and then combine all of them at the end.

### What's a Function?

A function is a block of code designed to perform a specific task. It's like a mini-program within your main program, allowing you to organize your code and make it easier to manage. It is your sous chef, assisting you in preparing various components of the dish, to make the perfect "Better-than-Gordon-Ramsay 😎" dish.

### Function Structure

Every function has a well-defined structure, much like a well-structured recipe. Let's dissect the anatomy of a function:

1.  **Function Declaration:** This is the function's name tag, introducing it to the program. It tells the program what the function is called and what it does. Just like everybody else you know, functions also identify by these "proper nouns".



```c
void greet(char name[]) {
  //Name of function ⇒ greet
  printf("Good Morning Legend\n");
  // Function's remaining body
}

```

2.  **Return Type:** This indicates the type of data the function produces, like the dessert you're serving after the main course. Return types can be of various datatypes: int, float, double, string or even an entire array or structure!! An example with int is as follows




```c
int addNumbers(int num1, int num2) {
  int sum = num1 + num2; // Value to return must be of the same type
  return sum // Do not forget this very important line!!
}

```

	

3.  **Parameter List:** This is the list of ingredients your function needs to do its job, like the spices you add to enhance the flavor. For calculating average, we need to take an array of numbers and the number of students 



```c
float calculateAverage(int marks[], int numStudents) {
  float sum = 0.0; //FoodForThought ==> Why sum float not int?
  
  for (int i = 0; i < numStudents; i++) { 
	  sum += marks[i]; 
  } 
  
  float average = sum / numStudents; 
  return average; 
}

```

4.  **Function Body:** This is where the action happens, like the cooking instructions that transform raw ingredients into a culinary masterpiece.



```c
void swapValues(int *a, int *b) {
  int temp = *a;
  *a = *b;
  *b = temp;
}

```

### Function Calling: Putting the Sous Chef to Work

To put your function to work, you need to call it, just like you'd call your sous chef to assist with your Mastershef Dish



```c
int num1 = 10, num2 = 20;
int sum = addNumbers(num1, num2);
printf("The sum of %d and %d is %d\n", num1, num2, sum);

```

### Expanding Your Culinary Skills

1.  **Reversing a String:** Write a function that takes a string as input and returns the reversed string.



```c
char *reverseString(char str[]) {
  int len = strlen(str);
  char revStr[len + 1];

  for (int i = 0; i < len; i++) {
    revStr[i] = str[len - 1 - i];
  }

  revStr[len] = '\0';
  return revStr;
}

```

2.  **Finding the Largest Element in an Array:** Write a function that takes an integer array and its size as input and returns the index of the largest element.



```c
int findLargest(int arr[], int size) {
  int largestIndex = 0;
  int max = arr[0];

  for (int i = 1; i < size; i++) {
    if (arr[i] > max) {
      max = arr[i];
      largestIndex = i;
    }
  }

  return largestIndex;
}

```





![enter image description here](https://preview.redd.it/xd4nhmjovxg61.png?auto=webp&s=d647fa7fa5bf1b5eb82b9cdd60736d6e19ca10ba)

## Logical Thinking in C

### What is logical thinking?
Logical thinking is essential for writing good C code. You need to be able to think about how your code will be executed and how the different parts of your code will interact with each other.

### How to think logically in C
To use logical thinking in C programming, you need to be able to think about the steps involved in solving a problem and express those steps in C code. By using this 5 step approach you will not only develop the ability to independently write and edit code, but will also become logical thinkers.

**1.  Analyze the Problem
2.  Formulate a Plan
3.  Develop Code to Solve the Problem
4.  Evaluate the Solution and Revise the Code
5.  Justify Decisions**

Here are some tips for logical thinking in C:

* **Use functions to organize your code.** This will make your code more readable and easier to maintain.
* **Use comments to explain what your code is doing.** This will help you and other people understand your code.
* **Use variables to store data.** This will make your code more efficient and reusable.
* **Use conditional statements to control the flow of your code.** This will allow you to execute different parts of your code depending on different conditions.
* **Use loops to repeat blocks of code.** This will save you from having to write the same code multiple times.

### Questions



![haha](https://pbs.twimg.com/media/FGg9HVZWUAIdn5L?format=jpg&name=large)


### Fibonacci Series in C
```c
#include <stdio.h>
int main()
{


int number_of_terms, iteration;
int term1 = 0, term2 = 1, next_term;

printf("Enter the number of terms till you want to display the numbers in the Fibonacci series: ");
scanf("%d", &number_of_terms);

printf("The Fibonacci series up till %d terms is: ",number_of_terms);

for (iteration = 1; iteration <= number_of_terms; iteration++)
{
printf("%d ", term1);
next_term = term1 + term2; // Next term is the sum of previous terms
term1 = term2;
term2 = next_term;
}
return 0;
}
```
### ***Elucidation***

**Declaration:** We declare the variable ‘number_of_terms’ to find the terms till which the series is to be displayed, the variable ‘iteration’ to traverse the for loop. Then, we initialize the first and second term as 0 and 1 respectively are their values are fixed.

**Input:** We take the input of the number of terms to be entered by the user till which he wishes to display the Fibonacci series.

**Logic:** We initialize the variable ‘iteration’ to 1. We make the loop run till the number of terms in the series and print the first term and second term.

-   Now, our task is to find the sum of both the terms, that is, 0 and 1 to obtain the next term.
-   When the loop runs for the second time, we store the result obtained, that is, 2, to the second term and the original second term to the original first term.
-   The same process is repeated until the variable ‘iteration’ becomes equal to the number of terms.

### Palindrome Series in C
```c
#include <stdio.h>
int main()
{

int number, number_reverse = 0, remainder, original_number;

printf("Enter an integer: ");
scanf("%d", &number);

original_number = number; // Storing the value of the number into a variable original_number

/* Reversing the number */
while( number!=0 )
{
remainder = number % 10;
number_reverse = number_reverse * 10 + remainder;
number /= 10;
}
// To check if the original number and the reversed number are equal or not
if (original_number == number_reverse)
printf("%d is a palindrome.\n", original_number);
else
printf("%d is not a palindrome.\n", original_number);
return 0;
}
```

### ***Elucidation***

**Declaration:** We declare the variable ‘number’ to store the value entered by the user to check if it is a palindrome or not, the variable ‘remainder’ to find the remainder when the integral division of that number is performed with 10, and the variable ‘original_number’ to store the value of the number entered by the user temporarily. We initialize the variable ‘number_reverse to 0 for loop traversal.

**Input:** We take the input of the number to check if it is a palindrome or not from the user in the variable ‘number’.

**Logic:** The while loop runs till the number entered by the user becomes 0

-   A set of conditions is given to extract the reversed number from the number entered by the user.
-   If the value of the variable ‘number_reverse’ matches to that of the original number, then the given number enter by the user is a palindrome.

### Explanation through Dry Run:

Consider the value of the number = 181

The while loop will run for 3 times, given as:

**1. First iteration, number = 181**

remainder = 181 % 10 = 1  
number_reverse = ( 0 * 10 ) + 1 = 1  
number = 181 / 10 = 18

**2. Second iteration, number = 18**

remainder = 18 % 10 = 8  
number_reverse = ( 1 * 10 ) + 8 = 18  
number = 18 / 10 = 1

**3. Third iteration, number = 1**

remainder = 1 % 10 = 1  
number_reverse = ( 18 * 10 ) + 1 = 181  
number = 1 / 10 = 0

The loop will no longer run as the base condition no longer continues to be satisfied as the number reached its minimum value = 0.

***Congratulations on completing this C programming foundations! Remember, practice is key to mastering programming. Explore more, solve problems, and enjoy the journey of coding! Happy coding! 😄***  

![enter image description here](https://starecat.com/content/wp-content/uploads/my-code-doesnt-work-i-have-no-idea-why-my-code-works.jpg)

