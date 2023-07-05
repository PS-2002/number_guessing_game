# number_guessing_game
#1choosing a random number between 1 and 100:
import random
logo = """
 ________                                  __  .__                                   ___.                 
 /  _____/ __ __   ____   ______ ______   _/  |_|  |__   ____       ____  __ __  _____\_ |__   ___________ 
/   \  ___|  |  \_/ __ \ /  ___//  ___/   \   __\  |  \_/ __ \     /    \|  |  \/     \| __ \_/ __ \_  __ \
\    \_\  \  |  /\  ___/ \___ \ \___ \     |  | |   Y  \  ___/    |   |  \  |  /  Y Y  \ \_\ \  ___/|  | \/
 \______  /____/  \___  >____  >____  >    |__| |___|  /\___  >   |___|  /____/|__|_|  /___  /\___  >__|   
        \/            \/     \/     \/               \/     \/         \/            \/    \/     \/       

"""
HARD_LEVEL_TURNS = 5
EASY_LEVEL_TURNS = 10



#4 create a function to check user's guess against the answer:(#11 track the number of turns and reduce it by 1)
def check(guess,answer,turns):
    if guess > answer:
        print("You guessed too high! ")
        return turns - 1
    elif guess < answer:
        print("You guessed too low! ")
        return turns - 1
    else:
        print(f"You got it right. The answer was {answer}")
#5 make a function to check difficulty:
def set_difficulty():
    level = input("Chose a difficulty: Type 'easy' or 'hard': ")
    if level == "easy":
        return EASY_LEVEL_TURNS
    else:
        return HARD_LEVEL_TURNS

#10 create a game function :
#2
def game():
    print(logo)
    print("Welcome to the number guessing game. ")
    print("I'm guessing a number between 1 and 100 ")
    answer = random.randint(1,100)

    
    turns = set_difficulty()
    #13 shifting (print(f"You have {turns} attempts remaining to guess the number. "))inside the while loop below

    #9 create a global variable of guess 
    guess = 0
    while guess != answer:
        print(f"You have {turns} attempts remaining to guess the number. ")
    #3 let the user guess a number:
        guess = int(input("Guess any number between 1 to 100: ")) 

    #8 calling the check function:(#12 updating a local variable namely turns)
        turns = check(guess,answer,turns)
        #13 telling the user that they have ran out of the guesses 
        if turns == 0:
            print("You have ran out of the guess. Game Over! ")
            return

game()




