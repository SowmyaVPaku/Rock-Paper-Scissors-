# GUI-based version of RPSLS

###################################################
# Student should add code where relevant to the following.

import simplegui
import random

# Functions that compute RPSLS
def name_to_number(name):
    if name == "rock":
        return 0
    elif name == "Spock":
        return 1
    elif name == "paper":
        return 2
    elif name=="lizard":
        return 3
    elif name == "scissors":
        return 4
    else:
        return "Error: Invalid Name."
        
    


def number_to_name(number):
    if number == 0:
        return "rock"
    elif number == 1:
        return "Spock"
    elif number == 2:
        return "paper"
    elif number == 3:
        return "lizard"
    elif number == 4:
        return "scissors"
    else:
        return "Error:Invalid Number"
        
    
     
    
# Handler for input field
def get_guess(guess):
    print "Player chose " + guess
    player_guess = name_to_number(guess)
    
    comp_guess = random.randint(0,4)
    computer_guess = int(comp_guess)
    rand = number_to_name(computer_guess)
    print "Computer chose " + rand
    if player_guess <= 4 and computer_guess <= 4:
        play(player_guess, computer_guess)
    else:
        print "Error: Bad input " + guess + " to rpsls"
        
def play(player_guess, computer_guess):
    if player_guess - computer_guess ==1 or player_guess - computer_guess == 2:
        print "Player Wins"
    elif player_guess - computer_guess or player_guess - computer_guess == 4:
        print "Computer Wins"
    else:
        print "Error: Bad input " + guess + " to rpsls"
    
    
    


# Create frame and assign callbacks to event handlers
frame = simplegui.create_frame("GUI-based RPSLS", 200, 200)
frame.add_input("Enter guess for RPSLS", get_guess, 200)


# Start the frame animation
frame.start()


###################################################
# Test

get_guess("Spock")
get_guess("dynamite")
get_guess("paper")
get_guess("lazer")

###################################################
# Sample expected output from test
# Note that computer's choices may vary from this sample.

#Player chose Spock
#Computer chose paper
#Computer wins!
#
#Error: Bad input "dynamite" to rpsls
#
#Player chose paper
#Computer chose scissors
#Computer wins!
#
#Error: Bad input "lazer" to rpsls
#
