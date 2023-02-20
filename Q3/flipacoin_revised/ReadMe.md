# Flip-A-Coin Revised

This is a revised version of the Flip-A-Coin Game.
The score has been updated as it shows when the player/computer gets 5 points.
It also provides option for the user to restart the game or not.

You may access the revised game through this [link](https://jeunilongo.github.io/CS3/Q3/flipacoin_revised/flipACoin.html)


## Added the following code:
```
function flip() {
				if(((pscore >= 5) || (cscore >= 5)) && !play){
					if(pscore == 5){
						alert(name + " wins the game.");
					} else {
						alert("Computer wins the game.");
					}
					
					var decide = confirm("Do you want to play again?");
					if(decide){
						pscore = 0;
						cscore = 0;
						document.getElementById("computerScore").innerHTML = cscore;
						document.getElementById("playerScore").innerHTML = pscore;
						play = true;
					} else {
					
					}
				} else{
					var random = (Math.random() * 2).toFixed(0);
					var choice = confirm("HEAD or TAIL: Click 'OK' for HEAD or 'Cancel' for TAIL");
					
					if(random == 0){ // random HEAD
						document.getElementById("random").innerHTML = "HEAD";
						if(choice) { //player's choice is head
							pscore++;
							document.getElementById("playerScore").innerHTML = pscore;
						} else {
							cscore++;
							document.getElementById("computerScore").innerHTML = cscore;
						}
					} else { // random TAIL
						document.getElementById("random").innerHTML = "TAIL";
						if(choice) { //player's choice is head
							cscore++;
							document.getElementById("computerScore").innerHTML = cscore;
						} else {
							pscore++;
							document.getElementById("playerScore").innerHTML = pscore;
						}
					}
				}
				
				if((pscore == 5) || (cscore == 5)){
					play = false;
				}	
			}
```
