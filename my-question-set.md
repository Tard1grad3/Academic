Question Setter
---------------
Name:  __Sadik Al Barid__         
Registration # __2019331046__            
Session: *2019-2020*            
GitHub Username: *Tard1grad3*               
Cell: *01797613318*              
Email: *sadik46@student.sust.edu*         

Question Set with Answers
=========================
<div align="center"><img src="sust-logo.png" alt="sust-logo" width="100px"></div>
<div style="text-align:center">
  <div align="center">Shahjalal University of Science and Technology
  </div>   
  <div align = "center">Department of Computer Science and Engineering
  </div>  
  <div align = "center"><span> 1<sup>st</sup> Year 1<sup>st</sup> Semester Final Examination &mdash;
  June 2020 (Session 2019-20) </span></div>  
  <br>
  <div align = "center"> Course No. &mdash; <b> CSE 133</b> </div>  
  <div align="center"> Course Title &mdash; <b> Structured Programming Language</b> </div>
  <br>
  <div align = "center">
    Time &mdash; <b> 3 Hours</b>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Credit:<b> 3.00</b>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Total Marks # <b> 100</b>
    </div><br>
    <div align = "center">(Answer all the questions)</div></div>
<div align="center"><h4>Group A</h4></div>
<div style="text-align:left">1. Answer the following Questions in short. (Any <b>Five</b>).</div>
<div align="right">5 &times; 2 = 10 </div>

(a) If y=20, what are the values of x after these operations:
(i)     x=y==y--
(ii)    x=5*y++

**Answer:** <br>
i)	y-- gives y==19 which is false (20 != 19). So, x=0 is assigned; <br>
ii)	y++ makes the value of y 20 again. So, x=5*20=105.

(b) Write down the output of the pseudo-code: <br>
```cpp
int x; x = long ('x'); printf ("%c", x--);
```

**Answer:** <br>
*Output:* `x`
>As, %c is the format specifier for character and x-- will decrement after printing

( c) What is the difference between #ifdef and #ifndef?

**Answer:**
```cpp
#ifdef myCondition
    // this part of the code is excluded before the compiler even sees it
    // if myCondition is not defined (via #define)
#endif

#ifndef myCondition
    // this part of the code is excluded before the compiler even sees it
    // if myCondition is defined (via #define)
#endif
```

(d) What is the output of the pseudo-code given below?
```cpp
int a = 48, *b = &a;
printf ("%x\n%c", *b, *b);
```
**Answer:** <br>
```
Output: 30
        0
```
>%x is the format specifier for hex and %c is the format specifier for character

(e) Look at the pseudo-code written below:
```cpp
  int mom = 42, wow = mom & (1 << 1);
  wow? printf ("My MOM is WOW"):
       printf ("My MOM is still WOW");
```
What is the value of wow and what is the output?

**Answer:** Value of wow is 2. <br>
*output:* `My MOM is WOW`

(f) What is structure in C programming language? Create a structure which can be used to represent a complex number.

**Answer:** A struct (or structure) is a collection of variables under a single name.
```cpp
struct complex {
 float imag;
 float real;
};
```

(g) What will be the output of the pseudo-code?
```cpp
char s[20], ss[20];
    	scanf ("%[OH My]", s);
   	getchar ();
    	scanf("%[^\n]", ss);
    	printf ("%s %s", s, ss);
```
*Input:*
```
My MOM
is WOW
isn't She?
```

**Answer:** <br>
*Output:* `My MOM is WOW.`

(h) What is a double pointer\ pointer to pointer \ pointer on pointer in C? Give an example.

**Answer:** It’s a pointer variable which can hold the address of another pointer variable. <br>
*Eg:*
```cpp
int x = 5, *p=&x, **q=&p;
```
>‘x’ can be accessed by **q.

<div align="left">2. Answer the following Questions. (Any <b>Four</b>).</div>
<div align="right">4 &times; 5 = 20 </div>

