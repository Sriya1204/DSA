time-O(n^2)

space- O(1)(no extra space)

class Solution {

public:

    int maximumWealth(vector<vector<int>>& accounts) {

        int m=accounts.size(),n=accounts[0].size(),i,j,sum=0,maxsum=0;

        for(i=0;i<m;i++)

        {

            sum=0;

            for(j=0;j<n;j++)

            {

                sum+=accounts[i][j];

            }

            if(sum>maxsum)

                maxsum=sum;

        }

        return maxsum;

    }

};
