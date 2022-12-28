#include<iostream>
#include<fstream>
#include <string>
#include <string.h>
#include <cmath>
#include <ctime>
#include <stdlib.h>
#include<vector>
using namespace std;
void enter();
void login();
void forget();
void Register();
void menu();
void member();
void member_back();
void display_all();
void search_by_name();
void delete_member();
void normal_menu();
void chicken_meals();
void price_chicken(int num, int q);
void pizza();
void price_pizza(int num, int q);
void desserts();
void desserts_prices(int num, int q);
void drinks();
void drinks_price(int num, int q);
void another_meal_or_drink();
void vegan_appetizers();
void apptizers_price(int num, int q);
void salads();
void salads_price(int num, int q);
void exit();
void account();
void exit_leader();
char name[200];
int main()
{
    cout << "Hello to Our Resturant " << endl;
    enter();
    return 0;
}
void enter()
{
    int choice;
    do
    {
        cout << endl << "*************************** Entery Page ***************************" << endl << endl;
        cout << "1)Login" << endl;
        cout << "2)Register" << endl;
        cout << "3)Forget Password" << endl;
        cout << "4)Exit" << endl;
        cout << "5)For Admins Only" << endl << endl << endl;
        cout << "Enter Your Choise : ";
        cin >> choice;
        switch (choice)
        {
        case 1:
            login();
            break;
        case 2:
            Register();
            break;
        case 3:
            forget();
            break;
        case 4:
            exit();
            break;
        case 5:
            member();
            break;
        default:
            cout << "Please Enter Number From the List " << endl;
            break;
        }
    } while (choice < 1 || choice >5);

}
void menu()
{
    cout << "----------------------------------------------------------------" << endl;
    cout << "************************ Resturnat Food ************************" << endl;
    cout << "----------------------------------------------------------------- " << endl << endl << endl;
    cout << "                         Menu                                     " << endl;
    cout << "------------                          -----------" << endl << endl;
    cout << " (1)chicken meals                      (4)appetizers" << endl << endl;
    cout << "   -chicken nagets                      -golden rolls      " << endl;
    cout << "   -chiken thighs                       -spring rolls      " << endl;
    cout << "   -roastchicken                        -mushu mushu       " << endl;
    cout << "   -chicken filet                       -pot stickers                  " << endl;
    cout << "   -chicken soap                        -drumstick         " << endl;
    cout << "                                               " << endl << endl;
    cout << " (2)salads                             (5)desserts         " << endl << endl;
    cout << "   -seaweed salad                       -choclate cake     " << endl;
    cout << "   -cheese salad                        -apple pie         " << endl;
    cout << "   -kelp salad                          -lemon cake        " << endl;
    cout << "   -kale salad                          -ice cream         " << endl << endl;
    cout << " (3)pizza meals                        (6)drinks           " << endl << endl;
    cout << "   -tona pizza                          -bottle of_pepsi     " << endl;
    cout << "   -cheese piazza                       -coca-cola         " << endl;
    cout << "   -hot_dog pizza                       -manga juice      " << endl;
    cout << "   -chicken pizza                       -orange juice  " << endl;
    cout << "   -meat pizza                          -cup of_tea   " << endl;
    cout << "                                        -bottle ofwater   " << endl;
    cout << "                                                       " << endl;
    cout << "Enter 0 to Back to Entery Page " << endl << endl;
    normal_menu();
}
void normal_menu()
{
    int number;
    do
    {
        cout << "Enter Your Choice : ";
        cin >> number;
        switch (number)
        {
        case 1:
            chicken_meals();
            break;
        case 2:
            salads();
            break;
        case 3:
            pizza();
            break;
        case 4:
            vegan_appetizers();
            break;
        case 5:
            desserts();
            break;
        case 6:
            drinks();
            break;
        case 0:
            enter();
            break;
        default:
            cout << "Please Enter a Number From the Options" << endl;
            break;
        }
    } while (number < 0 || number>6);
}
void chicken_meals()
{

    int number, num;
    cout << "----------------------------------------------------------------------" << endl;
    cout << "************************* Chicken Meals Menu *************************" << endl;
    cout << "----------------------------------------------------------------------" << endl << endl << endl;

    do
    {
        cout << "       Meals                   Prices" << endl;
        cout << "1)chicken nagets                20$" << endl;
        cout << "2)chiken thighs                 15$" << endl;
        cout << "3)roast chicken                 100$" << endl;
        cout << "4)chicken fliets                14$" << endl;
        cout << "5)chicken soap                  17$" << endl;
        cout << "6)Return Back " << endl << endl;
        cout << "Please Choose Number of Your Meal :   ";
        cin >> number;
    } while (number < 1 || number >6);
    if (number == 6)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        price_chicken(number, num);
    }
}
void price_chicken(int num, int q)
{

    int chicken[5] = { 20,15,100,14,17 };
    string chicken1[5] = { "chicken nagets","chiken thighs","roast chicken","chicken fliets","chicken soap" };
    fstream save("save.txt", ios::app | ios::out);
    save << chicken1[num - 1] << " " << chicken[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void salads()
{
    int number, num;
    cout << "-----------------------------------------------------------------" << endl;
    cout << "************************** Salads Menu **************************" << endl;
    cout << "-----------------------------------------------------------------" << endl << endl << endl;
    do
    {
        cout << "       meals               prices" << endl;
        cout << "1)seaweed salad             9,95$" << endl;
        cout << "2)cheese salad              11$"   << endl;
        cout << "3)kelp salad                12,96$"<< endl;
        cout << "4)kale salad                8.37$" << endl;
        cout << "5)Return Back " << endl << endl;
        cout << "Please Choose Number of Your Meal :  ";
        cin >> number;
    } while (number < 1 || number >5);
    if (number == 5)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        salads_price(number, num);
    }
}

void salads_price(int num, int q) {

    double salads[4] = { 9.95,11,12.96,8.37 };
    string salads1[4] = { "seaweed salad","cheese salad","kelp salad","kale salad" };
    fstream save("save.txt", ios::app | ios::out);
    save << salads1[num - 1] << " " << salads[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void pizza()
{

    int number, num;
    cout << "-----------------------------------------------------------------" << endl;
    cout << "***************************** Pizza Menu *****************************" << endl;
    cout << "-----------------------------------------------------------------" << endl << endl << endl;
    do
    {
        cout << "    meals               prices" << endl;
        cout << "1)tona pizza             40$   " << endl;
        cout << "2)cheese pizza           30$   " << endl;
        cout << "3)hot dog pizza          50$   " << endl;
        cout << "4)chicken pizza          60$   " << endl;
        cout << "5)meat pizza             70$   " << endl;
        cout << "6)Return Back " << endl << endl;
        cout << "Please Choose Number of Your Meal :  ";
        cin >> number;
    } while (number < 1 || number >6);
    if (number == 6)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        price_pizza(number, num);
    }
}
void price_pizza(int num, int q)
{

    int pizza[5] = { 40,30,50,60,70 };
    string pizza1[5] = { "tona pizza","cheese pizza","hot_dog pizza","chicken pizza","meat pizza" };
    fstream save("save.txt", ios::app | ios::out);
    save << pizza1[num - 1] << " " << pizza[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void vegan_appetizers()
{

    int number, num;
    cout << "------------------------------------------------------------------" << endl;
    cout << "************************* Apptizers Menu *************************" << endl;
    cout << "------------------------------------------------------------------" << endl << endl << endl;
    do
    {
        cout << "       meals               prices" << endl;
        cout << "1)golden rolls              6.50$" << endl;
        cout << "2)spring rolls              7.95$" << endl;
        cout << "3)mushu mushu               9.97$" << endl;
        cout << "4)pot stickers              7.56$" << endl;
        cout << "5)drumstick                 5.50$ " << endl;
        cout << "6)Return Back " << endl;
        cout << "Please Choose Number of Your Meal :  ";
        cin >> number;
    } while (number < 1 || number>6);
    if (number == 6)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        apptizers_price(number, num);
    }
}
void apptizers_price(int num, int q) {

    double apptizers[5] = { 6.50,7.95,9.97,7.56,5.50 };
    string apptizers1[5] = { "golden rolls","spring rolls","mushu mushu","pot stickers","drumstick" };
    fstream save("save.txt", ios::app | ios::out);
    save << apptizers1[num - 1] << " " << apptizers[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void desserts()
{

    int number, num;
    cout << "---------------------------------------------------------------------" << endl;
    cout << "*************************** Desserts Menu ***************************" << endl;
    cout << "---------------------------------------------------------------------" << endl << endl << endl;
    do
    {
        cout << "      desserts               prices" << endl;
        cout << "1)choclate cake               14$  " << endl;
        cout << "2)apple pie                   12$  " << endl;
        cout << "3)lemon cake                  16$  " << endl;
        cout << "4)ice cream                   13$  " << endl;
        cout << "5)cheese cake                 11$  " << endl;
        cout << "6)dan cakes                   17$  " << endl;
        cout << "7)Return Back " << endl << endl;
        cout << "Please Choose Number of Your Meal :  ";
        cin >> number;
    } while (number < 1 || number>7);
    if (number == 7)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        desserts_prices(number, num);
    }
}
void desserts_prices(int num, int q) {

    double desserts[6] = { 14,12,16,13,11,17 };
    string desserts1[6] = { "choclate cake","apple pie","lemon cake","ice cream","cheese cake" ,"dan cakes" };
    fstream save("save.txt", ios::app | ios::out);
    save << desserts1[num - 1] << " " << desserts[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void drinks()
{

    int number, num;
    cout << "-------------------------------------------------------------------" << endl;
    cout << "*************************** Drinks Menu ***************************" << endl;
    cout << "-------------------------------------------------------------------" << endl << endl << endl;
    do
    {
        cout << "     drinks               prices" << endl;
        cout << "1)botlle of_pepsi           4$ " << endl;
        cout << "2)coca cola                 5$ " << endl;
        cout << "3)manga juice               10$" << endl;
        cout << "4)orange juice              8$ " << endl;
        cout << "5)cup of tea                4$ " << endl;
        cout << "6)bottle of water           2$ " << endl;
        cout << "7)Return Back " << endl << endl;
        cout << "Please Choose Number of Your Meal :  ";
        cin >> number;
    } while (number < 1 || number>7);
    if (number == 7)
        menu();
    else{
        cout << "Please Enter The Quantity  :   ";
        cin >> num;
        drinks_price(number, num);
    }
}
void drinks_price(int num, int q) {

    int drinks[6] = { 4,5,10,8,4,2 };
    string drinks1[6] = { "botlle of_pepsi","coca cola","manga juice","orange juice","cup of_tea","bottle of_water" };
    fstream save("save.txt", ios::app | ios::out);
    save << drinks1[num - 1] << " " << drinks[num - 1] << " " << q << endl;
    another_meal_or_drink();
}
void another_meal_or_drink()
{
    string n;
    do
    {
        cout << "Do you want Another meal ?? write (yes or no) : ";
        cin >> n;
        cout<<endl;
    } while (n != "yes" && n != "no" && n != "YES" && n != "NO");
    if ((n == "yes") || (n == "YES"))
        menu();
    else if ((n == "no") || (n == "NO"))
        account();
}
void account()
{
    system("cls");
    fstream save("save.txt", ios::in | ios::app);
    string s, s1;
    double x1, x2;
    double sum = 0;
    cout << "                         Online Restaurant                     " << endl;
    cout << "                         -----------------" << endl;
    cout << "Date : Dec 26 2022" << endl;
    cout << "your name : " << name << endl;
    cout << "----------------------------------------------------------------------------" << endl;
    cout << "Items                  Price                 Quantity                  Total" << endl;
    cout << "----------------------------------------------------------------------------" << endl;
    while (save >> s >> s1)
    {
        save >> x1 >> x2;
        cout << s << " " << s1 << "\t\t" << x1 << "$" << "\t\t\t" << x2 << "\t\t\t" << x1 * x2<<"$" << endl;
        cout << "----------------------------------------------------------------------------" << endl;
        sum += (x1 * x2);
    }
    cout << "----------------------------------------------------------------------------" << endl;
    cout << "Sub Total                                                               " << sum <<"$"<< endl;
    double discount = (sum * 10.0) / 100.0;
    cout << "Discount 10%                                                            " << discount<<"$" << endl;
    cout << "----------------------------------------------------------------------------" << endl;
    cout << "Net Total                                                               " << sum - discount<<"$" << endl << endl << endl;
    cout << "Choose From Options : "<<endl;
    cout <<"1)Back to Menu "<<endl;
    cout <<"2)Exit "<<endl;
    cout << "Your Choice : ";
    int x;
    cin >> x;
    switch (x)
    {
    case 1:
        menu();
        break;
    case 2:
        exit();
        break;
    default:
        break;
    }
}
void member()
{

    int number;
    cout << "-----------------------------------------------------------------" << endl;
    cout << "**************************** Members ****************************" << endl;
    cout << "-----------------------------------------------------------------" << endl;
    do
    {
        cout << "1)Display all members " << endl;
        cout << "2)Search about member by name " << endl;
        cout << "3)Delete memeber " << endl;
        cout << "4)Return Back" << endl;
        cout << "5)Exit " << endl;
        cout << "Enter Your Choice : ";
        cin >> number;
    } while (number < 1 || number>5);
    switch (number)
    {
    case 1:
        display_all();
        break;
    case 2:
        search_by_name();
        break;
    case 3:
        delete_member();
        break;
    case 4:
        enter();
        break;
    case 5:
        exit();
        break;
    default:
        break;
    }
}
void Register()
{

   cout << "------------------------ Register Page --------------------------" << endl;
    string name;
    string pass, new_pass;
    cin.ignore(1, '\n');
    cout << "Enter Your Name : ";
    getline(cin, name);
    l:
    cout << "Enter Your Password : ";
    cin >> pass;
    int x=pass.size();
    if(x<8)
    {
        cout<<endl<<"Your Password Must Contain at least 8 (Numbers or Characters) , Enter Your Password Again "<<endl<<endl;
        goto l;
    }
    cout << "Please Enter Your Password Again : ";
    cin >> new_pass;
    while (pass != new_pass)
    {
        cout << "Two Password Not Equal Please Try Again" << endl << "Enter Your Password : ";
        cin >> pass;
        cout << " Enter Your Password : ";
        cin >> new_pass;
    }

    ofstream f2("team.txt", ios::app);
    f2 << name << "|" << pass << endl;
    cout << "                regustration is succesful                    " << endl << endl << endl;
    login();
}
void login()
{

    ofstream save("save.txt");
    save.close();
    cout << endl << endl << "------------------------ login page --------------------------" << endl << endl;
    char name2[200];
    int p = 0;
    char pass2[200];
    char pass[200];
    cin.ignore(1, '\n');
    cout << "Enter Your Name : ";
    cin.getline(name, 200);
    cout << "Enter Your Password : ";
    cin >> pass;
    ifstream file;
    file.open("team.txt");
    while (!file.eof())
    {
        file.getline(name2, 200, '|');
        file.getline(pass2, 200);
        if (strcmp(name, name2) == 0 && strcmp(pass, pass2) == 0)
        {
            p = 1;
            break;
        }
    }
    file.close();
    if (p == 1)
    {
        int c;
        cout << "                           Sucessful Login                      " << endl << endl << endl;
        do {
            cout << "1)Show Menu" << endl << "2)Logout" << endl;
            cout << "Enter Your Choice from Options : ";
            cin >> c;
            if (c == 1)
                menu();
            else if (c == 2)
                exit();
        } while (c < 1 || c > 2);
    }
    else
    {
        cout << "Error!" << endl;
        enter();
    }
}
void display_all()
{
    char name[200];
    char pass[200];
    ifstream file;
    file.open("team.txt");
    cout <<"\nName\t\t"<<"Password \n";
    while (file.getline(name, 200, '|'))
    {
        file.getline(pass, 200);
        cout << '\n' << name << "\t\t";
        cout <<pass << "\t\n\n";
    }
    file.close();
    member_back();
}
void search_by_name()
{
    string search, line;
    int offset;
    int p=0;
    ifstream myfile;
    myfile.open("team.txt");
    cin.ignore();
    cout << "Type the Name what You Want to Search : ";
    getline(cin, search);
    cout<<endl;
    if (myfile.is_open())
    {
        while (!myfile.eof())
        {
            getline(myfile, line);
            if ((offset = line.find(search, 0)) != string::npos)
            {
                p=1;
            }

        }
        myfile.close();
    }
    if(p==1)
    {
        cout << "This Name has been Founded" << endl<<endl<<endl;
        member_back();
    }
    else
    {
        cout<<"This Name has not been founded"<<endl<<endl<<endl;
        member_back();
    }

    system("PAUSE");
    member_back();
}
void forget()
{

    char name[200], n[200];
    char pass[200];
    int p = 0;
    cin.ignore();
    ifstream file("team.txt");
    cout << "Enter Your User name to Search for Your Password : ";
    cin.getline(n, 200);
    while (!file.eof())
    {
        file.getline(name, 200, '|');
        file.getline(pass, 200);
        if (strcmp(name, n) == 0)
        {
            p = 1;
            break;
        }
    }
    if (p == 1)
    {
        cout << "Your Name : " << name << endl << endl;
        cout << "Your Password : " << pass << endl << endl;
    }
    else
        cout << endl << endl << "                This Name Does not Exist                   " << endl << endl;
    cout <<"Choose From Options : "<<endl;
    cout <<"1)Back to Menu "<<endl;
    cout <<"2)Exit "<<endl;
    cout << "Your Choice : ";
    int x;
    cin >> x;
    while (x < 1 || x>2)
    {
        cout <<"Choose From Options : "<<endl;
        cout << "Your Choice : ";
        cin >> x;
    }
    switch (x)
    {
    case 1:
        enter();
        break;
    case 2:
        exit();
        break;
    default:
        break;
    }

}
void delete_member()
{
    int p=0;
    fstream note;
    fstream file;
    note.open("note.txt", ios::out);
    file.open("team.txt", ios::in);
    char name[200];
    char pass[200];
    char name2[200];
    char pass2[200];
    cin.ignore();
    cout << "Enter Name : ";
    cin.getline(name, 200);
    cout << "Enter Password : ";
    cin.getline(pass, 200);
    while (!file.eof())
    {
        file.getline(name2, 200, '|');
        file.getline(pass2, 200);
        if (strcmp(name, name2) == 0 && strcmp(pass, pass2) == 0) {
            p=1;
            continue;
        }
        else {
            note << name2 << '|' << pass2 << endl;
        }
    }
    file.close();
    note.close();
    file.open("team.txt", ios::out);
    note.open("note.txt", ios::in);
    while (!note.eof())
    {
        note.getline(name2, 200, '|');
        note.getline(pass2, 200);
        file << name2 << '|' << pass2 << endl;
    }
    if(p==1)
        cout << "Account has been removed";
    else
        cout<< "Account Does not Exist";
    file.close();
    note.close();
    remove("note.txt");
    cout << endl << endl;
    member_back();
}
void member_back() {

    cout <<"Choose From Options : "<<endl;
    cout <<"1)Back to Menu "<<endl;
    cout <<"2)Exit "<<endl;
    cout << "Your Choice : ";
    int x;
    cin >> x;
    while (x < 1 || x>2)
    {
        cout <<"Choose From Options : "<<endl;
        cout << "Your Choice : ";
        cin >> x;
    }
    switch (x)
    {
    case 1:
        member();
        break;
    case 2:
        exit_leader();
        break;
    default:
        break;
    }
}
void exit(){
    cout << "Thank You That You Orderd From Our Resturant \n Have a Nice day" << endl;
}
void exit_leader(){
    cout<<"                    Goodbye"<<endl;
}