(a) What is a bitfield? What will be the output of the following C program?
```cpp
#include<stdio.h>
int main ()
{
	struct fun
	{
		int a: 2;
		int b: 4;
		int c: 4;
		int d: 3;
	} field = {2, 3, 8, 7};
	printf("%d %d %d %d", field.a, field.b, field.c, field.d);
}
```

**Answer:** In C, we can specify size (in bits) of structure and union members. It is called a bitfield. <br>
*Output:* `-2 3 -8 -1.`
>Because, the left most bit is needed for +/- sign.

(b) Write a function to generate all the possible subsets of a set of size n **(n<=20)** using bit-masking.

**Answer:**<br>
```cpp
void subsets(char arr[], int n)
{
  for (i = 0; i < (1<<n); i++)
  {
    for(int j = 0; j < n; j++)
      if(i & (1<<j))
        printf("%c ", arr[j]);
    puts("");
  }
}
```

( c) Write a recursive function to find the value of **nCr**. **(1 <= n <= 25, 0 <= r <= n)**

**Answer:**<br>
```cpp
int nCr (int n, int r)
{
    if (r == 0 | r == n)
        return 1;
    else
        return nCr (n - 1, r - 1) + nCr (n - 1, r);
}
```

(d) Divide the numbers from **1** to **n** **(1 <= n <= 10<sup>6</sup>)** into two sets of equal sums. Print **YES**, if it is possible, and **NO** if not possible. If the division is possible, first, print the number of elements of the first set and the elements in a new line. Then, print the second set similarly.

**Answer:**<br>
```cpp
#include <stdio.h>
#define f(i, a, b) for(int i=a; i<b; i++)
#define ll long long


int main()
{
    int n;
    scanf ("%d", &n);
    if (n == 1 || n == 2) puts ("NO");
    else if (! ( (n / 2) & 1) && n % 4 != 1)
    {
        puts ("YES");
        printf ("%d\n", n / 2);
        f (i, 1, n + 1)
          if (i % 4 == 1 || ! (i % 4)) printf ("%d ", i);
        puts ("");
        printf ("%d\n", n / 2);
        f (i, 1, n + 1)
          if (i % 4 == 2 || i % 4 == 3) printf ("%d ", i);
    }
    else if (! ( ( (n - 3) / 2) & 1))
    {
        puts ("YES");
        printf ("%d\n", n - (n / 2));
        printf ("1 2 ");
        f (i, 4, n + 1)
          if (i % 4 == 3 || ! (i % 4)) printf ("%d ", i);
        puts ("");
        printf ("%d\n", n / 2);
        printf ("3 ");
        f (i, 4, n + 1)
          if (i % 4 == 1 || i % 4 == 2) printf ("%d ", i);
    }
    else puts ("NO");
    return 0;
}
```

(e) Sort an array using Quick sort algorithm in ascending order.

**Answer:** <br>
```cpp
#include <stdio.h>

static inline
void swap(int *a, int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

static
int partition(int *L, int left, int right)
{
    int pivot = left;
    int p_val = L[pivot];

    while (left < right)
    {
        while (L[left] <= p_val)
            left++;
        while (L[right] > p_val)
            right--;
        if (left < right)
            swap(&L[left], &L[right]);
    }
    swap(&L[pivot], &L[right]);
    return right;
}

static
void qSort(int *L, int start, int end)
{
    if (start >= end)
        return;
    int splitPoint = partition(L, start, end);
    qSort(L, start, splitPoint - 1);
    qSort(L, splitPoint + 1, end);
}

static void print_array(int *ptr, int left, int right)
{
    for (int i = left; i <= right; i++)
        printf("%3d ", ptr[i]);
    puts("");
}

int main(void)
{
    int arr[] = {12, 43, -16, 0, 2, 5, 1, 13, 2, 2, -1};
    qSort(arr, 0, 9);
    puts("Sorted Array:");
    print_array(arr, 0, 9);
}
```

