# simplecalculatorprojectjava

import java.util.Scanner;
import java.util.InputMismatchException;
public class Simplecalculatot {
    
   /**
     * Performs addition of two numbers
     * @param a first number
     * @param b second number
     * @return sum of a and b
     */
    static double add(double a, double b) {
        return a + b;
    }
    
    
  * Performs subtraction of two numbers
     * @param a first number (minuend)
     * @param b second number (subtrahend)
     * @return difference of a and b
     */
    static double sub(double a, double b) {
        return a - b;
    }
    
    /**
     * Performs multiplication of two numbers
     * @param a first number
     * @param b second number
     * @return product of a and b
     */
    static double mul(double a, double b) {
        return a * b;
    }
    
    /**
     * Performs division of two numbers
     * @param a dividend
     * @param b divisor
     * @return quotient of a divided by b
     */
    static double div(double a, double b) {
        return a / b;
    }
    
    /**
     * Performs modulus operation on two numbers
     * @param a dividend
     * @param b divisor
     * @return remainder when a is divided by b
     */
    static double mod(double a, double b) {
        return a % b;
    }
    
    /**
     * Main method - entry point of the calculator program
     * Displays menu, handles user input, and performs calculations
     * @param args command line arguments (not used)
     */
    public static void main(String[] args) {
        // Create Scanner object to read user input from console
        Scanner sc = new Scanner(System.in);
        
        // Main program loop - continues until user chooses to exit
        while (true) {
            // Display calculator menu options
            System.out.println("\\___simple calculator____");
            System.out.println("1. addition (+)");
            System.out.println("2. substraction (-)");
            System.out.println("3. multipication (*)");
            System.out.println("4. division (/)");
            System.out.println("5. modulus (%)");
            System.out.println("9. exit");
            System.out.println("choose 1 to 9 number ");
            
        // Variable to store user's menu choice
            int choice;
            
         // Try to read user's menu choice with error handling
            try {
                choice = sc.nextInt();
            } catch (InputMismatchException e) {
                // Handle case where user enters non-integer input
                System.out.println("plz enter valid number");
                sc.nextLine(); // Clear the invalid input from scanner buffer
                continue; // Go back to menu display
            }
            
         // Check if user wants to exit the program
            if (choice == 9) {
                System.out.println("thank you");
                break; // Exit the main loop
            }
            
        // Variables to store the two numbers for calculation
            double x, y;
            
         // Try to read the two numbers with error handling
            try {
                System.out.println("enter the first number");
                x = sc.nextDouble();
                System.out.println("enter the 2nd number");
                y = sc.nextDouble();
            } catch (InputMismatchException e) {
                // Handle case where user enters non-numeric input
                System.out.println("plz enter the valid number");
                sc.nextLine(); // Clear the invalid input from scanner buffer
                continue; // Go back to menu display
            }
            
          // Variable to store calculation result
            double result;
            
         // Process user's choice using switch statement
            switch (choice) {
                case 1: // Addition operation
                    result = add(x, y);
                    System.out.println("result=" + result);
                    break;
                    
         case 2: // Subtraction operation
                    result = sub(x, y);
                    System.out.println("result=" + result);
                    break;
                    
        case 3: // Multiplication operation
                    result = mul(x, y);
                    System.out.println("result=" + result);
                    break;
                    
         case 4: // Division operation
                    // Check for division by zero to prevent runtime error
                    if (y == 0) {
                        System.out.println("division by zero not allowed.");
                    } else {
                        result = div(x, y);
                        System.out.println("result=" + result);
                    }
                    break;
                    
         case 5: // Modulus operation
                    // Check for modulus by zero to prevent runtime error
                    if (y == 0) {
                        System.out.println("modulus by zero not allowed ");
                    } else {
                        result = mod(x, y);
                        System.out.println("result=" + result);
                    }
                    break;
                    
       default: // Handle invalid menu choices
                    System.out.println("invalid choice plz enter the number between 1 to 9");
            }
        } // End of main program loop
        
        // Close the Scanner to free up system resources
        sc.close();
    }
}
