# 1217
#include<stdio.h>
#include<string.h>
int main()
{ int n;
  int m;
  scanf("%d%d",&n,&m);//二维数组a[n][m]
  int a[n][m];
  int i;
  int j;
  for(i=0;i<n;i++)
   { for(j=0;j<m;j++)
     { int m;
       scanf("%d",&m);
       a[i][j]=m;
	 }
   }
   int bigmax[i];
   for(i=0;i<n;i++)                        //鞍点：行中最大，列中最小
   {    int max=a[i][0];
        for(j=0;j<m;j++)
        {if(a[i][j]>max)   //每行最大 
		 max=a[i][j]; }
	     bigmax[i]=max;}
   int bigsmall[j];
    for(j=0;j<m;j++)
    {  int min=a[0][j];
       for(i=0;i<n;i++)   //每列最小 
       { if(a[i][j]<min)
         min=a[i][j];
	   }
	   bigsmall[j]=min;
	}
   int count=0;
   for(i=0;i<n;i++)
   { for(j=0;j<m;j++)
     { if(a[i][j]==bigsmall[j]&&a[i][j]==bigmax[i])
        printf("a[%d][%d]=%d\n",i,j,a[i][j]);
      else
      count++;
	 }
	}
	if(count==m*n)
	printf("NO"); 
   return 0;                       
  } 
