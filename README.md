#include <fstream.h>

#include <iostream.h>

#include <conio.h>

void main() {

    clrscr();

    char filename[50];

    cout << "Enter filename: ";

    cin >> filename;

    // Create and write to file

    ofstream file(filename);

    if (!file) {

        cout << "Unable to create file.";

        getch();

        return;

    }

    cout << "Enter text to write to file: ";

    char text[100];

    cin.ignore();

    cin.getline(text, 100);

    file << text;

    file.close();

    // Read from file

    ifstream readFile(filename);

    if (!readFile) {

        cout << "Unable to open file for reading.";

        getch();

        return;

    }

    cout << "File contents:" << endl;

    char ch;

    while (readFile.get(ch)) {

        cout << ch;

    }

    readFile.close();

    getch();

}
