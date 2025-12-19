# UAMS-CODE-2
This Is My Uams Code Ypu can use it for help in Your studies
#include <iostream>
#include <conio.h>
#include <fstream>
using namespace std;

void uams();
void Main_Menu();
void Add_Student();
void View_Record();
void Update_Record();
void delete_Record();
void Admin_login();
void Save_Data_To_File();
void Load_Data_From_File();

string name[100];
string Cnic[100];
int roll_No[100];
float Matric_marks[100];
float Inter_Marks[100];
string section[100];
int Total_Students = 0;

int main()
{
    system("color 01");
    Load_Data_From_File();
    int press;
    Admin_login();
    while (true)
    {
        system("cls");

        uams();
        Main_Menu();
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        cout << "@@  Enter Option     :   @@ \n";
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        cin >> press;
        system("cls");
        if (press == 1)
        {
            cout << "\n--- Add Student Record ---\n";
            uams();
            Add_Student();
        }
        else if (press == 2)
        {
            uams();
            delete_Record();
        }
        else if (press == 3)
        {
            uams();
            View_Record();
        }
        else if (press == 4)
        {

            uams();
            cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
            cout << "@@  ______________________________________________________________________________________________________________  @@\n";
            cout << "@@||                                                                                                              ||@@\n";
            cout << "@@|| >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>> Update Student Record <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<  ||@@\n";
            cout << "@@||______________________________________________________________________________________________________________||@@\n";
            cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
            Update_Record();
        }
        else if (press == 5)
        {
            system("cls");
            break;
        }
        else
        {
            cout << "\n>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>  Invalid Input! Please restart and press 1 next time  <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<\n";
        }
    }

    return 0;
}

void Admin_login()
{
    system("cls");
    string user;
    string pass;

    string User_Name = "Ali_Abdullah";
    string Password = "CS_2025";

    uams();

    cout << "          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
    cout << "        @@@@@@@@@@@@@@        _____________________________________________________    @@@@@@@@@@@@@@@\n";
    cout << "    @@@@@@@@@@@@@@           ||  >>>>>>>>>>  A D M I N   M E N U   <<<<<<<<<<<   ||        @@@@@@@@@@@@@@@@\n";
    cout << "        @@@@@@@@@@@@@@                                                                 @@@@@@@@@@@@@@@\n";
    cout << "          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";

    cout << "\n\n";
    cout << "_________________________________________\n";
    cout << "|| ~~~~~~~~~ Enter Username ~~~~~~~ >> ||  : ";
    cin >> user;

    cout << "_______________________________________\n";
    cout << "|| ~~~~~~ Enter Password ~~~~~~~~ >> || : ";
    cin >> pass;

    if (user == User_Name && pass == Password)
    {
        cout << "\n  >>>>>>>>>>>>>>> Login Successful! <<<<<<<<<<<<<<<<<<<< \n";
        getch();
    }
    else
    {
        cout << "\n  >>>>>>>>>>>>>>>>>>>>>> Incorrect Username or Password! <<<<<<<<<<<<<<<<<<<<<<< \n";
        getch();
        exit(0);
    }
}

void uams()
{
    system("cls");
    cout << " \n\n\n";
    cout << "         ____________________________________________________________________________________________________________\n";
    cout << "        |                                                                                                            |\n";
    cout << "        |   |^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^|  |\n";
    cout << "        |   |  |***********************************************************************************************|  |  |\n";
    cout << "        |   |  |         _____      _____        ____         _____          ______          _____             |  |  |\n";
    cout << "        |   |  |        |:::::|    |:::::|     _|:::::|_      |::: \\        /::::: |        |:::::|_           |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |:::| |:::|     |:::::\\      /:::::: |      |:::| |:::|          |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |::|   |::|     |::::::\\    /::::::: |     |:::|_  |_|           |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |::|   |::|     |:::| |:\\  /::|  |:::|     |::::|___             |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |:::::::::|     |:::|    |_|     |:::|        |::::::|_          |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |::|   |::|     |:::|            |:::|       __   |::::|         |  |  |\n";
    cout << "        |   |  |         |:::|      |:::|     |::|   |::|     |:::|            |:::|      |:.|   |::::|        |  |  |\n";
    cout << "        |   |  |          |:::|    |:::|      |::|   |::|    _|:::|_          _|:::|_      |:::|___|:::|       |  |  |\n";
    cout << "        |   |  |             |:::::::|       |::::| |::::|  |:::::::|        |:::::::|      |:::::::|          |  |  |\n";
    cout << "        |   |  |                                                                                               |  |  |\n";
    cout << "        |   |  |            University         Admission            Management               System            |  |  |\n";
    cout << "        |   |  |                                                                                               |  |  |\n";
    cout << "        |   |  |                                                                                               |  |  |\n";
    cout << "        |   |  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^    |  |\n";
    cout << "        |   *******************************************************************************************************  |\n";
    cout << "        |____________________________________________________________________________________________________________|\n";
    cout << " \n\n\n";
}

