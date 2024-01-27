#include <iostream>
#include <cstdlib>  // For rand() function
#include <ctime>    // For time() function

int main() {
    // Seed the random number generator with the current time
    std::srand(static_cast<unsigned int>(std::time(0)));

    // Generate a random number between 1 and 100
    int secretNumber = std::rand() % 100 + 1;

    // Variables to store user input and track the number of attempts
    int guess, attempts = 0;

    std::cout << "Welcome to the Guess the Number Game!\n";
    std::cout << "Try to guess the number between 1 and 100.\n\n";

    do {
        // Get user input
        std::cout << "Enter your guess: ";
        std::cin >> guess;

        // Increment the number of attempts
        attempts++;

        // Provide feedback to the user
        if (guess == secretNumber) {
            std::cout << "Congratulations! You guessed the correct number in " << attempts << " attempts.\n";
        } else if (guess < secretNumber) {
            std::cout << "Too low! Try again.\n";
        } else {
            std::cout << "Too high! Try again.\n";
        }

    } while (guess != secretNumber);

    return 0;
}
