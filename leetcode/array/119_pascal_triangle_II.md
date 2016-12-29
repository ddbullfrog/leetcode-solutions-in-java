# 119. Pascal's Triangle II

### Question:

[https://leetcode.com/problems/pascals-triangle-ii/](https://leetcode.com/problems/pascals-triangle-ii/ "https://leetcode.com/problems/pascals-triangle-ii/")

Given an index k, return the kth row of the Pascal's triangle.

For example, given k = 3,
Return [1,3,3,1].

Note: Could you optimize your algorithm to use only O(k) extra space?

### **Solution**:

```java
public class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<Integer> result = new ArrayList<>();
        if (rowIndex < 0) {
            return result;
        }
        result.add(1);

        for (int i = 1; i <= rowIndex; i++) {
            List<Integer> temp = Arrays.asList(new Integer[i + 1]);
            temp.set(0, result.get(0));
            temp.set(i, result.get(i - 1));
            for (int j = 1; j < i; j++) {
                temp.set(j, result.get(j - 1) + result.get(j));
            }
            result = temp;
        }

        return result;
    }
}
```

### **Note**:



