Download Link: https://assignmentchef.com/product/solved-solvedprogram-1-java-intro
<br>
You are going to write a computer program that calculates ratingadjustments for different matches of a table tennis tournament.The program is to input information on a private database of tabletennis players that you are maintaining. This database is listedfirst in the input. It consists of the number of players inthe database followed by a certain number of records. Each recordconsists of an integer rating (given by USATT) and a name.

Following the database, there are an unknown number of lines of input,with each line containing 1 person’s name and list of unknown number ofintegers, terminated with a zero (0). The list of lines is terminated witha line that says “FINISHED!”.

If the integer is positive (e.g. 1678),it means that the person on this line won over a person with thatrating (1678). If the integer is negative, (e.g. -1802), it meansthat the person on this line lost to that person with thatrating (1802). For all the ratings listed on that line theplayer’s rating is to be adjusted according to the following table.

The players’ ratings are to be adjusted according to the USATT rules givenbelow.

if higher rated if lower ratedplayer wins player winsHigher | Lower Higher | Lowerrated | rated rated | ratedplayer | player player | playergains | loses loses | gainsRATING DIFFERENCE0-12 8 813-37 7 1038-62 6 1363-87 5 1688-112 4 20113-137 3 25138-162 2 30163-187 2 35188-212 1 40213-237 1 45238&amp;up 0 50

Make a Prog1 folder on your J drive, copy Prog1.java andP1.in from the class web site into that folder, and proceed as in Program 0to set up a project.

Next, you will be making two more new files.You must comment them appropriately. Follow the programming groundrules which are given on the CS 2430 web site.Make sure you remove any of my comments that tell you how to proceed. Youwill lose 1 point each time I see my “how-to-proceed” comments thatare NOT removed.

The first is a TableTennisPlayer.java file. It can onlyimport java.lang.Math. It can’t read or write anything.I am restricting you to what is described below to force you to usesome concepts covered in class. You will LOSE significant points if youdo NOT follow the restrictions given.

import java.lang.Math;

// Put your comment block here

public class TableTennisPlayer{private String name; // name of the Table Tennis Playerprivate int rating; // rating of Table Tennis Playerprivate int adjustmentForTournament; // value indicates how much// to adjust the rating// once the tournament is over.// This is adjusted for each match.

// No other object data are allowed! [-3 for any other object data]// You are not allowed to do any reading or printing in this class!// Remove these 3 “how-to-proceed” comment lines.

// Don’t forget comment block here too!public TableTennisPlayer ( String TableTennisPlayerName, int TTrating ){// This constructor should be simple to write!// Don’t forget to set adjustmentForTournament to 0

}

// Don’t forget comment block here too – I am finished reminding!!public int getRating(){// This should be even simpler!}

