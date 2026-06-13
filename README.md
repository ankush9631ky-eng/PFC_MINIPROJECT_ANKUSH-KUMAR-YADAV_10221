import java.util.Scanner;

class Courier {
    private String trackingId;
    private String sender;
    private String receiver;
    private String status;

    public Courier(String trackingId, String sender, String receiver, String status) {
        this.trackingId = trackingId;
        this.sender = sender;
        this.receiver = receiver;
        this.status = status;
    }

    public String getTrackingId() {
        return trackingId;
    }

    public void displayDetails() {
        System.out.println("Tracking ID : " + trackingId);
        System.out.println("Sender      : " + sender);
        System.out.println("Receiver    : " + receiver);
        System.out.println("Status      : " + status);
    }
}

public class CourierTrackingSystem {
    public static void main(String[] args) {

        Courier[] couriers = {
            new Courier("C101", "Ankush", "Rahul", "Delivered"),
            new Courier("C102", "Priya", "Aman", "In Transit"),
            new Courier("C103", "Riya", "Karan", "Out for Delivery")
        };

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Tracking ID: ");
        String id = sc.nextLine();

        boolean found = false;

        for (Courier c : couriers) {
            if (c.getTrackingId().equalsIgnoreCase(id)) {
                System.out.println("\nCourier Found!");
                c.displayDetails();
                found = true;
                break;
            }
        }

        if (!found) {
            System.out.println("Tracking ID not found!");
        }

        sc.close();
    }
}