(f) Look at the code given below. Is there any mistake which will cause compilation error? If yes, then correct it and print the output.
```cpp
#include <stdio.h>
#define sust 20 * 5 + 100

int main()
{
    int *n, m = 10;
    int m += sust;
    n = &sust;
    printf ("%d", * (--n) *m);
    return 0;
}

```

**Answer:** Here **int m += sust** will produce error because m was already declared in the previous line. Again, **n = &sust** will cause a compilation error. First, the value of sust needs to be stored in another variable then it can be assigned to n. The corrected code:
```cpp
#include <stdio.h>
#define sust 20 * 5 + 100

int main()
{
    int *n, m = 10, a = sust;
    m += sust;
    n = &a;
    printf ("%d", * (--n) *m);
    return 0;
}
```
*Output:* Any garbage value. Because **(--n)** is decrementing the address. So, the output can be any garbage value.


<div align="left">3. Answer the following Questions. (Any <b>Two</b>).</div>
<div align="right">2 &times; 10 = 20 </div>


(a) Write an efficient program to find out the sum of the following sequence for a given input **n**: 2<sup>2</sup>, 3<sup>2</sup>,5,<sup>2</sup>,7<sup>2</sup>,11<sup>2</sup>……till n. **(n<=10<sup>8</sup>)**
>Hint: Use Sieve of Eratosthenes.

**Answer:** <br>
```cpp
#include <stdio.h>
#include <math.h>
#include <stdbool.h>
#define sz 100000000

int  prime[sz], cnt;
bool siv[sz];

void sieve (int n)
{
    long long i, j;
    for (i = 3; i * i <= sz; i += 2)
        if (!siv[i])
            for (j = i * i; j <= n; j += i + i)
                siv[j] = 1;
    prime[cnt++] = 2;
    for (i = 3; i <= n; i += 2)
        if (!siv[i])
            prime[cnt++] = i;
}
int main()
{
    int n, i;
    long long ans = 0;
    scanf ("%d", &n);
    sieve (n);
    for (i = 0; i < cnt && prime[i] <= n; i++) ans += prime[i] * prime[i];
    printf ("%I64d\n", ans);
}
```

(b) You are given a weighed undirected graph with **n** nodes and **m** edges and two integers **a** and **b**.  You have to answer **q** independent queries.

**Input:** The first line contains three integer **n**, **m** and **q** **(0<=n,m,q<=100)**. Number of nodes, edges and queries respectively.<br>
Next **m** lines contain three integers **x,y,z** each where **z** denotes the weight between the path from **x** to **y**.<br>
Next **q** lines contain two integers **a** and **b** **(0<=a,b<=n)** each.

**Output:** Print the shortest path cost. If there is no path between the nodes, print ‘No Path’. If a and b are the same node, print ‘You Are Already in The Destination’.

**Answer:** <br>
```cpp
#include <stdio.h>
#include <string.h>
#include <math.h>
#define ll long long
#define sz 100
#define inf 999999999999999

ll adj[sz][sz];

int main()
{
    ll i, n, m, x, y, z, j, k, q, a, b;
    scanf ("%lld%lld%lld", &n, &m, &q);
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
        {
            if (i == j) adj[i][j] = 0;
            else adj[i][j] = inf;
        }
    for (i = 0; i < m; i++)
    {
        scanf ("%lld%lld%lld", &x, &y, &z);
        adj[x][y] = z, adj[y][x] = z;
    }
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
            for (k = 0; k < n; k++)
                if (adj[j][k] > (adj[j][i] + adj[i][k]))
                    adj[j][k] = adj[j][i] + adj[i][k];
    for (i = 0; i < q; i++)
    {
        scanf ("%lld%lld", &a, &b);
        if (adj[a][b] == inf)
            printf ("No Path\n");
        else if (adj[a][b] == 0)
            printf ("You Are Already in The Destination\n");
        else
            printf ("Shortest Path Cost: %lld\n", adj[a][b]);
    }
    return 0;
}
```

