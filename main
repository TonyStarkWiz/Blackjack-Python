from art import logo
import random
from replit import clear

def deal_card():
    cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10]
    return random.choice(cards)

def calculate_score(hand):
    total_score = sum(hand)
    if 11 in hand and total_score > 21:
        hand.remove(11)
        hand.append(1)
    return total_score

def compare(player_score, computer_score):
    if player_score > 21:
        return "You went over. You lose! 😭"
    elif computer_score > 21:
        return "Computer went over. You win! 😁"
    elif player_score == computer_score:
        return "It's a draw! 🙃"
    elif computer_score == 0:
        return "Computer has a Blackjack. You lose! 😱"
    elif player_score == 0:
        return "You have a Blackjack. You win! 😎"
    elif player_score > computer_score:
        return "You win! 😃"
    else:
        return "You lose! 😤"

def play_game():
    print(logo)
    player_hand = [deal_card() for _ in range(2)]
    computer_hand = [deal_card() for _ in range(2)]
    game_over = False
    
    while not game_over:
        player_score = calculate_score(player_hand)
        computer_score = calculate_score(computer_hand)
        
        print(f"Your cards: {player_hand}, current score: {player_score}")
        print(f"Computer's first card: {computer_hand[0]}")
        
        if player_score == 0 or computer_score == 0 or player_score > 21:
            game_over = True
        else:
            another_card = input("Type 'y' to get another card, or 'n' to pass: ")
            if another_card == 'y':
                player_hand.append(deal_card())
            else:
                game_over = True
    
    while computer_score != 0 and computer_score < 17:
        computer_hand.append(deal_card())
        computer_score = calculate_score(computer_hand)
    
    print(f"Your final hand: {player_hand}, final score: {player_score}")
    print(f"Computer's final hand: {computer_hand}, final score: {computer_score}")
    print(compare(player_score, computer_score))
while input("Do you want to play a game of Blackjack? Type 'y' or 'n': ") == "y":
  clear()
  play_game()
