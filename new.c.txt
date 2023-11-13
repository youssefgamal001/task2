#include <stdio.h>
#include <stdbool.h>
#include <string.h>
// Define a union to store user activity
union UserActivity
{
    int active;    // 1 for active, 0 for inactive
    bool isActive; // Using a bool to indicate user's activity
};

// Structure to represent user information
struct User
{
    char username[50];
    char password[50];
    union UserActivity activity;
};

int main()
{
    // Create a user and set their activity
    struct User user1;
    strcpy(user1.username, "exampleuser");
    strcpy(user1.password, "password123");
    user1.activity.isActive = true; // User is active

    // Check if the user is active
    if (user1.activity.isActive)
    {
        printf("User is active\n");
    }
    else
    {
        printf("User is inactive\n");
    }

    return 0;
}