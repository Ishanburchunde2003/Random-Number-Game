import java.util.Scanner;
import java.util.Random;

public class RandomNumberGame {
    public static void main(String args[]) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("What is your name?");
        String name = scanner.nextLine();
        String uppercaseName = name.toUpperCase();
        System.out.println("Hello, " + uppercaseName + ". I am thinking of a number between 1 and 100.");
        int myNumber = getRandomNumber(1, 100);

        for (int i = 0; i < 10; i++) {
            Scanner guessScanner = new Scanner(System.in);
            System.out.println("Take a guess:");
            int yourGuess = guessScanner.nextInt();

            if (yourGuess == myNumber) {
                System.out.println("Congratulations! You have correctly guessed the number.");
                break;
            } else if (yourGuess < myNumber) {
                System.out.println("Your guess is too low.");
            } else if (yourGuess > myNumber) {
                System.out.println("Your guess is too high.");
            }

            if (i >= 9) {
                System.out.println("Sorry, you did not guess the correct number. The number I was thinking of was " + myNumber + ".");
            }
        }
    }

    public static int getRandomNumber(int min, int max) {
        Random rand = new Random();
        return rand.nextInt(max - min + 1) + min;
    }
}
