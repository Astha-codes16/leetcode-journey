isme ek approach ye bhi hai ki for first string say 'S' we store the frequency of each letter
then for the second string say "T" we keep decreasing the frequency of the letter which we keep finding
in the frequency array
and at last the array should be all zero !!

class Solution {
public:
    bool isAnagram(string s, string t) {
        map<char,int>mpp1;
        map<char,int>mpp2;
      if(s.size()!=t.size())
      {
        return false;
      }  
      for(int i=0;i<s.size();i++)
      {
        mpp1[s[i]]++;
        mpp2[t[i]]++;
              }
           
              if(mpp1==mpp2)
              {
                return true;
              }
              else
              {
                return false;
              }
      
    }
};
