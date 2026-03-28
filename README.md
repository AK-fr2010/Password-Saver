# Password-Saver
    import java.util.Scanner;

     public class Main {
       public static void main(String[] args) {
         Scanner scanner = new Scanner(System.in);
          boolean isPasswordValid = false; // The Gatekeeper

        while (!isPasswordValid) { // Loop starts here
            System.out.print("Please Enter Your Password: ");
            String password = scanner.nextLine().trim();

            if (password.isEmpty()) {
                System.out.println(">> Error: Password cannot be empty.");
            }
            else if (password.length() < 8) {
                System.out.println(">> Error: Password must be at least 8 characters.");
            }
            else {
                // If it passes length/empty, check confirmation
                System.out.print("Please re-enter your password to confirm: ");
                String rePassword = scanner.nextLine().trim();

                if (password.equals(rePassword)) {
                    System.out.println("===================================");
                    System.out.println("SUCCESS: Your Password is saved!");
                    System.out.println("===================================");
                    isPasswordValid = true; // This breaks the loop!
                } else {
                    System.out.println(">> Error: Passwords do not match. Try again.");
                }
            }
        }

        scanner.close();
    }
}
