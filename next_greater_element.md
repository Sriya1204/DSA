Bruteforce: Iterating through two loops, time-O(n^2) space-O(1)

Optimized solution using stack:

Time -O(2n) Space-O(n)

class Solution {
public:
    vector<int> nextGreaterElements(vector<int>& nums) {
        int n=nums.size(),i;
        vector<int>nge(n,-1);
        stack<int>s;
        for(i=2*n-1;i>=0;i--)
        {
            int ind=i%n;
            if(s.empty()){
                s.push(nums[ind]);
                nge[ind]=-1;
            }
            else if(nums[ind]<s.top())
            {
                nge[ind]=s.top();
                s.push(nums[ind]);
            }
            else
            {
                while(!s.empty()&&nums[ind]>=s.top())
                {
                    s.pop();
                }
                if(s.empty())
                {
                   nge[ind]=-1;
                    s.push(nums[ind]);
                }
                else
                {
                nge[ind]=s.top();
                    s.push(nums[ind]);
                }
            }
        }
        return nge;
    }
};
