//kings
//black jack
//card game
//mac
//10-11-18

import java.util.*;
import java.io.*;
public class game{ // This is the class

  static ArrayList<Integer> deck = new ArrayList<Integer>();
//  static ArrayList<ArrayList<Object>> players = new ArrayList<Object>();
  //static Object[] players = new Object[4];

  static ArrayList<Integer> player1 = new ArrayList<Integer>();
  static ArrayList<Integer> player2 = new ArrayList<Integer>();
  static ArrayList<Integer> player3 = new ArrayList<Integer>();
  static ArrayList<Integer> player4 = new ArrayList<Integer>();

  public static void main(String[] args) { //main function
  Scanner keyboard = new Scanner(System.in);

  System.out.println("\n");



  createDeck();
  System.out.println(deck);
  shuffleDeck();
  System.out.println(deck);
  System.out.println(deck.size());
  initialHands();
  System.out.println(deck);
  System.out.println(deck.size());
  System.out.println("player one has: "+player1);
  System.out.println("player two has: "+player2);
  System.out.println("player three has: "+player3);
  System.out.println("player four has: "+player4);
  ace();




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
      deck.add(20);               //adds aces
    }
  }//end deck_create

  public static void shuffleDeck(){
    Collections.shuffle(deck);          //credit: https://beginnersbook.com/2013/12/how-to-initialize-an-arraylist/
  }//ends deck_shuffle

  public static void initialHands(){         //assigns 2 cards to each player
    for (int i=0;i<2 ;i++ ) {
      player1.add(deck.get(i));
      player2.add(deck.get(i+5));
      player3.add(deck.get(i+6));
      player4.add(deck.get(i+7));
      deck.remove(i);
      deck.remove(i+5);
      deck.remove(i+6);
      deck.remove(i+7);
    }
  }//end hands

  public static boolean ace(){   //checks for 20. if 1 would be better, 1 goes in the hand. if not, 11 does
    for (int i=1;i<=4 ;i++ ) {
      for (int j : player1) {
        if (player1.equals(20)) {
          return true;
        }//end if
      }//end inner for
      return false;
    }//end big for
    return false;
  }//end ace
  }

