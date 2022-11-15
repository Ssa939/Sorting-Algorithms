# Sorting-Algorithms
//Different sorting algorithms with there programs in java.
1. MERGE SORT(This algorithm uses divide and conquer rule. In this large problems are divided in smallest possible problems and solved seperately. Then this sorted elements are merged, hence Merge sort)
Time Complexity:n log n
public class MergeSort
{
  public static void conquer(int arr[], int si, int mid, int ei)
  {
    int merged[]=new int[ei-si+1];
    int idx1=si;
    int idx2=mid+1;
    int x=0;
    while(idx1 <= mid && idx2 <= ei)
    {
      if(arr[idx1] <= arr[idx2]) 
      {
        merged[x++]= arr[idx1++];
      }
      else
      {
        merged[x++]= arr[idx2++];
      }
   }
   while(idx1 <= mid)
   {
     merged[x++] = arr[idx1++];
   }
   while(idx2 <= ei)
   {
     merged[x++] = arr[idx2++];
   }
    for(int i=0, j=si; i<merged.length; i++, j++)
    {
      arr[j] = merged[i];
    }
    
  }
  public static void divide(int arr[], int si, int ei)
  {
    if(si>=ei)
    {
     return;
    }
    int mid=si+(ei-si)/2;
    divide(arr, si, mid);
    divide(arr, mid+1, ei);
    conquer(arr, si, mid, ei);
    
  }
  public static void main(String args[])
  {
  int arr[]={7,4,3,2,9};
  int n=arr.length;
  
  divide(arr, 0, n-1);
  for(int i=0; i<n; i++)
  {
    System.out.print(arr[i]+" ");
  }
  System.out.println();
  }
}

OUTPUT:2 3 4 7 9




2. QUICK SORT

public class QuickSort()
{
  public sattic int partition(int arr[], int low, int high)
  {
    int pivot=arr[high];
    int i=low-1;
    
    for(j=low;j<high; j++)
    {
     if(arr[i]<pivot)
     {
      i++;
      int temp=int[i];
      int [i]=int [j];
      int [j]=temp;
      }
    }
  }

  public static void quickSort(int arr[], int low, int high)
  {
    if(low < high)
    {
       int pidx=partition(arr, low, high);
       quickSort(arr, low, pidx-1);
       quickSort(arr, pidx+1, high);
    }
  }
  public static void main(String args[])
  {
    int arr[]={3, 8, 1, 7, 4};
    int n= arr.length;
    
  
  }

}
