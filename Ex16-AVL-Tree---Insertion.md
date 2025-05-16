# Ex16 AVL Tree - Insertion
## DATE: 16.5.25
## AIM: 
To write a C function to insert the elements in an AVL Tree.

## Algorithm
1. Start 
2. If the node is NULL, create a new node with value x. 
3. Insert x recursively into the left or right subtree based on comparison. 
4. Calculate the balance factor (BF) after insertion. 
5. If BF is -2 or 2, perform appropriate rotations (RR, RL, LL, or LR). 
6. Update the height of the current node. 
7. Return the new root after insertion and balancing.. 
8. End 

## Program:
```
/*
Program to insert the elements in an AVL Tree
Developed by: MONISH R
RegisterNumber:  212223220061
*/
node * insert(node *T,int x)
{
if(T==NULL)
{
T=(node*)malloc(sizeof(node));
T->data=x;
T->left=NULL;
T->right=NULL;
}
else
if(x > T->data) // insert in right subtree
{
T->right=insert(T->right,x);
if(BF(T)==-2)
{
if(x>T->right->data)
T=RR(T);
else
T=RL(T);
}
}
else
if(x<T->data)
{
T->left=insert(T->left,x);
if(BF(T)==2)
{
    if(x < T->left->data)
T=LL(T);
else
T=LR(T);
}
}
T->ht=height(T);
return(T);
}
 


```

## Output:
![Screenshot 2025-05-16 200235](https://github.com/user-attachments/assets/3fd59bbb-ffe0-4ea9-83bb-4ce2897dbb37)



## Result:
Thus, the function to insert the elements in an AVL Tree is implemented successfully in C programming language.
