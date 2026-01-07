# Palindrome – Notes (Java)

A **palindrome** is a string or number that reads the same forward and backward.  
Examples: `madam`, `racecar`, `121`.

## Common Concepts / Logic Points
- Compare characters from start and end.
- Move inward each step.
- If any mismatch → NOT a palindrome.
- For numbers, reverse the digits and compare.
- Can be solved using loop, recursion, stack, or reverse methods.

---

## METHOD 1: Two-Pointer Method
**Logic:** Use left & right pointers and compare characters.

```java
public boolean isPalindrome(String s) {
    int i = 0, j = s.length() - 1;

    while (i < j) {
        if (s.charAt(i) != s.charAt(j))
            return false;
        i++;
        j--;
    }
    return true;
}
```

**Time Complexity:** O(n)  
**Space Complexity:** O(1)

---

## METHOD 2: Reverse String Method
**Logic:** Reverse the string and check equality.

```java
public boolean isPalindrome(String s) {
    String rev = new StringBuilder(s).reverse().toString();
    return s.equals(rev);
}
```

**Time Complexity:** O(n)  
**Space Complexity:** O(n)

---

## METHOD 3: Recursion Method
**Logic:** Check first and last characters, then recurse inward.

```java
public boolean isPalindrome(String s, int i, int j) {
    if (i >= j) return true;
    if (s.charAt(i) != s.charAt(j)) return false;
    return isPalindrome(s, i + 1, j - 1);
}
```

Example call:
```java
isPalindrome("madam", 0, 4);
```

**Time Complexity:** O(n)  
**Space Complexity:** O(n) (due to recursion stack)

---

## METHOD 4: Stack Method
**Logic:** Push all characters into a stack and pop to get reversed string.

```java
import java.util.Stack;

public boolean isPalindrome(String s) {
    Stack<Character> st = new Stack<>();

    for (char c : s.toCharArray())
        st.push(c);

    String rev = "";
    while (!st.isEmpty())
        rev += st.pop();

    return s.equals(rev);
}
```

**Time Complexity:** O(n)  
**Space Complexity:** O(n)

---

## METHOD 5: Integer Palindrome
**Logic:** Reverse the number using modulo (%) and compare.

```java
public boolean isPalindrome(int n) {
    int temp = n, rev = 0;

    while (n > 0) {
        rev = rev * 10 + (n % 10);
        n /= 10;
    }
    return rev == temp;
}
```

**Time Complexity:** O(d) — d = number of digits  
**Space Complexity:** O(1)
