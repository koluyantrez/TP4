# TP4 Software Reproducibility

## Question 1.1.1
Q1 Due to birthday paradox, It require around 2¹²⁸ operations
Q2 
Q3 

## Question 1.2.1
Q1 size is16.7 kB | permission : -rwxr-xr-x | 11th Gen Intel® Core™ i5-1135G7 × 8 |there is any intermediat file
Q2 Binary file ay be different 
Q3 I don't have the same output because it takes the information during the compilation
Q4 I have the same output 
Q5 It works if the architectures are compatible
Q6 Tt is preferable to share the source code


## Question 1.2.2
Q1 When I compile the program multiple times, I have the same number. Computers use the *srand* default value.
Q2 When a run the program without recompiling, I have the same number too. But it's not the case for everyone

## Question 1.2.3
Q1 It's buildtime reproducible, I have the same binary.
Q2 I have different number when I run it multiple times
Q3 Comparing to the previous version

## Question 1.2.4
Q2 I guess that more iteration give a better approximation but it is not the case. Time execution don't really change for us.
Q3 With \_\_DATE__,\_\_TIME__, sha512sum give a different output. When I remove it, it the same output.
Q4 The use of *srand()* and the number of iteration make it not runtime reproducible. We can fix it.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(int argc, char* argv[]) {
double x,y,z;
int count = 0;
srand(67); // seed fixed
int n = 9000; // Number of iterations fixed
time_t started = time(NULL);
printf("Execution started on %s",ctime(&started));
for (int i = 0; i < n; i++) {
x = (double) rand() / RAND_MAX;
y = (double) rand() / RAND_MAX;
z = x * x + y * y;
if (z <= 1) count++;
}
printf("The approximation of Pi using %d iterations is %f \n", n, (count / (double) n) * 4);
time_t stopped = time(0);
printf("Execution stopped on %s",ctime(&stopped));
return(0);
}
```

## Question 1.2.5
Q1 2 parameters : number of iteration and the value of seed. If we use the same value, it reproducible at buildtime and at runtime.
Q2 
Q3
Q4 

## Question 1.2.6
