Key point: Every row is sorted, And last number of first reow is less than first element of next row. i.e; When we consider the elements row wise through all rows, we obtain sorted list of elements.

So, consider the matrix as a single array of length m*n (m- no.of rows, n-no.of columns)

As they are sorted, consider their indices and perform binary search.

The row and column number of the element can be found by (mid/no.columns) and (mid%rows).

time- O(log2(m*n)), space-O(1)

class Solution {

public:

    bool searchMatrix(vector<vector<int>>& matrix, int target) {

        int m=matrix.size();

        int n=matrix[0].size();

        if(m==0)

            return false;

        if(m*n==1)

        {

            if(matrix[0][0]==target)

                return true;

            return false;

        }

        int start=0,end=m*n-1;

        int mid,r,c;

        while(start<=end)

        {

            mid=start+(end-start)/2;

            r=mid/n;

            c=mid%n;

            if(matrix[r][c]==target)

                return true;

            else if(matrix[r][c]<target)

                start=mid+1;

            else

                end=mid-1;

        }

        return false;

    }

};
