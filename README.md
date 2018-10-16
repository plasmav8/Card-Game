# Card-Game
CSCE 111
//kings
//black jack
//card game
//mac
//10-11-18

import java.util.*;
import java.util.Random;
public class game{ // This is the class
  public static void main(String[] args) { //main function
  Scanner keyboard = new Scanner(System.in);

  Random hand = new Random();

  int[] deck = {1, 1, 1, 1, 2, 2, 2, 2, 3, 3, 3, 3, 4, 4, 4, 4, 5, 5, 5, 5, 6, 6, 6, 6, 7, 7, 7, 7, 8, 8,
  8, 8, 9, 9, 9, 9, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10, 10,};



  System.out.println("\n");

  int player1 = hand.nextInt(52);
  System.out.print("Player 1, your hand is: ");
  for (int i=0; i < 2; i++) {
    System.out.print(deck[player1] + ", ");
  }//end for
  //System.out.print("\b \b"); trying to delete the comma after last card, doesnt work

  System.out.println("\n");



  int player2 = hand.nextInt(52);
  System.out.print("Player 2, your hand is: ");
  for (int i=0; i < 2; i++) {
    System.out.print(deck[player2] + ", ");
  }//end for
  //System.out.print("\b \b"); trying to delete the comma after last card, doesnt work

  System.out.println("\n");


  int player3 = hand.nextInt(52);
  System.out.print("Player 3, your hand is: ");
  for (int i=0; i < 2; i++) {
    System.out.print(deck[player3] + ", ");
  }//end for
  //System.out.print("\b \b"); trying to delete the comma after last card, doesnt work

  System.out.println("\n");


  int player4 = hand.nextInt(52);
  System.out.print("Player 4, your hand is: ");
  for (int i=0; i < 2; i++) {
    System.out.print(deck[player4] + ", ");
  }//end for
  //System.out.print("\b \b"); trying to delete the comma after last card, doesnt work

  System.out.println("\n");
   //*/ //above is setting up hands



  }//end main
}//end class

//this is only dealing each player their cards
