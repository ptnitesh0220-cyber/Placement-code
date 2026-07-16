#include<stdio.h>
int r,c;
void findmax(int fsmax[],int r,int dp[][c]){
    int fmax=dp[r][0],smax=-1;
    for(int col=1;col<c;col++){
        if(dp[r][col]>fmax){
            smax=fmax;
            fmax=dp[r][col];
        }
        else if(dp[r][col]>smax){
            smax=dp[r][col];
        }
    }
    fsmax[0]=fmax;
    fsmax[1]=smax;
}
int main(){
    scanf("%d%d",&r,&c);
    int mat[r][c],dp[r][c];
    for(int i=0;i<r;i++){
        for(int j=0;j<c;j++){
            scanf("%d",&mat[i][j]);
            if(i==0){
                dp[0][j]=mat[i][j];
            }
        }
    }
    int fsmax[2];
    for(int i=1;i<r;i++){
        findmax(fsmax,i-1,dp);
        for(int j=0;j<c;j++){
            dp[i][j]=mat[i][j]+(dp[i-1][j]==fsmax[0]?fsmax[1]:fsmax[0]);
        }
    }
    findmax(fsmax,r-1,dp);
    printf("%d",fsmax[0]);
}
