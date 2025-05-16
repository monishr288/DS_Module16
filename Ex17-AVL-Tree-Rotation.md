# Ex17 AVL Tree – Rotation
## DATE: 16.5.25
## AIM:
To write a C function to perform right rotation in an AVL Tree.

## Algorithm
1. Start 
2. Set y to the left child of x. 
3. Set the left child of x to be the right child of y. 
4. Set the right child of y to be x. 
5. Update the height of x and y. 
6. Return y as the new root after rotation. 
7. End  
 

## Program:
```
/*
Program to perform right rotation in AVL Tree
Developed by: MONISH R
RegisterNumber:  212223220061
*/
node * rotateleft(node *x)
{
node *y;
y=x->right;
x->right=y->left;
y->left=x;
x->ht=height(x);
y->ht=height(y);
return(y);
}
```

## Output:

![Screenshot 2025-05-16 200945](https://github.com/user-attachments/assets/39708624-0aa9-4c9c-9a20-1c747fa4f6b9)


## Result:
Thus, the function to perform right rotation in an AVL Tree is implemented successfully.
