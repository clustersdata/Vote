# Vote

Vote

Problem Description

美国大选是按各州的投票结果来确定最终的结果的，如果得到超过一半的州的支持就可以当选，而每个州的投票结果又是由该州选民投票产生的，如果某个州超过一半的选民支持希拉里，则她将赢得该州的支持。现在给出每个州的选民人数，请问希拉里至少需要赢得多少选民的支持才能当选？


Input

多组输入数据

每组数据的第一行包括一个整数N（1<=N<=101）,表示美国的州数，N=0表示输入结束

接下来一行包括N个正整数，分别表示每个州的选民数，每个州的选民数不超过100

Output

对于每组数据输出一行，表示希拉里至少需要赢得支持的选民数

Sample Input

3 5 7 5 0

Sample Output

6


代码：

#include <stdio.h>


int main()

{

    int n, t, c,f[102], i, j, k;
    

    while(scanf("%d",&n) != EOF && n != 0)
    
    {
    
        for(i = 0; i < n; i ++)
        
        {
        
            scanf("%d",&f[i]);
            
        }
        
        for(i = 0; i < n; i ++)
        
        {
        
            for(j = 0; j < n - i - 1; j ++)
            
            {
            
                if(f[j] > f[j + 1])
                
                {
                
                    t = f[j];
                    
                    f[j] = f[j + 1];
                    
                    f[j + 1] = t;
                    
                }
                
            }
            
        }
        
        c = 0;
        
                  if(n % 2 != 0)
                  
                      k = (n + 1) / 2;
                      
                  else
                  
                      k = n / 2 + 1;
                      
        for(i = 0; i < k; i ++)
        
        {
        
                    
                    if(f[i] % 2 != 0)
                    
            c += (f[i] + 1) / 2;
            
                       else
                       
                           c += f[i] / 2 + 1;
                           
        }
        
        printf("%d\n",c);
        
    }
    

    return 0;
    
}
