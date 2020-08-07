---
layout: post
title:      "RUBY TIC TAC TOE"
date:       2020-08-07 01:07:51 +0000
permalink:  ruby_tic_tac_toe
---


Before I get started I just want to say as a person with minimal coding experience, Ruby Tic Tac Toe was very challenging. I'm glad to say that I made it through (with A LOT of help of course) even though at times I felt discouraged.

I did appreciate Learn breaking down the application of tic tac toe into steps. It made it easier to grasp concepts without feeling overwhelmed. I chose to blog about Tic Tac Toe to review the concepts.

Tic Tac Toe has about 10 steps in order to complete one full game

**Step1: Make the Display Board**
      This is done by creating an array.
			
			
**Step 2: Display Tic Tac Toe**
       This is done by displaying the board from the player's point of view. The interpolation syntax #{}. I learned the hardway the spacing has to meet certain specifications to even pass.
			 

**Step 3: Tic Tac Toe Move**
      The string needs to be converted to an integer via user_input.to_i  . It is also important to know arrays start from 0 so 1 needs to be substracted from the spaces "1"-"9" (user_input.to_i - 1)
     
      
      The move method takes in three arguments and tells the computer where the player would like to put their "X" or "O". This is done with board[user_input] = player


**Step 4: Tic Tac Toe Position Taken**
      This is to determine if the space is occupied before the user adds their input.
			
			def position_taken?(board, index)
           board[index] == "X" || board[index] == "O"
      end
"==" is used to check for equality.  "||" or double pipe is used to represent the boolean operator OR.

**Step 5: Valid Tic Tac Toe Move**
     This method works in conjunction with #position_taken to determine if there is an available space on the board and that space is not filled. The boolean operator (&& or double-ampersand) is used because both sides must equal true to be able to run. I definitely had trouble with lab because of the new introduction of between? which returns true unless the obj mininmum is less than zero or the max is greater than zero. (!) is the boolean operator that reverses the logical state it's in.
		 
			def valid_move?(board,index)
            index.between?(0,8) && !position_taken?(board, index)
      end
			
**Step 6 : Tic Tac Toe Turn**
This is a CLI ( command line interface) to execute a single turn of tic tac toe. Recursion means calling a function from itself.

    def turn(board)
        puts "Please enter 1-9:"
       user_input = gets.strip
       bob = input_to_index(user_input)
   if valid_move?(board,bob)
      move(board, bob) 
   else 
      turn(board)
 end
     display_board(board)
end

**Step 7: Tic tac toe play loop**
This method will loop the game 9 times simulating a real game of tic tac toe. We want to avoid an infinite loop so it's important to have an 'end' to prevent a break. 
    
		def play(board)
         counter = 0
      until counter == 9
    turn(board)
       counter += 1
           end
    end

**Step 8: Tic Tac Toe Current Player**
*Turn count determines whose turn it is. If the turn count is an even number, the #currentplayer method should return "X", otherwise, it should return "O". To determine if a number is even we check if it is divisible by 2 using % or the modulo operator.

def current_player(board)
  turn_count(board) % 2 == 0? "X" : "O"
end
  
**Step 9: Tic Tac Toe Game Status**
 We want to know if the game has been won, has a draw, is there a winner, or is the board full. This involved nested arrays, iteration and booleans. 
 
 
 Looking back on these methods I did not understand entire concepts but I do believe it was a good, fun intro into the following lessons. I'm much further along and many of the concepts above aren't as foreign to me.







        

  