public String getName(){// This should be as simple as getRating!}

public void updateAdjustment(int adjustValue){// Update adjustmentForTournament}

public void updateRating(){// Update rating using adjustmentForTournament}

public String toString(){// name followed by colon followed by space followed by rating}

public int ratingAdjustment ( int loserRating ){// NOTE THAT THIS IS ALWAYS PASSED THE LOSER RATING: loserRatingfinal int NUMBER_OF_LEVELS = 11;final int level[]= {12, 37, 62, 87, 112, 137, 162, 187, 212, 237, 3000}; // levelsfinal int expected[] = {8, 7, 6, 5, 4, 3, 2, 2, 1, 1, 0};// expected values when// higher rated player wins.final int unexpected[] ={8, 10, 13, 16, 20, 25, 30, 35, 40, 45, 50};// unexpected values when// lower rated player wins.

// See information above as well as discussion here &amp; in class.// pseudocode for algorithm:// calculate the difference [the absolute value of the difference, using Math.abs]// find the index in the level table where the difference// is less than or equal.// use this index together with which rating is higher to return a rating// adjustment.// The magic #s used here are the only allowable magic numbers.

}

// That’s all. You can’t have any other methods or data.// [-2 for each additional method added.// You can’t read or write in any method.// If you get the urge to put in more data or methods, you have some// misunderstanding that needs to be cleared up!

}

Next, you will be making a TableTennisPlayerDatabase.java file which will readand store a list of Table Tennis Players. Then, it will read in matches andcalculate the adjustments to be made to the ratings. It will import java.util.Scanner.

import java.util.Scanner;

public class TableTennisPlayerDatabase{// Array of table tennis players.// This must be allocated exactly the right size at run-time.// After that, just use list.length to get at the number of elements.private TableTennisPlayer list[];

Scanner stdin; // read from stdin

public void run() throws java.io.IOException{stdin = new Scanner(System.in);. . . // see below

}

// No other object data are allowed!

// You MUST have several good methods, including run.// If you don’t have several GOOD methods, expect to loose several points!// The run method MUST be public and ALL others private! [-1 for other public methods, other than run!]// Reminder: ARE YOU REMOVING MY COMMENTS??

}

—————————————————————————–

You will read in a set of table tennis records. Next, you will read andprocess a series of players’ matches. One player’s match will consist ofa name followed a zero-terminated list of ratings that a player beat or wasbeaten by. You must calculate an adjustment to be made to the player for eachof these ratings.

The input file has the format:

number_of_table_tennis_playerslist_of_table_tennis_playerslist_of_names_and_matches

The list_of_table_tennis_players will be “number_of_table_tennis_players”lines, with each line having format:

rating_table_tennis_player name_of_table_tennis_player

The list_of_names_and_matches is a variable number of lines, with eachline containing a name and series of integers terminated by zero; eachnonzero integer represents a rating, positive indicating that the personwhose name appears on this line beat a person with that rating, negativeindicating that the person whose name appears on this line lost to aperson with the rating, -rating.

name series of integers terminated by a zero

See the sample input.

Your program will read and store the table tennis player informationin a TableTennisPlayerDatabase object. Then, it will read and processname and matches until “FINISHED!” is read. For each integer on a line, it willcalculate the adjustment value to be made to the name on that line.

See the sample output for the exact wording of all the messages.

Assumptions: To simplify the program (after all, it is program 1!), youcan assume the following and don’t need to check for these:

1. The first line in the file will be a number, call it M.2. The next M lines will be table tennis player info.,in the proper format.3. The next set of lines will be of the form:name series of integer terminated with zeroNo name will appear more than once in the second portionof the input.4. There will be no spaces in any name.

What you do need to check when processing a match: Is the name in the list?If it isn’t, then print out an error message (see sample output below)and then stop processing the matches. Continue on processingwith the next match.

——————————————————————–Programming Requirements

1. The program source files must be called TableTennisPlayer.javaand TableTennisPlayerDatabase.javaRemember that java is case-sensitive, even file names!

2. You must follow the software development ground rules.

3. You must use the declarations as given above.

4. You program must be modular. The methods must be “natural”.All methods must be less than or equal to 30 lines in length.

5. Your “run” method should be short, mostly method calls, something like:

Read TableTennisPlayer InfoPrint TableTennisPlayer Infodone = falseplayerNumber = 0while not donedone = Process One-Name-Match(++playerNumber)Update TableTennisPlayer ratingsPrint TableTennisPlayer Info

Of course, this will also have to keep track of and print the playernumber.

6. Note that the output isn’t formatted very well. That’s okay.We’ll be switching to Applets/Frames after a couple more programs.Recall that the GRADER requires that you match the output exactly.In this case, it shouldn’t be too difficult,since I am not having you do any special or fancy formatting.

7. You must use SE_Tools to keep an up-to-date log of the time spent working.You must use the automatic punch in and punch out when possible.Provide specific comments about what you worked on during that period.Access SE Tools from CSSE page. [up to -4 if you do NOT log all your timeor you do NOT provide specific comments as to what you were working on.]

————————————————————————–Procedural Hints/Requirements

1. You can open this file and copy over the declarations to your java files.

2. Build and test the program in pieces, one method at a time.Write a small method. Then compile and run and test it.

3. Use the next() method of Scanner to read in a String, use nextInt()method to read an integer and use nextFloat() to read in a float.

4. You can start testing by typing in data. Later, to save typing,you can read data from a file. You can make an input file, sayP1.in, with some data in it (such as the sample input) and thenread from the file by putting the following in the run method:

//stdin = new Scanner(System.in);stdin = new Scanner( new java.io.File(“P1.in”) );

After your program is well-tested and it is awaiting therunning of the Grader, change it to:

stdin = new Scanner(System.in);//stdin = new Scanner( new java.io.File(“P1.in”) );

DON’T FORGET, or your grade won’t be very high!!!Make sure the file, P1.in is in the Prog1 solution folder and NOTin any subfolders.

5. Note that in TableTennisPlayerDatabase you will need to“find” a TableTennisPlayer based on name.You should make a private find method to do it.This is a good indicationthat you should make a method to do it. This would bewhat we called a linear search in CS1430 — so you should havethis method/function and call it as many times as necessary.

6. Run your program as in Prog0.

7. If you have questions OR problems, put a copy of the ENTIRE java project inan S drive folder given by:

S:CoursesCSSEscanlancs2430Your_user_Name

Then I can look at your code.

————————————————————————–

Sample Input:231082 HARROD2070 KELLY1810 HOUED2018 HOGSHEAD813 EPSTEIN2663 BUTLERJ1717 FELSTEIN1764 ALSTOTT1845 LONERGANT1930 FAHLSTROM1793 BUTLERA2258 LONERGANS1592 BHADURI2579 BOGGAN2045 MARCUS1627 MOREHEAD1265 PETERSON1693 SCANLAN1860 NUSINOW1843 REED1778 DAHLIN2317 GEE1989 MADRIGALMADRIGAL 1693 0SCANLAN -1989 1793 0BHADURI 2018 0HOGSHEAD -2045 -1592 0MARCUS 2018 0SCANMAN 1234 5678 -987 0SCANLON 0LONERGANT 1843 0REED -1845 0GEE 2258 0LONERGANS -2317 0SMITH 1000 0JONES -900 0BUTLERA -1693 0FINISHED!

Corresponding Sample Output:

Current ListThe Table Tennis Players with their ratings are:HARROD: 1082KELLY: 2070HOUED: 1810HOGSHEAD: 2018EPSTEIN: 813BUTLERJ: 2663FELSTEIN: 1717ALSTOTT: 1764LONERGANT: 1845FAHLSTROM: 1930BUTLERA: 1793LONERGANS: 2258BHADURI: 1592BOGGAN: 2579MARCUS: 2045MOREHEAD: 1627PETERSON: 1265SCANLAN: 1693NUSINOW: 1860REED: 1843DAHLIN: 1778GEE: 2317MADRIGAL: 1989Processing Player’s Matches for a TournamentPlayer Number 1 — MADRIGALNo adjustment necessary for MADRIGAL as ratings differential is too large.Player Number 2 — SCANLANNo adjustment necessary for SCANLAN as ratings differential is too large.Adjusting ratings upward by 20 for SCANLAN; he/she has beaten a player of rating 1793.Player Number 3 — BHADURIAdjusting ratings upward by 50 for BHADURI; he/she has beaten a player of rating 2018.Player Number 4 — HOGSHEADAdjusting ratings downward by 7 for HOGSHEAD; he/she has lost to a player of rating 2045.Adjusting ratings downward by 50 for HOGSHEAD; he/she has lost to a player of rating 1592.Player Number 5 — MARCUSAdjusting ratings upward by 7 for MARCUS; he/she has beaten a player of rating 2018.Player Number 6 — SCANMAN is not in list! No results processed.Player Number 7 — SCANLON is not in list! No results processed.Player Number 8 — LONERGANTAdjusting ratings upward by 8 for LONERGANT; he/she has beaten a player of rating 1843.Player Number 9 — REEDAdjusting ratings downward by 8 for REED; he/she has lost to a player of rating 1845.Player Number 10 — GEEAdjusting ratings upward by 6 for GEE; he/she has beaten a player of rating 2258.Player Number 11 — LONERGANSAdjusting ratings downward by 6 for LONERGANS; he/she has lost to a player of rating 2317.Player Number 12 — SMITH is not in list! No results processed.Player Number 13 — JONES is not in list! No results processed.Player Number 14 — BUTLERAAdjusting ratings downward by 20 for BUTLERA; he/she has lost to a player of rating 1693.Updated ListThe Table Tennis Players with their ratings are:HARROD: 1082KELLY: 2070HOUED: 1810HOGSHEAD: 1961EPSTEIN: 813BUTLERJ: 2663FELSTEIN: 1717ALSTOTT: 1764LONERGANT: 1853FAHLSTROM: 1930BUTLERA: 1773LONERGANS: 2252BHADURI: 1642BOGGAN: 2579MARCUS: 2052MOREHEAD: 1627PETERSON: 1265SCANLAN: 1713NUSINOW: 1860REED: 1835DAHLIN: 1778GEE: 2323MADRIGAL: 1989Normal Termination of Program 1