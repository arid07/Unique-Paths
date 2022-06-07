# Unique-Paths
#include <bits/stdc++.h> 
  int dfs(int i,int j,vector<vector<int> >&dp){
        
        if(i<0 || j<0)
            return 0;
        if(i==0 && j==0)
            return 1;
        
        if(dp[i][j]!=-1)
            return dp[i][j];
        
        int left=dfs(i,j-1,dp);
        int up=dfs(i-1,j,dp);
        
        return dp[i][j]=left+up;
    }
int uniquePaths(int m, int n) {
	// Write your code here.
    
        vector<vector<int> > dp(m,vector<int>(n,-1));
        return dfs(m-1,n-1,dp);
}
