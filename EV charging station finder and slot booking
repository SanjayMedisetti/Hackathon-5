import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class ChargingStation {
    private String location;
    private int availableSlots;
    private boolean fastCharging;

    public ChargingStation(String location, int availableSlots, boolean fastCharging) {
        this.location = location;
        this.availableSlots = availableSlots;
        this.fastCharging = fastCharging;
    }

    public String getLocation() {
        return location;
    }

    public int getAvailableSlots() {
        return availableSlots;
    }

    public boolean isFastCharging() {
        return fastCharging;
    }

    public void bookSlot() {
        if (availableSlots > 0) {
            availableSlots--;
            System.out.println("Slot booked successfully at " + location);
        } else {
            System.out.println("No available slots at " + location);
        }
    }
}

public class Main {

    public static void main(String[] args) {
        List<ChargingStation> stations = new ArrayList<>();
        stations.add(new ChargingStation("Downtown", 5, true));
        stations.add(new ChargingStation("Uptown", 2, false));
        stations.add(new ChargingStation("Suburb", 3, true));
        stations.add(new ChargingStation("City Center", 1, true));
        stations.add(new ChargingStation("Highway", 4, false));

        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the EV Charging Station Finder!");

        System.out.println("Do you want to filter by fast charging? (yes/no)");
        String fastChargingFilter = scanner.nextLine();

        List<ChargingStation> filteredStations = new ArrayList<>();

        for (ChargingStation station : stations) {
            if (fastChargingFilter.equalsIgnoreCase("yes")) {
                if (station.isFastCharging()) {
                    filteredStations.add(station);
                }
            } else {
                filteredStations.add(station);
            }
        }

        System.out.println("Available Charging Stations:");
        for (int i = 0; i < filteredStations.size(); i++) {
            ChargingStation station = filteredStations.get(i);
            System.out.println((i + 1) + ". " + station.getLocation() + " - Slots available: " + station.getAvailableSlots() + 
                               " - Fast Charging: " + station.isFastCharging());
        }

        System.out.println("Select a station to book a slot (enter the number):");
        int choice = scanner.nextInt();

        if (choice > 0 && choice <= filteredStations.size()) {
            ChargingStation selectedStation = filteredStations.get(choice - 1);
            selectedStation.bookSlot();
        } else {
            System.out.println("Invalid selection. Exiting.");
        }

        scanner.close();
    }
}
