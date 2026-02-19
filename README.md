# Codsoft-
Task 1 Number Game codsoft intership in java programming 
import java.util.Scanner;
import java.util.Random;

/*
 * --------------------------------------------
 * Number Guessing Game in Java
 * Author  : Kajal Pradeep Shinde
 * Purpose : Practice Java basics (loops, conditions, input)
 * --------------------------------------------
 */

class Main {

    // Method to generate a random number
    static int generateRandomNumber() {
        Random random = new Random();
        return random.nextInt(10) + 1;   // generates number between 1 to 10
    }

    // Method to take user input
    static int takeUserInput(Scanner sc) {
        System.out.print("Enter your guess: ");
        return sc.nextInt();
    }

    // Method to check the guess
    static void checkGuess(int guess, int number) {
        if (guess > number) {
            System.out.println("Too High! Try again.");
        } else if (guess < number) {
            System.out.println("Too Low! Try again.");
        } else {
            System.out.println("🎉 Congratulations! You guessed the correct number.");
        }
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int number = generateRandomNumber();
        int guess = 0;
        int attempts = 0;

        System.out.println("=================================");
        System.out.println("     NUMBER GUESSING GAME");
        System.out.println("=================================");
        System.out.println("Guess a number between 1 and 10");
        System.out.println();

        // Loop until user guesses correctly
        while (guess != number) {
            guess = takeUserInput(sc);
            attempts++;
            checkGuess(guess, number);
            System.out.println();
        }

        System.out.println("---------------------------------");
        System.out.println("Total Attempts: " + attempts);
        System.out.println("Thank you for playing!");
        System.out.println("---------------------------------");

        sc.close();
    }
}