( c) Write a complete C program using **binary search** which returns an index **i** of a **sorted** array with **no duplicate elements** such that **arr[i]=i**. If there exists no such index return **-1**.

**Answer:**
```cpp
#include <stdio.h>

int bi_Srch (int arr[], int high, int low)
{
    if (high >= low)
    {
        int mid = (low + high) / 2;
        if (mid == arr[mid])
            return mid;
        else if (mid > arr[mid])
            return bi_Srch (arr, high, (mid + 1));
        else
            return bi_Srch (arr, (mid - 1), low);
    }
    return -1;
}

int main()
{
    int arr[10] = {-150, -6, -2, -1, 3, 5, 41, 65, 250};
    int n = sizeof (arr) / sizeof (arr[0]);
    printf ("%d", bi_Srch (arr, n - 1, 0));
    return 0;
}
```


<div align="center"><h4>Group B</h4></div>
<div align="left">1. Answer the following Questions in short. (Any <b>Five</b>).</div>
<div align="right">5 &times; 2 = 10 </div>


(a) What is the difference between abs() and fabs() functions?

**Answer:** abs() is used for getting the absolute value of an integer number whereas fabs() is used for floating/double type data.
abs() is faster than fabs().

(b) What is the output of the following pseudo-code?
```cpp
int n='0', m=0;
while(n) n&=n-1, m++;
printf("%d", m);
```
**Answer:**<br>
*Output:* `2`
>It is basically counting the number of set bits in number 48 (ASCII value of 0 character).

( c) What is the output for the following piece of code?
```cpp
#include<stdio.h>
int main()
{
	int a = 3;
	int *b;
	b = &a;
	b++;
	printf("%d ",*b);
	return 0;
}
```
**Answer:** Garbage value. Here b is the pointer variable which holds the address of another variable called a. When b is incremented, the address stored in b is incremented. As a result, some garbage value will be displayed.

(d) What is NULL pointer? When does a dangling pointer arise?

**Answer:** NULL is used to indicate that the pointer doesn’t point to a valid location. Dangling pointers arise when an object is deleted or deallocated, without modifying the value of the pointer.

(e) What will be the output of the following printf function:
```cpp
 printf("%d\t%d", sizeof(void), sizeof(void *));
 ```
**Answer:** <br>
*Output:* `1 8`
>sizeof void is 1 and the sizeof void pointer is 4\8 (varies from compiler to compiler).

(f) Will the following pseudo- code print anything? If yes, write the output. If no, explain the reason.
```cpp
int i = 0, j = 1, k = 0;
if(++k, j, i++)
	printf("%d|%d|%d", i, j, k);
```
**Answer:** It will print nothing. In the above program, the if (++k, j, i++) will appears like if (1, 1, 0). As a result, the condition is false. So, it will print nothing.

(g) Write down two uses of circumflex.

**Answer:** <br>
i) As bitwise X-OR operator. <br>
ii) To exclude the characters inside [^ABCD…] from a string during user input.

(h) What is the output of the following pseudo code?
```cpp
int i = 010, j = 0x10;
printf ("%i|%i", i, j);
```
*Output:* `8|16`
>010 represents octal and 0x10 represents hex numbers.

<div align="left">2. Answer the following Questions. (Any <b>Four</b>).</div>
<div align="right">4 &times; 5 = 20 </div>

(a) What will be the output for the following two C programs?
```cpp
i) int main ()                                                     ii) int main ()
   {					                               {
   struct one {				                               struct two {
   int a: 8;				                               int a: 3;
   int b: 9;				                               int b: 7;
   int c: 6;				                               int c: 5;
   int d: 1;				                               int d: 6;
   } field1;			       	                               } field2 = { 2, 3, 4, 5 }
   printf("%d", sizeof(field1));		                       printf("%d", sizeof(field2));
   }					                               }
```
**Answer:** <br>
i) Sum of the bits assigned is, 8+9+6+1 = 24. 1 byte = 8 bits. So, the output will be: 3. <br>
ii) Sum of the bits assigned is, 3+7+5+6 = 21, It is greater than 2 bytes, so it automatically takes 3 bytes. So, the output will be: 3.

