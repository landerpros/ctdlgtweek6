//Sort Dutch National Flag colors
// Red=0, White=1, Blue=2

#include <iostream>
using namespace std;
 
void Partition(int A[], int first, int last){
    if (first>=last) return;
    int c=A[first];
    int i=first+1,j=last;
    while (i<=j){
        while (A[i]<=c && i<=j) i++;
        while (A[j]>c && i<=j) j--;
        if (i<j) swap(A[i],A[j]);
    }
swap(A[first],A[j]);
Partition(A, first,j-1);
Partition(A, j+1,last);
}

void QuickSort(int A[], int N){
    Partition(A,0,N-1);
}

void printFun(int a[], int n)
{
    for (int i = 0; i < n; ++i)
        printf("%d  ", a[i]);
    printf("\n");
}

void MergeArrays(int a[], int b[], int A[],int m, int n, int p){
    for(int i=0; i<(n+1); ++i){
        A[i]=a[i];
    }
    for(int i=0; i<(p+1-n); ++i){
        A[i+n+1]=b[i];
    }
    int i=m,j=n+1;
    while (i<j && j<=p){
        if (A[i]<=A[j]) i++;
        else {//chen Aj vao vi tri i
            int x=A[j];
            for (int k=j-1;k>=i;k--)
                A[k+1]=A[k];
            A[i]=x;
            i++; j++;
        }
    }
}

//test
int main()
{
    int a[] = {2, 1, 2, 0, 0, 2, 1, 2, 0, 1, 1, 0};
    int sizea = sizeof(a) / sizeof(int);
    
    int b[] = {2, 2, 0, 1, 0, 1, 2, 0, 0};
    int sizeb = sizeof(b) / sizeof(int);
    
    int A[sizea+sizeb];
    
    printFun(a, sizea);
    QuickSort(a, sizea);
    printFun(a, sizea);
    
    printFun(b, sizeb);
    QuickSort(b, sizeb);
    printFun(b, sizeb);
    
    MergeArrays(a, b, A, 0, sizea-1, sizea+sizeb-1);
    printFun(A, sizea+sizeb);
    
    return 0;
}
