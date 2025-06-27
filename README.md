# Pao_Ying_Chub_Game
My R programming projects

play_game <- function(){
  cat("Welcome to the Pao Ying Chub game.\n")
  cat("You can choose hammer, scissor, paper, or quit to exit.\n")
  
  hands <- c('hammer','scissor','paper') # Removed 'quit' from hands for computer's choice
  round <- 1
  player_score <- 0
  comp_score <- 0
  
  while(round <= 10){
    comp_hand <- sample(hands, 1)
    player_hand <- readline("Choose it (hammer/scissor/paper/quit): ")
    
    cat("Round :",round,"\n")
    
    cat("Player =", player_hand, "\n","Com =", comp_hand, "\n")
    
    if(!(player_hand %in% c(hands, "quit"))){ # Check if input is valid (including "quit")
      cat("Invalid! Please choose hammer / scissor / paper / quit.\n")
      next # Skip to the next round
    }
    
    if (player_hand == "quit") {
      cat("Exiting game.\n")
      break # Exit the loop entirely
    }
    
    if (comp_hand == "quit") {
      cat("Computer quit. You win!\n")
      break # Exit the loop entirely
    }
    
    
    if (player_hand == comp_hand) {
      cat('Result : Tie!\n')
    } else if ((player_hand == 'hammer' & comp_hand == 'scissor') |
               (player_hand == 'scissor' & comp_hand == 'paper') |
               (player_hand == 'paper' & comp_hand == 'hammer')) {
      cat('Result : You win!\n')
      player_score <- player_score + 1
    } else {
      cat('Result : You lose!\n')
      comp_score <- comp_score + 1
    }
    
    round <- round + 1
    cat("You score =", player_score, "& Com score =", comp_score, "\n")
  }
  
  cat("\n")
  
  cat("Final Score: You =", player_score, " Computer =", comp_score, "\n")#Final Score display
  if(player_score > comp_score){
    cat('You are winner!!!\n')
  }else if(player_score < comp_score){
    cat('You Loser!! 555555555++\n')
  }else{
    cat('Please play again!!\n')
  }
}

play_game()
