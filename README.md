#include <stdio.h>

struct Mobile {
    int id;
    char name[30];
    float price;
};

int main() {
    struct Mobile m[50];
    int n = 0, choice, i, id;

    while (1) {
        printf("\n===== MOBILE SHOP MANAGEMENT =====\n");
        printf("1. Add Mobile\n");
        printf("2. Display Mobiles\n");
        printf("3. Search Mobile\n");
        printf("4. Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        if (choice == 1) {
            printf("Enter Mobile ID: ");
            scanf("%d", &m[n].id);

            printf("Enter Mobile Name: ");
            scanf("%s", m[n].name);

            printf("Enter Price: ");
            scanf("%f", &m[n].price);

            n++;
            printf("Mobile added successfully!\n");
        }

        else if (choice == 2) {
            printf("\n--- Mobile Details ---\n");

            for (i = 0; i < n; i++) {
                printf("\nID: %d", m[i].id);
                printf("\nName: %s", m[i].name);
                printf("\nPrice: Rs. %.2f\n", m[i].price);
            }
        }

        else if (choice == 3) {
            printf("Enter Mobile ID: ");
            scanf("%d", &id);

            for (i = 0; i < n; i++) {
                if (m[i].id == id) {
                    printf("\nMobile Found!\n");
                    printf("Name: %s\n", m[i].name);
                    printf("Price: Rs. %.2f\n", m[i].price);
                    break;
                }
            }

            if (i == n)
                printf("Mobile not found.\n");
        }

        else if (choice == 4) {
            printf("Thank you!\n");
            break;
        }

        else {
            printf("Invalid choice!\n");
        }
    }

    return 0;
}
