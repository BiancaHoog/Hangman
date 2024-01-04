import random

def pick_random_word():
    word_list = ['python', 'hangman', 'game', 'word', 'play', 'loop']
    return random.choice(word_list)

def is_game_over(hidden_word, letters_guessed, number_of_incorrect_guesses):
    if number_of_incorrect_guesses >= 6:
        return True
    for letter in hidden_word:
        if letter not in letters_guessed:
            return False
    return True

def ask_user_for_guess(letters_guessed):
    while True:
        guess = input("Enter your guess: ")
        if len(guess) == 1 and guess.isalpha() and guess not in letters_guessed:
            return guess
        else:
            print("Invalid guess. Please enter a single letter that hasn't been guessed before.")

def print_hidden_word(hidden_word, letters_guessed):
    for letter in hidden_word:
        if letter in letters_guessed:
            print(letter, end=' ')
        else:
            print('_', end=' ')
    print()

def print_gallows(number_of_body_parts):
    gallows = [
        '''
        # _______
        # |    |
        # |
        # |
        # |
        # |
        # |
        # |
        # --------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |
        # |
        # |
        # |
        # |
        # ---------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |    |
        # |    |
        # |
        # |
        # |
        # ---------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |  --|
        # |    |
        # |
        # |
        # |
        # ---------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |  --|--
        # |    |
        # |
        # |
        # |
        # ---------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |  --|--
        # |    |
        # |   / 
        # |  /   
        # |
        # ---------
        ''',
        '''
        # _______
        # |    |
        # |    O
        # |  --|--
        # |    |
        # |   / \\
        # |  /   \\
        # |
        # ---------
        '''
    ]
    print(gallows[number_of_body_parts])

def play_hangman():
    play_again = True

    while play_again:
        hidden_word = pick_random_word()
        letters_guessed = []
        number_of_incorrect_guesses = 0

        while not is_game_over(hidden_word, letters_guessed, number_of_incorrect_guesses):
            print_hidden_word(hidden_word, letters_guessed)
            print_gallows(number_of_incorrect_guesses)

            guess = ask_user_for_guess(letters_guessed)
            letters_guessed.append(guess)

            if guess not in hidden_word:
                number_of_incorrect_guesses += 1

        print_hidden_word(hidden_word, letters_guessed)
        print_gallows(number_of_incorrect_guesses)

        if number_of_incorrect_guesses >= 6:
            print("Game over. You lost!")
        else:
            print("Congratulations! You won!")

        response = input("Do you want to play again? (yes/no): ")
        if response.lower() != 'yes':
            play_again = False

play_hangman()
