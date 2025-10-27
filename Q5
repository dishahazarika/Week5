// Write a C program to implement a header linked list where the header node stores a count of the total number of elements. The program should update the count during insertion and deletion

#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

struct header {
    int count;
    struct node *next;
};
struct header *head = NULL;

void insert() {
    struct node *newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter data: ");
    scanf("%d", &newnode->data);
    newnode->next = head->next;
    head->next = newnode;
    head->count++;
}

void delete_begin() {
    if (head->next == NULL)
        printf("List empty\n");
    else {
        struct node *temp = head->next;
        head->next = temp->next;
        free(temp);
        head->count--;
    }
}

void display() {
    struct node *temp = head->next;
    printf("Count: %d\nList: ", head->count);
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    head = (struct header*)malloc(sizeof(struct header));
    head->count = 0;
    head->next = NULL;

    int ch;
    while (1) {
        printf("\n1.Insert\n2.Delete from Beginning\n3.Display\n4.Exit\nEnter choice: ");
        scanf("%d", &ch);
        switch (ch) {
            case 1: insert(); break;
            case 2: delete_begin(); break;
            case 3: display(); break;
            case 4: exit(0);
            default: printf("Invalid choice\n");
        }
    }
}
