# Codility_BinaryGap
Find longest sequence of zeros in binary representation of an integer.

# Task description
A binary gap within a positive integer N is any maximal sequence of consecutive zeros that is surrounded by ones at both ends in the binary representation of N.

For example, number 9 has binary representation 1001 and contains a binary gap of length 2. The number 529 has binary representation 1000010001 and contains two binary gaps: one of length 4 and one of length 3. The number 20 has binary representation 10100 and contains one binary gap of length 1. The number 15 has binary representation 1111 and has no binary gaps. The number 32 has binary representation 100000 and has no binary gaps.

# Link Details
[trainingGSRFNX-DN6](https://app.codility.com/demo/results/trainingGSRFNX-DN6/)

# Programming Language
Java SE 11

# Solution Code

```
import java.util.*;

class Solution {
    public int solution(int N) {
        // write your code in Java SE 11

        int count=0;
        ArrayList<Integer> arr=new ArrayList<>();
        String binary=Integer.toBinaryString(N);

        if(binary.contains("0") && binary.contains("1")){
            for(int i=0; i< binary.length(); i++){
                if(binary.charAt(i)=='1'){
                    int temp=count;
                    count=i;
                    arr.add(count-temp-1);
                }
            }
            int result=Collections.max(arr);
            if(result!=-1){
                return result;
            }
        }
        return 0;
    }
}
```
