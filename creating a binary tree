#include <stdio.h>
#include <stdlib.h>
#include<malloc.h>
#include<string.h>
struct node
{
    int info;
    struct node *rlink;
    struct node *llink;
};
typedef struct node* NODE;
NODE getnode()
{
    NODE x;
    x=(NODE)malloc(sizeof(struct node));
    if(x==NULL)
        printf(" creation of node not possible \n");
    return x;
}
NODE insert_tree(int item,NODE root)
{
    NODE temp,cur,prev;
    char direction[30];
    int i;
    temp=getnode();
    temp->info=item;
    temp->rlink=temp->llink=NULL;
    if(root==NULL)
        return temp;
    printf(" enter the direction \n");
    scanf("%s", direction);
    toupper(direction);
    cur=root;
    prev=NULL;
    for(i=0;i<strlen(direction)&&cur!=NULL;i++)
    {
        prev=cur;
        if(direction[i]=='L')
            cur=cur->llink;
        else
            cur=cur->rlink;


    }
    if(cur!=NULL&&i!=strlen(direction))
    {
        printf(" creation of node not possible \n");
        free(temp);
        return root;
    }
    if(direction[i-1]=='L')
        prev->llink=temp;
    else
        prev->rlink=temp;
    return root;



}
void preorder(NODE root)
{
    if(root!=NULL)
    {
        printf("%d",root->info);
        preorder(root->llink);
        preorder(root->rlink);
    }

}
void inorder(NODE root)
{
    if(root!=NULL)
    {
        inorder(root->llink);
        printf("%d",root->info);
        inorder(root->rlink);
    }
}
void postorder(NODE root)
{
    if(root!=NULL)
    {
        postorder(root->llink);
        postorder(root->rlink);
        printf("%d",root->info);
    }
}


void main()
{

    NODE root;
    root=getnode();
    root=NULL;
    int item;
    for(;;)
    {
        printf(" enter -999 to exit\n");
        printf(" enter the item \n");
        scanf("%d",&item);
        if(item==-999)
            break;
        root=insert_tree(item,root);

    }
    printf(" the preorder traversal is \n");
    preorder(root);
    printf(" the inoredr traversal is \n");
    inorder(root);
    printf(" the post order traversal is \n");
    postorder(root);

}
