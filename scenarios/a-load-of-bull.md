# A load of bull
> A game designed to limit customer's contact with the rep

TUI have an in-resort app that can be downloaded by its customers.  This app allows our customers to book and pay for any of the additional services and products we offer at our hotels.

One of the services the app allows customers to book is an appointment with one of our in-resort representatives - or reps.

This feature has proven so popular that the resort team at head office have had to devise a way to limit the number of appointments booked via this method.  On checkout within the app - the customer is required to play a game of Bulls & Cows (https://en.wikipedia.org/wiki/Bulls_and_Cows) - a precursor to the highly popular board game `mastermind`.

If the customer cracks the hidden code in 6 or less guesses they are allowed to continue to book an appointment.  Otherwise, they cannot book an appointment.  Of course, the customer can just keep trying if they choose!

You have been requested to implement the game.

## Bulls & Cows

The game is for 2 players (in our version anyway) - the code setter (the app in this case) and the code breaker (our customer).  At the start of the game the code setter generates a random 4 digit number - repeating numbers are allowed.  The code breaker then gets as many guesses as it takes for them to crack the code.

After each guess the code setter gives the code breaker feedback as to how many Bulls (correct number in the correct position) and Cows (correct number, but incorrect position) they have guessed.  The game is over when the code breaker receives '4 Bulls, 0 Cows' from their guess.

A typical game (played in a terminal) might run like this...


```bash
$ bulls_and_cows

Random code generated...
# Code: 9305 - this is hidden from the code breaker

Enter guess [1]: 1234
Result: 0 Bulls, 1 Cow

Enter guess [2]: 5678
Result: 0 Bulls, 1 Cow

Enter guess [3]: 9012
Result: 1 Bulls, 1 Cow

Enter guess [4]: 9087
Result: 1 Bulls, 1 Cow

Enter guess [5]: 1087
Result: 0 Bulls, 1 Cow

Enter guess [6]: 9205
Result: 3 Bulls, 0 Cows

Enter guess [7]: 9305
Result: 4 Bulls, 0 Cows

[7] guesses.  Sorry, you are not allowed a rep appointment :-(

Try again? Y


Random code generated...
# Code: 5678 - this is hidden from the code breaker

Enter guess [1]: 1234
Result: 0 Bulls, 0 Cows

Enter guess [2]: 5678
Result: 4 Bulls, 0 Cows

[2] guesses.  Congratulations, you are allowed a rep appointment :-)

Try again? N

$
```
