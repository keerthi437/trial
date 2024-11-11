#include <stdio.h>
#include <stdlib.h>
struct Node {
    int key;
    struct Node* left;
    struct Node* right;
};
struct Node* newNode(int item)
{
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->key = item;
    temp->left = temp->right = NULL;
    return temp;
}
struct Node* insert(struct Node* node, int key) {
  if (node == NULL) 
        return newNode(key);
    if (node->key == key)
        return node;
    if (node->key < key)
        node->right = insert(node->right, key);
  else
        node->left = insert(node->left, key);
return node;
