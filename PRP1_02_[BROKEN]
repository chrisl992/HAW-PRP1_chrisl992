//PRP1_Praktikum02
//Primzahlen
//Chris Lucas Siewert
//2022.10.27
//Version 0.2 Beta

#define _CRT_SECURE_NO_WARNINGS    //for scanf because of safety issues
#include <stdio.h>        //Used library

//Funktions


int even_or_uneven(int);

int prime_or_not(int);

void primefactors(int);

int input_validation(int);


//Main Program 
int main(void) 
{

	unsigned int n;  //variable n (for input number)

	

	//(if (scanf("%u", &n) != 1) 
	//{
		//printf("Input error\n");
		//return;
	//}

	//printf("The number you enterd is ");

		//Input Validation

	do
	{

		printf("Please Enter a positve Number\n");   //Question to the User

		scanf("%u", &n);    //Scanning user input

	} 
	while (!input_validation(&n));


	//Task 2.2 is Number even or uneven
	if (even_or_uneven(n)) 
	{     

		printf("Your Number is even.\n");

	}
	else 
	{

		printf("Your Number is uneven.\n");

	}

	//Task 2.3 Is Number prime or not
	if (prime_or_not(n)) 
	{

		printf("The Number you entered is a Prime.\n");

	}
	else 
	{

		printf("The Number you entered is not a Prime.\n");

	}

	//Task 2.4 and 2.5 list of Primes and Primefactors (Combined)
	for (int i = 0; i < n; i++)
	{
		//For Loop that srats with 0 and adds every Round 1, 
		//Combined with Prime_or_not we can make a List of Primes

		if (n <= 1000)
		{


			if (prime_or_not(i))
			{

				printf("%4d", i); // 4 spaces

			}
		}
		else
		{
			return 0;
		}
	}
		
	primefactors(n);

	printf("\n");

	return;
}



//Input Validation
int input_validation(int n)
{
	if ((int) n <= 0)
	{
		printf("\nInput error, input invalid! Must be positiv!\n");
	}
	else
	{
		return 1;
	}
}


//Function for task 2.2 even or uneven 
int even_or_uneven(int n)
{

	return ((n % 2) == 0); //Is Number mod 2 then return 0 -> goes to if, if not -> goes to else 

}

//Function for task 2.3
int prime_or_not(int n)
{
	int prime_min = 2;
	//Since 0, 1, 2 and even Numbers are special they need to be sepratly
	if (n == 0) return 0; 
	if (n == 1) return 0;
	if (n == 2) return 1; 
	if (even_or_uneven(n)) return 0;

	for (int i = prime_min + 1; i < n; i += 2) //For Array -> i+=2 equal to i = i+2
	{              //NEEDS TO BE LIMITED TO 1000

		if ((n % i) == 0) //If n Mod i equals a result without rest then return 0 -> Number is Prime, else Return 1
		{
			return 0;
		}

	}

	return 1;

}

//Function for 2.4 and 2.5
void primefactors(int n) 
{

	int prime_min = 2;
	int factor = prime_min;  //2, The first Prime, gets posted

	if (n == 0) return; //exeption for 0 to not show up

	do 
	{

		int divide_mod = (n % factor) == 0; //n can be devided with mod 0

		if (divide_mod)
		{
			n = n / factor;
			printf("\n\n"); //next line

			printf("%i", factor);

		}
		else 
		{

			do 
			{

				factor++;

			} while (!prime_or_not(factor));


		}


	} while (n > 1);

	printf("\n"); 

	return;

}
