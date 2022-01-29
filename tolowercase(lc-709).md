time- O(n)

space- O(1)

class Solution {

public:

    string toLowerCase(string s) {

        int i,n=s.size();

        for(i=0;i<n;i++)

        {

            if(s[i]>=65&&s[i]<=90)

            s[i]=s[i]-'A'+'a';

        }

        return s;

    }

};
