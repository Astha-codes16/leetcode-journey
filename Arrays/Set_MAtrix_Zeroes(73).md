class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int rows=matrix.size();
        int cols=matrix[0].size();
            bool firstrowimp=false;
            bool firstcolimp=false;
            //checking whether there are zeroes in first row or col
        for(int i=0;i<cols;i++)
        {
            if(matrix[0][i]==0)
            {
                firstrowimp=true;
            }
        }
        for(int j=0;j<rows;j++)
        {
           if(matrix[j][0]==0)
            {
               firstcolimp=true;
            } 
        }
        //if there are zeroes then mark the starting element of that particular col and row as zero ((like guards))
        for(int i=1;i<rows;i++)
        {
            for(int j=1;j<cols;j++)
            {
                if(matrix[i][j]==0)
                {
                    matrix[i][0]=0;
                    matrix[0][j]=0;
                }
            }
        }
        //if the guards are marked zero that means the whole row or the col is impacted
        // so turn all the row and col element to zeroes
         for(int i=1;i<rows;i++)
        {
            for(int j=1;j<cols;j++)
            {
                
                    if(matrix[i][0]==0 ||
                    matrix[0][j]==0)
                    {
                        matrix[i][j]=0;
                    }
                
            }
        }
        //if the first row or the first col is impacted then turn all the elements of that row and col to zero
        

        //had we done it in the first step tab dikkat ho jaati as saare guards zero ho jaate na 
        if(firstrowimp)
        {
            for(int i=0;i<cols;i++)
            {
                matrix[0][i]=0;
            }
        }
        if(firstcolimp)
        {
            for(int j=0;j<rows;j++)
            {
                matrix[j][0]=0;
            }
        }
    }
};
