Ceaser cipher

#include <iostream>
#include <string>
using namespace std;

int main() {
    int shift;
    string text;

    cout << "Enter the name: ";
    getline(cin, text);

    shift = 3;
    string encryptedText = "";

    for (int i = 0; i < text.length(); i++) {
        char ch = text[i];

        if (isupper(ch)) {
            ch = (ch - 'A' + shift) % 26 + 'A';
        } else if (islower(ch)) {
            ch = (ch - 'a' + shift) % 26 + 'a';
        }

        encryptedText = encryptedText + ch;
    }

    cout << "\n";
    cout << "Encrypted Name: " << encryptedText << endl;

    string decryptedText = "";

    for (int i = 0; i < encryptedText.length(); i++) {
        char ch = encryptedText[i];

        if (isupper(ch)) {
            ch = (ch - 'A' - shift + 26) % 26 + 'A';
        } else if (islower(ch)) {
            ch = (ch - 'a' - shift + 26) % 26 + 'a';
        }

        decryptedText += ch;
    }

    cout << "\n";
    cout << "Decrypted Name: " << decryptedText << endl;

    return 0;
}

Modified Ceaser cipher 

#include <iostream>
#include <string>
using namespace std;

int main() {
    string text;
    int key;

    cout << "Enter your name: ";
    getline(cin, text);

    cout << "Enter key: ";
    cin >> key;

    string encryptedText = "";

    for (int i = 0; i < text.length(); i++) {
        char ch = text[i];
        if (isupper(ch)) {
            ch = (ch - 'A' + key) % 26 + 'A';
        } else if (islower(ch)) {
            ch = (ch - 'a' + key) % 26 + 'a';
        }
        encryptedText = encryptedText + ch;
    }

    cout << "\n";
    cout << "Encrypted Name: " << encryptedText << endl;

    string decryptedText = "";
    for (int i = 0; i < encryptedText.length(); i++) {
        char ch = encryptedText[i];
        if (isupper(ch)) {
            ch = (ch - 'A' - key + 26) % 26 + 'A';
        } else if (islower(ch)) {
            ch = (ch - 'a' - key + 26) % 26 + 'a';
        }
        decryptedText = decryptedText + ch;
    }

    cout << "\n";
    cout << "Decrypted Name: " << decryptedText << endl;
}

Stream cipher 

#include <iostream>
#include <string>
using namespace std;

int main() {
    string plaintext;
    char key;

    cout << "Enter the plaintext: ";
    getline(cin, plaintext);

    cout << "Enter the key: ";
    cin >> key;

    string encryptedText;
    string decryptedText;

    for (int i = 0; i < plaintext.length(); i++) {
        char c = plaintext[i];
        c = c ^ key;
        encryptedText += c;
    }

    cout << "Encrypted Text: " << encryptedText << endl;

    for (int i = 0; i < encryptedText.length(); i++) {
        char c = encryptedText[i];
        c = c ^ key;
        decryptedText += c;
    }

    cout << "Decrypted Text: " << decryptedText << endl;
    return 0;
}

Block cipher 

#include <iostream>
#include <string>
#include <bitset>

using namespace std;

int main() {
    string plaintext;
    string key;

    cout << "Enter the plain text: ";
    getline(cin, plaintext);

    cout << "Enter the key: ";
    getline(cin, key);

    string encryptedText;

    for (int i = 0; i < plaintext.length(); i += 4) {
        string block = plaintext.substr(i, 4);

        while (block.length() < 4) {
            block += ' ';
        }

        string encryptedBlock;
        for (int j = 0; j < 4; j++) {
            char c = block[j] ^ key[j];
            encryptedBlock += c;
        }

        encryptedText += encryptedBlock;
    }

    string decryptedText;
    for (int i = 0; i < encryptedText.length(); i += 4) {
        string block = encryptedText.substr(i, 4);

        string decryptedBlock;
        for (int j = 0; j < 4; j++) {
            char c = block[j] ^ key[j];
            decryptedBlock += c;
        }

        decryptedText += decryptedBlock;
    }

    cout << "Decrypted Text: " << decryptedText << endl;

    return 0;
}

Playfair cipher 
