Create two arrays/vectors to store the row sum and column sum.

Traverse through matrix and if element is 1, check its row and column sum, if they are 1, the current position is a spl postion and increemnt count.

time-O(nm)+O(nm)

space- O(m+n)

class Solution {

public:

    int numSpecial(vector<vector<int>>& mat) {

        vector<int>r(mat.size(),0),c(mat[0].size(),0);

        int m=mat.size(),n=mat[0].size(),i,j,count=0;

        for(i=0;i<m;i++)

        {

            for(j=0;j<n;j++)

            {

                if(mat[i][j]==1)

                {

                    r[i]++;

                    c[j]++;

                }

            }

        }

        for(i=0;i<m;i++)

        {

            for(j=0;j<n;j++)

            {

                if(mat[i][j]==1)

                {

                    if(r[i]==1&&c[j]==1)

                        count++;

                }

            }

        }

        return count;

    }

};
