#import java.util.Scanner;
 
public class AtmMachine{
 
    private static Scanner in; 
    private static float balance = 0; // initial balance to 0 for everyone
    private static int anotherTransaction;
 
    public static void main(String args[]){
        in = new Scanner(System.in);
 
        // call our transaction method here 
        transaction();
    }
 
    private static void transaction(){
        // here is where most of work is
 
        int choice; 
 
        System.out.println("Please select an option"); 
        System.out.println("1. Withdraw");
        System.out.println("2. Deposit");
        System.out.println("3. Balance");
 
        choice = in.nextInt();
 
        switch(choice){
            case 1:
                float amount; 
                System.out.println("Please enter amount to withdraw: "); 
                amount = in.nextFloat();
                if(amount > balance || amount == 0){
                    System.out.println("You have insufficient funds\n\n"); 
                    anotherTransaction(); // ask if they want another transaction
                } else {
                    // they have some cash
                    // update balance 
                    balance = balance - amount; 
                    System.out.println("You have withdrawn "+amount+" and your new balance is "+balance+"\n");
                    anotherTransaction(); 
                }
            break; 
 
            c
