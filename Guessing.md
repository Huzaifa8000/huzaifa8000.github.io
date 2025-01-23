```mermaid
flowchart TD
  Start([Start]) --> Difficulty{Choose Difficulty?}
  Difficulty -->|Easy| SetRangeEasy[Set Range 1-10]
  Difficulty -->|Medium| SetRangeMed[Set Range 1-50]
  Difficulty -->|Hard| SetRangeHard[Set Range 1-100]
  SetRangeEasy & SetRangeMed & SetRangeHard --> GenerateRandomNumber
  GenerateRandomNumber --> Instructions[Instructions]
  Instructions --> InputGuess
  InputGuess --> ValidateInput{Is Input Valid?}
  ValidateInput -- No --> InvalidInput[Error Message] --> InputGuess
  ValidateInput -- Yes --> AttemptsCheck{Attempts Left?}
  AttemptsCheck -- No --> OutOfAttempts[Game Over]
  OutOfAttempts --> PlayAgain{Play Again?}
  PlayAgain -- Yes --> Start
  PlayAgain -- No --> End([End])
  AttemptsCheck -- Yes --> CheckGuess{Is the Guess Correct?}
  CheckGuess -- Yes --> Congratulate[You Won!]
  Congratulate --> PlayAgain
  CheckGuess -- No --> CheckHigher{Is guess Higher?}
   CheckHigher --> |yes| HintLower[Hint: Guess Lower]
   CheckHigher --> |No| HintHigher[Hint: Guess Higher]
   HintLower --> InputGuess
   HintHigher --> InputGuess
   Win --> END[End Game] 
```

# **Documentation/Descriptions** 
#### **Start:** Begins the game.
#### ** Choose Difficulty: ** The user selects a difficulty level, setting the set range of numbers. 
#### **Generate Random Number:** The system picks a number within the set range.
#### **Display Instructions:** The user sees game instructions.
#### **Prompt User for Guess:** The user inputs a guess.
#### **Validate Input:** Checks if the input is valid.
##### **_Invalid Input:_** Displays an error message and prompts again.
#### **Check Attempts:** Verifies if there are attempts left.
##### **_No Attempts:_** Displays Game over message and option to play again.
##### **_Attempts Left:_** Checks the guess.
#### **Check Guess:** Determines if the guess is correct.
##### **_Correct:_** Displays a winning message and offers to play again.
##### **_Incorrect:_** Checks if the guess is higher or lower and provides hints.
#### **Play Again:** Decision point for restarting the game or ending it.
