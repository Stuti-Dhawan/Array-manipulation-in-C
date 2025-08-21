# Array-manipulation-in-C
#include <stdio.h>
void create()
{
    int len;
    printf("Enter the length of array: ");
    scanf("%d",&len);
    int arr[len];
    printf("Enter the elements of the array:\n");
    for (int i=0;i<len;i++)
    {
        scanf("%d",&arr[i]);
    }
    for (int i=0;i<len;i++)
    {
        printf("The %dth element is: %d\n",i+1,arr[i]);
    }
}
void insertbyvalue(int arr[],int size)
{
    int num, index;
    printf("Enter the value to be entered in the array: ");
    scanf("%d",&num);
    for (int i=0;i<size;i++)
    {
        if(arr[i]>num)
        {
            index=i;
            for (int j=i;j<size;j++)
            {
                arr[j+1]=arr[j];
            }
            arr[i]=num;
            break;
        }
    }
    printf("Now the array is:\n");
    for (int k=0;k<(size+1);k++)
    {
        printf("The %dth element is: %d\n",k+1,arr[k]);
    }
}
void insertbyposition(int arr[],int size)
{
    int num, pos;
    printf("Enter the value to be entered in the array: ");
    scanf("%d",&num);
    printf("Enter the position of this value: ");
    scanf("%d",&pos);
    for (int j=pos;j<size;j++)
    {
        arr[j+1]=arr[j];
    }
    arr[pos]=num;
    printf("Now the array is:\n");
    for (int k=0;k<(size+1);k++)
    {
        printf("The %dth element is: %d\n",k+1,arr[k]);
    }
}
void deletionbyvalue(int arr[],int size)
{
    int num;
    printf("Enter the value to be deleted from the array: ");
    scanf("%d",&num);
    int pos=-1;
    for (int i=0;i<size;i++)
    {
        if (arr[i]==num)
        {
            pos=i;
            break;
        }
    }
    if (pos == -1) 
    {
        printf("Element not found.\n");
        return;
    }
    for (int j=0;j<size;j++)
    {
        if(j>=pos)
        {
            arr[j]=arr[j+1];
            
        }
    }
    printf("Now the array is:\n");
    for (int k=0;k<(size-1);k++)
    {
        printf("The %dth element is: %d\n",k+1,arr[k]);
    }
}
void deletionbyposition(int arr[],int size)
{
    int pos;
    printf("Enter the position whose value is to be deleted from the array: ");
    scanf("%d",&pos);
    for (int j=0;j<size;j++)
    {
        if(j>=pos)
        {
            arr[j]=arr[j+1];
            
        }
    }
    printf("Now the array is:\n");
    for (int k=0;k<(size-1);k++)
    {
        printf("The %dth element is: %d\n",k+1,arr[k]);
    }
}
void maximum(int arr[],int size)
{
    int max=arr[0];
    for (int i=0;i<size;i++)
    {
        if (arr[i]>max)
        {
            max=arr[i];
        }
    }
    printf("The maximum of all the element of this array is: %d",max);
}
void minimum(int arr[],int size)
{
    int min=arr[0];
    for (int i=0;i<size;i++)
    {
        if (arr[i]<min)
        {
            min=arr[i];
        }
    }
    printf("The minimum of all the element of this array is: %d",min);
}
void sum(int arr[],int size)
{
    float s=0;
    for (int i=0;i<size;i++)
    {
        s=s+arr[i];
    }
    printf("The sum of all the elements of this array is: %f",s);
}
void average(int arr[],int size)
{
    float s=0;
    float avg, a=size;
    for (int i=0;i<size;i++)
    {
        s=s+arr[i];
    }
    avg=s/a;
    printf("The average of all the elements of this array is: %f",avg);
}
int main() {
    int n;
    printf("OPERATIONS ON ARRAY:\n");
    printf("1. Creation of array\n");
    printf("2. Insertion by value (sorted array)\n");
    printf("3. Insertion by position in an array\n");
    printf("4. Deletion by value (sorted array)\n");
    printf("5. Deletion by position in an array\n");
    printf("6. Maximum of all elements of an array\n");
    printf("7. Minimum of all elements of an array\n");
    printf("8. Sum of all the elements of an array\n");
    printf("9. Average of all the elements of an array\n");
    printf("Enter your choice:");
    scanf("%d", &n);
    switch(n)
    {
        case 1:
        {
            printf("CREATION OF AN ARRAY:\n");
            create();
            break;
        }
        case 2:
        {
            printf("INSERTING VALUE INSIDE AN ARRAY BY VALUE (SORTED ARRAY):\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the sorted array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            insertbyvalue(arr,len);
            break;
        }
        case 3:
        {
            printf("INSERTING VALUE INSIDE AN ARRAY BY POSITION:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            insertbyposition(arr,len);
            break;
        }
        case 4:
        {
            printf("DELETING VALUE INSIDE AN ARRAY BY VALUE (SORTED ARRAY):\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the sorted array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            deletionbyvalue(arr,len);
            break;
        }
        case 5:
        {
            printf("DELETING VALUE INSIDE AN ARRAY BY POSITION:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            deletionbyposition(arr,len);
            break;
        }
        case 6:
        {
            printf("FINDING THE MAXIMUM OF ALL THE ELEMENTS OF A GIVEN ARRAY:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            maximum(arr,len);
            break;
        }
        case 7:
        {
            printf("FINDING THE MINIMUM OF ALL THE ELEMENTS OF A GIVEN ARRAY:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            minimum(arr,len);
            break;
        }
        case 8:
        {
            printf("SUM OF ALL THE ELEMENTS OF AN ARRAY:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            sum(arr,len);
            break;
        }
        case 9:
        {
            printf("AVERAGE OF ALL THE ELEMENTS OF AN ARRAY:\n");
            int len;
            printf("Enter the length of array: ");
            scanf("%d",&len);
            int arr[len];
            printf("Enter the elements of the array:\n");
            for (int i=0;i<len;i++)
            {
                scanf("%d",&arr[i]);
            }
            average(arr,len);
            break;
        }
    }
    return 0;
}
