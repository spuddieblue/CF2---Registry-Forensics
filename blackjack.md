# Blackjack Game with Betting

Write a Java program for a simplified blackjack game with betting functionality. The program should include the following features:

1. The player starts with a pot of $100.
2. The player can place bets for each round, and their pot updates based on wins or losses.
3. The player and dealer each receive two initial cards with values between 1 and 11.
4. The player can choose to "hit" to receive another card or "stand" to keep their current total.
5. If the player's total exceeds 21, they "bust" and lose the round.
6. The dealer automatically "hits" until their total is at least 17, but they also "bust" if their total exceeds 21.
7. The winner is determined based on the totals, with ties resulting in no change to the pot.
8. The player can quit the game by entering a bet of `0` or when they run out of money.
9. The game should ask the player if they want to play another round after each game.

**Additional Requirements:**

- Include appropriate input validation for betting amounts and player actions (`hit` or `stand`).
- The game should terminate gracefully, thanking the player and displaying their final pot amount.

Implement this game in Java using a simple console interface.

