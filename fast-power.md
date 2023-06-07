## Fast power $a^b\\%M$
If we use Brute force we can simply multiply ($a * a * \.\.\.* a$) $b$ times and while multiplying take the modulo with $M$ everytime, The time complexity of this approach is $O(b)$.

Question is can we optimize it further ?Yes we can.

Before we start remember this basic property $a^{x+y}=a^x*a^y$.
### Algorithm
let's first take the value of $b$ is $13$, the binary representation of $13$ is $1101$.
#### let's simplify $a^b$
$a^{b(13)}=a^{1101}=a^{2^{3}+2^{2}+2^{0}}=a^{2^3}*a^{2^2}*a^{2^0}=a^{8}*a^{4}*a^{1}$
 as you can see we are multiplying $a^{2^i}$ factor only if $ith$ bit of $b$ is set.


let's define $2$ variables, $result=1$ (which will be use to store the final result) and a variable $x=a\\%M$ (which we will be use to calculate the value of the factor for $ith$ bit $i.e\ a^{2^i}$ so that we can easily use it in every iteration).

Now let's iterate over the binary of $b(13)$ and calculate the $result$

 

 1. check the $0th$ bit of $b(13)=110|1|$ is it set or not? yes it's set.<br /> then we need to multiply $a^{2^0}=a^1$ (the value of $x$ is $a\\%M$).<br />
 $result = result * x \\% M$ [after this operation the value of $result$ will become $a\\%M$]<br />
 $x=x*x\%M$ [after this operation the value of $x$ will become $a^2\\%M$]
 
 2. check the $1st$ bit of $b(13)=11|0|1$ is it set or not? no it's not.<br /> then we don't need to multiply anything to result.<br />
 $x=x*x\\%M$ [after this operation the value of $x$ will become $a^4\\%M$]

 3. check the $2nd$ bit of $b(13)=1|1|01$ is it set or not? yes it's set.<br /> so we need to multiply $a^{2^2}=a^4$ (the value of $x$ is
    $a^4\\%M$).<br />
    $result = result * x \\% M$ [after this operation the value of $result$ will become $a * a^4\\%M$]<br />
    $x=x*x\\%M$ [after this operation the value of $x$ will become $a^8\\%M$]

 4. check the $3rd$ bit of $b(13)=|1|101$ is it set or not? yes it's set.<br /> so we need to multiply $a^{2^3}=a^8$ (the value of $x$ is
    $a^8\\%M$).<br />
    $result = result * x \\% M$ [after this operation the value of $result$ will become $a * a^4 * a^8\\%M$]<br />
    $x=x*x\\%M$ [after this operation the value of $x$ will become $a^{16}\\%M$]

we iterated over all the bits of $b$ and as you can see the final value of the variable $result$ is $a * a^4 * a^8\\%M$ which is correct right?

Can you guess the overall complexity? Yes it's $O(log(b))$ which is much faster then brute force.

### Use case
If you see a problem where $b >= 10^7$ , using brute force will surely give you **TLE** in that case the only savior is this Algorithm.

### Code

```cpp
const int M = 1000000007;

int mpow(int a, int b) {
  int r = 1;
  while (b) {
    if (b & 1) {
      r = (r * a) % M;
    }
    a = (a * a) % M;
    b >>= 1;
  }
  return r;
}
```

