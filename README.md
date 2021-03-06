# Snake-Water-Gun-game
game_material = {"s": "snake", "w": "water", "g": "gun"}
computer_material = ["snake", "water", "gun"]
game_run = 1
yes="you won"
no="you loose"
mine_point=0
computer_points=0


import random

print("Hey welcome to Snake Water Game\nHere is s=snake\nw=water\ng=gun\nlets play the game\nEnter your word")
while game_run <= 5:
    v = game_material.get(input())
    print("You Choose--",v)
    computer = random.choice(computer_material)
    print("Computer Choose--",computer)
    if v==computer:
        print("draw")
        print("-----------------------------")
    elif v == "snake" and computer == "water":
        mine_point=mine_point+1
        print("snake drink water so")
        print(yes)
        print("-----------------------------")
    elif v == "snake" and computer == "gun":
        computer_points = computer_points + 1
        print("snake killed by gun so")
        print(no)
        print("-----------------------------")
    elif v == "water" and computer == "snake":
        computer_points=computer_points+1
        print("ur water drank by snake so")
        print(no)
        print("-----------------------------")
    elif v == "water" and computer == "gun":
        mine_point=mine_point+1
        print("your water stop gun so")
        print(yes)
        print("-----------------------------")
    elif v == "gun" and computer == "snake":
        mine_point=mine_point+1
        print("snake killed by your gun so")
        print(yes)
        print("-----------------------------")
    elif v == "gun" and computer == "water":
        computer_points = computer_points + 1
        print("because your bullet stop by water so")
        print(no)
        print("-----------------------------")

    game_run = game_run + 1

result=f"\nyour point is {mine_point},computer point is {computer_points} "
print(result)

if mine_point>computer_points:
    print("great u won the game")
elif mine_point<computer_points:
    print("you loose the game\ncomputer won the game")
else:
    print("draw the game")

print("game completed")


