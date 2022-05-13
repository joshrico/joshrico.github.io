---
layout: project
type: project
image: images/craps-vegas.jpg
title: "Play Craps"
permalink: projects/PlayCraps
date: 2018-09-21
labels:
- Java
- Game
summary: A Java implementation of the casino game Craps.
---
<img class="ui medium right floated rounded image" src="../images/play-craps.png" alt="play-craps">

This project was my introduction to programming and its applications. The idea of the project was to apply the knowledge of Java I had been taught into an implementation of the game Craps. 

Briefly, Craps is a game where the player rolls a pair of dice. On the initial roll, if the player rolls either a 7 or 11, the player wins. If a 2, 3, or 12 is rolled, then the player loses. However, if the player rolls a number other than the ones mentioned, the player must roll the same number to win. Additionally, if they roll a 7, the player loses. The game continues until the player wins or loses.

The application runs and instantly prints out the results of the Craps. From another perspective, you are "rolling" by pressing the effective "run code" button. The program calls a function that randomly generates a number between 1 and 6, which then calls another function to print the respective die face. The program then adds the two function calls together in order to check with the win-lose conditions. 

This project had shown me just how powerful programming could be, along with its broad applications. Although this project may have been just a small implementation of the Java coding language, it was one of the significant starting points in my Computer Science career.

Source Code:
```
import java.util.Random;

public class PlayCraps {
    
    public static void main(String args[]) {
        winBet();
        
    }
    public static void printDie(int die){
    // prints the dice
        String a = ("| x  x  x  |");
        String b = (" ---------- ");
        String c = ("|    x     |");
        String d = ("|  x   x   |");
        String e = ("|          |");
        
        if (die == 1){
            System.out.println(b);
            System.out.println(e);
            System.out.println(c);
            System.out.println(e);
            System.out.println(b);
        }
        else if (die == 2){
            System.out.println(b);
            System.out.println(e);
            System.out.println(d);
            System.out.println(e);
            System.out.println(b);
        }
        else if (die == 3){
            System.out.println(b);
            System.out.println(e);
            System.out.println(a);
            System.out.println(e);
            System.out.println(b);
        }
        else if (die == 4){
            System.out.println(b);
            System.out.println(d);
            System.out.println(e);
            System.out.println(d);
            System.out.println(b);
        }
        else if (die == 5){
            System.out.println(b);
            System.out.println(d);
            System.out.println(c);
            System.out.println(d);
            System.out.println(b);
        }
        else{
            System.out.println(b);
            System.out.println(a);
	        System.out.println(e);
            System.out.println(a);
            System.out.println(b);
        }
    }

    public static int rollDie(){
	// rolls the dice
        Random randomNum = new Random();
        int roll = randomNum.nextInt(6)+1;
        printDie(roll);
        return roll;
    }
    public static int sumOfDice(){
	// adds the sum of the dice rolled
        int die1 = rollDie();
        int die2 = rollDie();
        int sum = die1 + die2;        
        return sum;
    }
    public static void winBet(){
        System.out.println("Let's play Craps!");
	// checks the result of each roll
        boolean flag = true;
        int firstRoll= sumOfDice();
        int reRoll;
        
        if (firstRoll == 7 || firstRoll == 11){
        flag = false;
        System.out.println("You won: " + firstRoll);
        }
        else if (firstRoll == 2 || firstRoll == 3 || firstRoll == 12){
        flag = false;
        System.out.println("Sucker: " + firstRoll);
        }
        else{
        flag = true;
        System.out.println(firstRoll + ": re-rolling");
        }
        
        while (flag==true){
            reRoll = sumOfDice();
        
            if (reRoll == firstRoll){
            flag = false;
            System.out.println("You have won: " + reRoll);
            }
            else if (reRoll == 7){
            flag = false;
            System.out.println("You have lost: " + reRoll);
            }
            else{
            flag = true;
            System.out.println("Keep going: " + reRoll);
            }
        }
    }
}

```
