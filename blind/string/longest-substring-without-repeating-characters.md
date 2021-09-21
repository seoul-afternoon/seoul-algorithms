### [longest-substring-without-repeating-characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

### Problem

Given a string s, find the length of the longest substring without repeating characters.

### Idea
Put Characters in the set for checking duplicate. \
Put Characters in the queue for removing until duplicated word

### Solution
1. touring and add queue, set
2. if char already exists in set, removing character until char

### Code
Time Complexity : O(n) \
Space Complexity : O(n)
```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int result = 0;
        Set<Character> characters = new HashSet<>();
        Queue<Character> queue = new LinkedList<>();
        for(char c : s.toCharArray()) {
            while(characters.contains(c)) {
                Character ch = queue.poll();
                characters.remove(ch);
                if(ch == c) break;
            }   
            characters.add(c);
            queue.add(c);
            result = Math.max(result, characters.size());
        }
        return result;
    }
}
```



