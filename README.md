# Penalty Shootout Text Based Game in Python

It is a penalty shootout game where user and AI opponent gets turns for the penalty.



## Usage

```python


import random
import time

total_penalties = 0

spot =['left','right','centre']
ask = input("Enter your name to continue: ")
print(f"Hello {ask} ! Welcome to penalty shootout game.")
time.sleep(2)

comDiveDirection = random.choice(spot)
comShootDirection = random.choice(spot)
userScore = 0
comScore = 0

def playerTurn():
	global playerDirection
	global comDiveDirection
	global userScore
	
	global total_penalties
	total_penalties+=1
	playerDirection = input("Choose your spot: ")

	while playerDirection not in spot:
		playerDirection = input("Choose your spot: ")
	else:
		if playerDirection =='left' and comDiveDirection =='right':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		elif playerDirection =='centre' and comDiveDirection =='centre':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		elif playerDirection =='right' and comDiveDirection =='left':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		else:
			print('It\'s a goal')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
			userScore+=1
			print(f'userscore:{userScore} and comScore:{comScore}')
			
def comTurn():
	global playerDirection
	global comShootDirection
	global comScore
	playerDirection = input("Choose your spot to save: ")
	
	global total_penalties
	total_penalties+=1

	while playerDirection not in spot:
		playerDirection = input("Choose your spot to save: ")
	else:
		if comShootDirection =='left' and playerDirection =='right':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		elif comShootDirection =='centre' and playerDirection =='centre':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		elif comShootDirection =='right' and playerDirection =='left':
			print('It\'s a save')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
		else:
			print('It\'s a goal')
			print(f'Player has chosen {playerDirection} and com has chosen {comDiveDirection}')
			comScore+=1
			print(f'userscore:{userScore} and comScore:{comScore}')
			

	
			
def totalScore():
	if userScore> comScore:
		print('You have won the game!')
	elif userScore == comScore:
		print('It\'s a tie!')
		print(f'userscore:{userScore} and comScore:{comScore}')
	else:
		print('You have lost the game')
		print(f'userscore:{userScore} and comScore:{comScore}')
			


   
   
while total_penalties<5:
	playerTurn()
	comTurn()

totalScore()
	
	








```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
