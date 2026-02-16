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
