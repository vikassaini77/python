# python
import random

def guess_the_number():
    # Computer selects a random number between 1 and 100
    secret_number = random.randint(1, 100)
    attempts = 0
    print("Welcome to the 'Guess the Number' game!")
    print("I'm thinking of a number between 1 and 100.")
    
    while True:
        try:
            # Player makes a guess
            guess = int(input("Enter your guess: "))
            
            # Check if the guess is within the valid range
            if guess < 1 or guess > 100:
                print("Please enter a number between 1 and 100.")
                continue

            attempts += 1

            # Provide hints and feedback
            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"Congratulations! You've guessed the number {secret_number} correctly!")
                print(f"It took you {attempts} attempts.")
                break
        
        # Handle invalid input
        except ValueError:
            print("Oops! That doesn't look like a number. Please enter a valid number.")

# Start the game
guess_the_number()
