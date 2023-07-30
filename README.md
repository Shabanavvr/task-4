# task-4
import java.util.Scanner;

public class ElectricityBillingSystem {
    private String customerName;
    private int customerId;
    private double previousReading;
    private double currentReading;
    private double unitsConsumed;

    public ElectricityBillingSystem(String customerName, int customerId, double previousReading, double currentReading) {
        this.customerName = customerName;
        this.customerId = customerId;
        this.previousReading = previousReading;
        this.currentReading = currentReading;
        this.unitsConsumed = currentReading - previousReading;
    }

    public double calculateBill() {
        double perUnitRate = 0.10; // $0.10 per unit
        return unitsConsumed * perUnitRate;
    }

    public void displayBill() {
        System.out.println("\nElectricity Bill for Customer: " + customerName);
        System.out.println("Customer ID: " + customerId);
        System.out.println("Units Consumed: " + unitsConsumed + " units");
        System.out.println("Total Bill: $" + calculateBill());
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Electricity Billing System!");

        System.out.print("Enter customer name: ");
        String customerName = scanner.nextLine();

        System.out.print("Enter customer ID: ");
        int customerId = scanner.nextInt();

        System.out.print("Enter previous meter reading (in units): ");
        double previousReading = scanner.nextDouble();

        System.out.print("Enter current meter reading (in units): ");
        double currentReading = scanner.nextDouble();

        // Create the customer
        ElectricityBillingSystem customer = new ElectricityBillingSystem(customerName, customerId, previousReading, currentReading);

        // Display the bill
        customer.displayBill();

        scanner.close();
    }
}
