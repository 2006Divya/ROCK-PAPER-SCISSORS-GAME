# ROCK-PAPER-SCISSORS-GAME
import random

def get_user_choice():
    choice=input("Choose rock, paper or scissors:").lower()
    while choice not in ["rock","paper","scissors"]:
        choice=input("Invalid choice. Please choose rock,paper or scissors:").lower()
    return choice


# Function to get computer choice
def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"])
   

# Function to determine the winner
def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "tie"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "You won"
    else:
        return "You lose"

# Main game function
def play_game():
    user_score = 0
    computer_score = 0
    while True:
        user_choice = get_user_choice()
        computer_choice = get_computer_choice()
        winner = determine_winner(user_choice, computer_choice)
        if winner == "You won!":
            user_score += 1
        elif winner == "You lose":
            computer_score += 1
        print(f"\n You chose: {user_choice}")
        print(f"\n Computer chose: {computer_choice}")
        print(winner)
        print(f"Scores -> You: {user_score}, Computer: {computer_score}\n")
        play_again = input("Do you want to play again? (yes/no): ").lower()
        if play_again!='yes':
            break

    print("\nFinal Scores -> You: ",user_score," Computer: ",computer_score)
    print("Thanks for playing!")

# Run the game
print(        "ROCK PAPER SCISSORS GAME"   )
print(        "************************"   )


print(        "GENERAL INSTRUCTIONS"      )
print("1. User need to enter choice from the given choices")
print("2. Computer will generate a random choice")
print("3. If both of your choice is same , result will be tie")
print("4. In this rock beats scissors , scissors beat paper and paper beats rock")
print("   |user    |computer |")
print("   |rock    |scissors |")
print("   |paper   |rock     |")
print("   |scissors|paper    |")
print("   any of the above combinations matches the result will be you won")
print("5. Otherwise the result will be you lose")
print("6. Finally your scores and result will be displayed")
print("7. You can play this game any number of times") 
play_game()


        

