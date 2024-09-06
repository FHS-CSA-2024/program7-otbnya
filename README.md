import java.util.Scanner;

public class SchruteBuckConverter {

    // Constants for conversion rates
    private static final int KLEVINS_PER_SCHRUTE_BUCK = 20;
    private static final int STANLEY_NICKELS_PER_KLEVIN = 12;
    private static final int STANLEY_NICKELS_PER_SCHRUTE_BUCK = 100;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input for schrute-bucks, klevins, and stanley-nickels
        System.out.print("Enter schrute-bucks: ");
        int schruteBucks = scanner.nextInt();

        System.out.print("Enter klevins: ");
        int klevins = scanner.nextInt();

        System.out.print("Enter stanley-nickels: ");
        int stanleyNickels = scanner.nextInt();

        // Convert to decimal schrute-bucks
        double decimalSchruteBucks = convertToDecimalSchruteBucks(schruteBucks, klevins, stanleyNickels);

        // Output the result
        System.out.printf("Decimal schrute-bucks = $%.2f%n", decimalSchruteBucks);
        
        // Close the scanner
        scanner.close();
    }

    private static double convertToDecimalSchruteBucks(int schruteBucks, int klevins, int stanleyNickels) {
        // Calculate the total stanley nickels from the old system
        int totalStanleyNickels = (schruteBucks * STANLEY_NICKELS_PER_SCHRUTE_BUCK) +
                                   (klevins * STANLEY_NICKELS_PER_KLEVIN) +
                                   stanleyNickels;

        // Convert total stanley nickels to decimal schrute bucks
        return totalStanleyNickels / (double) STANLEY_NICKELS_PER_SCHRUTE_BUCK;
    }
}
