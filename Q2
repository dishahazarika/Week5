//Implement a C program for a circular linked list that inserts a node at the beginning and deletes a node from the end.

#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};
struct node *last = NULL;

void insert_begin() {
    struct node *newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter data: ");
    scanf("%d", &newnode->data);
    if (last == NULL) {
        last = newnode;
        last->next = last;
    } else {
        newnode->next = last->next;
        last->next = newnode;
    }
}

void delete_end() {
    if (last == NULL)
        printf("List empty\n");
    else if (last->next == last) {
        free(last);
        last = NULL;
    } else {
        struct node *temp = last->next;
        while (temp->next != last)
            temp = temp->next;
        temp->next = last->next;
        free(last);
        last = temp;
    }
}

void display() {
    if (last == NULL) {
        printf("List empty\n");
        return;
    }
    struct node *temp = last->next;
    printf("List: ");
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != last->next);
    printf("\n");
}

int main() {
    int ch;
    while (1) {
        printf("\n1.Insert at Beginning\n2.Delete from End\n3.Display\n4.Exit\nEnter choice: ");
        scanf("%d", &ch);
        switch (ch) {
            case 1: insert_begin(); break;
            case 2: delete_end(); break;
            case 3: display(); break;
            case 4: exit(0);
            default: printf("Invalid choice\n");
        }
    }
}
