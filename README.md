# SkiTrip
import java.util.Scanner;

public class P03_SkiTrip {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        int numberDays = Integer.parseInt(scanner.nextLine());
        String apartmentType = scanner.nextLine();
        String oppinionType = scanner.nextLine();

        double roomForOnePersonPrice = 18.00;
        double apartmentPrice = 25.00;
        double presidentApartmentPrice = 35.00;
        int numberNights = numberDays - 1;
        double endSum = 0;

        if (apartmentType.equalsIgnoreCase("room for one person")){
             endSum = numberNights * roomForOnePersonPrice;
        }
        else if (apartmentType.equalsIgnoreCase("apartment")){

            if (numberNights < 10){
                endSum = (numberNights * apartmentPrice) - (0.30 * (numberNights * apartmentPrice));
            }
            else if(numberNights < 16){
                endSum = (numberNights * apartmentPrice) - (0.35 * (numberNights * apartmentPrice));
            }
            else {
                endSum = (numberNights * apartmentPrice) - (0.50 * (numberNights * apartmentPrice));
            }

        }
        else if (apartmentType.equalsIgnoreCase("president apartment")){

            if (numberNights < 10){
                endSum = (numberNights * presidentApartmentPrice) - (0.10 * (numberNights * presidentApartmentPrice));
            }
            else if(numberNights < 16){
                endSum = (numberNights * presidentApartmentPrice) - (0.15 * (numberNights * presidentApartmentPrice));
            }
            else {
                endSum = (numberNights * presidentApartmentPrice) - (0.20 * (numberNights * presidentApartmentPrice));
            }

        }
        if (oppinionType.equalsIgnoreCase("positive")){
            endSum = endSum + (endSum * 0.25);
        }
        else if (oppinionType.equalsIgnoreCase("negative")){
            endSum = endSum - (endSum * 0.10);
        }
        System.out.printf("%.2f\n",endSum);
    }
}
