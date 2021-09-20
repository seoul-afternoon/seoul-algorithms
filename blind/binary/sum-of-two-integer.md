### [Sum of two integer](https://leetcode.com/problems/sum-of-two-integers/)

### Note
```
"&" AND operation, for example, 2 (0010) & 7 (0111) => 2 (0010)
"^" XOR operation, for example, 2 (0010) ^ 7 (0111) => 5 (0101)
"~" NOT operation, for example, ~2(0010) => -3 (1101) what??? Don't get frustrated here. It's called two's complement.

1111 is -1, in two's complement
1110 is -2, which is ~2 + 1, ~0010 => 1101, 1101 + 1 = 1110 => 2
1101 is -3, which is ~3 + 1

so if you want to get a negative number, you can simply do ~x + 1
```

### Idea - 1
Use Iteration

### Solution
1. Get carry, used by and gate.
2. Remain different values.
3. Move carry left as one. 

### Code
Time Complexity : O(n) <- n is input bit length \
Space Complexity : O(1)
```java
class Solution {
    public int getSum(int a, int b) {
        if(a == 0) return b;
        if(b == 0) return a;
        
        while(b != 0) {
            int carry = a & b;
            a = a ^ b;
            b = carry << 1;
        }
        
        return a;
    }
}
```


### Idea - 2
Use Recursive

### Solution
1. Get carry, used by and gate.
2. Remain different values.
3. Move carry left as one. 

### Code
```java
class Solution {
    public int getSum(int a, int b) {
        return b == 0 ? a : getSum(a ^ b, (a & b) << 1);
    }
}
```