(b) If `int a = 63`, make it `a = 39` using only two operations and bit-masking.
>Hint: Remove all the bits except the last 3 bits then set the 5th bit.

**Answer:**
```cpp
#include<stdio.h>
int main()
{
    int a = 63;
    a = (a & ( (1 << 3) - 1));
    a |= (1 << 5);
    printf ("%d", a);
    return 0;
}
```

( c) Write a function to find the sum of first n **(n<=20)** terms of Fibonacci series using recursion.

**Answer:**
```cpp
int fib_sum (int n)
{
    if (n <= 1)
        return n;
    return fib_sum (n - 1) + fib_sum (n - 2) + 1;
}
```

(d) Write a program to calculate the number of trailing zeroes in **n!** **(1 <= n <= 10<sup>9</sup>)**.

**Answer:**
```cpp
#include <stdio.h>
#include <math.h>

int main()
{
    int n, k = 1, ans = 0;
    scanf ("%d", &n);
    while (pow (5, k) <= n) ans += n / pow (5, k), k++;
    printf ("%d", ans);
    return 0;
}
```

(e) Sort an array using Merge Sort algorithm in ascending order.

**Answer:**
```cpp
#include <stdio.h>
#define f(i, a, b) for(int i=a; i<=b; i++)
#define sz 10

int a[11] = { 100, 145, 59, 526, 56, 313, 333, 1, 426, 894, 0 };
int b[10];

void merging (int low, int mid, int high)
{
    int l1, l2, i;
    for (l1 = low, l2 = mid + 1, i = low; l1 <= mid && l2 <= high; i++)
    {
        if (a[l1] <= a[l2]) b[i] = a[l1++];
        else b[i] = a[l2++];
    }
    while (l1 <= mid) b[i++] = a[l1++];
    while (l2 <= high) b[i++] = a[l2++];
    for (i = low; i <= high; i++) a[i] = b[i];
}

void sort (int low, int high)
{
    int mid;
    if (low < high)
    {
        mid = (low + high) / 2;
        sort (low, mid);
        sort (mid + 1, high);
        merging (low, mid, high);
    }
    else return;
}

int main()
{
    int i;
    printf ("Before sorting: ");
    f (i, 0, sz) printf ("%d ", a[i]);
    puts ("");
    sort (0, sz);
    printf ("After sorting: ");
    f (i, 0, sz) printf ("%d ", a[i]);
}
```

(f) Look at the code given below. Is there any mistake which will cause compilation error? If yes, then correct it and print the output.
```cpp
#include <string.h>
#define sust 20 * 5 + 100

int main()
{
    int n = (sust * 4) / 2, m = sust--;
    printf ("%d", n-- * m);
    return 0;
}
```
**Answer:** The code has no header file included for standard output. Again, **m = sust--** will produce error. It needs to be written like **m = sust - 1**. The corrected code:
```cpp
#include <stdio.h>
#define sust 20 * 5 + 100

int main()
{
    int n = (sust * 4) / 2, m = sust - 1;
    printf ("%d", n-- * m);
    return 0;
}
```
*Output:* `49750`

<div align="left">3. Answer the following Questions. (Any <b>Two</b>).</div>
<div align="right">2 &times; 10 = 20 </div>


(a) 	Write a program to solve the equation ( √(x-3) - ∛{ (3x + 2)/2 } )<sup>7</sup> = (x - √{ (x<sup>2</sup>-1984)/5 } )<sup>3</sup> using binary search.          

