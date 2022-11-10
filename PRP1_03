
//PRP1_Praktikum03
//Lottoschein
//Chris Lucas Siewert
//2022.11.05
//Version 0.4 Beta (With Comments)

#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <stdbool.h>	//boolean
#include <stdlib.h>     //srand, rand



short getShort(			// [out] user input
	char text[], int min, int max)		// [in] question text for user input
{
	short value;		// user input
	int finished = 0;	// flag for correct user input
	char ch;			// character behind number
	int retVal;			// return value of scanf

	do {
						// get user input
		printf("%s: ", text);
		ch = '\0';		//ch = \0 Rest of buffer that scanf is not Jumped 
		retVal = scanf("%hd%c", &value, &ch);		//& = Poiter that points at the memory address of Value
						// check for valid user input

		if (retVal != 2) printf("Das war keine korrekte Zahl!\n");		//If return ungleich 2 dann zahl nicht korrekt -> Mehr als zwei Parameter also 2
		else if (ch != '\n') printf("Unerwartete Zeichen hinter der Zahl!\n");		//Anderer imput als Enter
		else if (value<min || value>max) printf("Wert ausserhalb des erlaubten Berreiches!\n");		
			else finished = 1;		//If not finished then restart while
						

		while (ch != '\n') scanf("%c", &ch);		// clear input stream
						

	} while (!finished);		// repeat if not finished
						

	return value;		// return user input
}


int main(void)
{

	int tipp[6];		//Defining the six Lotto-Numbers as Int array
	int gezogen[6];		//Defining the six Random Lotto Numbers as Int array

	printf("Lotto 6 aus 49!\nWaehlen sie ihre 6 Lottozahlen.\n");		//Unser Interface
	printf("Bestaetigen sie ihre Zahlen mit der Entertaste.\n");

	tipp[0] = getShort("Geben sie ihren 1. Tipp ein", 1, 49);		//getting the six Lotto Numbers from Function getShort
	tipp[1] = getShort("Geben sie ihren 2. Tipp ein", 1, 49);
	tipp[2] = getShort("Geben sie ihren 3. Tipp ein", 1, 49);
	tipp[3] = getShort("Geben sie ihren 4. Tipp ein", 1, 49);
	tipp[4] = getShort("Geben sie ihren 5. Tipp ein", 1, 49);
	tipp[5] = getShort("Geben sie ihren 6. Tipp ein", 1, 49);


	for (int i = 0; i < 6; i++) {
		int zahl;
		bool doppelt = false;		//Bool is a int, False is int 0, true is Int 1, Bool is Int 0 or 1
		srand(time(NULL));		//Seed for srand is made with current Time of Computer watch. (Makes it all random)
		do {
			doppelt = false;		//Reset of Doppelt = True
			zahl = rand() % 49 + 1;		//Mod 49 limits numbers from 0 to 48, + 1 makes it 1 to 49 
			

			for (int j = 0; j < i; j++) {		//loop for testing if numbers are double
				if (gezogen[j] == zahl) {
					doppelt = true;		//If 1 (True) new Number is generated, if 0 false then break
					break;		//Stopping the for loop. (stopping unnesseary looping
				}
			}
		} while (doppelt);		//While loop for generating non doubled Numbers
		gezogen[i] = zahl;		//putting generated Number into Array
	}

	printf("\nDie zahlen sind: %i, %i, %i, %i, %i, %i \n",gezogen[0], gezogen[1], gezogen[2], gezogen[3], gezogen[4], gezogen[5]);		//Output of Random generated Numbers (Yes i was lazy..)

	int richtige = 0;

											//Checking how many Numbers were correct
	for (int i = 0; i < 6; i++) {			//Looping for tipp Array
		for (int j = 0; j < 6; j++) {		//Looping for gezogene Array
			if (tipp[i] == gezogen[j]) {
				richtige++;
				break;						//Breaking inner for loop to stop unnessesary looping
			}
		}
	}

	printf("\nSie haben %i richtige Zahlen\n", richtige);	//Output Amout of correct numbers

	if (richtige == 2) {
		printf("Sie haben 5 Euro gewonnen");				//Output of winnings
	}
	else if (richtige == 3) {
		printf("Sie haben 50 Euro gewonnen");
	}
	else if (richtige == 4) {
		printf("Sie haben 1000 Euro gewonnen");
	}
	else if (richtige == 5) {
		printf("Sie haben 50,000 Euro gewonnen");
	}
	else if (richtige == 6) {
		printf("JACKPOT!!! Sie haben 1,000,000 Euro gewonnen!");
	}

	return 0;
}
