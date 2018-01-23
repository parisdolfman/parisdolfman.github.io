---
layout: post
title:      "Tic Tac Toe Code Explained"
date:       2018-01-23 20:16:37 +0000
permalink:  tic_tac_toe_code_explained
---


After completing the last lab for my Tic Tac Toe game I learned various things about the way that Ruby works as a language. Working on individual methods and learning how they function as a part was difficult, but I gained real understanding once I put all of them together. Below I have a copy of my code and some explanation as to how my thought process worked while writing it. 

```
WIN_COMBINATIONS = [ 
 [0,1,2],
 [3,4,5],
 [6,7,8],
 [0,3,6],
 [1,4,7],
 [2,5,8],
 [0,4,8],
 [6,4,2]
]

def display_board(board)
  puts " #{board[0]} | #{board[1]} | #{board[2]} "
  puts "-----------"
  puts " #{board[3]} | #{board[4]} | #{board[5]} "
  puts "-----------"
  puts " #{board[6]} | #{board[7]} | #{board[8]} "
end

def input_to_index(number)
 number.to_i - 1
end

def move(board, index, current_player)
  board[index] = current_player
end

def position_taken?(board, index)
  board[index] != " " && board[index] != ""
end


def valid_move?(board, index)
  index.between?(0,8) && !position_taken?(board, index)
end


def turn(board)
  puts "Please enter 1-9:"
  input = gets.strip
  index = input_to_index(input)
  if valid_move?(board, index)
    move(board, index, current_player(board))
    display_board(board)
  else
    turn(board)
  end
end

def current_player(board)
  turn_count(board) % 2 == 0 ? "X" : "O"
 # if turn_count(board) % 2 == 0
 #   "X"
 # else "O"
 # end
end

def turn_count(board)
  counter = 0
  board.each do |space|
    if space == "X" || space == "O"
      counter += 1
    end
  end
 counter
end

def won?(board)
 WIN_COMBINATIONS.detect do |combo|
    element_1 = combo[0]
    element_2 = combo[1]
    element_3 = combo[2]
    index_1 = board[element_1]
    index_2 = board[element_2]
    index_3 = board[element_3]
    index_1 == index_2 && index_2 == index_3 && position_taken?(board, element_1)
  end
end

def full?(board)
 board.all? do |index|
   index == "X" || index == "O"
  end
 end

def draw?(board)
 full?(board) && !won?(board)
end

def over?(board)
full?(board) || won?(board) || draw?(board)
end

def winner(board)
   if winning = won?(board)
   board[winning[0]]
 end
end

def play(board)
 until over?(board)
   turn(board)
 end

  if won?(board)
    winner = winner(board)
    puts "Congratulations #{winner}!"
  else draw?(board)
   puts "Cat's Game!"
  draw?(board)
  end
 end

```

The first thing I did was define a constant called WIN_COMBINATIONS. This constant lists each possible winning combination in the form of a nested array. This data is referenced throughout the rest of the code and tells the program how to operate based on whether or not the winning combinations are satisfied.
Afterwards I defined the display board according to what it should look like to the user. Within each index of the board is string interpolation - the variable used inside refers back to the original array of the display board. This string interpolation allows us to access different indexes of the board and operate on them.
The  block within #input_to_index tells the program to take the user's input, converts the input to an interger and subtracts 1 from the input.
The reason we do this is because the first array of the board is 0, not 1. If the user wants to access space 3, the index in the array would actually be 2.
The #move method takes in the argument of the board, the index, and the current_player which is defined as board[index] since we needed a variable to be able to access the individual index being operated on - as opposed to being hardcoded, ex: board[0].
In #position_taken? we pass the arguments of the board and the index. If the index of the board is not empty then the position is not taken. 

Post continued in Part II.

