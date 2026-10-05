// Online C++ compiler (editor)
// Write and run C++ online using this editor.

#include <iostream>
using namespace std;

// Fungsi decimal ke binary
void decimalToBinary(int decimal) {
    int binary[32];
    int i = 0;

    if (decimal == 0) {
        cout << "Your binary is: 0" << endl;
        return;
    }

    while (decimal > 0) {
        binary[i] = decimal % 2;
        decimal = decimal / 2;
        i++;
    }

    cout << "Your binary is: ";

    for (int j = i - 1; j >= 0; j--) {
        cout << binary[j];
    }

    cout << endl;
}

// Fungsi binary ke decimal
int binaryToDecimal(long long binary) {
    int decimal = 0;
    int base = 1;

    while (binary > 0) {
        int digit = binary % 10;

        decimal += digit * base;
        base *= 2;
        binary /= 10;
    }

    return decimal;
}

int main() {
    int option;
    int decimal;
    long long binary;
    int repeat;

    do {
        cout << "[1] Decimal to binary" << endl;
        cout << "[2] Binary to decimal" << endl;

        cout << "Input your option: ";
        cin >> option;

        if (option == 1) {
            cout << "Input your decimal: ";
            cin >> decimal;

            decimalToBinary(decimal);
        }
        else if (option == 2) {
            cout << "Input your binary: ";
            cin >> binary;

            cout << "Your decimal is: "
                 << binaryToDecimal(binary) << endl;
        }
        else {
            cout << "Invalid option!" << endl;
        }

        cout << "Repeat? [0:No/1:Yes]: ";
        cin >> repeat;

        cout << endl;

    } while (repeat == 1);

    cout << "Program ends" << endl;

    return 0;
}
