// Write a C program to create a doubly linked list and implement functions to insert a node after a given node and to delete a node from the beginning. 
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev, *next;
};
struct node *head = NULL;

void create() {
    struct node *newnode, *temp;
    int choice = 1;
    while (choice) {
        newnode = (struct node*)malloc(sizeof(struct node));
        printf("Enter data: ");
        scanf("%d", &newnode->data);
        newnode->prev = newnode->next = NULL;
        if (head == NULL)
            head = temp = newnode;
        else {
            temp->next = newnode;
            newnode->prev = temp;
            temp = newnode;
        }
        printf("Continue? (1/0): ");
        scanf("%d", &choice);
    }
}

void insert_after() {
    int val;
    struct node *temp = head, *newnode;
    printf("Enter value after which to insert: ");
    scanf("%d", &val);
    while (temp != NULL && temp->data != val)
        temp = temp->next;
    if (temp == NULL) {
        printf("Node not found\n");
        return;
    }
    newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter new data: ");
    scanf("%d", &newnode->data);
    newnode->next = temp->next;
    newnode->prev = temp;
    if (temp->next != NULL)
        temp->next->prev = newnode;
    temp->next = newnode;
}

void delete_begin() {
    if (head == NULL)
        printf("Empty list\n");
    else {
        struct node *temp = head;
        head = head->next;
        if (head != NULL)
            head->prev = NULL;
        free(temp);
    }
}

void display() {
    struct node *temp = head;
    printf("List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    int ch;
    while (1) {
        printf("\n1.Create\n2.Insert after node\n3.Delete from beginning\n4.Display\n5.Exit\nEnter choice: ");
        scanf("%d", &ch);
        switch (ch) {
            case 1: create(); break;
            case 2: insert_after(); break;
            case 3: delete_begin(); break;
            case 4: display(); break;
            case 5: exit(0);
            default: printf("Invalid choice\n");
        }
    }
}
