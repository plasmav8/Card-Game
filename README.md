//kings
//black jack
//card game
//team members: chase Hogan, Michael Richards, James Woodcock, Issac Rodriguez
//mac and windows
//10-11-18
/*
Rules:
1. each player is dealt 2 cards, in order
2. the number on the card is the value of the card on the face card. Kings, queens, jacks are worth 10
3. an ace can be worth 1 or 11, depending on player choice
4. the sum of both cards are the first score
5. if anyone has 21, they are the winner; players decide if they want a card or not
6. in order to draw a card, the player will need to recall one of the 13 colonies. Give them the option to skip their turn too
7. if the card they get makes the sum of their cards to be > 21, they lose
8. if all players get over 21, there are no winners
9. if a player gets a joker, value set as 22, they automatically lose the game (the mine sweeping aspect of our game)
*/

import java.util.*;
import java.util.stream.*;
import java.io.*;

public class game3{ // This is the class

  static ArrayList<Integer> deck = new ArrayList<Integer>();
  //  static ArrayList<ArrayList<Object>> players = new ArrayList<Object>();
  //static Object[] players = new Object[4];

  static ArrayList<Integer> player1 = new ArrayList<Integer>();
  static ArrayList<Integer> player2 = new ArrayList<Integer>();
  static ArrayList<Integer> player3 = new ArrayList<Integer>();
  static ArrayList<Integer> player4 = new ArrayList<Integer>();
  static ArrayList<Integer> dealer = new ArrayList<Integer>();

