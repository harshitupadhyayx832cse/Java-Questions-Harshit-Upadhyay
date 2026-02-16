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
