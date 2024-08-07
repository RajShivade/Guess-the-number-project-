# Guess the Number Project :-

# Overview:-

The "Guess the Number" project is a simple console-based game where the player attempts to guess a randomly generated number between 1 and 100. The game provides feedback on whether the guess is too high or too low and adjusts the number of remaining attempts based on the chosen difficulty level. The game ends when the player either guesses the number correctly or runs out of attempts.

# Project Overview:-

- The game works as follows:

~The game starts by displaying a welcome message and the game's logo.

~The player chooses a difficulty level, which determines the number of attempts they get.

~The game generates a random number between 1 and 100.

~The player attempts to guess the number within the allowed attempts.

~After each guess, the game informs the player whether the guess is too high, too low, or correct.

~The game ends when the player guesses correctly or runs out of attempts.

# Files and Dependencies:-

- Main Python Script:

main.py: Contains the game logic and functions required to play the game.

- Dependencies:-
 ~random: Used to generate a random number between 1 and 100.
 ~art: Used to display the game logo.

- Functions: 
  check_answer(guess, answer, turns)
  Checks the user's guess against the actual answer.

 ~ Parameters:
   guess (int): The user's guess.
   answer (int): The correct number.
   turns (int): The remaining attempts.

 ~ Returns:
   The number of remaining attempts after a guess.

- set_difficulty()
  Prompts the user to choose a difficulty level and sets the number of attempts accordingly.

 ~ Returns:
   The number of attempts based on the chosen difficulty level.

 ~ game()
   Main function to start the game.

~Displays the game logo and welcome message.
~Generates a random number between 1 and 100.
~Sets the difficulty level based on user input.
~Allows the user to guess the number, providing feedback and tracking remaining attempts.
~Ends the game when the number is guessed correctly or attempts run out.

# Game Logic:-

1 Welcome and Setup:

~The game begins by displaying a logo and a welcome message.
~A random number between 1 and 100 is generated.
~The player is prompted to choose a difficulty level (easy or hard), which sets the number of attempts.

2 Guessing Loop:

~The player is informed of the number of remaining attempts.
~The player makes a guess.
~The guess is checked against the actual number:
~If the guess is too high, the player is informed, and the number of attempts is decremented.
~If the guess is too low, the player is informed, and the number of attempts is decremented.
~If the guess is correct, the player is congratulated, and the game ends.
~If the player runs out of attempts without guessing the number, the game ends with a loss message.

# Sample code :

from random import randint
from art import logo

EASY_LEVEL_TURNS = 5
HARD_LEVEL_TURNS = 10

def check_answer(guess, answer, turns):
  if guess > answer:
    print("Too high.")
    return turns - 1
  elif guess < answer:
    print("Too low.")
    return turns - 1
  else:
    print(f"You got it! The answer was {answer}.")

def set_difficulty():
  level = input("Choose a difficulty. Type 'easy' or 'hard': ")
  if level == "easy":
    return EASY_LEVEL_TURNS
  else:
    return HARD_LEVEL_TURNS

def game():
  print(logo)
  print("Welcome to the Number Guessing Game!")
  print("I'm thinking of a number between 1 and 100.")
  answer = randint(1, 100)
  turns = set_difficulty()
  guess = 0
  while guess != answer:
    print(f"You have {turns} attempts remaining to guess the number.")
    guess = int(input("Make a guess: "))
    turns = check_answer(guess, answer, turns)
    if turns == 0:
      print("You've run out of guesses, you lose.")
      return
    elif guess != answer:
      print("Guess again.")

game()


# How to Run the Game:-

~ Ensure you have Python installed on your machine.
~ Install the art package using pip if not already installed

pip install art

~ Save the provided code into a file named main.py.
~ Run the script from the command line

python main.py

~ Follow the prompts to play the game.

# Conclusion:-

The "Guess the Number" project is an excellent way to practice basic Python programming, including working with functions, loops, conditionals, and user input. It provides a fun and interactive experience while reinforcing core programming concepts.
