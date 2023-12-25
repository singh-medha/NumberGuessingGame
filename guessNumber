import random

class SameLowerAndUpperBoundExecption(Exception):
    def __init__(self, message = "Same Lower and Upper Bound Exception"):
        self.message = message
        super().__init__(self.message)

class NumberOutOfRangeException(Exception):
    def __init__(self, message = "Number out of Range Exception"):
        self.message = message
        super().__init__(self.message)
    
def inputGuessedValue(correctNumber, lowerLimit, upperLimit):
    guessedValue = input("What is your guess number? ")
    if(guessedValue == 'q'):
        print('The correct value is ', correctNumber)
    guessedValue = int(guessedValue)
    if(guessedValue > upperLimit or guessedValue < lowerLimit):
        raise NumberOutOfRangeExecption('The number you have entered is out of the range')
    return guessedValue 

def incrementNumberOfIterations(countIterations, numberOfNewAttempts):
    return countIterations + numberOfNewAttempts
        
def provideHintToUser(lowerBound, upperBound):
    print(f"Guess a greater value i.e., within range {lowerBound}-{upperBound}")
    
def generateRandomNumber(lowerLimit, upperLimit):
    return random.randint(lowerLimit, upperLimit)
    
def playNumberGuessingGame():
    try:
        lowerLimit = int(input('Enter the lower limit: '))
        upperLimit = int(input('Enter the upper limit: '))
    except ValueError:
        print('Input is not a valid integer')
    try:
        if(lowerLimit == upperLimit):
            raise SameLowerAndUpperBoundExecption('Enter a different value for the lower and upper bound')
        correctNumber = generateRandomNumber(lowerLimit, upperLimit)
    except UnboundLocalError:
        print('Please ensure that you have entered values for lower and upper limit')
    print(f"I've generated a number between {lowerLimit}-{upperLimit}! Enter q to quit the game")
    lowerBound, upperBound = lowerLimit, upperLimit
    countIterations = 0
    while(True):
        guessedValue = inputGuessedValue(correctNumber, lowerLimit, upperLimit) 
        if(guessedValue > upperBound or guessedValue < lowerBound):
            print('Utilise the hints, and try again')
            countIterations = incrementNumberOfIterations(countIterations, 2)
            guessedValue = inputGuessedValue(correctNumber, lowerLimit, upperLimit)
        else:
            countIterations = incrementNumberOfIterations(countIterations, 1)
        if(guessedValue == correctNumber):
            print(f"Yay! You guessed it right in {countIterations} times!")
            break
        elif(correctNumber > guessedValue):
            lowerBound = guessedValue
            provideHintToUser(lowerBound, upperBound)
        else:
            upperBound = guessedValue
            provideHintToUser(lowerBound, upperBound)  

playNumberGuessingGame()
    

    
