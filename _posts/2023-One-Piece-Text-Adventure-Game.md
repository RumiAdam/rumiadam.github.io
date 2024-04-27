---
title: "One Piece: Text Adventure"
date: 2023-10-21
tags: [python, user-input, game development, text adventure]
header:
  image: "/images/onepiece.jpg"
excerpt: "An interactive text game in Python with random plot twists and survival challenges. It's like a choose-your-own-adventure game where you need courage and a bit of survival knowledge, especially for a zombie apocalypse scenario. Created using Jupyter Notebooks."
mathjax: "true"
---

## The Game
In an era where wealth, fame, and power echoed across the seas, one man's declaration resonated above all, the Pirate King, Gold Roger. As he stood tall on the scaffold, facing the inevitable, his parting words ignited a fervor that would shape the destiny of countless adventurers. 'My treasure? It's yours if you want it. Find it! I left all the world has at that place!' With those words, the Grand Line became the focal point of dreams and aspirations, a vast and treacherous sea promising untold treasures and unimaginable challenges. Gold Roger's execution marked the beginning of a new age: the Great Pirate Era. As the news of his final utterance spread like wildfire, a surge of pirates, young and old, set sail, driven by the desire to claim the greatest treasure of them all: the One Piece. In the wake of this declaration, you, a spirited young pirate, stand at the crossroads of destiny. The choices made in the pursuit of your dreams will echo through the corridors of time. Will you seize the opportunity, face the challenges of the Grand Line, and uncover the mysteries of Gold Roger's legacy? The journey is yours to embark upon, the seas are yours to navigate, and the fabled One Piece awaits those who dare to dream. This is the dawn of your Grand Line Quest!

As the protagonist of this immersive text adventure game, you step into the worn boots of a young and ambitious pirate. Your journey commences with the news of the Pirate King Gold Roger's demise, a legend whose execution sparked a new era of piracy. The world is abuzz with excitement and trepidation as countless dreamers set sail in pursuit of the ultimate treasure: the One Piece.

Haunted by the shadows of Gold Roger's last words, your character is gripped by a potent mix of grief and determination. The Pirate King's enigmatic declaration echoes in your ears:

"My treasure? It's yours if you want it. Find it! I left all the world has there!"

Fueled by the call to adventure, you embark on a quest that will navigate the perilous waters of the Grand Line. The weight of Gold Roger's legacy rests on your shoulders, motivating you to explore uncharted territories, face formidable foes, and uncover the mysteries based on the One Piece story Source: (Oda, E. 1997-present. One Piece. Shueisha).

The game is composed of 3 main stages and 2 transition stages

Stage 1: East Blue - "Choosing the Legacy" Introduction to the Grand Line Quest Devil Fruit choice and initial challenges in East Blue

Stage 2: Vast Horizons - "Navigating Ambitions" Set sail into the Grand Line Ship navigation challenges

Stage 3: Island of Alabasta - "Quest for the Log Pose" Explore Alabasta to find the rare Log Pose

Stage 4: Skypiea - "Above the Clouds" Ascend to Skypiea

Stage 5: Ancient Archives - "Island of the Gods" Explore Skypiea beat the final boss, and unveil the first Road Poneglyph

## Instructions

To run the game, I suggest copy-pasting the following code block into a Jupyter Notebook code cell.
Then, you only need to run the cell to start the game and follow the printed commands!