**Answer:**
```cpp
#include <stdio.h>
#include <math.h>

double croot (double n, double dis)
{
    double l = 0, h = n, m;
    while (h - l > dis)
    {
        m = (l + h) / 2;
        if (m * m * m <= n) l = m;
        else h = m;
    }
    return (l + h) / 2;
}

int main()
{
    int m = 0;;
    double l = 45, h = 1e18, dis = .00000001, mid;
    while (h - l > dis)
    {
        mid = (h + l) / 2;
        if (pow (sqrt (mid - 3) - croot ( (1.5 * mid + 1), dis), 7.0) <= pow (mid - sqrt ( (mid * mid - 1984) / 5), 3)) l = mid;
        else h = mid;
    }
    m = (l + h) / 2;
    printf ("%d\n", m);
    return 0;
}
```

(b) Write a program to print the shortest path between two nodes of a weighed undirected graph (answering queries).
>Your path should look like this: **3->5->2->9** (just an example).

**Answer:**
```cpp
#include <stdio.h>
#include <string.h>
#include <math.h>
#define ll long long
#define sz 100
#define inf 999999999999999

ll adj[sz][sz], Next_Node[sz][sz];

ll min (ll x, ll y)
{
    ll a = x < y ? x : y;
    return a;
}

int main()
{
    ll i, n, m, x, y, z, j, k, q, a, b;
    scanf ("%lld %lld %lld", &n, &m, &q);
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
        {
            if (i == j)
            {
                adj[i][j] = 0;
                Next_Node[i][j] = 0;
            }
            else
            {
                adj[i][j] = inf;
                Next_Node[i][j] = j;
            }
        }
    for (i = 0; i < m; i++)
    {
        scanf ("%lld %lld %lld", &x, &y, &z);
        adj[x][y] = z;
        adj[y][x] = z;
    }
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
            for (k = 0; k < n; k++)
            {
                if (adj[j][k] > (adj[j][i] + adj[i][k]))
                {
                    adj[j][k] = adj[j][i] + adj[i][k];
                    Next_Node[j][k] = Next_Node[j][i];
                }
            }
    for (i = 0; i < q; i++)
    {
        scanf ("%lld %lld", &a, &b);
        if (adj[a][b] == inf)
            printf ("No Path\n");
        else if (adj[a][b] == 0)
            printf ("You Are Already in The Destination\n");
        else
        {
            printf ("The Shortest Path is: %lld", a);
            printf ("-->%lld", Next_Node[a][b]);
            if (Next_Node[a][b] == b)
                puts ("");
            while (Next_Node[a][b] != b)
            {
                a = Next_Node[a][b];
                if (Next_Node[a][b] == b)
                {
                    printf ("-->%lld\n", Next_Node[a][b]);
                    break;
                }
                printf ("-->%lld", Next_Node[a][b]);
            }
        }
    }
    return 0;
}
```

( c) You are given an English word of lowercase letters with at least one vowel present in it. Write a complete program to output the word in Pig Latin. To construct a Pig Latin word, the first vowel occurring in the input word is placed at the start of the new word along with the remaining alphabets of it. The alphabets present before the first vowel are shifted at the end of the new word followed by “ay”. <br>
**Example:** <br>
```
Input: s = "paris"
Output: arispay
```
```
Input: s = "amazon"
Output: amazonay
```
**Answer:**
```cpp

#include <stdio.h>
#include <string.h>
#define isvowel(v) (v=='a' || v=='e' || v=='i' || v=='o' || v=='u')

int main()
{
    char word[80];
    int len, i, pos;
    scanf ("%s", word);
    len = strlen (word);
    for (i = 0; ; i++)
        if (isvowel (word[i]))
        {
            pos = i;
            break;
        }
    while (i < len) printf ("%c", word[i]), i++;
    for (i = 0; i < pos; i++)
        printf ("%c", word[i]);
    printf ("ay");
    return (0);
}
```

---

  <div align="center"><h2>END</h2></div>

- [x] I am declaring that, the above work is my own work. Whatever added above
except the template is the result of my brainstorming. I also understand that
submitting work that isn’t my own may result in permanent failure of this course
as well as the whole current semester.
