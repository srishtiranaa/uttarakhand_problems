# uttarakhand_problems
#include <iostream>
#include <string>
#include <vector>

using namespace std;

class Problem {
public:
    string title;
    string description;

    Problem(string t, string d) : title(t), description(d) {}
};
a
class UttarakhandProblems {
private:
    vector<Problem> problems;

public:
    UttarakhandProblems() {
        // Initialize with some problems
        problems.push_back(Problem("Environmental Degradation", 
            "Uttarakhand faces severe environmental issues due to deforestation, landslides, and climate change."));
        problems.push_back(Problem("Infrastructure Challenges", 
            "The state struggles with inadequate infrastructure, including poor road conditions and limited public transport."));
        problems.push_back(Problem("Water Scarcity", 
            "Many regions in Uttarakhand face water scarcity, especially during the dry season, affecting agriculture and daily life."));
        problems.push_back(Problem("Tourism Impact", 
            "While tourism is a major source of income, it also leads to environmental degradation and cultural disruption."));
        problems.push_back(Problem("Social Issues", 
            "Uttarakhand faces various social issues, including unemployment, education challenges, and health care access."));
    }

    void displayProblems() {
        cout << "Problems in Uttarakhand:\n";
        for (size_t i = 0; i < problems.size(); ++i) {
            cout << i + 1 << ". " << problems[i].title << endl;
        }
        cout << "Enter the number of the problem you want to learn more about (0 to exit): ";
    }

    void displayProblemDetails(int index) {
        if (index >= 0 && index < problems.size()) {
            cout << "\nTitle: " << problems[index].title << endl;
            cout << "Description: " << problems[index].description << endl;
        } else {
            cout << "Invalid selection." << endl;
        }
    }
};

int main() {
    UttarakhandProblems ukProblems;
    int choice;

    while (true) {
        ukProblems.displayProblems();
        cin >> choice;

        if (choice == 0) {
            cout << "Exiting the program." << endl;
            break;
        }

        ukProblems.displayProblemDetails(choice - 1);
        cout << "\nPress Enter to continue...";
        cin.ignore();
        cin.get(); // Wait for user to press Enter
        cout << endl;
    }

    return 0;
}
