# TP4 Software Reproducibility

## Question 1.1.1
Q1 Due to birthday paradox, It require around 2¹²⁸ operations

Q2 *ab* and *ca* have the same output

Q3 TAR archives are not inherently reproducible because they record build‑specific metadata, they can vary depending on the machine.

## Question 1.2.1
Q1 size is16.7 kB | permission : -rwxr-xr-x | 11th Gen Intel® Core™ i5-1135G7 × 8 |there is any intermediat file

Q2 Binary file ay be different 

Q3 I don't have the same output because it takes the information during the compilation

Q4 I have the same output 

Q5 It works if the architectures are compatible

Q6 Tt is preferable to share the source code

Q7 This is possible like that : *SOURCE_DATE_EPOCH=1700000000 gcc -o example example.c*  


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

Q2 I forgot what is *"single-stage and multi-stage"*. I have an image with a size of 291MB

Q4 We copy the work done in buildtime-stage (the file *random*). We can execute it without compile it with gcc.

Q6 If there is some hardware influence, we should not have the same output.

Q7 If "save" and "load" are ideal for creating a perfect backup, it should give the same environement. 


## Question 1.2.6
Q1 My binary result is a991017cad17e16e9cf4438ac580f79d2d856e443ababb5555935d7a32ad7823

Q2 My installation path is result/bin/montecarlo-pi

Q3 yes

Q4 *nix shell nixpkgs#hello* is temporary. For the next session, *hello* is not installed untill we execute the command. It is not the case for the other command.

Q5 It is the stock of nix, it is immutable to avoid any dependency issue and to conserve reproductibility.

Q6 It freezes all of dependancy to preserve the reproducibility used by flake. All of that is in flake.lock.

Q7 It should fail. Because it preserve the reproductibility and for secure reason.

Q8 Nix doesn't pay attention because it uses the version locked in flake.lock

Q9 You have to share flake.lock for dependancy and reproductibility. It would look like **Listening 9** with a description.

## Question 1.3
Q1 More guarantee for dependency and reproducibility and more security (sandbox)

Q2 It's might be possible to exploit the kernel's issue.

Q3 If all parameters are fixed (temperature, p, ...), it may be true. But there is some parameters that it's difficult to fixed them.

Q4 The other student can install nix. Or we can share the source code.

Q5 Up to know, I'm good with overleaf. But it still interesting to learn how to do that. I was intrigued with the live changes.

Q6 In the main document, it is perhaps better to make references to the other PDF for the questions. By the way, thank you for the stickers !

