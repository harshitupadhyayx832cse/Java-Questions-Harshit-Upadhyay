# Java-Questions-Harshit-Upadhyay
1. Smart Billing System (Operators + if-else)

Write a Java program that:

* Takes item price and quantity from the user
* Calculates total bill
* Applies:

  * 5% discount if bill ≥ 2000
  * 10% discount if bill ≥ 5000
* Adds 18% GST on the discounted amount
* Displays final payable amount

Focus: arithmetic operators, relational operators, nested if-else

import java.util.Scanner;

public class SmartBillingSystem {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        
        System.out.print("Enter item price: ");
        double price = sc.nextDouble();

        System.out.print("Enter quantity: ");
        int quantity = sc.nextInt();

        
        double totalBill = price * quantity;
        double discount = 0;

        
        if (totalBill >= 2000) {

            if (totalBill >= 5000) {
                discount = totalBill * 0.10;   
            } else {
                discount = totalBill * 0.05;   
            }

        } else {
            discount = 0;   
        }

        double discountedAmount = totalBill - discount;

     
        double gst = discountedAmount * 0.18;
        double finalAmount = discountedAmount + gst;

       
        System.out.println("\n----- BILL DETAILS -----");
        System.out.println("Total Bill: " + totalBill);
        System.out.println("Discount: " + discount);
        System.out.println("Amount after Discount: " + discountedAmount);
        System.out.println("GST (18%): " + gst);
        System.out.println("Final Payable Amount: " + finalAmount);

        sc.close();
    }
}

2. Employee Salary Calculator (Variables + if-else)

Write a Java program to calculate net salary:

* Input: basic salary
* If basic ≥ 30000:

  * HRA = 20%
  * DA = 15%
* Else:

  * HRA = 10%
  * DA = 8%
* Deduct PF = 12% of basic
* Print net salary

Focus: variables, percentage calculation, conditionals

import java.util.Scanner;

public class EmployeeSalaryCalculator {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Basic Salary: ");
        double basic = sc.nextDouble();

        double hra, da, pf, netSalary;

        
        if (basic >= 30000) {
            hra = basic * 0.20;   
            da = basic * 0.15;    
        } else {
            hra = basic * 0.10;   
            da = basic * 0.08;    
        }

      
        pf = basic * 0.12;

        
        netSalary = basic + hra + da - pf;

       
        System.out.println("\n----- SALARY DETAILS -----");
        System.out.println("Basic Salary: " + basic);
        System.out.println("HRA: " + hra);
        System.out.println("DA: " + da);
        System.out.println("PF Deduction: " + pf);
        System.out.println("Net Salary: " + netSalary);

        sc.close();
    }
}

3. Number Classification Tool (if-else + operators)

Write a Java program that:

* Accepts an integer
* Checks whether the number is:

  * Positive or negative
  * Even or odd
  * Divisible by both 5 and 7

Focus: modulus operator, logical operators, multiple if-else

import java.util.Scanner;

public class NumberClassificationTool {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

      
        System.out.print("Enter an integer: ");
        int number = sc.nextInt();

      
        if (number > 0) {
            System.out.println("The number is Positive.");
        } else if (number < 0) {
            System.out.println("The number is Negative.");
        } else {
            System.out.println("The number is Zero.");
        }

       
        if (number % 2 == 0) {
            System.out.println("The number is Even.");
        } else {
            System.out.println("The number is Odd.");
        }

       
        if (number % 5 == 0 && number % 7 == 0) {
            System.out.println("The number is divisible by both 5 and 7.");
        } else {
            System.out.println("The number is NOT divisible by both 5 and 7.");
        }

        sc.close();
    }
}

4. Menu-Driven Calculator (switch case)

Write a Java program using switch that:

* Takes two numbers from the user
* Displays menu:

  1. Addition
  2. Subtraction
  3. Multiplication
  4. Division
  5. Modulus
* Performs operation based on user choice

Focus: switch case, arithmetic operators

import java.util.Scanner;

public class MenuDrivenCalculator {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        
        System.out.print("Enter first number: ");
        double num1 = sc.nextDouble();

        System.out.print("Enter second number: ");
        double num2 = sc.nextDouble();

        
        System.out.println("\n---- MENU ----");
        System.out.println("1. Addition");
        System.out.println("2. Subtraction");
        System.out.println("3. Multiplication");
        System.out.println("4. Division");
        System.out.println("5. Modulus");
        System.out.print("Enter your choice (1-5): ");

