17. Letter Combinations of a Phone Number
 https://leetcode.com/problems/letter-combinations-of-a-phone-number
code===>
class Solution {
public:
vector<string>Mapped={"","","abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"};
vector<string>result;
void solve(string& ans,string& digits,int letteridx,int idx)
{    if(idx==digits.size())
{
    result.push_back(ans);
    return;
}  
    int k=0;
    string Letters=Mapped[digits[idx]-'0'];
    if (letteridx==Letters.size()) return;
    ans.push_back(Letters[letteridx]);
    solve(ans,digits,k,idx+1);
    ans.pop_back();
    solve(ans,digits,letteridx+1,idx);
}
    vector<string> letterCombinations(string digits) {
        if(digits.size()==0)
        {
            return {};
        }
       string ans="";
       int letteridx=0;
       int idx=0;
       solve(ans,digits,letteridx,idx); 
       return result;
    }
};

explanation==>
Firstly we find the string mapped to the first number in digits 
then we push the first letter of the the string corresponding to the string of first digit  
we keep repeating the process till the base condition is not hit
after popping we keep the i same (you can check by the page diagram) but inc the letter idx
also after finding the Letters we check when letteridx is inbound or not..

TC==>
SC==>depth of recursion i.e how many recursion calls so it will be equal to size og digits
