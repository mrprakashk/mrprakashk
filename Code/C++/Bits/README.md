
No. of 1 bits

   int count = 0;
   while(A !=0) {
       if(A&1 != 0) count++;
       A=A>>1;
   }
   return count;
   
Trailing zeros

int count=0;
    while((A&1) ==0) {
        count++;
        A>>=1;
    }
    return count;


Reverse Bits

    int res = 0;
    for(int i =0; i<32; i++) {
        int lsb = A&1;
        int reverse = lsb<<(31-i);
        res = res | reverse;
        A>>=1;
    }
    return res;
    
Divide Integers

    if(dividend == 1<<31 && divisor ==-1) return INT_MAX;
    bool sign = (dividend >= 0 == divisor >= 0) ? true : false;
    bool isPos = (dividend < 0 == divisor < 0) ? true : sign;
    
    dividend = abs(dividend);
    divisor = abs(divisor);
    
    int res =0; 
    while(dividend - divisor >= 0) {
        int count =0;
        while(dividend - (divisor<<1<<count) >= 0) count++;
        res += 1<<count;
        dividend -= divisor<<count;
    }
    return isPos? res : -res;
    
Different Bits sum pairwise

#define mod 1000000007
 
    long s=0,c=0,i,j;
    long n = A.size();
    for(i=0;i<31;i++)
    {
        c=0;
        for(j=0;j<A.size();j++)
        {
                if( A[j] & (1<<i) ) c++;
        }
        s+=(c*(n-c)*2);
    }
    s=s%mod;
    s = (int) s ;
    return s%mod;

    
    
    
