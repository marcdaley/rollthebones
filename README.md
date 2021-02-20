# rollthebones
Game of chance with dice

#Roll the bones, add the total, guess a number, who's the winner or the loser
from random import randint
from time import sleep

def get_user_guess():
  guess = int(raw_input("Guess a number: "))
  return guess

def roll_dice(number_of_sides):
  first_roll = randint(1, number_of_sides)
  second_roll = randint(1, number_of_sides)
  max_val = number_of_sides * 2
  print 'The max possible value is %d' % max_val
  guess = get_user_guess()
  if guess > max_val:
    print '%d is too high of a number!' % guess
  else:
    print 'Rolling....'
    sleep(2)
    print 'Your number is %d' % first_roll
    sleep(1)
    print 'Your number is %d' % second_roll
    sleep(1)
    total_roll = first_roll + second_roll
    print 'Result of the roll is %d' % total_roll
    if guess > total_roll:
      print "Winner winner chicken dinner!"
    else:
      print "No soup for you!"

roll_dice(6)
