time- O(m*n) space-O(1)

class Solution {

public:

    vector<vector<int>> flipAndInvertImage(vector<vector<int>>& a) {

        int m=a.size(),n=a[0].size();

        int i,j,t;

        for(i=0;i<m;i++)

        {

           reverse(a[i].begin(),a[i].end());

            for(j=0;j<n;j++)

            {

                if(a[i][j]==0)

                    a[i][j]=1;

                else

                    a[i][j]=0;

            }

        }

        return a;

    }

};
