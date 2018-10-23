//kings
//black jack
//card game
//mac
//10-11-18

import java.util.*;
import java.io.*;
import java.util.stream.*;
public class game{ // This is the class
  Scanner input = new Scanner(System.in);
  static ArrayList<Integer> deck = new ArrayList<Integer>();
//  static ArrayList<ArrayList<Object>> players = new ArrayList<Object>();


  static ArrayList<Integer> player1 = new ArrayList<Integer>();
  static ArrayList<Integer> player2 = new ArrayList<Integer>();
  static ArrayList<Integer> player3 = new ArrayList<Integer>();
  static ArrayList<Integer> player4 = new ArrayList<Integer>();
  static Object[][] players = {{player1}, {player2}, {player3}, {player4}};  //this is a 2 dimensional array that holds the arraylist for each player.
  //credit: https://www.youtube.com/watch?v=udHgmxK9oAI


  public static void main(String[] args) { //main function
  Scanner keyboard = new Scanner(System.in);

  System.out.println("\n");


  createDeck();
  System.out.println(deck);
  shuffleDeck();
  System.out.println(deck);
  System.out.println(deck.size());
  deal();
  System.out.println(deck);
  System.out.println(deck.size());
  currentHand();
  ace();
  System.out.println(check());
  System.out.println(players[2][0]);




  }//end main


  public static void createDeck(){     //adds cards to the deck ArrayList
    for (int i = 2;i<=10 ;i++ ) {
      deck.add(i);
      deck.add(i);                //adds face value cards
      deck.add(i);
      deck.add(i);
    }//end for loop
    for (int i=0;i<12 ;i++ ) {
      deck.add(10);               //adds kings, queens, and jacks
    }//end for loop
    for (int i=0;i<4 ;i++ ) {
      deck.add(20);               //adds aces - 20 is just a random place holder number
    }
  }//end deck_create

  public static void shuffleDeck(){     //shuffles the deck of cards
    Collections.shuffle(deck);          //credit: https://beginnersbook.com/2013/12/how-to-initialize-an-arraylist/
  }//ends deck_shuffle

  public static void deal(){         //assigns 2 cards to each player
    for (int i=0;i<2 ;i++ ) {
      player1.add(deck.get(i));
      player2.add(deck.get(i+1));
      player3.add(deck.get(i+2));
      player4.add(deck.get(i+3));
      deck.remove(i);
      deck.remove(i+1);
      deck.remove(i+2);
      deck.remove(i+3);
    }
  }//end hands

  public static void currentHand(){                     //this just prints out what cards each player currently has
    System.out.println("player one has: "+player1);
    System.out.println("player two has: "+player2);
    System.out.println("player three has: "+player3);
    System.out.println("player four has: "+player4);
  }

  public static int check(){
    int sum =0;
    for (int i : player1){
      sum+=i;
    }//end for
    return sum;
  }
}