void Add_Student()
{

    if (Total_Students >= 100)
    {
        cout << "\n>>>>>>>>>>>>>>>>>>>>>>>>>>>. Limit Reached <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<< \n";
        getch();
        return;
    }
    cin.ignore();
    cout << " ~~~~~~~~~~~~~~~~ Enter Student Name ~~~~~~~~~~~~~~ >>> :     ";
    getline(cin, name[Total_Students]);
    cout << "********************** Enter Cnic  ******************** :     ";
    cin >> Cnic[Total_Students];
    cout << "~~~~~~~~~~~~~~~~~~~~ Enter Roll Number ~~~~~~~~~~~~ >>> :     ";
    cin >> roll_No[Total_Students];
    cout << " >>>>>>>>>>>>>>>>> Enter Matric  Marks >>>>>>>>>>>>>>>> :     ";
    cin >> Matric_marks[Total_Students];
    cout << ">>>>>>>>>>>>>>>>>> Enter Inter Marks >>>>>>>>>>>>>>>>>> :     ";
    cin >> Inter_Marks[Total_Students];
    cout << ">>>>>>>>>>>>>>>>>>  Enter section >>>>>>>>>>>>>>>>>>>>> :     ";
    cin >> section[Total_Students];
    cout << "\n >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>> Returning to Main Menu <<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<< \n\n";
    Total_Students++;
    Save_Data_To_File();
    getch();
}
void View_Record()

{
    if (Total_Students == 0)
    {
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        cout << "@@  No Student Record Found    @@\n";
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        getch();
        return;
    }

    for (int i = 0; i < Total_Students; i++)
    {
        cout << "\n >>>>> Student Details <<<<<<<<<<< \n";
        cout << "Student     : " << i + 1 << endl;
        cout << "Name        : " << name[i] << endl;
        cout << "CNIC        : " << Cnic[i] << endl;
        cout << "Roll No     : " << roll_No[i] << endl;
        cout << "Matric Marks: " << Matric_marks[i] << endl;
        cout << "Inter Marks : " << Inter_Marks[i] << endl;
        cout << "Section     : " << section[i] << endl;
    }
    getch();
}

