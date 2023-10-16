import random

# Create a list of the multiplication table
multiplication_table = [[i * j for j in range(1, 11)] for i in range(1, 11)]

# Initialize the player's score
score = 0

# Initialize the number of incorrect attempts the player has
incorrect_attempts = 3

# Initialize the game is over flag
game_over = False

# Initialize the set of asked multiplication problems
asked_problems = set()

# Initialize the set of asked multiplication numbers
asked_numbers = set()

while not game_over:
    # Ask a random multiplication problem
    while True:
        number1 = random.randint(1, 10)
        number2 = random.randint(1, 10)
        question = f"{number1} x {number2} = ?"

        # Only ask if the problem hasn't been asked before
        if question not in asked_problems and (number1, number2) not in asked_numbers:
            break

    # Get the player's answer
    answer = input(question)

    # Try to convert the answer to an int
    try:
        int_answer = int(answer)

        # Check the answer
        if int_answer == multiplication_table[number1 - 1][number2 - 1]:
            # Correct answer, increment the score and print a correct answer message
            score += 5
            print("Correct! The correct answer is:", multiplication_table[number1 - 1][number2 - 1], "Your total score is:", score)
        else:
            # Incorrect answer, decrement the number of incorrect attempts and print an incorrect answer message
            incorrect_attempts -= 1
            print("Incorrect! The correct answer is:", multiplication_table[number1 - 1][number2 - 1])
    except ValueError:
        # If the answer can't be converted to an int, print an error message and ask a new question
        print("Invalid answer!")

    # If the player has run out of incorrect attempts, end the game
    if incorrect_attempts == 0:
        game_over = True

    # Update the asked problems and numbers
    asked_problems.add(question)
    asked_numbers.add((number1, number2))

# Print the game over message
print("Game over. Your score is:", score)

# Check if the player got all of the multiplication questions correct
if score == 100:
    print("Congratulations! You got all of the multiplication questions correct.")
