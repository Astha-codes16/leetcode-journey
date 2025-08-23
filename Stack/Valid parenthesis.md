// Approach==> last jiska closing bracketaaya hai ussi ka opening bracket aana chahiye.. 
class Solution {
public:
    bool isValid(string s) {
        stack<char>st;
        for(int i=0;i<s.size();i++)
        {
            if(s[i]=='('||s[i]=='{'||s[i]=='[')
            {
                st.push(s[i]);
            }
            else
            {
                if(st.size()==0)
                {
                    return false; //handling less no. of opening brackets and more number of closing    brackets
                }
                else if(st.top()=='(' && s[i]==')' ||st.top()=='{' && s[i]=='}'||st.top()=='[' && s[i]==']')
                {
                    st.pop();
                }
                else 
                {
                    return false;
                }
            }

        }
      return st.size()==0;  // handling more opening brackets and less closing brackets
    }
};