void Main_Menu()
{

    cout << " ________________________________________________________________________________________\n";
    cout << "||_______________________________________________________________________________________||\n";
    cout << "||                                                                                       ||\n";
    cout << "||                         @@@@@@@@@@@@@@@@@@@@@@@@@@@                                   ||\n";
    cout << "||            @@@@@@@@@@@@@@@@@@@@@ MAIN MENU @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@         ||\n";
    cout << "||                        @@@@@@@@@@@@@@@@@@@@@@@@@@@@                                   ||\n";
    cout << "||_______________________________________________________________________________________||\n";
    cout << "||_______________________________________________________________________________________||\n";
    cout << "1. Add Student Record\n";
    cout << "2. Delete Student record\n";
    cout << "3. View Record\n";
    cout << "4. Update Record\n";
    cout << "5. Exit\n";
}
void Update_Record()
{
    if (Total_Students == 0)
    {
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        cout << "@@  No Student Record Found    @@\n";
        cout << "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        getch();
        return;
    }

    int Search_Roll_NO;
    cout << "\n~~~~~~~~~~~ Enter Roll Number to Update ~~~~~~~~~~~~~>>>>>  : ";
    cin >> Search_Roll_NO;

    int index = -1;

    for (int i = 0; i < Total_Students; i++)
    {
        if (roll_No[i] == Search_Roll_NO)
        {
            index = i; // store the found index
        }
    }

    if (index == -1) // if not found
    {
        cout << " @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        cout << " @@  Student Not Found!         @@\n";
        cout << " @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@\n";
        getch();
        return;
    }

    cin.ignore(); // clear Trash or Garbage values from the input buffers
    cout << "\n~~~~~~~~~~~~~ Enter New Student Name ~~~~~~~~~~~~~ >>> : ";
    getline(cin, name[index]);
    cout << "********************** Enter New CNIC ******************** : ";
    cin >> Cnic[index];
    cout << "~~~~~~~~~~~~~~~~~~~~ Enter New Roll Number ~~~~~~~~~~~~ >>> : ";
    cin >> roll_No[index];
    cout << " >>>>>>>>>>>>>>>>> Enter New Matric Marks >>>>>>>>>>>>>>>> : ";
    cin >> Matric_marks[index];
    cout << ">>>>>>>>>>>>>>>>>> Enter New Inter Marks >>>>>>>>>>>>>>>>>> : ";
    cin >> Inter_Marks[index];
    cout << ">>>>>>>>>>>>>>>>>>  Enter New Section >>>>>>>>>>>>>>>>>>>>> : ";
    cin >> section[index];
    cout << "\n >>>>>>>>>>>>>>>>>>> Student Record Updated Successfully <<<<<<<<<<<<<<<<<<\n";
    Save_Data_To_File();
    getch();
}

void delete_Record()
{
    if (Total_Students == 0)
    {

        cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                        \n";
        cout << "                 @@@@@@@@@@@@@@@@@@@@@ No student  Data to Delete @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@             \n";
        cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                       \n";
        getch();
        return;
    }

    int Search_Roll_NO;
    cout << " \n~~~~~~~~~~~Enter Roll Number to Delete~~~~~~~~~~~~~~>>>>>  : ";
    cin >> Search_Roll_NO;

    int index = -1;

    for (int i = 0; i < Total_Students; i++)
    {
        if (roll_No[i] == Search_Roll_NO && index == -1)
        {
            index = i; // mark position
        }
    }

    if (index == -1)
    {

        cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                        \n";
        cout << "                 @@@@@@@@@@@@@@@@@@@@@ Student is not Registered @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@             \n";
        cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                       \n";
        getch();
        return;
    }

    for (int i = index; i < Total_Students - 1; i++)
    {
        name[i] = name[i + 1];
        Cnic[i] = Cnic[i + 1];
        roll_No[i] = roll_No[i + 1];
        Matric_marks[i] = Matric_marks[i + 1];
        Inter_Marks[i] = Inter_Marks[i + 1];
        section[i] = section[i + 1];
    }

    Total_Students--;

    cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                        \n";
    cout << "                 @@@@@@@@@@@@@@@@@@@@@  student  Data is Deleted  @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@             \n";
    cout << "                                 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                       \n";
    Save_Data_To_File();
    getch();
}
void Save_Data_To_File()
{
    ofstream file;
    file.open("Students.txt", ios::out); // open in write mode, overwrites old data
    if (!file)
    {
        cout << "Error opening file!" << endl;
        return;
    }

    for (int i = 0; i < Total_Students; i++)
    {
        file << name[i] << "\n";
        file << Cnic[i] << "\n";
        file << roll_No[i] << "\n";
        file << Matric_marks[i] << "\n";
        file << Inter_Marks[i] << "\n";
        file << section[i] << "\n";
    }
    file.close();
}
void Load_Data_From_File()
{
    ifstream file;
    file.open("Students.txt", ios::in); // open in read mode
    if (!file)
    {
        cout << "No saved data found!" << endl;
        return;
    }

    Total_Students = 0; // reset
    while (!file.eof())
    {
        getline(file, name[Total_Students]);
        getline(file, Cnic[Total_Students]);
        file >> roll_No[Total_Students];
        file >> Matric_marks[Total_Students];
        file >> Inter_Marks[Total_Students];
        file.ignore(); // ignore newline
        getline(file, section[Total_Students]);
        Total_Students++;
        if (Total_Students >= 100)
            break; // avoid overflow
    }
    file.close();
}

