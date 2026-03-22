# CGPA-Calculator
This is my first Repository.
<br>
Author- Freya Vaghela

#include <iostream>
using namespace std;

// Function to calculate grade point
float calculateGradePoint(float percentage)
{
    if (percentage >= 90)
        return 10;
    else if (percentage >= 80)
        return 9;
    else if (percentage >= 70)
        return 8;
    else if (percentage >= 60)
        return 7;
    else if (percentage >= 50)
        return 6;
    else if (percentage >= 40)
        return 5;
    else
        return 0; // Fail
}

int main()
{

    int subjects = 6;
    float ta1, mid, ta2, university;
    int credit;
    float totalMarks, percentage, gradePoint;
    float totalCreditPoints = 0, totalCredits = 0;

    cout << " CGPA Calculator (6 Subjects) " << endl;

    for (int i = 1; i <= subjects; i++)
    {

        cout << "Subject " << i << endl;

        cout << "Enter TA-1 marks (out of 25): ";
        cin >> ta1;

        cout << "Enter Mid Sem marks (out of 50): ";
        cin >> mid;

        cout << "Enter TA-2 marks (out of 25): ";
        cin >> ta2;

        cout << "Enter University marks (out of 100): ";
        cin >> university;

        cout << "Enter Credit of Subject: ";
        cin >> credit;

        // Total marks out of 200
        totalMarks = ta1 + mid + ta2 + university;

        // Convert to percentage
        percentage = (totalMarks / 200) * 100;

        // Convert to grade point
        gradePoint = calculateGradePoint(percentage);

        cout << "Total Marks = " << totalMarks << "/200" << endl;
        cout << "Percentage = " << percentage << "%" << endl;
        cout << "Grade Point = " << gradePoint << endl;

        totalCreditPoints += gradePoint * credit;
        totalCredits += credit;
    }

    float cgpa = totalCreditPoints / totalCredits;

    cout << "FINAL RESULT" << endl;
    cout << "Total Credits = " << totalCredits << endl;
    cout << "CGPA = " << cgpa << endl;

    return 0;
}