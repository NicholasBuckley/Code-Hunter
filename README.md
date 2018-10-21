# Code-Hunter
// Code Hunter Debugged.cpp : This file contains the 'main' function. Program execution begins and ends there.
//Nicholas Buckley 10.21.2018

#include "pch.h"
#include <iostream>
#include <string>

using namespace std;


int main()
{
	string textToAnalyze;
	int foo = 0;
	int vowels = 0;
	int consonants = 0;
	int digits = 0;
	int spaces = 0;
	int lengthOfStringSubmittedForAnalysis = 0;
	int unknownCharacters = 0;
	int checkSum = 0;
	int bar = 0;

	cout << "Welcome to the CIA code Hunter Program!" << endl;
	cout << "Please type in text to analyze: " << endl;
	getline(cin, textToAnalyze);

	for (int i = 0; i < textToAnalyze.length(); ++i)
	{
		if (textToAnalyze[i] == 'a' || textToAnalyze[i] == 'e' || textToAnalyze[i] == 'i' ||
			textToAnalyze[i] == 'o' || textToAnalyze[i] == 'u' || textToAnalyze[i] == 'A' ||
			textToAnalyze[i] == 'E' || textToAnalyze[i] == 'I' || textToAnalyze[i] == 'O' ||
			textToAnalyze[i] == 'U')
		{
			++vowels; // Changed this line to add everytime there is a vowel instead of subtract
		}
		else if ((textToAnalyze[i] >= 'a'&& textToAnalyze[i] <= 'z') || (textToAnalyze[i] >= 'A'&& textToAnalyze[i] <= 'Z'))
		{
			++consonants; // Changed this comment to an actual line of code to add every time there is a consonant
		}
		else if (textToAnalyze[i] >= '0' && textToAnalyze[i] <= '9')
		{
			++digits;
		}
		else if (textToAnalyze[i] == ' ')
		{
			++spaces;
		}
		else
		{
			++unknownCharacters;
		}
	}

	lengthOfStringSubmittedForAnalysis = textToAnalyze.length();
	checkSum = unknownCharacters + vowels + consonants + digits + spaces;

	cout << "Vowels: " << vowels << endl;
	cout << "Consonants: " << consonants << endl;
	cout << "Digits: " << digits << endl;
	cout << "White spaces: " << spaces << endl;
	cout << "Length of string submitted for analysis: " << lengthOfStringSubmittedForAnalysis << endl;
	cout << "Number of characters CodeHunter could not identify: " << unknownCharacters << endl;
	cout << "Checksum: " << checkSum << endl;

	if (checkSum == lengthOfStringSubmittedForAnalysis)
	{
		cout << "This program self checking has found this Analysis to be valid." << endl;
	}
	else
	{
		cout << "WARNING! *** This program self checking has found this Analysis to be invalid! Do not use this data!\n" << endl;
		cout << ""<<checkSum<<"\n"; // Add this line to help me determine how far off the count was
	}

	system("pause");

	return 0;
}
