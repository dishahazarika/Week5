//Write a menu-driven C program to implement a singly linked list that supports creating the list, inserting a node at the beginning, deleting a node from the end, and displaying the list. 

#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};
struct node *head = NULL;

void create() {
    struct node *newnode, *temp;
    int choice = 1;
    while (choice) {
        newnode = (struct node*)malloc(sizeof(struct node));
        printf("Enter data: ");
        scanf("%d", &newnode->data);
        newnode->next = NULL;
        if (head == NULL)
            head = temp = newnode;
        else {
            temp->next = newnode;
            temp = newnode;
        }
        printf("Do you want to continue(1/0): ");
        scanf("%d", &choice);
    }
}

void insert_begin() {
    struct node *newnode;
    newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter data: ");
    scanf("%d", &newnode->data);
    newnode->next = head;
    head = newnode;
}

void delete_end() {
    struct node *temp = head, *prev;
    if (head == NULL)
        printf("List is empty\n");
    else if (head->next == NULL) {
        free(head);
        head = NULL;
    } else {
        while (temp->next != NULL) {
            prev = temp;
            temp = temp->next;
        }
        prev->next = NULL;
        free(temp);
    }
}

void display() {
    struct node *temp = head;
    if (temp == NULL)
        printf("List is empty\n");
    else {
        printf("List: ");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int main() {
    int ch;
    while (1) {
        printf("\n1.Create\n2.Insert at Beginning\n3.Delete from End\n4.Display\n5.Exit\nEnter choice: ");
        scanf("%d", &ch);
        switch (ch) {
            case 1: create(); break;
            case 2: insert_begin(); break;
            case 3: delete_end(); break;
            case 4: display(); break;
            case 5: exit(0);
            default: printf("Invalid choice\n");
        }
    }
}
