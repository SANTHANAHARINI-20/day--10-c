# day--10-c

1.Write a C program to calculate the electricity bill based on the number of units consumed using conditional statements and the given tariff slabs.
Code:
#include <stdio.h>
int main()
{
    int units;
    float bill = 0;
    printf("Enter units: ");
    scanf("%d", &units);
    if (units < 0)
        printf("Invalid units");
    else
    {
        if (units <= 100)
            bill = units * 1.5;
        else if (units <= 200)
            bill = 100 * 1.5 + (units - 100) * 2.5;
        else if (units <= 300)
            bill = 100 * 1.5 + 100 * 2.5 + (units - 200) * 4;
        else
            bill = 100 * 1.5 + 100 * 2.5 + 100 * 4 + (units - 300) * 6;

        printf("Electricity Bill = Rs. %.2f", bill);
    }
    return 0;
}

Output:
Enter units: 250
Electricity Bill = Rs. 600.00

2: Write a C program to display all Armstrong numbers between 1 and a given limit using loops and conditional statements.
Code:
#include <stdio.h>

int main()
{
    int limit, num, temp, digit, count, sum, power;
    printf("Enter limit: ");
    scanf("%d", &limit);
    printf("Armstrong Numbers: ");
    for (num = 1; num <= limit; num++)
    {
        temp = num;
        count = 0;
        while (temp > 0)
        {
            count++;
            temp = temp / 10;
        }
        temp = num;
        sum = 0;
        while (temp > 0)
        {
            digit = temp % 10;
            power = 1;
            for (int i = 1; i <= count; i++)
                power = power * digit;
            sum = sum + power;
            temp = temp / 10;
        }
        if (sum == num)
            printf("%d ", num);
    }
    return 0;
}

Output:
Enter limit: 500
Armstrong Numbers: 1 2 3 4 5 6 7 8 9 153 370 371 407

3: Write a menu-driven C program using functions to perform addition, subtraction, multiplication, division, and modulus operations based on the user's choice.

#include <stdio.h>
int add(int a, int b)
{
    return a + b;
}
int sub(int a, int b)
{
    return a - b;
}
int mul(int a, int b)
{
    return a * b;
}
float divide(int a, int b)
{
    return (float)a / b;
}
int mod(int a, int b)
{
    return a % b;
}
int main()
{
    int a, b, choice;
    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");
    printf("5. Modulus\n");
    printf("Enter choice: ");
    scanf("%d", &choice);
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    switch (choice)
    {
        case 1:
            printf("Addition = %d", add(a, b));
            break;
        case 2:
            printf("Subtraction = %d", sub(a, b));
            break;
        case 3:
            printf("Multiplication = %d", mul(a, b));
            break;
        case 4:
            if (b != 0)
                printf("Division = %.2f", divide(a, b));
            else
                printf("Division by zero not allowed");
            break;
        case 5:
            if (b != 0)
                printf("Modulus = %d", mod(a, b));
            else
                printf("Modulus by zero not allowed");
            break;
        default:
            printf("Invalid Choice");
    }
    return 0;
}

Output:
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Modulus

Enter choice: 1
Enter two numbers: 20 10
Addition = 30
