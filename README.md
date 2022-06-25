# maximum-sum-of-subarray-in-cpp

**PROBLEM STATEMENT**

Write an efficient program to find the sum of the contiguous subarray within a one-dimensional array of numbers that has the largest sum. 

**CODE**

```

// By using dp

#include<bits/stdc++.h>
using namespace std;
int solve(int a[],int n)
{
    int curr_max=a[0];
    int max_so=a[0];
    for(int i=1;i<n;i++)
    {
        curr_max=max(a[i],curr_max+a[i]);
        max_so=max(max_so,curr_max);
    }
    return max_so;
}
 int main()
 {
     int a[]= {-2, -3, 4, -1, -2, 1, 5, -3};
     int n=sizeof(a)/sizeof(a[0]);
     cout<<solve(a,n);
     return 0;
 }
 
 
 //  By using Kadan's algorithm
 
 
 #include<bits/stdc++.h>
using namespace std;
int solve(int a[],int n)
{
   int mx=INT_MIN;
   int end_sum=0;
   int cnt=0;
   for(int i=0;i<n;i++)
   {
       end_sum+=a[i];
       if(mx<end_sum)
       {
           mx=end_sum;
            cnt++;
       }
       if(end_sum<0)
       {
           end_sum=0;
       }
      // cnt++;
   }
   return cnt;
   
}
 int main()
 {
     int a[]= { -2, -3, 4, -1, -2, 1, 5, -3 };
     int n=sizeof(a)/sizeof(a[0]);
     cout<<solve(a,n);
     return 0;
 }
 
