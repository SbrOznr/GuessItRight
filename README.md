
//Guess The Right Number on C lang

#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <time.h>

int main(){
	
	int u,nmb[1],counter=5;// u= user's input , nmb= random number , counter= counter for tries
	
	srand(time(NULL));
	
	nmb[1]=rand()%21;
	//printf("%d\n",nmb[1]);
	
	printf("Welcome to the Game !\n");

	for(;;){
		
		if(counter>0){
		
		printf("Enter a number between 0-20 : ");
		scanf("%d",&u);
		
		if(u<0 || u>20){
			printf("It's not valid. Enter a new number : ");
			scanf("%d",&u);
		}

		if(u<nmb[1]){
			printf("Sry ,%d is less than my number. You have %d guess left.\n\n",u,counter-1);
			counter--;
		}
		else if(u>nmb[1]){
			printf("Sry, %d is bigger than my number. You have %d guess left.\n\n",u,counter-1);
			counter--;
		}
		else if(u==nmb[1]){
			printf("Congratulations. You guessed it right!");
			break;
		}
	 }
	 else {
	 	printf("You lost the game. Die !!!");
	 	break;
	 }
	 
  }
	
	getch();
	return 0;
}
