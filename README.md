# ATM-Interface
8645_Madhumidha S_Mini project 

ATM Interface:
=====================================================

import java.util.Scanner;

public class Main {
 
    public static void main(String[] args) {
 
        String userName = "Madhu";
        String AccountType = "Savings";
        String Status = "Active";
        String password = "1234";
        String bankName = "AA Bank Limited";

        double userBalance = 5000;
 
        Scanner bankScanner = new Scanner(System.in);

        System.out.println("Welcome to " + bankName);
        System.out.println("Please Insert Your Card ");
        String Insertcard = bankScanner.nextLine();
        System.out.println("Please Enter Your PIN Number ");

        String enteredPassword = bankScanner.nextLine();

        while(!enteredPassword.equalsIgnoreCase(password)){

              System.out.println("Invalid pin");
              System.out.println("Please Enter Your valid PIN Number");

              enteredPassword = bankScanner.nextLine();
        }
        
        if(enteredPassword.equalsIgnoreCase(password)) {
           
            System.out.println("Account Holder Name : " + userName);
            System.out.println("Account Type : " + AccountType);
            System.out.println("Account Status : " + Status);
            System.out.println("Please choose the following options ");
            System.out.println("1 - Show Balance , 2 - Deposit Amount , 3 - Withdraw Amount , 4 - Exit");

            int userChoice = bankScanner.nextInt();
            
            if (userChoice == 1) {

                System.out.println("Your Current Balance is " + userBalance);
                System.out.println(" ");
                System.out.println("You can remove your card...!!! ");
                System.out.println("Thank you...!!! Visit again...!!! ");

            } else if (userChoice == 2) {

                System.out.println("Please Enter The Amount To Deposit ");
                double depositAmount = bankScanner.nextDouble();
                
                userBalance += depositAmount;

                System.out.println("You have successfully deposited " + depositAmount+ " \nNow your balance is: " + userBalance);
                System.out.println(" ");
                System.out.println("You can remove your card...!!! ");
                System.out.println("Thank you...!!! Visit again...!!! ");

            } else if (userChoice == 3) {

                System.out.println("Please Enter the Amount to Witdraw");

                double withdrawAmount = bankScanner.nextDouble();
                
                if (withdrawAmount > userBalance) {

                    System.out.println("Insufficient Balance. Please Try Again");

                } else {

                    userBalance -= withdrawAmount;

                            System.out.println("You have successfully withdraw " + withdrawAmount + " \nNow your balance is: " + userBalance);


                            System.out.println("Please Collect Your Cash...!!!");
                            System.out.println(" ");
                            System.out.println("You can remove your card...!!! ");
                            System.out.println("Thank you...!!! Visit again...!!! ");
            }
 
        }
         else if(userChoice == 4){

            System.out.println("Thank you...!!! Have a Nice day...!!! ");
        }
    }
    }
}
