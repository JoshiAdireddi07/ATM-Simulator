# ATM-Simulator
 Checks balance, withdraw, deposit developed using java\

 
  import java.util.Scanner;

    public class SimpleATM {
    public static void main(String[] args) {
        double balance = 5000.0;  // Initial balance
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n🏧 Welcome to the ATM");
            System.out.println("1. 💰 Check Balance");
            System.out.println("2. ➕ Deposit Money");
            System.out.println("3. ➖ Withdraw Money");
            System.out.println("4. ❌ Exit");
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.println("✅ Your Balance: ₹" + balance);
                    break;
                case 2:
                    System.out.print("Enter deposit amount: ₹");
                    double deposit = sc.nextDouble();
                    if (deposit > 0) {
                        balance += deposit;
                        System.out.println("💵 Deposited successfully!");
                    } else {
                        System.out.println("⚠️ Invalid deposit amount.");
                    }
                    break;
                case 3:
                    System.out.print("Enter withdrawal amount: ₹");
                    double withdraw = sc.nextDouble();
                    if (withdraw > 0 && withdraw <= balance) {
                        balance -= withdraw;
                        System.out.println("💸 Withdrawn successfully!");
                    } else {
                        System.out.println("⚠️ Insufficient balance or invalid amount.");
                    }
                    break;
                case 4:
                    System.out.println("👋 Thank you for using the ATM. Goodbye!");
                    return;
                default:
                    System.out.println("❌ Invalid choice. Try again.");
            }
        }
    }
}