        int choice = sc.nextInt();

        
        switch (choice) {

            case 1:
                System.out.println("Result = " + (num1 + num2));
                break;

            case 2:
                System.out.println("Result = " + (num1 - num2));
                break;

            case 3:
                System.out.println("Result = " + (num1 * num2));
                break;

            case 4:
                if (num2 != 0) {
                    System.out.println("Result = " + (num1 / num2));
                } else {
                    System.out.println("Division by zero is not allowed.");
                }
                break;

            case 5:
                System.out.println("Result = " + (num1 % num2));
                break;

            default:
                System.out.println("Invalid choice. Please select between 1 to 5.");
        }

        sc.close();
    }
}

5. Electricity Bill Generator (if-else ladder)

Write a Java program to calculate electricity bill:

* Input units consumed
* Charges:

  * First 100 units → ₹2/unit
  * Next 100 units → ₹3/unit
  * Above 200 units → ₹5/unit
* Add fixed meter charge ₹150

Focus: if-else ladder, real-world logic

import java.util.Scanner;

public class ElectricityBillGenerator {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        
        System.out.print("Enter units consumed: ");
        int units = sc.nextInt();

        double billAmount;

       
        if (units <= 100) {
            billAmount = units * 2;
        }
        else if (units <= 200) {
            billAmount = (100 * 2) + ((units - 100) * 3);
        }
        else {
            billAmount = (100 * 2) + (100 * 3) + ((units - 200) * 5);
        }

        
        billAmount = billAmount + 150;

       
        System.out.println("\n----- ELECTRICITY BILL -----");
        System.out.println("Units Consumed: " + units);
        System.out.println("Fixed Meter Charge: 150");
        System.out.println("Total Bill Amount: ₹" + billAmount);

        sc.close();
    }
}

6. ATM Withdrawal System (if-else + logical operators)

Write a Java program that:

* Takes account balance and withdrawal amount
* Conditions:

  * Withdrawal must be multiple of 100
  * Minimum balance after withdrawal must be ₹1000
* Print success or failure message

Focus: compound conditions, logical AND

import java.util.Scanner;

public class ATMWithdrawalSystem {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

       
        System.out.print("Enter Account Balance: ");
        double balance = sc.nextDouble();

        System.out.print("Enter Withdrawal Amount: ");
        double withdrawAmount = sc.nextDouble();

       
        if (withdrawAmount % 100 == 0 && (balance - withdrawAmount) >= 1000) {

            balance = balance - withdrawAmount;

            System.out.println("\nWithdrawal Successful!");
            System.out.println("Remaining Balance: ₹" + balance);

        } else {

            System.out.println("\nWithdrawal Failed!");

            if (withdrawAmount % 100 != 0) {
                System.out.println("Reason: Amount must be multiple of 100.");
            }

            if ((balance - withdrawAmount) < 1000) {
                System.out.println("Reason: Minimum balance of ₹1000 must be maintained.");
            }
        }

        sc.close();
    }
}

7. Reverse and Digit Analysis of a Number (loops + operators)

Write a Java program that:

* Takes an integer
* Finds:

  * Reverse of the number
  * Sum of digits
  * Count of digits

Focus: while loop, % and / operators

import java.util.Scanner;

public class ReverseAndDigitAnalysis {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

       
        System.out.print("Enter an integer: ");
        int number = sc.nextInt();

        int originalNumber = number;   
        int reverse = 0;
        int sum = 0;
        int count = 0;

       
        while (number != 0) {

            int digit = number % 10;  
            reverse = reverse * 10 + digit;  
            sum = sum + digit;         

            number = number / 10;      
        }

        
        System.out.println("\n----- RESULT -----");
        System.out.println("Original Number: " + originalNumber);
        System.out.println("Reverse: " + reverse);
        System.out.println("Sum of Digits: " + sum);
        System.out.println("Count of Digits: " + count);

        sc.close();
    }
}

8. Pattern Printing Program (nested loops)

Write a Java program to print the following pattern for given n:


1
12
123
1234


Focus: nested for loops, loop control

import java.util.Scanner;

public class PatternPrinting {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

       
        System.out.print("Enter value of n: ");
        int n = sc.nextInt();

       
        for (int i = 1; i <= n; i++) {

            
            for (int j = 1; j <= i; j++) {
                System.out.print(j);
            }

            
            System.out.println();
        }

        sc.close();
    }
}
