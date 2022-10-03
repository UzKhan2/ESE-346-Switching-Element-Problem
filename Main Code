#include <cstdlib>
#include <iostream>
#include <ctime>
using namespace std;

int main()
{
	int ptest=0; // Random number variable
	int test= 10000; // Number of iterations 
	double avg_busy[20], avg_drp[20];
	double busy, drp, input; // Variable to keep track of data
	srand(time(NULL)); // Seed random variable
	for (int i=1; i<=20; ++i) // 20 loops for steps 0f .05 to 1
	{
		busy = 0; 
		drp = 0; // Reset data after every loop
		for (int j=1; j<=test; ++j) // iteration loop
		{
			input = 0; // Reset succesfull inputs after a loop
			for (int k=1; k<=10; ++k) // Loop of 10 fro 10 input slots
			{
				ptest = rand() % 100 + 1;  // Generates random number 1 to 100
		        if (ptest <= (i*5)) // Numbers represent prob (1-5 is 5%)e
			    	input++; // Packet arrived count 	
			}
			if (input > 3)
			{
				busy = busy + 3; // Max busy is 3
				drp = drp + (input - 3); // Add rest to dropped	
			}
			else
				busy = busy + input; // Anything less than 3	
		}
		avg_busy[i] = busy/test;
		avg_drp[i] = drp/test; // Divide by iterations to get average	
	}         
	for (int c=1; c<=20; c++) // Display loop
	{
	cout << "Average Busy for " << (c*5./100) << "  "<< avg_busy[c] <<"   ";	
	cout << "Average Dropped for " << (c*5./100) << "  "<< avg_drp[c] << endl;	
	}
	return 0;
}
