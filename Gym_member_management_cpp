#include <iostream>
using namespace std;

// Node structure for gym member
struct Node {
    int memberID;
    string name;
    string membershipType;
    Node* next;
};

// Head pointer
Node* head = NULL;

// Insert a new member
void insertMember() {
    Node* newNode = new Node;

    cout << "\nEnter Member ID: ";
    cin >> newNode->memberID;

    cout << "Enter Member Name: ";
    cin >> newNode->name;

    cout << "Enter Membership Type: ";
    cin >> newNode->membershipType;

    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
    } else {
        Node* temp = head;

        while (temp->next != NULL) {
            temp = temp->next;
        }

        temp->next = newNode;
    }

    cout << "Member added successfully!\n";
}

// Delete a member
void deleteMember() {
    int id;
    cout << "\nEnter Member ID to delete: ";
    cin >> id;

    if (head == NULL) {
        cout << "No members found.\n";
        return;
    }

    // If first member is to be deleted
    if (head->memberID == id) {
        Node* temp = head;
        head = head->next;
        delete temp;

        cout << "Member deleted successfully!\n";
        return;
    }

    Node* temp = head;

    while (temp->next != NULL && temp->next->memberID != id) {
        temp = temp->next;
    }

    if (temp->next == NULL) {
        cout << "Member not found.\n";
    } else {
        Node* deleteNode = temp->next;
        temp->next = deleteNode->next;
        delete deleteNode;

        cout << "Member deleted successfully!\n";
    }
}

// Search for a member
void searchMember() {
    int id;
    cout << "\nEnter Member ID to search: ";
    cin >> id;

    Node* temp = head;

    while (temp != NULL) {
        if (temp->memberID == id) {
            cout << "\nMember Found!\n";
            cout << "Member ID: " << temp->memberID << endl;
            cout << "Name: " << temp->name << endl;
            cout << "Membership Type: " << temp->membershipType << endl;
            return;
        }

        temp = temp->next;
    }

    cout << "Member not found.\n";
}

// Display all members
void displayMembers() {
    if (head == NULL) {
        cout << "\nNo active members found.\n";
        return;
    }

    Node* temp = head;

    cout << "\n--- Active Gym Members ---\n";

    while (temp != NULL) {
        cout << "ID: " << temp->memberID
             << " | Name: " << temp->name
             << " | Membership: " << temp->membershipType << endl;

        temp = temp->next;
    }
}

// Main function
int main() {
    int choice;

    do {
        cout << "\n===== GYM MEMBER MANAGEMENT =====\n";
        cout << "1. Add Member\n";
        cout << "2. Delete Member\n";
        cout << "3. Search Member\n";
        cout << "4. Display Members\n";
        cout << "5. Exit\n";

        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                insertMember();
                break;

            case 2:
                deleteMember();
                break;

            case 3:
                searchMember();
                break;

            case 4:
                displayMembers();
                break;

            case 5:
                cout << "Exiting program...\n";
                break;

            default:
                cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 5);

    return 0;
}