  public static void main(String[] args) { //main function
  Scanner keyboard = new Scanner(System.in);

  System.out.println("\n");


  createDeck();
  //System.out.println(deck);
  shuffleDeck();
  //System.out.println(deck);
  //System.out.println(deck.size());
  initialHands();
  //System.out.println(deck);
  //System.out.println("Deck size: ");
  //System.out.println(deck.size());
  //System.out.println("\n");
  System.out.println("Player 1 has: "+player1);
  System.out.println("Player 2 has: "+player2);
  System.out.println("Player 3 has: "+player3);
  System.out.println("Player 4 has: "+player4+"\n");




  turn1(player1);
  turn2(player2);
  turn3(player3);
  turn4(player4);



        int sum = 0;
          for (int i : player1)
          sum = sum + i;
        System.out.println("Player 1 total: "+sum);
        int sum2 = 0;
          for (int i : player2)
          sum2 = sum2 + i;
        System.out.println("Player 2 total: "+sum2);
        int sum3 = 0;
          for (int i : player3)
          sum3 = sum3 + i;
        System.out.println("Player 3 total: "+sum3);
        int sum4 = 0;
          for (int i : player4)
          sum4 = sum4 + i;
        System.out.println("Player 4 total: "+sum4);




          //the highest number is the winner
if(sum > sum2){
  if(sum > sum3){
    if(sum > sum4){
      System.out.println("\n\nPlayer 1 wins!!");
    }//end if
  }//end if
}//end if

if(sum2 > sum){
  if(sum2 > sum3){
    if(sum2 > sum4){
      System.out.println("\n\nPlayer 2 wins!!");
    }//end if
  }//end if
}//end if

if(sum3 > sum){
  if(sum3 > sum2){
    if(sum3 > sum4){
      System.out.println("\n\nPlayer 3 wins!!");
    }//end if
  }//end if
}//end if

if(sum4 > sum){
  if(sum4 > sum2){
    if(sum4 > sum3){
      System.out.println("\n\nPlayer 4 wins!!");
    }//end if
  }//end if
}//end if












  }//end main


public static void createDeck(){     //adds cards to the deck ArrayList
    for (int i = 1;i<=9 ;i++ ) {
      deck.add(i);
      deck.add(i);                //adds face value cards
      deck.add(i);
      deck.add(i);
    }//end for loop
    for (int i=0;i<12 ;i++ ) {
      deck.add(10);               //adds kings, queens, and jacks
    }//end for loop
    for (int i=0;i<4 ;i++ ) {
      var a = 20;
      deck.add(a);               //adds aces
    }
    for (int i=0;i<1 ;i++ ) {
      deck.add(22);
    }//end for                  //this is the bomb
  }//end deck_create

public static void shuffleDeck(){
    Collections.shuffle(deck);          //credit: https://beginnersbook.com/2013/12/how-to-initialize-an-arraylist/
  }//ends deck_shuffle

public static void initialHands(){         //assigns 2 cards to each player
    for (int i=0;i<2 ;i++ ) {
      if (deck.get(i)==20) {
        Scanner input = new Scanner(System.in);
        System.out.println("Player 1: you were dealt an ace. Would you like it to be a 1 or an 11?");
        int ace = input.nextInt();
        if (ace == 1) {
          player1.add(1);
          deck.remove(i);
        }//end if
        else if (ace == 11) {
          player1.add(11);
          deck.remove(i);
        }//end else if
      }//end if
      else {
        player1.add(deck.get(i));
        deck.remove(i);
      }//end else

      if (deck.get(i)==20) {
        Scanner input = new Scanner(System.in);
        System.out.println("Player 2: you were dealt an ace. Would you like it to be a 1 or an 11?");
        int ace = input.nextInt();
        if (ace == 1) {
          player2.add(1);
          deck.remove(i);
        }//end if
        else if (ace == 11) {
          player2.add(11);
          deck.remove(i);
        }//end else if
      }//end if
      else {
        player2.add(deck.get(i));
        deck.remove(i);
      }//end else

      if (deck.get(i)==20) {
        Scanner input = new Scanner(System.in);
        System.out.println("Player 3: you were dealt an ace. Would you like it to be a 1 or an 11?");
        int ace = input.nextInt();
        if (ace == 1) {
          player3.add(1);
          deck.remove(i);
        }//end if
        else if (ace == 11) {
          player3.add(11);
          deck.remove(i);
        }//end else if
      }//end if
      else {
        player3.add(deck.get(i));
        deck.remove(i);
      }// end else

      if (deck.get(i)==20) {
        Scanner input = new Scanner(System.in);
        System.out.println("Player 4: you were dealt an ace. Would you like it to be a 1 or an 11?");
        int ace = input.nextInt();
        if (ace == 1) {
          player4.add(1);
          deck.remove(i);
        }//end if
        else if (ace == 11) {
          player4.add(11);
          deck.remove(i);
        }//end else if
      }//end if
      else {
        player4.add(deck.get(i));
        deck.remove(i);
      }//end else

    }//ends for loop
  }//end hands

public static int turn1(ArrayList<Integer> player1) {
     int sum = 0;

     for (int i : player1)
         sum = sum + i;
         System.out.println("Player 1 your hand is: " + player1);
         System.out.println("Your total is: " + sum);

            Scanner keyboard = new Scanner(System.in);
             String hit;//= keyboard.nextLine();
             do {
               if(sum > 21){
                 System.out.println("You busted!");
                 player1.clear();
                 player1.add(0);
                 break;
               }//end >21 if
               System.out.println("Player 1 enter one of the 13 colonies (no caps) to hit, or enter s to stay.");
               hit = keyboard.nextLine();
               if(hit.equals("connecticut")||hit.equals("delaware")||hit.equals("georgia")||hit.equals("maryland")||hit.equals("massachusetts")||hit.equals("new jersey")
               ||hit.equals("new york")||hit.equals("new hampshire")||hit.equals("north carolina")||hit.equals("pennsylvania")||hit.equals("rhode island")||hit.equals("south carolina")||hit.equals("virginia")){
                 //System.out.println("hitting");
                 aceCheck(player1,deck);

                 System.out.println("\nPlayer 1 your hand is now: " + player1);
                      int sum2 = 0;
                      for (int i : player1)
                      sum2 = sum2 + i;
                 System.out.println("Your total is: " + sum2);
                 if(sum2 > 21){
                   System.out.println("You busted!");
                   player1.clear();
                   player1.add(0);

                   break;
                 }//end >21 if

               }//end if
                if(hit.equals("s")){
                  break;//end loop by not hitting
                }//end if
             } //end do
             while (!hit.equals(null));



      System.out.println("\n\n\n");
     return sum;
}//end turn1

public static int turn2(ArrayList<Integer> player2) {
   int sum = 0;

   for (int i : player2)
       sum = sum + i;
       System.out.println("Player 2 your hand is: " + player2);
       System.out.println("Your total is: " + sum);

          Scanner keyboard = new Scanner(System.in);
           String hit;//= keyboard.nextLine();
           do {
             if(sum > 21){
               System.out.println("You busted!");
               player2.clear();
               player2.add(0);
               break;
             }//end >21 if
             System.out.println("Player 2 enter one of the 13 colonies to hit (h), or enter s to stay.");
             hit = keyboard.nextLine();
             if(hit.equals("connecticut")||hit.equals("delaware")||hit.equals("georgia")||hit.equals("maryland")||hit.equals("massachusetts")||hit.equals("new jersey")
             ||hit.equals("new york")||hit.equals("new hampshire")||hit.equals("north carolina")||hit.equals("pennsylvania")||hit.equals("rhode island")||hit.equals("south carolina")||hit.equals("virginia")){
               //System.out.println("hitting");
               aceCheck(player2,deck);
               System.out.println("\nPlayer 2 your hand is now: " + player2);
                    int sum2 = 0;
                    for (int i : player2)
                    sum2 = sum2 + i;
               System.out.println("Your total is: " + sum2);
               if(sum2 > 21){
                 System.out.println("You busted!");
                 player2.clear();
                 player2.add(0);
                 break;
               }//end >21 if

             }//end if
              if(hit.equals("s")){
                break;//end loop by not hitting
              }//end if
           } //end do
           while (!hit.equals(null));



      System.out.println("\n\n\n");
   return sum;
}//end turn2

public static int turn3(ArrayList<Integer> player3) {
   int sum = 0;

   for (int i : player3)
       sum = sum + i;
       System.out.println("Player 3 your hand is: " + player3);
       System.out.println("Your total is: " + sum);

          Scanner keyboard = new Scanner(System.in);
           String hit;//= keyboard.nextLine();
           do {
             if(sum > 21){
               System.out.println("You busted!");
               player3.clear();
               player3.add(0);
               break;
             }//end >21 if
             System.out.println("Player 3 enter one of the 13 colonies to hit (h), or enter s to stay.");
             hit = keyboard.nextLine();
             if(hit.equals("connecticut")||hit.equals("delaware")||hit.equals("georgia")||hit.equals("maryland")||hit.equals("massachusetts")||hit.equals("new jersey")
             ||hit.equals("new york")||hit.equals("new hampshire")||hit.equals("north carolina")||hit.equals("pennsylvania")||hit.equals("rhode island")||hit.equals("south carolina")||hit.equals("virginia")){
               //System.out.println("hitting");
               aceCheck(player3,deck);
               System.out.println("\nPlayer 3 your hand is now: " + player3);
                    int sum2 = 0;
                    for (int i : player3)
                    sum2 = sum2 + i;
               System.out.println("Your total is: " + sum2);
               if(sum2 > 21){
                 System.out.println("You busted!");
                 player3.clear();
                 player3.add(0);
                 break;
               }//end >21 if

             }//end if
              if(hit.equals("s")){
                break;//end loop by not hitting
              }//end if
           } //end do
           while (!hit.equals(null));


      System.out.println("\n\n\n");
   return sum;
}//end turn3

public static int turn4(ArrayList<Integer> player4) {
   int sum = 0;

   for (int i : player4)
       sum = sum + i;
       System.out.println("Player 4 your hand is: " + player4);
       System.out.println("Your total is: " + sum);

          Scanner keyboard = new Scanner(System.in);
           String hit;//= keyboard.nextLine();
           do {
             if(sum > 21){
               System.out.println("You busted!");
               player4.clear();
               player4.add(0);
               break;
             }//end >21 if
             System.out.println("Player 4 enter one of the 13 colonies to hit (h), or enter s to stay.");
             hit = keyboard.nextLine();
             if(hit.equals("connecticut")||hit.equals("delaware")||hit.equals("georgia")||hit.equals("maryland")||hit.equals("massachusetts")||hit.equals("new jersey")
             ||hit.equals("new york")||hit.equals("new hampshire")||hit.equals("north carolina")||hit.equals("pennsylvania")||hit.equals("rhode island")||hit.equals("south carolina")||hit.equals("virginia")){
               //System.out.println("hitting");
               aceCheck(player4, deck);
               System.out.println("\nPlayer 4 your hand is now: " + player4);
                    int sum2 = 0;
                    for (int i : player4)
                    sum2 = sum2 + i;
               System.out.println("Your total is: " + sum2);
               if(sum2 > 21){
                 System.out.println("You busted!");
                 player4.clear();
                 player4.add(0);
                 break;
               }//end >21 if

             }//end if
              if(hit.equals("s")){
                break;//end loop by not hitting
              }//end if
           } //end do
           while (!hit.equals(null));


      System.out.println("\n\n\n");
   return sum;
}//end turn4

static void aceCheck(ArrayList<Integer> player, ArrayList<Integer> deck) {
  if (deck.get(0)==20) {                                                        
    Scanner input = new Scanner(System.in);
    System.out.println("you got an ace. Do you want a 1 or an 11?");
    int ace = input.nextInt();
    if (ace == 1) {                   //this method checks the next card in the deck. if it is an ace, it allows the
      player.add(1);                  //player to decide if it is a 1 or an 11
      deck.remove(0);
    }//ends if
    else if (ace == 11) {
      player.add(11);
      deck.remove(0);
    }//ends else if
  }//ends the if statement that checks for an ace
  else {
     player.add(deck.get(0));
     deck.remove(0);
  }//ends else.    this is what runs if the next card in the deck is not an ace card
}//ends aceHeck method

}//end class
