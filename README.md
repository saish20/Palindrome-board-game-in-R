# Palindrome-board-game-in-R

Created a board game in which a player collects letters to form a five-letter palindrome (e.g. ‘VGDGV’ or ‘BUKUB’) in a minimum number of moves.

The rules of the game:

- The player’s token starts on a specified white square not on the edge of the board.

- If, at the start of a turn, the player’s token is on a square that is not on the edge of the board then the token moves at random to one of the adjacent squares.

- If, at the start of a turn, the token is on a square that is on the edge of the board then the token moves at random to one of the 64 squares on the board.

- If the token lands on a white square the player can choose whether to add the letter to their collection or not. Note that letters are not removed from squares, but a copy of the letter can be collected. The player can never have more than five letters in their collection.

- If a token lands on a green square then

  - with probability p the letters in their collection are replaced with the letters F, F, H and K.
  - with probability 1−p all copies, of the letter on the square, in their collection are removed from their collection (eg if the green square shows an A then they would remove     all As from their collection with probability 1−p).

- When a player adds a letter to their collection they check whether they can form a five-letter palindrome (they can rearrange the letters in their collection in any order).

- The game ends when they have formed a five-letter palindrome.


Strategy:
Collecting the first three letters at random while satisfying the competing requirements of completing the game and then collecting the remaining two letters in a way which when added to the initial collection of three letters, form a palindrome, i.e. the following two letters will always be a subset of the initial three letters. The collection of the first three letters, though random, is only accepted when their frequency is higher than others. This will reduce the steps in finding the subsequent two letters since the likelihood of finding those would be slightly higher than the rest.
