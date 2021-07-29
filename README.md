# python guess game

#A python program to guess a random number
import random
import math
import time

name= input("Enter your name:")
print("\n\tOk",name,"Lets start The game:")
#creating upper lower range for random number
upper = int(input("enter upper bound:"))
lower = int(input("enter lower bound:"))

#generating random number
x= random.randint(lower,upper)

#creating a guess number with math log function
print("\n\tYou've only",round(math.log(upper-lower + 1,2)),"chances to guess the number!")

#the next line will open after 3 second
time.sleep(3)
count= 0

#creating loop for guessing minimum number of guess
while count <= math.log(upper-lower + 1,2):
    count= count+1
     #guess numer input
    guess= int(input("Guess a number:-"))

    if guess==x:
        print("Congratulations!you hitted the guess number in",count,"try")

        break #once guess is correct, loop will be break
    elif guess > x:
        print("your guess too larger.Please try a small one!")
        time.sleep(2)

    elif guess<x:
        print("Your guess too small.Try a big one!")
        time.sleep(2)
        
        #when guess is more than minimum number ,then the output will be this     
if count > math.log(upper-lower + 1,2):
    print("\n\t Sorry",name,"The random number is %d"%x)
    print("Better Luck Next TIme!")

