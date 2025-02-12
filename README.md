// bai tong hop.cpp : This file contains the 'main' function. Program execution begins and ends there.
//

#include <iostream>
#include <cmath>
#include <vector>
#include <unordered_map>

using namespace std;
void case1() {
    char strHello[100] = "Xin chao";
    cout << strHello;
    cout << "\n";   
}
void bai2() {
    int int9 = 9;
    int int8 = 8;
    cout << "Ket qua phep cong 9 + 8 la: " << int9 + int8;
    cout << "\n";
}
void bai3() {
    char strTenNguoiDung[100];
    cout << "Nhap vao ten nguoi dung: ";
    cin >> strTenNguoiDung;
    cout << "Ten nguoi dung: " << strTenNguoiDung << "\n";
}
void bai4() {
    int intSo1, intSo2;
    cout << "Nhap vo so thu nhat";
    cin >> intSo1;
    cout << "Nhaop vo so thu hai";
    cin >> intSo2;
    cout << "tong cua hai so";
    cout << intSo1 + intSo2;
    cout << "\n";
}
void bai5() {
    int intSo1 = 10;
    int intSo2 = 100;

    int temp = intSo1;
    intSo1 = intSo2;
    intSo2 = temp;

    cout << "So sau khi hoan doi";
    cout << "So 1" << intSo1 << endl;
    cout << "So 2" << intSo2 << endl;
}
void bai6() {
    float flA;
    float flB;
    cout << "Nhap so float thu nhat: ";
    cin >> flA;
    cout << "Nhap so float thu hai: ";
    cin >> flB;
    cout << "Tong 2 so float: " << flA + flB << "\n";
    cout << "Hieu 2 so float: " << flA - flB << "\n";
    cout << "Tich 2 so float: " << flA * flB << "\n";
    cout << "Thuong 2 so float: " << flA / flB;
    cout << "\n";
}
void bai7() {
    float flA, flB, flC, flMin, flMax;

    cout << "Nhap so A: ";
    cin >> flA;
    cout << "Nhap so B: ";
    cin >> flB;
    cout << "Nhap so C: ";
    cin >> flC;

    flMin = flA;
    flMax = flA;

    if (flMin > flB) {
        flMin = flB;
    }
    if (flMin > flC) {
        flMin = flC;
    }
    if (flMax < flB) {
        flMax = flB;
    }
    if (flMax < flC) {
        flMax = flC;
    }
    cout << "So be nhat la: " << flMin << endl;
    cout << "So lon nhat la: " << flMax;
    cout << "\n";
}
bool isPrime(int n) {
    if (n <= 1) {
        return false;
    }
    if (n <= 3) {
        return true;
    }
    if (n % 2 == 0 || n % 3 == 0) {
        return false;
    }

    for (int i = 5; i * i <= n; i += 6) {
        if (n % i == 0 || n % (i + 2) == 0) {
            return false;
        }
    }

    return true;
}
void bai8() {
    int n;
    float flResult = 0;
    float flInput = 0;
    cout << "Nhap vao so n(n < 100): ";
    cin >> n;

    for (int i = 0; i < n; i++) {
        int intPos = i + 1;
        cout << "Nhap so thu " << intPos << ": ";
        cin >> flInput;
        flResult = flResult + flInput;
    }
    cout << "Trung binh cong: " << flResult / n;
    cout << "\n";
}
void bai9() {
    float a, b, c;
    float flChuvi, fldientich;
    cout << " nhap canh a";
    cin >> a;
    cout << "nhap canh b";
    cin >> b;
    cout << "nhap canh c";
    cin >> c;
    if ((a + b > c) && (a + c > b) && (b + c > a)) {
        flChuvi = a + b + c;
        float flnuachuvi = flChuvi / 2;
        fldientich = sqrt(flnuachuvi * (flnuachuvi - a) * (flnuachuvi - b) * (flnuachuvi - c));
        cout << "Chu vi: " << flChuvi << endl;
        cout << " Dien tich: " << fldientich << endl;
    }
    else {
        cout << " khong phai tam giac \n";
    }
}
void bai10() {
    float a, b, c, delta;
    cout << "nhap so a";
    cin >> a;
    cout << "nhap so b";
    cin >> b;
    cout << "nhap so c";
    cin >> c;
    delta = b * b - 4 * a * c;
    if (a == 0) {
        cout << "khong phai phuong trinh bac 2 " << endl;
    }
    else {
        delta = b * b - 4 * a * c;
        if (delta < 0) {
            cout << "Phuong trinh vo nghiem." << endl;
        }
        else if (delta == 0) {
            delta = delta = -b / (2 * a);
            cout << "Phuong trinh co nghiem kep: x1 = x2 = " << delta << endl;
        }
        else {
            delta = (-b + sqrt(delta)) / (2 * a);
            delta = (-b - sqrt(delta)) / (2 * a);
            cout << "Phuong trinh co hai nghiem phan biet:" << endl;
            cout << "x1 = " << delta << endl;
            cout << "x2 = " << delta << endl;
        }
    }
}

