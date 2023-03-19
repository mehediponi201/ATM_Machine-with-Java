
import java.util.Scanner;

/**
 *
 * @author poni
 *
 */
public class ATM {

    public static Scanner sc = new Scanner(System.in);
    static double balance;

    static void checkBalance() {
        System.out.println("Your balance is: " + balance);
    }

    static void withdraw() {
        System.out.print("Enter amount to withdraw: ");
        double amount = sc.nextDouble();
        if (amount > balance) {
            System.out.println("Insufficient balance!");
        } else if (balance > amount) {
            balance = balance - amount;
            System.out.println("You have withdrawn " + amount + ",Your new balance is " + balance);
        }
    }

    static void deposit() {
        System.out.print("Enter amount to deposit: ");
        double amount = sc.nextDouble();
        balance = balance + amount;
        System.out.println("You have deposited " + amount + ",your new balance is " + balance);
    }

    public static void main(String[] args) {

        int ac_no = 12345;
        int pass = 123;
        System.out.print("Enter your Account No:");
        int account_no = sc.nextInt();
        System.out.print("Enter your password: ");
        int password = sc.nextInt();
        if (account_no == ac_no && pass == password) {
            System.out.println("Enter the amount of Balance:");
            balance = sc.nextDouble();
            int choice;
            for (int i = 1; i <= 4; i++) {
                System.out.println("\nATM MENU:");
                System.out.println("1. Cheak Balance");
                System.out.println("2. Withdraw");
                System.out.println("3. Deposit");
                System.out.println("4. Exit");

                System.out.print("Enter your choice: ");
                choice = sc.nextInt();
                switch (choice) {
                    case 1:
                        checkBalance();
                        break;
                    case 2:
                        withdraw();
                        break;
                    case 3:
                        deposit();
                        break;
                    case 4:
                        System.out.println("Thank you for using the ATM!");
                        break;
                    default:
                        System.out.println("Invalid choice!");
                }
            }
        } else {
            System.out.println("Contact the authorithy!!!! Your account no & password is not correct");
        }

    }
}
