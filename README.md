# Minimum-Average-Difference_
#Leetcode

class Solution {
public:
    int minimumAverageDifference(vector<int>& nums) {
        int n=nums.size();
         long long sum=0;
         for(int i=0;i<n;i++)
         {
             sum=sum+nums[i];
         }
         long long ls=0;
         long long rs=0;
         int result=INT_MAX;
         int index=-1;
         for(int i=0;i<n;i++)
         {
             ls=ls+nums[i];
             rs=sum-ls;
             int n1=i+1;
             int n2=n-n1;
             long long left_avg=ls/n1;
             long long rigth_avg=(i==n-1) ? 0 : rs/n2;
             int diff=abs(left_avg-rigth_avg);
             if(result>diff)
             {
                 result=diff;
                 index=i;
             }
         }
       return index; 
    }
};