vector<int> twoSum(const vector<int>& nums, int target) {
    unordered_map<int, int> numMap; 
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (numMap.find(complement) != numMap.end()) {
            return { numMap[complement] + 1, i + 1 }; 
        }
        numMap[nums[i]] = i;
    }
    return {}; 
}

int main()
{
    int intInput;
    bool isRunning = true;

    while (isRunning) {
        cout << "Nhap vao menu tuong ung: " << "\n";
        cout << "1: Bai 1" << "\n";
        cout << "2: Bai 2" << "\n";
        cout << "3: Bai 3" << "\n";
        cout << "4: Bai 4" << "\n";
        cout << "5: Bai 5" << "\n";
        cout << "6: Bai 6" << "\n";
        cout << "7: Bai 7" << "\n";
        cout << "8: Bai 8" << "\n";
        cout << "9: Bai 9" << "\n";
        cout << "10: Bai 10" << "\n";
        cout << "11: Bai 11" << "\n";
        cout << "12: Bai 12" << "\n";
        cout << "13: Bai 13" << "\n";
        cout << "14: Bai 14" << "\n";
        cout << "0: Thoat" << "\n";

        cin >> intInput;

        switch (intInput) {
        case 1: {
            case1();
            break;
        }
        case 2: {
            bai2();
            break;
        }
        case 3: {
            bai3();
            break;
        }
        case 4: {
            bai4();
            break;
        }
        case 5: {
            bai5();
            break;
        }
        case 6: {
            bai6();
            break;
        }
        case 7: {
            bai7();
            break;
        }
        case 8: {
            bai8();
            break;
        }
        case 0: {
            isRunning = false;
            break;
        }
        case 9: {
            bai9();
            break;
        }
        case 10: {
            bai10();
            break;
        }
        case 11: {
            int n;

            cout << " nhap so nguyen duong n ";
            cin >> n;

            for (int i = 1; i <= n; i++) {
                for (int j = 1; j <= i; j++) {
                    cout << j << " ";
                }
                cout << endl;
                break;
            }
        case 12: {
            int n;
            cout << "Nhap so nguyen duong n: ";
            cin >> n;

            if (isPrime(n)) {
                cout << n << " la so nguyen to." << endl;
            }
            else {
                cout << n << " khong phai la so nguyen to." << endl;
            }

            return 0;
        }
        case 13: {
            vector<int> nums;
            int n, target;

            cout << "Nhap so phan tu cua mang: ";
            cin >> n;

            cout << "Nhap cac phan tu cua mang: ";
            for (int i = 0; i < n; i++) {
                int num;
                cin >> num;
                nums.push_back(num);
            }

            cout << "Nhap gia tri target: ";
            cin >> target;

            vector<int> result = twoSum(nums, target);

            if (!result.empty()) {
                cout << "Vi tri cua hai so co tong bang target: [" << result[0] << ", " << result[1] << "]" << endl;
            }
            else {
                cout << "Khong co cap so nao trong mang co tong bang target." << endl;
            }

            return 0;
        }
        }
        case 14: {
            vector<int> nums = { 3,1,2,10,1 };
            vector<int> numsResult; 

            int sum = 0;
            for (int i = 0; i < nums.size(); i++) {
                sum += nums[i];
                numsResult.push_back(sum);
            }
            cout << " numsResult = [ ";
            for (int i = 0; i < numsResult.size(); i++) {
                cout << numsResult[i];
                if (i < numsResult.size() - 1) {
                    cout << " , ";
                }
            }
            cout << " ] " << endl;
            return 0;
        }
        }
    }
}

// Run program: Ctrl + F5 or Debug > Start Without Debugging menu
// Debug program: F5 or Debug > Start Debugging menu

// Tips for Getting Started: 
//   1. Use the Solution Explorer window to add/manage files
//   2. Use the Team Explorer window to connect to source control
//   3. Use the Output window to see build output and other messages
//   4. Use the Error List window to view errors
//   5. Go to Project > Add New Item to create new code files, or Project > Add Existing Item to add existing code files to the project
//   6. In the future, to open this project again, go to File > Open > Project and select the .sln file
