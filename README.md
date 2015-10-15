#include <iostream>
#include <string>

using namespace std;

string TicBoard[3][3] = { { "R1C1", "R1C2", "R1C3" }, { "R2C1", "R2C2", "R2C3" }, { "R3C1", "R3C2", "R3C3" } };
string choice;

void ComputerAI();
void BoardDisplay();
void PutInBoard(string &move);
void FirstCorner();
void FirstEdge();
string start;

int main(){

	cout << "Enter    "  ;
	cin >> start;

	cout << " We'll play a game of Tic-Tac-Toe.You go first. \n Place an X anywhere on the board. To choose where you want it to go, turn on caps lock and type this exactly or it won't work!: \n R#C# (row number, column number) And remember that there are only 3 rows and 3 columns." << endl;
	BoardDisplay();

	//Player's first Move
	cin >> choice;

	PutInBoard(choice);

	BoardDisplay();

	//Computer's first, first move
	

	
}

//Board's display function
void BoardDisplay(){
	cout << "___" << TicBoard[0][0] << "__|__" << TicBoard[0][1] << "__|__" << TicBoard[0][2] << "___" << endl;
	cout << "___" << TicBoard[1][0] << "__|__" << TicBoard[1][1] << "__|__" << TicBoard[1][2] << "___" << endl;
	cout << "   " << TicBoard[2][0] << "  |  " << TicBoard[2][1] << "  |  " << TicBoard[2][2] << "   " << endl << endl;
}

void ComputerAI(){
	// CHECKING BOARD CHECKING BOARD CHECKING BOARD CHECKING BOARD CHECKING BOARD
	// Still find it weird when it’s like this

	//Check Row 1
	if (TicBoard[0][0] == "_X__" && TicBoard[0][1] == "_X__" && TicBoard[0][2] != "_X__"){
		TicBoard[0][2] == "_O__";
	}
	else if (TicBoard[0][0] == "_X__" && TicBoard[0][1] != "_X__" && TicBoard[0][2] == "_X__"){
		TicBoard[0][1] == "_O__";
	}
	else if (TicBoard[0][0] != "_X__" && TicBoard[0][1] == "_X__" && TicBoard[0][2] == "_X__"){
		TicBoard[0][0] == "_O__";
	}


	//Check Row 2
	if (TicBoard[1][0] == "_X__" && TicBoard[1][1] == "_X__" && TicBoard[1][2] != "_X__"){
		TicBoard[0][2] == "_O__";
	}
	else if (TicBoard[1][0] == "__X__" && TicBoard[1][1] != "_X__" && TicBoard[1][2] == "_X__"){
		TicBoard[1][1] == "_O__";
	}
	else if (TicBoard[1][0] != "_X__" && TicBoard[1][1] == "_X__" && TicBoard[1][2] == "_X__"){
		TicBoard[1][0] == "_O__";
	}


	//Check Row 3
	if (TicBoard[2][0] == " X  " && TicBoard[2][1] == " X  " && TicBoard[2][2] != " X  "){
		TicBoard[2][2] == " O  ";
	}
	else if (TicBoard[2][0] == " X  " && TicBoard[2][1] != " X  " && TicBoard[2][2] == " X  "){
		TicBoard[2][1] == " O  ";
	}
	else if (TicBoard[2][0] != " X  " && TicBoard[2][1] == " X  " && TicBoard[2][2] == " X  "){
		TicBoard[2][0] == " O  ";
	}


	//Check Column 1
	if (TicBoard[0][0] == "_X__" && TicBoard[1][0] == "_X__" && TicBoard[2][0] != " X  "){
		TicBoard[2][0] == " O  ";
	}
	else if (TicBoard[0][0] == "_X__" && TicBoard[1][0] != "_X__" && TicBoard[2][0] == " X  "){
		TicBoard[1][0] == "_O__";
	}
	else if (TicBoard[0][0] != "_X__" && TicBoard[1][0] == "_X__" && TicBoard[2][0] == " X  "){
		TicBoard[0][0] == "_O__";
	}


	//Check Column 2
	if (TicBoard[0][1] == "_X__" && TicBoard[1][1] == "_X__" && TicBoard[2][1] != " X  "){
		TicBoard[2][1] == " O  ";
	}
	else if (TicBoard[0][1] == "X" && TicBoard[1][1] != "_X__" && TicBoard[2][1] == " X  "){
		TicBoard[1][0] == " O  ";
	}
	else if (TicBoard[0][1] != "_X__" && TicBoard[1][1] == "_X__" && TicBoard[2][1] == " X  "){
		TicBoard[0][1] == "_O__";
	}


	//Check Column 3
	if (TicBoard[0][0] == "_X__" && TicBoard[1][2] == "_X__" && TicBoard[2][2] != " X  "){
		TicBoard[2][2] == "  O  ";
	}
	else if (TicBoard[0][0] == "_X__" && TicBoard[1][2] != "_X__" && TicBoard[2][2] == " X  "){
		TicBoard[1][2] == " O  ";
	}
	else if (TicBoard[0][2] != "_X__" && TicBoard[1][2] == "_X__" && TicBoard[2][2] == " X  "){
		TicBoard[0][2] == "_O__";
	}
	//Check Diagonal 1
	if (TicBoard[0][0] == "X" && TicBoard[1][1] == "X" && TicBoard[2][2] != "X") {
		TicBoard[2][2] == " O  ";
	}
	else if (TicBoard[0][0] == "_X__" && TicBoard[1][1] != "_X__" && TicBoard[2][2] == " X  ") {
		TicBoard[1][1] == "_O__";
	}
	else if (TicBoard[0][0] != "_X__" && TicBoard[1][1] == "_X__" && TicBoard[2][2] == " X  ") {
		TicBoard[0][0] == "_O__";
	}

	//Check Diagonal 2
	if (TicBoard[0][2] == "_X__" && TicBoard[1][1] == "_X__" && TicBoard[2][0] != " X  ") {
		TicBoard[2][0] == " O  ";
	}
	else if (TicBoard[0][2] == "_X__" && TicBoard[1][1] != "_X__" && TicBoard[2][0] == " X  ") {
		TicBoard[1][1] == "_O__";
	}
	else if (TicBoard[0][2] != "_X__" && TicBoard[1][1] == "_X__" && TicBoard[2][0] == " X  ") {
		TicBoard[0][2] == "_O__";
	}

	//CHECKING BOARD CHECKING BOARD CHECKING BOARD CHECKING BOARD CHECKING BOARD

}
void FirstCorner(){
	if (choice == "R1C1"&&"R1C3"&&"R3C3"&&"R3C1"){
		BoardDisplay();
		TicBoard[1][1]=" O  ";
		
	}
	
	
}

void FirstEdge(){
	if (choice == "R1C2"&&"R2C1"&&"R2C3"&&"R3C2"){
		BoardDisplay();
		TicBoard[1][1] = " O  ";
	}

}


//Function for player's choice being inserted into board
void PutInBoard(string &move){

	if (move == "R1C1") TicBoard[0][0] = "_X__";
	if (move == "R1C2") TicBoard[0][1] = "_X__";
	if (move == "R1C3") TicBoard[0][2] = "_X__";
	if (move == "R2C1") TicBoard[1][0] = "_X__";
	if (move == "R2C2") TicBoard[1][1] = "_X__";
	if (move == "R2C3") TicBoard[1][2] = "_X__";
	if (move == "R3C1") TicBoard[2][0] = " X  ";
	if (move == "R3C2") TicBoard[2][1] = " X  ";
	if (move == "R3C3") TicBoard[2][2] = " X  ";
}