```python

"""
My idea for this game would be closer to an actual game than just a text adventure 
I first design the game and stages on paper with several what-if scenarios.
"""

##############################################################################

#import library for the game
import random

# include border for user interface
def print_border(text, border_char, border_length):
    border = border_char * border_length
    print(border)
    print(text)
    print(border)
    
# key to start the game and continue to the next steps during the game
def press_enter_to_continue():
    input("\n")

#Game tips or guide
input("> Press Enter to start your Adventure!")
input("> Some tips before starting:")
input("> Press Enter when you see blank cells throughout the game to continue progressively")
input("> Or interact and answer to the different questions/mini-game to progress")
input("> Don't forget to scroll down to read all the text before pressing any key")
    
#Stage 1 intro 
def stage_1():
    print_border("Stage 1: East Blue - Choosing the Legacy", border_char="<>", border_length=50)
    print("Introduction:")
    print("As a young and aspiring pirate, you find yourself standing at the crossroads of destiny,")
    print("driven by the profound words of Gold Roger echoing in your mind.") 
    print("The vastness of the East Blue, a region known for its mystery and danger, beckons you to make a pivotal choice.")
    print("In this stage, you must decide which Devil Fruit to consume, as it will shape the course of your adventure—granting")
    print("unique powers that will aid you on your quest for the One Piece.")
    
    press_enter_to_continue()
    
    #character intro
    print("\n Welcome Pirate! Please chose your character's name")
    players_name = input()
    

    print(f"Alright ! {players_name} here are your stats:")
    
    #introduction of points for the character similar to RPG game
    players_health = 100
    players_strenght = 25
    players_magic = 0
    print(f"{'<>' * 50}")
    print(f"health:  {players_health}")
    print(f"strenght:{players_strenght}")
    print(f"magic:   {players_magic}")
    print(f"{'<>' * 50}")
    return players_name
#Call the introduction
players_name = stage_1()


#Stage 1 start with the choice between devil fruit/powers

def merchant(players_name):
    press_enter_to_continue()
    print(f"{players_name} exited by the prospect of starting the adventure,")
    print("walks through Foosha villages and towards a bustling port town,")
    print("a melting pot of dreams where the salty breeze carries the whispers of adventure.")
    
    press_enter_to_continue()
    print(f"Near the port, a mysterious merchant materializes. Intrigued by this mysterious entity, {players_name} approaches.")
    print("The enigmatic figure extends an offer—a choice between three Devil Fruits to aid during your journey.")
    print("The merchant provides a glimpse into the powers of each:")
    
    press_enter_to_continue()
    print("Do you want to know more about the devil fruits?")
    answer_1 = input(" ")
    if answer_1 in ["Yes","yes","y","Y"]:
        print(f"""
        •	Gomu Gomu no Mi (Rubber-Rubber Fruit):
        Grants the power of elasticity, allowing the user to stretch and contort.
        Enhanced melee combat skills.

        •	Mera Mera no Mi (Flame-Flame Fruit):
        Bestows the power to manipulate and become fire, offering magic ranged attacks.

        •	Kira Kira no Mi (Diamond-Diamond Fruit):
         Paramecia-type Devil Fruit that transforms the user's body into diamond.
        Provides unparalleled strength, durability, and defensive capabilities.""")
        press_enter_to_continue()
        
        print("Mysterious merchant:once a fruit is chosen, there's no turning back.")
        print("The powers bestowed come at the cost of never being able to swim again.")
        
    elif answer_1 in ["No", "no", "n","N"]:
            print("Merchant: You won't last 1 min on Grand Line without a Devil Fruit!")
            print("Are you sure?")
            answer_2 = input("> ")
            if answer_2 in ["Yes","yes","y","Y"]:
                print("You seem to be lost young pirate! let me help you!")
                print("Here are the Devil Fruit available:")
                print(f"""
                    •	Gomu Gomu no Mi (Rubber-Rubber Fruit):
                    Grants the power of elasticity, allowing the user to stretch and contort.
                    Enhanced melee combat skills.

                    •	Mera Mera no Mi (Flame-Flame Fruit):
                    Bestows the power to manipulate and become fire, offering magic ranged attacks.

                    •	Kira Kira no Mi (Diamond-Diamond Fruit):
                     Paramecia-type Devil Fruit that transforms the user's body into diamond.
                    Provides unparalleled strength, durability, and defensive capabilities.""")
                press_enter_to_continue()
                print("Mysterious merchant:once a fruit is chosen, there's no turning back.")
                print("The powers bestowed come at the cost of never being able to swim again.")
                
            else:
                    print("You seem to be lost young pirate! let me help you!")
                    print("Here are the Devil Fruit available:")
                    print(f"""
                        •	Gomu Gomu no Mi (Rubber-Rubber Fruit):
                    Grants the power of elasticity, allowing the user to stretch and contort.
                    Enhanced melee combat skills.

                    •	Mera Mera no Mi (Flame-Flame Fruit):
                    Bestows the power to manipulate and become fire, offering magic ranged attacks.

                    •	Kira Kira no Mi (Diamond-Diamond Fruit):
                     Paramecia-type Devil Fruit that transforms the user's body into diamond.
                    Provides unparalleled strength, durability, and defensive capabilities.""")
                    press_enter_to_continue()
                    
                    print("Mysterious merchant:once a fruit is chosen, there's no turning back.")
                    print("The powers bestowed come at the cost of never being able to swim again.")  
                
    #here pushing the player to select a power. The first idea was also to continue without power,
    #and face an opponent in stage 1 with a 100% chance to loose and return back to the merchant.
    #the game would have been too long and complex 
    else:
            print("You seem to be lost young pirate! let me help you!")
            print("Here are the Devil Fruit available:")
            print(f"""
                    •	Gomu Gomu no Mi (Rubber-Rubber Fruit):
                Grants the power of elasticity, allowing the user to stretch and contort.
                Enhanced melee combat skills.

                    •	Mera Mera no Mi (Flame-Flame Fruit):
                Bestows the power to manipulate and become fire, offering magic ranged attacks.

                    •	Kira Kira no Mi (Diamond-Diamond Fruit):
                Paramecia-type Devil Fruit that transforms the user's body into diamond.
                Provides unparalleled strength, durability, and defensive capabilities.""")

            press_enter_to_continue()
            print("Mysterious merchant:once a fruit is chosen, there's no turning back.")
            print("The powers bestowed come at the cost of never being able to swim again.")
    press_enter_to_continue()
    
# Call the merchant function
merchant(players_name)
#function for the devil fruit selection
def devil_fruit_selection():
    # Player's initial stats
    players_health = 100
    players_strength = 25
    players_magic = 0

    devil_fruits = {
        1: {"name": "Gomu Gomu no Mi", "power": "Stretchable body and enhanced physical abilities", "stat_bonus": "strength"},
        2: {"name": "Mera Mera no Mi", "power": "Control over fire and generation of flames", "stat_bonus": "magic"},
        3: {"name": "Kira Kira no Mi", "power": "Invisibility and intangibility", "stat_bonus": "health"}}
    

    print("\nChoose your Devil Fruit:")
    for number, fruit in devil_fruits.items():
        print(f"{number}. {fruit['name']} - {fruit['power']}")

    while True:
        try:
            choice = int(input("\nEnter the number of your chosen Devil Fruit: "))
            if choice in devil_fruits:
                selected_fruit = devil_fruits[choice]
                print(f"\nYou have chosen the {selected_fruit['name']}!")
                print(f"Your new power: {selected_fruit['power']}")
                print("""⠀⠀⠀⠀⠀⠀⠀⠀⣀⡀⠀⠀⠀⠀⠀⠀
⣠⡄⠀⠀⣀⡴⠞⠉⢉⡇⠀⠀⠀⠀⠀⠀
⢯⣠⡴⠟⠋⣙⣦⡠⢤⡀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⢠⠖⣪⠍⠉⡏⡽⡟⡶⡄⠀⠀⠀
⠀⠀⢸⡇⡖⣧⠰⢲⢈⠏⣁⠀⣙⡿⡄⠀
⠀⠀⣼⣗⠓⢩⠉⣁⡀⢓⢚⣹⢀⣿⡇⠀
⠀⠀⣿⣿⢱⡯⡈⣡⠃⣧⡦⡦⣹⢹⡿⠀
⠀⠀⢹⣿⣬⡥⣞⣓⡷⣇⢛⣱⢿⣡⡇⠀
⠀⠀⠀⠙⢿⣿⣿⣿⣿⣿⣵⡶⣿⠏⠀⠀
⠀⠀⠀⠀⠀⠀⠙⠋⠛⠛⠛⠋⠁⠀⠀⠀""")

                # Update the specified stat based on the Devil Fruit choice
                if selected_fruit['stat_bonus'] == "strength":
                    players_strength += 50
                elif selected_fruit['stat_bonus'] == "magic":
                    players_magic += 100
                elif selected_fruit['stat_bonus'] == "health":
                    players_health += 50

                # Display updated stats based on choice
                
                print(f"\nUpdated Stats:")
                print(f"{'<>' * 50}")
                print(f"Health: {players_health}")
                print(f"Strength: {players_strength}")
                print(f"Magic: {players_magic}")
                print(f"{'<>' * 50}")
                break
            else:
                print("Invalid choice. Please enter a valid number.")
        except ValueError:
            print("Invalid input. Please enter a number.")

# Call the Devil Fruit selection function
devil_fruit_selection()
press_enter_to_continue()

print("After testing your new powers, you walk to the port to meet Nami the navigator,")
print("and set sail and begin his journey with his newly aquired power!")
print(f"{'<>' * 50}")

#start of stage 2
def stage_2(players_name):
    press_enter_to_continue()
    print_border("Stage 2: Vast Horizons - Navigating Ambitions", border_char="69", border_length=40)
    print("With newfound powers and the ambition to find the legendary One Piece,")
    print(f"{players_name} sets sail on a small ship, navigating the vast and unpredictable seas.")

    print("Nami mentioned a mysterious object which will help you in finding the one piece,")
    print("it is located at Alabasta !")
    press_enter_to_continue()
    print("Nami ask you which road to take to go to Alabasta? do you want to choose Calm Belt or Red Line?")
    press_enter_to_continue()
    
    # Offer the player a choice between two paths, with the harder path leading to a game
    print("\nChoose your path:")
    print("1. Sail through the Calm Belt (Easier)")
    print("2. Navigate the Red Line (Harder)")
    print(f"{'69' * 50}")
    
    path_choice = input("Enter the number of your chosen path: ")
    
    if path_choice == "1":
        print("\nYou decide to sail through the Calm Belt, expecting an easier journey.")
        print("The calm and serene seas of the Calm Belt carry you smoothly to your destination.")
        print("Congratulations! You reached your destination.")
    elif path_choice == "2":
        print("\nYou bravely choose to navigate the Red Line, anticipating a more challenging route.")
        # Call the Ship Navigation Challenge for the Red Line
        ship_navigation_challenge()
    #forcing the player to chose the easier path if we chose != 1 or 2
    else:
        print("You had too many beer on the ship captain! better take the Calm Belt")
        press_enter_to_continue()
        print("The calm and serene seas of the Calm Belt carry you smoothly to your destination.")
        print("Congratulations! You reached your destination.")
# mini game during the boat trip
def ship_navigation_challenge():
    print("Welcome to the Ship Navigation Challenge!")
    print("Navigate your ship through the treacherous waters and overcome obstacles.")

    # Set initial variables
    player_position = 0
    obstacles = ["Storm", "Sea Creature", "Rival Pirate Ship"]

    while True:
        print("\nCurrent Position:", player_position)
        print("1. Sail Forward")
        print("2. Maneuver Left")
        print("3. Maneuver Right")
        print("4. Quit")

        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            player_position += random.randint(2, 5)
            print(f"{'69' * 50}")
        elif choice == "2":
            player_position -= random.randint(2, 3)
        elif choice == "3":
            player_position += random.randint(2, 3)
        elif choice == "4":
            print("Quitting Ship Navigation Challenge.")
            break
        else:
            print("We will never reach Alabasta! Please enter a number between 1 and 3, or 4 to quit the mini-game.")

        # Generate a random obstacle
        obstacle = random.choice(obstacles)

        # Check for obstacles, but no game over path here if they loose the game. it's only easier or harder navigation
        if obstacle == "Storm":
            print("You encountered a storm! Navigate carefully.")
            player_position -= 1
        elif obstacle == "Sea Creature":
            print("A sea creature approaches! Maneuver to avoid it.")
            player_position -= 1
        elif obstacle == "Rival Pirate Ship":
            print("A rival pirate ship is spotted! Engage in a ship battle.")
            player_position -= 1

        # Check if the player reaches the destination
        if player_position >= 10:
            print("Congratulations! You reached your destination.")
            break
    
# Call the stage 2 function
stage_2(players_name)

#Stage 3
def stage_3(players_name):
    press_enter_to_continue()
    print_border("Stage 3: Island of Alabasta - Quest for the Log Pose", border_char="*", border_length=60)
    print(f"\nAfter navigating through the seas, {players_name} arrives at an unfamiliar island.")
    print("The air is thick with mystery as you explore, and rumors circulate about a rare tool called the Log Pose,")
    print("capable of pointing to the elusive One Piece.Rumors swirl of an ancient temple housing the rare Log Pose.")
    press_enter_to_continue()
    print("Explore the the area nearby to find more information about this ancient temple")
    press_enter_to_continue()
    while True:
        print("\n Options:")
        print("1. Explore the Port")
        print("2. Visit the City")
        print(f"{'*' * 50}")
        #choice for exploration to the player
        choice = input("Enter your choice (1-2): ")

        if choice == "1":
            print(f"{'*' * 50}")
            print("You explore the bustling port, talking to sailors and traders.But no clue")
            print("2. Visit the City")
            choice = input("Enter your choice (2): ")
            if choice == "2":
                print(f"{'*' * 50}")
                print("You wander through the city, listening to the locals' stories.")
                print("You overhead a conversation between two locals and learned about the location of the temple!")
                print("The Log pose sould be located in the oldest temple deep inside the forest")
                break
            else:
                print(f"{'*' * 50}")
                print("There is only the city left to find clues, let's ask the people in the city")
                press_enter_to_continue()
                print("You wander through the city, listening to the locals' stories.")
                print("You overhead a conversation between two locals and learned about the location of the temple!")
                print("The Log pose sould be located in the oldest temple deep inside the forest")
                break
                    
        elif choice == "2":
            print(f"{'*' * 50}")
            print("You wander through the city, listening to the locals' stories.")
            print("You overhead a conversation between two locals and learned about the location of the temple!")
            print("The Log pose sould be located in the oldest temple deep inside the forest")
            break
            
        else:
            print("Invalid choice. Please enter a number between 1 and 2.")

    press_enter_to_continue()
    print("Congratulations! You have found a clue about the Log Pose's location.")
    print("Let's head to the Forest and the ancient temple.")
    press_enter_to_continue()
    print("After few hours, you reach the temple and start exploring!")
    press_enter_to_continue()
    print("As you enter the temple, you notice an unusually shaped set of rocks along one wall.")
    print("Upon closer inspection, you discover a concealed door.")
    print("The door is adorned with three rock cylinders, each marked with numbers from 1 to 9.")
    print("It seems to be a combination lock, and you deduce that aligning the numbers correctly will unlock the door.")
    press_enter_to_continue()
    print("let's try to unlock this door, the log pose is certainly behind!")
    print(f"{'*' * 70}")
    
    press_enter_to_continue()
    lock_combination = [random.randint(1, 9), random.randint(1, 9), random.randint(1, 9)]
    

    # mini game to unlock the door - the first idea for this game was to guess each code
    #having a sound as hint: the closer the number, the louder the sound/volume of the click
    #i had to import pygame library for game immersion, as only the text of volume+number is not fun
    #then I dicided to continue with a more simpler lock game (difficult to guess but with a hint)
    attempts = 3
    while attempts > 0:
        print(f"\nYou have {attempts} attempts left.")
        try:
            entered_combination = [int(input("Rotate the first cylinder to align the 1st number: ")),
                                   int(input("Rotate the second cylinder to align the 2nd number: ")),
                                   int(input("Rotate the third cylinder to align the 3rd number: "))]
            
            if all(1 <= num <= 9 for num in entered_combination):
                if entered_combination == lock_combination:
                    print(f"{'*' * 60}")
                    print("The rock cylinders click into place. The door swings open, revealing a hidden chamber!")
                    break
        
                else:
                    print(f"{'*' * 50}")
                    print("The lock resists your attempt. Try rotating the cylinders to align the numbers correctly.")
                    attempts -= 1
    
                if attempts == 1:
                    press_enter_to_continue()
                    print(f"{players_name}! Nami is showing you a shiny object at the foot of one of the stone pillar in the room")
                    print("There seem to be numbers written on it...")
                    press_enter_to_continue()
                    print(f"......{lock_combination}")
                    press_enter_to_continue()
                    print("this objects seems to have been place here recently! let's be carefull")
            
                if attempts == 0:
                    print("You've run out of attempts. The door remains locked. We should have tried the code on the shiny object!")
                    press_enter_to_continue()
                    print(f"{players_name} use his devil fruit power to break the door... and succeed!")
                    break
        except ValueError:
            print("You are locking the door!!! Please enter a number between 1-9.")
            print(f"{'*' * 60}")
            attempts -= 1
            if attempts == 1:
                press_enter_to_continue()
                print(f"{players_name}! Nami is showing you a shiny object at the foot of one of the stone pillar in the room")
                print("There seem to be numbers written on it...")
                press_enter_to_continue()
                print(f"......{lock_combination}")
                press_enter_to_continue()
                print("this objects seems to have been place here recently! let's be carefull")
            if attempts == 0:
                print("You've run out of attempts.")
                print("The door remains locked. We should have tried the code on the shiny object!")
                print(f"{'*' * 70}")
                press_enter_to_continue()
                print(f"{players_name} use his devil fruit power to break the door... and succeed!")
                break
        
    press_enter_to_continue()
    print(f"Nami and {players_name} discover the log pose inside the chamber")
    
    print("The Log Pose is akin to a compass, featuring an arrow within a sphere, also indicating altitude.") 
    print("To their surprise, the Log Pose pointer points directly to the sky!")
    print("At this moment, a resonant voice echoes within the sacred halls of the temple: 'This is Skypiea, my nakama!")
    press_enter_to_continue()
    print("The crew is greeted by a new member, Usopp the sniper,")
    print("who, like them, was in search of the Log Pose and is eager to join their crew.")
    press_enter_to_continue()
    print("Armed with the Log Pose, the crew sets sail once again,")
    print("following its mystical guidance toward the sky-bound realm of Skypiea")
    print(f"{'*' * 80}")
# Call the stage 3 function
stage_3(players_name) 

#stage 4 intro
def stage_4():
    print_border("Stage 4: Skypiea - Above the Clouds", border_char="V", border_length=40)
    print("\nAfter recruiting Usopp, the crew learns that reaching Skypiea requires navigating a unique and powerful phenomenon known as the Knock Up Stream.")
    print("With the ship upgraded for this daring adventure, the crew sets sail to the area where the Knock Up Stream is known to occur.")
    press_enter_to_continue()
    print("As the crew arrives at the stream location, they notice four distinct areas, forming a square, from which the stream emanates.")
    print("The crew observes a particular pattern in the sequence of the Knock Up Stream.")
    print("The team realizes that there is a 15-min interval between each stream.")
    press_enter_to_continue()
    print("The crew is relying on you to position the ship correctly.")
    print(f"{'V' * 50}")
    press_enter_to_continue()
    # Define the knock up stream sequence mini game
    stream_sequence = [1, 4, 3, 2, 1]
    print("the observed pattern: ")
    print(stream_sequence)
          
    # the last observed stream here is set, could have also use random between 1-4
    press_enter_to_continue()
    print("last_observed_stream = 3")
    print(f"{'V' * 50}")
    # Calculate the next stream in the sequence
    next_stream = 2
    # Prompt the player for their guess
    print("Guess the next direction to catch the Knock Up Stream:")
    print("1. Upper Left")
    print("2. Upper Right")
    print("3. Lower Left")
    print("4. Lower Right")
    attempts = 1
    while attempts > 0:
        try:
            player_guess = int(input("Enter your guess (1-4): "))

    # Check if the guess is correct. Here I wanted to incorporate a penalty if guess is wrong according to the waiting time
    # the waiting time would have diminish the character stamina/health, giving him a disadventage for the final boss fight
    #if he guesses right, he arrives in stage 5 early and meet someone there who give him an item usefull for the final fight
    # but i chose to go to a simpler game mechanics
    
            if player_guess == next_stream:
                print("Congratulations! You positioned the ship correctly.")
                print("The crew catches the Knock Up Stream, expediting the journey to Skypiea.")
                attempts -= 1
            else:
                if player_guess == 4:
                    waiting_time = "15min"
                    print(f"The crew will have to wait {waiting_time} for the next opportunity to catch the Knock Up Stream.")
                    attempts -= 1
                    break
                elif player_guess == 3:
                    waiting_time = "30min"
                    print(f"The crew will have to wait {waiting_time} for the next opportunity to catch the Knock Up Stream.")
                    attempts -= 1
                elif player_guess == 2:
                    waiting_time ="45min"
                    print(f"The crew will have to wait {waiting_time} for the next opportunity to catch the Knock Up Stream.")
                    attempts -= 1
                else:
                    print("there is no stream in this direction")
                    attempts -= 1
        except ValueError:
            print("Enter a valid number between 1 and 4")
        
press_enter_to_continue()

#Call the stage 4 function
stage_4()  

#Final stage: stage 5

def stage_5(players_name):
    press_enter_to_continue()
    print_border("Stage 5: Ancient Archives - Island of the Gods", border_char="=", border_length=60)
    print("\nThe ship docks on Skypiea's ethereal shores, surrounded by towering structures and divine monuments supported by clouds.")
    print("The air is filled with a sense of reverence as the crew steps onto the sacred grounds of the Island of the Gods.")
    print("The crew starts to explore skypiea and look for any sign of the One Piece...")
    print(f"{'=' * 120}")
    press_enter_to_continue()
    print("\n Options: ")
    print("1. Explore the ancient library")
    print("2. Walk around the garden of Enel")
    print(f"{'=' * 50}")
    choice = input("Enter your choice (1-2): ")

    if choice == "1" or choice == "2":
            print("While walking, Usopp, using his sniper goggles, notices a huge shiny object!")
            print("It looks like a massive golden cube with ancient engravings on it!")
            press_enter_to_continue()
    else:
            print("Lightning strike nearby! KAAABOOOOM!")
            print("Usopp takes out his sniper binoculars and looks in that direction.")
            press_enter_to_continue()
            print("He sees a colossal golden cube with ancient engravings on it!")
    
    print("They all shouted at once: THE ONE PIECE?!?!?!")
    press_enter_to_continue()
    print("Let's go and check!")
    press_enter_to_continue()
    print(f"As {players_name} and the crew approach the golden cube, a powerful figure descends before them.")
    print("The sky crackles with energy as Enel, the guardian of the treasure, stands before them.")
    press_enter_to_continue()
    print("Enel: Who dares to approach the sacred cube? Identify yourselves, intruders!")
    print("The crew exchanges determined glances, ready for the final challenge.")
    print(f"{'=' * 50}")
    
    # Give the player a choice to talk or fight, but in the end forcing the player to the final fight
    print("\nOptions:")
    print("1. Convince Enel to let you explore the cube peacefully.")
    print("2. Prepare for battle against Enel.")
    print(f"{'=' * 50}")

    choice = input("Enter your choice (1-2): ")

    if choice == "1":
        print(f"{players_name} attempts to reason with Enel, explaining their quest for the One Piece and peaceful intentions.")
        print("Enel seems unmoved, demanding their departure.")
        print("What will you do next?")
        print(f"{'=' * 50}")
        
        # Give the player another choice
        print("\nOptions:")
        print("1. Persist in convincing Enel.")
        print("2. Prepare for battle against Enel.")
        print(f"{'=' * 50}")

        choice = input("Enter your choice (1-2): ")

        if choice == "1":
            print(f"{players_name} continues to plead, hoping to find common ground with Enel.")
            print("Enel remains stern, unwilling to allow any further approach to the cube.")
            print("The crew faces a difficult decision but is ready to fight")
            final_battle()
            
        elif choice == "2":
            print(f"{players_name} and the crew prepare for battle against Enel.")
            print("A fierce clash ensues, with Enel using powerful lightning-based attacks.")
            final_battle()
        else:
            print("Invalid choice. Enel's patience wears thin, and the crew faces consequences.")
            final_battle()

    elif choice == "2":
        print(f"{players_name} and the crew brace themselves for battle against Enel.")
        print("Enel, sensing their determination, readies himself for the confrontation.")
        print("A fierce clash ensues, with Enel using powerful lightning-based attacks.")
        final_battle()
        
        
    else:
        print("Invalid choice. Enel senses a threat and start the final battle.")
        final_battle()
        # implement battle

def final_battle():
    #for this final fight, the initial idea was based on the devil fruit choice, the attacks would have been specific
    #if the player choose the first devil fruit - rubber power, he would have been nearly immunise to electrical attack for example
    #each different attach would have had a random range and the player could have chose which attach with a probability to hit critical
    #but the mechanics was changed due to time and not enough python practice.
    #Enel Stats
    enel_health = 1000
    enel_strength = 10
    enel_magic = 100
    
    #players stats
    players_health = 300  
    players_strength = 100
    players_magic = 100
    
    # Player's attacks
    player_attacks = ["GOMU GOMU NO RED HAWK!!! (Critical Hit)","DIAMOND SHIELD","MERA MERA NO JET PISTOL"]
    
    # Enel's attacks
    enel_attacks = ["EL THOR!!! (Critical Hit)", "RAIGO", "GORO GORO NO MO LIGHTING BOLT"]
    
    print(f"\nFinal Battle against Enel begins!")
    
    # Create dictionaries to map attacks to values
    player_attack_ranges = {
    "GOMU GOMU NO RED HAWK!!! (Critical Hit)": (400, 500),
    "DIAMOND SHIELD": (100, 200),
    "MERA MERA NO JET PISTOL": (200, 400)}

    enel_attack_ranges = {
    "EL THOR!!! (Critical Hit)": (50, 100),
    "RAIGO": (30, 100),
    "GORO GORO NO MO LIGHTING BOLT": (20, 100)}
    
    # Create dictionaries to store attack values
    player_attack_values = {attack: random.randint(*player_attack_ranges[attack]) for attack in player_attacks}
    enel_attack_values = {attack: random.randint(*enel_attack_ranges[attack]) for attack in enel_attacks}
    
    #number of round
    round = 0
    # Battle until one reach health = 0
    while players_health >0 or enel_health >0:
        round += 1
        print(f"{'=' * 50}")
        print(f"round:{round}")
        # Player's turn
        player_attack = random.choice(player_attacks)
        player_damage = player_attack_values[player_attack]
        enel_health -= player_damage
        print(f"{players_name} attacks Enel with {player_attack} and deals {player_damage} damage. Enel's health: {enel_health}")

        # Check if Enel's health is zero or negative
        if enel_health <= 0:
            print("Congratulations! Enel has been defeated.")
            print(f"{'=' * 50}")
            press_enter_to_continue()
            print("As they beat Enel, the crew approaches the One Piece...")
            press_enter_to_continue()
            print("Enel with his last words laughing at the crew: BAKAAA, this is not the ONE PIECE,")
            print("it’s only part of the treasure, 1 out of the 4 road poneglyph!")
            press_enter_to_continue()
            print("Road Poneglyph Revelation:The culmination of the stage revolves around the revelation of the first Road Poneglyph's location.")
            print("The crew inspect the celestial clues obtained from skypia, unveiling the path leading to the next part of the Grand Line.")         
            print("The Log Pose reacts, guiding the crew toward a distant and uncharted destination.")
            print(f"{'=' * 120}")
            press_enter_to_continue()
            print("As the crew sets sail once again, the mysteries of the Ancient Archives linger in their minds.")
            print("The journey continues into the unexplored territories of the Grand Line,")        
            print("propelled by the desire to uncover the remaining Road Poneglyphs and reach the legendary One Piece.")        
            adventure_win()
            break

        # Enel's turn
        enel_attack = random.choice(enel_attacks)
        enel_damage = enel_attack_values[enel_attack]
        players_health -= enel_damage
        print(f"Enel counterattacks with {enel_attack} and deals {enel_damage} damage. {players_name}'s health: {players_health}")
        print(f"{'=' * 50}")
        press_enter_to_continue()
        
        # Check if players health is zero or negative
        if players_health <= 0:
            print(f"Oh no!You have been defeated.")
            print("Enel last attack has pushed you out of skypia! and free fall to the sea")
            game_over()
            break
        

#introduction of ACCII chart for the end of the game     
def adventure_win():
    print("""⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣠⡴⠚⢉⡃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣉⠛⠻⢶⢦⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠖⢫⢗⣴⡿⣻⠟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠑⢰⣜⣎⣎⠷⢄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⠞⢁⣴⢣⣫⠌⣽⢃⣀⡤⠤⠀⠀⠀⠀⠀⠀⠀⠤⠤⠤⢤⣀⣠⡟⣟⣘⠘⡆⠑⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠂⠀⡴⠃⣰⡿⣴⡧⠷⠚⠉⠁⣀⣠⠤⢤⣒⣒⣂⣀⣠⣠⣄⣠⣤⣶⣿⡟⠙⠻⢼⣾⡞⡆⠈⣷⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡜⢁⣾⠟⠋⠙⣿⣶⣶⣶⣷⣶⣶⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣶⣶⣦⣤⣌⣙⠿⣕⡀⠿⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣎⠴⠋⠀⣠⠔⣢⣼⣿⣿⣿⣿⣿⡿⠉⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡿⠟⠛⢫⡙⠈⠳⣄⢻⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⡄⠀⠀⣠⠞⠁⢀⡤⣚⣵⣿⣿⣿⣿⣿⣿⣿⠏⠀⠀⠀⢻⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣦⣄⠈⠲⣄⠈⣳⣇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⢿⣶⣴⣉⣀⣴⣫⣾⣿⣿⣿⣿⣿⡟⣿⣿⠋⠀⠀⠀⠀⠀⢿⣿⣿⣿⣿⠘⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣆⡈⢧⡈⢙⣆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡟⢸⣿⠇⠀⠀⠀⠀⠀⠀⠀⢻⣿⣿⣿⠀⠘⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡀⠙⣄⠹⣦⡀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⠋⠀⡙⣿⣿⣿⣿⣿⣿⣿⣿⣿⠀⣸⣟⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⠀⠀⠘⣿⣿⣿⡿⣿⣿⣿⣿⣿⣿⡟⢿⡜⣎⢦⠙⣷⡀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⡼⠃⢠⣯⣾⣿⣿⣿⣿⣿⣿⣿⣿⠁⠀⣻⡧⣀⠀⠀⠀⠀⠀⠀⠀⠀⠸⣿⣿⢀⣤⠶⢻⣿⣿⡷⢿⣿⣿⣿⣿⣿⣿⣴⡿⡜⣾⡇⠈⣷⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⣼⠁⢠⣿⣿⠟⠋⣽⣿⣿⣿⣿⣿⣧⠶⠚⢻⡏⠛⠲⢦⣀⠀⠀⣠⠀⠀⠀⢿⣿⠋⠀⠀⠸⣿⣿⠀⢸⣿⣿⣿⣿⣿⣿⣿⡅⠙⠀⠘⣄⠙⣧⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⠃⠀⣼⡟⠁⠀⣠⣿⣿⣿⣿⣿⣿⠁⠀⠀⠈⢇⠀⠀⠉⠈⠑⠀⠙⢦⠀⠀⢸⡏⠀⢀⣠⣶⣿⠇⠀⠀⣿⣿⣿⣿⣿⣿⣿⣿⣄⠀⠀⢸⠀⠸⡇⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⠀⠀⡇⠁⠄⣰⣿⣿⣿⣿⣿⣿⣇⠀⠀⠠⣄⣿⣶⣦⣄⡄⠀⠀⢄⣿⠆⠀⠘⠃⣰⣿⣷⡿⠿⠶⣦⡀⣿⣿⢻⣿⣿⣿⣿⡝⠻⣦⣠⠀⠇⠀⢳⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⠇⠀⢁⣴⡾⠿⢻⣿⣿⣿⣿⣿⣿⠀⣠⣾⠟⠉⠠⠶⠛⠇⠀⠀⣿⠁⠀⠀⠀⠈⠛⣙⣉⣉⣀⣠⡴⠛⣿⡏⣿⣿⣿⣿⣿⡇⠀⠀⠙⠈⢡⠀⣼⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⡖⣾⠄⠀⠀⠀⠀⠀⣿⣿⣿⣿⣿⣟⢿⡇⠀⠁⠀⠀⠀⠀⠀⠀⠀⠀⠉⠣⠘⠂⠀⣀⣐⣀⣈⣁⡤⠤⠷⠶⣟⠀⣿⣿⣿⣿⣿⡇⠀⠀⠀⠀⠱⠀⣧⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠁⢯⡆⠐⡄⠀⠀⠀⣾⣿⡇⣿⣿⣿⣆⢹⣷⠞⠚⠋⠉⠉⠉⠉⠉⠉⠉⠉⠉⠉⠉⠉⠁⠀⠀⢀⠀⠀⢀⠀⢸⢀⣿⣿⣿⣿⠹⣇⠀⠀⠀⠀⡇⠀⣸⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢸⡃⠀⢳⢰⡀⣄⠈⣿⡀⣼⣛⢻⡏⣿⠃⠀⡆⠀⢠⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⡇⠀⣸⡤⢸⢸⡿⣿⢻⣿⡄⠉⠀⠀⠀⢸⠀⢠⡏⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⢧⠀⠈⣧⢷⡙⣮⢯⡧⣇⣯⣷⢹⣸⡆⠦⢽⣄⣘⡆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠤⠤⠒⠚⡟⠋⠹⢀⡟⡾⣾⣿⢸⠈⢻⣦⣄⣠⢄⡟⣀⡞⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠈⢣⣤⠘⢿⡻⠈⠉⠁⠹⣜⢯⡓⢧⢳⡀⢸⡁⠀⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠀⢀⡼⣽⢗⣫⢏⡞⠀⠛⠿⡿⢃⡞⠀⡞⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠳⣅⠀⠝⣆⠺⣔⢴⣬⣳⢭⣩⣦⢳⣄⠀⠀⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⡞⣱⢗⣋⡽⢋⡀⠀⠀⡀⣠⠊⣰⡜⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠢⣄⠈⢳⣌⡛⠋⠉⠁⠀⠈⠳⢼⡷⢤⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣤⡾⢋⣴⡿⠉⠱⣶⠿⢟⡵⣺⠞⢁⣴⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠓⠤⣀⢀⠀⢦⡿⣔⠯⣷⠆⢻⣶⣬⣳⠲⠤⣄⣀⣀⣀⣤⠤⠤⢖⡻⣟⣭⣴⣿⠏⢳⣺⠴⢀⡀⢉⡜⡁⣠⠞⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠻⢥⣀⠉⠻⣋⠀⠀⠈⠓⢻⢎⠙⠒⠯⣄⡀⢀⣐⡶⠾⠛⠋⡽⣸⠃⠉⠀⠀⠀⢚⡩⠞⢡⣾⠟⠁⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⡬⠵⣶⡤⣄⡐⠦⠄⢸⢸⠀⠀⠀⠀⠉⠉⠀⠀⠀⠀⣸⠁⡏⠄⣀⣀⣤⠮⣭⣤⠚⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡾⢃⣴⣿⣿⣿⣿⣿⣷⣦⡟⢸⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡏⠀⣷⣛⣉⣬⣤⣤⡈⠹⢳⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⣠⠴⠚⠉⠛⠒⢲⡏⣰⣿⣿⣿⣿⣿⣿⣿⣿⣿⠃⡞⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣧⠀⢻⣿⣿⣿⣿⣿⣿⣧⠈⠙⠦⣄⡤⠴⠦⣤⡀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢀⡞⢉⣴⣾⣿⣿⣷⣿⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⡏⣰⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⡀⠸⣿⣿⣿⣿⣿⣿⣿⣷⣄⣤⣤⣤⣴⣶⣭⡙⢦⡀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⢠⠏⣠⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠟⡴⠃⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢳⡀⠹⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⡄⠱⡄⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⡟⢠⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡫⠞⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⢤⡙⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠀⣿⡀⠀⠀⠀⠀
⠀⠀⢀⡴⠞⣡⣬⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠻⠥⠯⢤⣄⣀⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣀⣀⣤⠤⠽⠦⠭⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⡞⢿⣦⡀⠀⠀
⠀⣰⠏⣡⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣧⡀⠀⠀⠀⠀⠉⠙⠲⢤⠀⠀⠀⠀⠤⠒⠋⠉⠁⠀⠀⠀⠀⠀⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣜⠛⣆⠀
⠼⠁⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣆⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⡆⠘⢆""")
        
def game_over():
    print("""⡶⠛⠲⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⡶⠚⢲⡀⠀
⣰⠛⠃⠀⢠⣏⠀⠀⠀⠀⣀⣠⣤⣤⣤⣤⣤⣤⣤⣀⡀⠀⠀⠀⣸⡇⠀⠈⠙⣧
⠸⣦⣤⣄⠀⠙⢷⣤⣶⠟⠛⢉⣁⣠⣤⣤⣤⣀⣉⠙⠻⢷⣤⡾⠋⢀⣠⣤⣴⠟
⠀⠀⠀⠈⠳⣤⡾⠋⣀⣴⣿⣿⠿⠿⠟⠛⠿⠿⣿⣿⣶⣄⠙⢿⣦⠟⠁⠀⠀⠀
⠀⠀⠀⢀⣾⠟⢀⣼⣿⠟⠋⠀⠀⠀⠀⠀⠀⠀⠀⠉⠻⣿⣷⡄⠹⣷⡀⠀⠀⠀
⠀⠀⠀⣾⡏⢠⣿⣿⡯⠤⠤⠤⠒⠒⠒⠒⠒⠒⠒⠤⠤⠽⣿⣿⡆⠹⣷⡀⠀⠀
⠀⠀⢸⣟⣠⡿⠿⠟⠒⣒⣒⣈⣉⣉⣉⣉⣉⣉⣉⣁⣒⣒⡛⠻⠿⢤⣹⣇⠀⠀
⠀⠀⣾⡭⢤⣤⣠⡞⠉⠉⢀⣀⣀⠀⠀⠀⠀⢀⣀⣀⠀⠈⢹⣦⣤⡤⠴⣿⠀⠀
⠀⠀⣿⡇⢸⣿⣿⣇⠀⣼⣿⣿⣿⣷⠀⠀⣼⣿⣿⣿⣷⠀⢸⣿⣿⡇⠀⣿⠀⠀
⠀⠀⢻⡇⠸⣿⣿⣿⡄⢿⣿⣿⣿⡿⠀⠀⢿⣿⣿⣿⡿⢀⣿⣿⣿⡇⢸⣿⠀⠀
⠀⠀⠸⣿⡀⢿⣿⣿⣿⣆⠉⠛⠋⠁⢴⣶⠀⠉⠛⠉⣠⣿⣿⣿⡿⠀⣾⠇⠀⠀
⠀⠀⠀⢻⣷⡈⢻⣿⣿⣿⣿⣶⣤⣀⣈⣁⣀⡤⣴⣿⣿⣿⣿⡿⠁⣼⠟⠀⠀⠀
⠀⠀⠀⢀⣽⣷⣄⠙⢿⣿⣿⡟⢲⠧⡦⠼⠤⢷⢺⣿⣿⡿⠋⣠⣾⢿⣄⠀⠀⠀
⢰⠟⠛⠟⠁⣨⡿⢷⣤⣈⠙⢿⡙⠒⠓⠒⠓⠚⣹⠛⢉⣠⣾⠿⣧⡀⠙⠋⠙⣆
⠹⣄⡀⠀⠐⡏⠀⠀⠉⠛⠿⣶⣿⣦⣤⣤⣤⣶⣷⡾⠟⠋⠀⠀⢸⡇⠀⢠⣤⠟
⠀⠀⠳⢤⠼⠃⠀⠀⠀⠀⠀⠀⠈⠉⠉⠉⠉⠁⠀⠀⠀⠀⠀⠀⠘⠷⢤⠾⠁⠀""")
    
    print("You woke up from your dream!!! You can't believe it...it was so real!")
    print("You wake up and get ready to go Pr.Chase Python Class...;)")

# Call the stage 5 function
stage_5(players_name)

```
