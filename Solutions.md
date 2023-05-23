# C-Practice-Hackerearth

1- Ali helping innocents
#include<stdio.h>
int main()
{
	char str[9];
	scanf("%s",str);
	if(str[2]=='A' || str[2]=='E' || str[2]=='I' || str[2]=='O'  ||str[2]=='U' || str[2]=='Y') 
		{ printf("invalid");  }
	else if( (str[0]+str[1])%2 != 0 || (str[3]+str[4])%2 != 0 ||   (str[4]+str[5])%2 != 0  || (str[7]+str[8])%2 != 0  )
	{ printf("invalid"); }
	else
	{ printf("valid");  }
	return 0;
}


2- Roy and Profile picture
#include<stdio.h>
int main()
{
	int l,n,w,h;
	scanf("%d %d",&l,&n);
	for(int i=0;i<n;i++)
	{
		scanf("%d %d",&w,&h);
		if(w<l||h<l) {printf("UPLOAD ANOTHER\n");}
		else if(w==h) {printf("ACCEPTED\n");}
		else printf("CROP IT\n");
	}
	return 0;
}

3- Count Divisors
#include <stdio.h>

int main(){
	int l, r, k;
	int count = 0;
	scanf("%d %d %d \n" , &l, &r, &k);
	for(int i = l; i<=r; i++)
	 {
		if(i%k==0) count++;
	 }
	 printf("%d \n", count);
	 return 0;
	     
}

4- Life, the Universe, and Everything
#include <stdio.h>

int main() {
    int number;
    while (scanf("%d", &number)) {
        if (number == 42) {
            break;
        }
        printf("%d\n", number);
    }
    return 0;
}

5- Factorial
#include <stdio.h>

int main(){
	int n;
	int fact=1;
	scanf("%d \n", &n);
	for(int i=1; i<=n; i++)
	{
      fact = fact*i;
	}
	printf("%d \n", fact);
	return 0;
}

6- Find Product using modulo 1000000007
#include <stdio.h>

#define MOD 1000000007

int main() {
    int N;
    long long int product = 1;
    scanf("%d", &N);
    int arr[N];
    for (int i = 0; i < N; i++) {
        scanf("%d", &arr[i]);
    }
    for (int i = 0; i < N; i++) {
        product = (product * arr[i]) % MOD;
    }
    printf("%lld\n", product);
    return 0;
}

7- String Palindrome
#include <stdio.h>
#include <string.h>

int isPalindrome(char S[]) {
    int len = strlen(S);
    int i, j;
    for (i = 0, j = len - 1; i < j; i++, j--) {
        if (S[i] != S[j]) {
            return 0; 
        }
    }
    return 1;  
}
int main() {
    char S[100];
    scanf("%s", S);
    if (isPalindrome(S)) {
        printf("YES\n");
    } else {
        printf("NO\n");
    }
    return 0;
}

8- Toggle String

#include <stdio.h>
#include <string.h>
int toggle(char S[]){
	int length = strlen(S);
	for(int i = 0 ; i<=length; i++){
		if(isupper(S[i])){
			S[i] = tolower(S[i]);
		}
		else if(islower(S[i])){
			S[i] = toupper(S[i]);
		}
	}
}
int main(){
	char S[100];
	scanf("%[^\n]", S);
	toggle(S);
	printf("%s \n", S );
	return 0;
}

9- Divisibility
#include <stdio.h>
int main(){
	int n;
	scanf("%d\n", &n);
	int a[n];
	int last;
	int count=0;
	for(int i = 0; i<n; i++){
		scanf("%d\n", &a[i]);
	}
	for(int j = 0; j<n; j++){
		last = a[j]%10;	
		if(last%10==0) count++;	
	}
	if(count==n) printf("Yes\n");
	else printf("No\n");
	return 0;
}

10- ZOOs
#include <stdio.h>
#include <string.h>
int main(){
	char s[100];
	scanf("%s\n", s);
	int x=0,y=0;
	int length = strlen(s);
	for(int i=0; i<length; i++){
		if(s[i]=='z'){
			x++;
			}
		else if(s[i]=='o'){
		 y++;
		 }
		else{
		  break;
		}
	}
	if(2*x==y){
	  printf("Yes\n");
	  }
	else {
	  printf("No\n");
	}
	return 0;
}

11- Split Houses
#include<stdio.h>
int main()
{
int n,flag=0;
scanf("%d",&n);
char c[n];
scanf("%s",c);
for(int i=0;i<strlen(c);i++)
{
if(c[i]=='H'&&c[i+1]=='H')
{
flag=1;
}
else
{
if(c[i]=='.')
c[i]='B';
}
}
if(flag==1)
{
printf("NO\n");
}
else
{
printf("YES\n");
printf("%s",c);
}
}

12- Best Index
#include <stdio.h>
#include <limits.h>

int main() {
    long long int n, i, j, size, x = 0, ind, ans = INT_MIN, sum = 0;
    scanf("%lld", &n);
    long long int a[n + 1], b[n + 2];
    for (i = 1; i <= n; i++) {
        scanf("%lld", &a[i]);
        b[i] = b[i - 1] + a[i];
    }
    for (j = 0; j < n; j++) {
        x = 0;
        sum = 0;
        size = 2 * (n - j + 1);
        while ((x * (x + 1)) <= size) {
            x++;
        }
        ind = (x * (x - 1)) / 2 + j - 1;
        sum += b[ind] - b[j - 1];
        if (ans < sum) {
            ans = sum;
        }
    }
    printf("%lld\n", ans);
    return 0;
}


