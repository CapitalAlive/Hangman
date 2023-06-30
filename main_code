import random


def list_to_string(any_list):
    string = ""
    for element in any_list:
        string += element
    return string
wins = 0
loses = 0
player_choice = ""
print("\nH A N G M A N")
while player_choice != "exit":
    player_choice = input('Type "play" to play the game, "results" to show the scoreboard, and "exit" to quit:')
    if player_choice not in ["play", "results", "exit"]:
        continue
    elif player_choice == "play":
        chances_left = 8
        words_list = ["python", "java", "swift", "javascript"]
        chosen_word = list(random.choice(words_list))
        original_word = str(chosen_word)
        win_status = False
        coded_word = ["-" for index in range(len(chosen_word))]
        guess_hist =[]
        while chances_left > 0:
            print("\n" + list_to_string(coded_word))
            letter_input = input("Input a letter: ")
            if letter_input in guess_hist:
                print("You've already guessed this letter.")
                continue
            if not letter_input.islower() and len(letter_input) > 0:
                print("Please, enter a lowercase letter from the English alphabet.")
                continue
            if not (letter_input.isalpha()) or (len(letter_input) != 1):
                print("Please, input a single letter.")
                continue

            guess_hist.append(letter_input)

            if (letter_input not in str(chosen_word)) and (letter_input not in str(coded_word)):
                chances_left -= 1
                print("That letter doesn't appear in the word.")

            else:
                while letter_input in str(chosen_word):
                    for index in range(len(chosen_word)):
                        if chosen_word[index] == letter_input:
                            chosen_word[index] = "-"
                            coded_word[index] = letter_input
            if str(coded_word) == original_word:

                print(f"You guessed the word {list_to_string(coded_word)}!\nYou survived!")
                win_status = True
                wins +=1
                break
        if win_status == False:
            print("You lost!")
            loses += 1
    elif player_choice == "results":
        print(f"You won: {wins} times.\nYou lost: {loses} times.")
