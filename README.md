# Data-Structures
Data Structures 2nd SEM
#include<stdio.h>
#include<stdlib.h>
struct employee
{
int id;
char name[50];
char category[10];
};
struct employee *read(struct employee *temp);
struct employee *display(struct employee *temp);
struct employee *modify(struct employee *temp);
struct employee *search(struct employee *temp);

struct employee *read(struct employee *temp)
{
printf("\nEnter the id of employee\n");
scanf("%d",&temp->id);
printf("Enter the name\n");
scanf("%s",temp->name);
printf("Enter the category\n");
scanf("%s",temp->category);
return temp;
}
struct employee *display(struct employee *temp)
{
printf("%d\t",temp->id);
printf("%s\t",temp->name);
printf("%s\t",temp->category);
printf("\n\n");
return temp;
} 
struct employee *search(struct employee *temp)
{
printf("%d",temp->id);
printf("%s",temp->name);
printf("%s",temp->category);
return temp;
}
struct employee *modify(struct employee *temp)
{
printf("Enter the id of employee\n");
scanf("%d",&temp->id);
printf("Enter the name\n");
scanf("%s",temp->name);
printf("Enter the category\n");
scanf("%s",temp->category);
return temp;
}
int main()
{
int n;
printf("Enter the no of employee record to be filled\n");
scanf("%d",&n);
int choice;
int key=1;
struct employee *a;
a=malloc(n*sizeof(struct employee));
while(key)
{
printf("1.Read\n2.Display\n3.Modify\n4.Search\n5.Terminate\n");
scanf("%d",&choice);
switch(choice)
{
case 1:
for(int i=0;i<n;i++)
{
printf("Enter the Employee information %d",i+1);
read(&a[i]);
}
break;
case 2:
for(int i=0;i<n;i++)
{
display(&a[i]);
}
break;
case 3:
{
int t=0;

printf("Enter the id you want to modify\n");
scanf("%d",&t);
for(int i=0;i<n;i++)
{
if(a[i].id==t)
{
modify(&a[i]);
}
}

break;
}
case 4:
{
int d=0;
printf("Enter the id you want to search\n");
scanf("%d",&d);
for(int i=0;i<n;i++)
{
if(a[i].id==d)
{
display(&a[i]);
}
}
break;
}
case 5:
key=0;
break;
}
}
return 0;
}
