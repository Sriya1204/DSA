time- O(n), space-O(1)

class Solution {

public:

    int diagonalSum(vector<vector<int>>& a) {

        int n=a.size();

        int i,j,sum=0;

       i=0,j=0;

       for(i=0;i<n;i++)

       {

           sum+=a[i][i];

           sum=sum+a[i][n-i-1];

       }

        if(n%2==0)

            return sum;

        else

            return sum-a[(n-1)/2][(n-1)/2];

    }

};
