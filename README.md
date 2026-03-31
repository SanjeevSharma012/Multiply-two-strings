# Multiply Strings (Java)

## 🚀 Problem Statement
Given two numbers in the form of strings `s1` and `s2`, return their product as a string.

- The numbers can be **very large**
- They may also be **negative**
- You **cannot directly convert** them into primitive data types like `int` or `long` due to overflow

---

## ❌ Initial Approach (Issue)

```java
int num1 = Integer.parseInt(s1);
int num2 = Integer.parseInt(s2);
int result = num1 * num2;


Problems:
Integer.parseInt() fails for large inputs
long also fails due to overflow
Results become incorrect for big numbers
✅ Optimized Approach (Using BigInteger)
import java.math.BigInteger;

class Solution {
    public String multiplyStrings(String s1, String s2) {
        BigInteger num1 = new BigInteger(s1);
        BigInteger num2 = new BigInteger(s2);

        BigInteger result = num1.multiply(num2);

        return result.toString();
    }
}
🔥 Why BigInteger?
Handles very large numbers
Supports negative values
Avoids overflow issues
📌 Example

Input:

s1 = "-8463473661618"
s2 = "9002072436211"

Output:

-76188802963849181904049398
⚠️ Edge Cases
One of the numbers is "0"
Negative numbers
Very large inputs (100+ digits)
🧠 Interview Insight
Avoid int and long for large inputs
Use BigInteger if allowed
Otherwise, implement manual string multiplication
📚 Complexity
Time Complexity: O(n * m)
Space Complexity: O(n + m)
✨ Author

Sanjeev Sharma
