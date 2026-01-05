## 1. Add Digits / Digital Root

**Concept:**
- Repeatedly add digits until a single digit.
- Formula: `1 + (num - 1) % 9`
- Works because repeated digit sum = num % 9.

**Example:**
Input: 38 → 3+8 = 11 → 1+1 = 2 → Output: 2

**Java Code:**
```java
class Solution {
    public int addDigits(int num) {
        if(num == 0) return 0;
        return 1 + (num - 1) % 9;
    }
}

## 2. First Non-Repeating Character

**Concept:**
- Problem: Find the index of the first character in a string that appears only once.
- Approach:
  1. Use a frequency array `int[26]` to count occurrences of each lowercase letter.
  2. Loop through the string to find the first character with frequency 1.
- Important Points:
  - `s.charAt(i) - 'a'` maps a character to the correct index in the frequency array.
  - Two loops are needed:
    - First loop: count frequency
    - Second loop: find first unique character

**Example:**
Input: `"leetcode"`  
Step 1: Count frequencies → `l=1, e=3, t=1, c=1, o=1`  
Step 2: Find first unique → `'l'` at index 0  
Output: `0`


**Java Code:**
```java
class Solution {
    public int firstUniqChar(String s) {
        int[] freq = new int[26]; 

        for (int i = 0; i < s.length(); i++) {
            freq[s.charAt(i) - 'a']++;
        }
        
        for (int i = 0; i < s.length(); i++) {
            if (freq[s.charAt(i) - 'a'] == 1) {
                return i; 
            }
        }

        return -1; 
    }
}


## 3. Alice & Bob Number Game

**Concept:**
- Form an array by removing minimum elements in pairs and appending in a specific order.
- Steps:
  1. Sort the array first so that minimum elements come first.
  2. Loop in pairs (`i += 2`) because each round uses 2 numbers (Alice and Bob).
  3. Alice removes `nums[i]`, Bob removes `nums[i+1]`.
  4. Append Bob first, then Alice.
  5. Use `idx` to track the next position in the output array.

**Example:**
Input: `[5,4,2,3]`  
Sorted: `[2,3,4,5]`  

- **Round 1:** Alice = 2, Bob = 3 → Append Bob first → arr = [3], then Alice → arr = [3,2]  
- **Round 2:** Alice = 4, Bob = 5 → Append Bob → arr = [3,2,5], then Alice → arr = [3,2,5,4]  

Output: `[3,2,5,4]`  

Input: `[2,5]` → Output: `[5,2]`

**Java Code:**
```java
import java.util.Arrays;

class Solution {
    public int[] numberGame(int[] nums) {
        Arrays.sort(nums); 

        int[] arr = new int[nums.length];
        int idx = 0; 

        for(int i = 0; i < nums.length - 1; i += 2) {
            int alice = nums[i];       
            int bob = nums[i + 1];     

            arr[idx++] = bob;           
            arr[idx++] = alice;         
        }

        return arr;
    }
}

