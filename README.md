# Cprimary
判断对称素数
#include <stdio.h>
#include <math.h>
int isPrime(int n)
{
    if(n==1)
        return 0;
    if(n==2||n==3)
        return 1;
    if(n%2==0||n%3==0)
        return 0;

    for(int i=5;i*i<=n;i+=6)
    {
        if(n%i==0||n%(i+2)==0)
            return 0;
    }

    return 1;
}
int isSymm(int m)
{
    int v,w,x,y,z;
    if((int)(log10(m)+1)==5)
    {
        v=m%10;
        w=m/10%10;
        x=m/100%10;
        y=m/1000%10;
        z=m/10000%10;
        if(v==z&&w==y)
            return 2;
        else
            return 3;
    }
     else if((int)(log10(m)+1)==4)
    {
        v=m%10;
        w=m/10%10;
        x=m/100%10;
        y=m/1000%10;
        if(v==y&&w==x)
            return 2;
        else
            return 3;
    }
     else if((int)(log10(m)+1)==3)
    {
        v=m%10;
        w=m/10%10;
        x=m/100%10;

        if(v==x)
            return 2;
        else
            return 3;
    }
     else if((int)(log10(m)+1)==2)
    {
        v=m%10;
        w=m/10%10;
        if(v==w)
            return 2;
        else
            return 3;
    }
    else if((int)(log10(m)+1)==1)
        return 2;
    else
        return 3;
}
int main()
{
    long long a,b,c,d,e;
    scanf("%lld %lld %lld %lld %lld",&a,&b,&c,&d,&e);

       if(a<100000&&isPrime(a)==1&&isSymm(a)==2)
        printf("Yes\n");
    else
    printf("No\n");

          if(b<100000&&isPrime(b)==1&&isSymm(b)==2)
        printf("Yes\n");
    else
    printf("No\n");

          if(c<100000&&isPrime(c)==1&&isSymm(c)==2)
        printf("Yes\n");
    else
    printf("No\n");

          if(d<100000&&isPrime(d)==1&&isSymm(d)==2)
        printf("Yes\n");
    else
    printf("No\n");

          if(e<100000&&isPrime(e)==1&&isSymm(e)==2)
        printf("Yes\n");
    else
    printf("No\n");

    return 0;
}
