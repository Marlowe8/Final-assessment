# Final-assessment

#include <iostream>
#include <iomanip>
#include <string>
using namespace std;
class Menu{
public:
	string MenuName;
	double MenuPrice;
public:
	Menu();
	Menu(string item, double price){
		MenuName = item;
		MenuPrice = price;
	}
};
Menu::Menu()//Default Constructor
{}
string DisplayMenu() {
	string select;
	cout << left << setw(10) << "Coffee" << left << setw(15) << "\tPrice (AED)" << left << setw(15) << "Tea" << left << setw(15) << "Price (AED)" << endl;
	cout << left << setw(10) << "Ice Coffee" << left << setw(15) << "\t3" << left << setw(15) << "Ice Tea" << left << setw(15) << "3" << endl;
	cout << left << setw(10) << "Milk Coffee" << left << setw(15) << "\t2" << left << setw(15) << "Milk Tea" << left << setw(15) << "2" << endl;
	cout << left << setw(10) << "Black Coffee" << left << setw(15) << "\t1" << left << setw(15) << "Black Tea" << left << setw(15) << "1" << endl;
	cout << "Select Coffee or Tea (Note It is key sensitive): ";
	cin >> select;
	while (select != "tea" || select != "coffee") {
		if (select == "Tea" || select == "tea" || select == "TEA"|| select == "Coffee" || select == "coffee" || select == "COFFEE") {
			break;
		}
		else {
			cout << "Try again" << endl;
			cin.clear();
			cin.ignore();
			cin >> select;
		}
	}
	return select;
}
int main(){
	int i, choice;
	double money,change;
	int sizeArr, sizeArr1;
	string ChoiceMenu;
	char Csugar;
	Menu menuCoffee[] = {Menu("Ice Coffee", 3.0), Menu("Milk Coffee", 2.0), Menu("Black Coffee", 1.0)};
	Menu menuTea[] = { Menu("Ice Tea", 3.0), Menu("Milk Tea", 2.0), Menu("Black Tea", 1.0) };
	ChoiceMenu = DisplayMenu();
	if (ChoiceMenu == "Tea" || ChoiceMenu == "tea" || ChoiceMenu == "TEA") {
		system("cls");
		cout <<"No." << left << setw(10) << "\tTea" << right << setw(15) << "Price (AED)" << endl;
		for (i = 0; i <3 ; i++) {
			cout <<i +1 << "\t" << left << setw(10) << menuTea[i].MenuName << right << setw(15) << menuTea[i].MenuPrice << endl;
		}
		cout << endl;
		cout << "Press 1 for Ice Tea" << endl
			<< "Press 2 for Milk Tea" << endl
			<< "Press 3 for Black Tea" << endl << endl;
		cin >> choice;
		while (cin.fail() || choice != (choice >= 1 && choice <= 3)) {
			if (choice >= 1 && choice <= 3) {
				break;
			}
			cout << "Try again" << endl;
			cin.clear();
			cin.ignore();
			cin >> choice;
		}
		switch (choice) {
		case 1: {
			cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Ice Tea with sugar" << endl;
					cout << "Total is 3 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 3.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 3.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Ice Tea without sugar " << endl;
					cout << "Total is 3 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 3.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 3.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}
		}break;
		case 2: {cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Milk Tea with sugar" << endl;
					cout << "Total is 2 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 2.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 2.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Milk Tea without sugar " << endl;
					cout << "Total is 2 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 2.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 2.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}}break;
		case 3: {cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Black Tea with sugar" << endl;
					cout << "Total is 1 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 1.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 1.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Black Tea without sugar " << endl;
					cout << "Total is 1 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 1.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 1.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}} break;
		}
	}
	else {
		system("cls");
		cout << left << setw(10) << "Coffee" << right << setw(15) << "Price (AED)" << endl;
		for (i = 0; i < 3; i++) {
			cout << left << setw(10) << menuCoffee[i].MenuName << right  << "\t" << menuTea[i].MenuPrice << endl;
		}
		cout << endl;
		cout << "Press 1 for Ice Coffee" << endl
			<< "Press 2 for Milk Coffee" << endl
			<< "Press 3 for Black Coffee" << endl << endl;
		cin >> choice;
		while (cin.fail() || choice != (choice >= 1 && choice <= 3)) {
			if (choice >= 1 && choice <= 3) {
				break;
			}
			cout << "Try again" << endl;
			cin.clear();
			cin.ignore();
			cin >> choice;
		}
		switch (choice) {
		case 1: {
			cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Ice Coffee with sugar" << endl;
					cout << "Total is 3 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 3.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 3.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Ice Coffee without sugar " << endl;
					cout << "Total is 3 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 3.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 3.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}
		}break;
		case 2: {cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Milk Coffee with sugar" << endl;
					cout << "Total is 2 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 2.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 2.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Milk Coffee without sugar " << endl;
					cout << "Total is 2 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 2.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 2.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}}break;
		case 3: {cout << "Do you want sugar with your drink? Press(Y/N)";
			cin >> Csugar;
			while (cin.fail() || Csugar != 'Y' || Csugar != 'N') {
				if (Csugar == 'Y' || Csugar == 'y') {
					cout << "You have ordered Black Coffee with sugar" << endl;
					cout << "Total is 1 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 1.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 1.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else if (Csugar == 'N' || Csugar == 'n') {
					cout << "You have ordered Black Coffee without sugar " << endl;
					cout << "Total is 1 AED Enter how much money you'll pay: "; cin >> money;
					while (cin.fail()) {
						cout << "Try again" << endl;
						cin.clear();
						cin.ignore();
						cin >> money;
					}
					if (money < 1.0) {
						cout << "You don't have enough money, ordered cancelled" << endl;
						return 0;
					}
					else {
						change = money - 1.00;
						cout << "Your change is: " << change << "AED" << endl;
					}
					break;
				}
				else {
					cout << "Try again" << endl;
					cin.clear();
					cin.ignore();
					cin >> Csugar;
				}
			}} break;
		}
	}
	return 0;
}
