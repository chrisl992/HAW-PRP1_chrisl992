//PRP1_Praktikum1
//Asking the User the Questions of all Questions
//Chris Lucas Siewert
//2022.10.07
//Version 0.1 Beta

#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>  //Used Library

int main() {

	int userAnswer;        //User Answer
	char userRestart = 'Y';      //User Input for Restart or ending of Program

	while (userRestart != 'X') {		//While Loop to Restart or end he Program

		system("cls"); //Clearing Console

		printf("Hello User\n");    //Greeting the User
		printf("I am Deep Thought!\n");

		printf("User can you tell me the answer to the question of all questions?\n");  //Asking the User

		userAnswer = 0;
		scanf("%d", &userAnswer);   //Reading User Input
		
		if (userAnswer == 42) {                 //If User Input is 42 = Correct
			printf("This checks out, you are Correct!\n");    //Print output if Correct
		
		}
		else {
			printf("Error, Try again!\n");   //Print output if false
			
		}
		
		while (getchar() != '\n') {}	//Deleting Inputbuffer

		printf("Would you like to try again?\n  Type: [Y/X]\n");	//Print Output if you want to try again, 
		scanf("%c", &userRestart);	

		while (getchar() != '\n') {}	//Deleting Inputbuffer
		
	}

		return 0;
}
