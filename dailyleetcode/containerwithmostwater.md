Problem link:

https://leetcode.com/problems/container-with-most-water/

To find the coontainer with most water,i.e; Max area that can be enclosed btw 2 vertical lines.

Approches:

1\. Bruteforce:

   Consider every container and find the area enclosed between.Find the maximum area.

   Time- O(n^2)

   Space- O(1)

2\. Optimized approach- using 2 pointers

   For the area enclosed to be maximum, the length and breadth of the rectangle should be maximum.

   Let us consider two pointers i and j oointing at 0,n-1 respectively. While i doesnot crosses or equal to j, if height at i is less than height at j, we move i to check if a line exitst with height greater than i, so that the are enclosed is maximized.

   Similarly, j is decremeneted if height at j is less than height at i, searching for j where area enclosed can be maximum.

   Area enclosed or the water contained is the product of diff btw j and i ,and the minimum of heights at i and j; 

   Time-O(n)

   Space-O(1)

   class Solution {

public:

    int maxArea(vector<int>& height) {

        int n=height.size(),i,j;

        int water=0;

        i=0,j=n-1;

        while(i<j)

        {

            water=max(water,min(height[i],height[j])*(j-i));

            if(height[i]<height[j])

            {

                i++;

            }

            else if(height[i]>height[j])

                j--;

            else

            {

                i++;

                j--;

            }

        }

        return water;

    }

};
